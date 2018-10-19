---
title: 在事件处理程序中适当设定变量作用范围
TOCTitle: Scoping variables appropriately in event handlers
ms:assetid: 95b71535-abfd-43f1-a471-2026b522eac1
ms:mtpsurl: https://msdn.microsoft.com/library/office/bb646475(v=office.15)
ms:contentKeyID: 55119788
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: ac26dfb245dd9b4621093a91ff36846c686f6e41
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407602"
---
# <a name="scoping-variables-appropriately-in-event-handlers"></a><span data-ttu-id="88041-102">在事件处理程序中适当设定变量作用范围</span><span class="sxs-lookup"><span data-stu-id="88041-102">Scoping Variables Appropriately in Event Handlers</span></span>

<span data-ttu-id="88041-p101">对事件处理程序进行编程时常见的一个错误是将事件处理程序连接到已声明的其作用域对于处理事件来说过于有限的对象。对象的生命不仅必须跨越将回调方法作为对象的事件处理程序来连接的函数，还必须跨越实际处理事件的回调方法本身。否则，如果对象在作用域外，不再在回调方法中定义，则不会调用回调方法，并且不会按需处理事件。</span><span class="sxs-lookup"><span data-stu-id="88041-p101">A common mistake in programming event handlers is connecting the event handler to an object that has been declared with a scope too limited for the purpose of handling the event. The object must have a life that spans not just over the function that connects the callback method as an event handler of the object, but also over the callback method itself where the event is actually handled. Otherwise, if the object is out of scope and is no longer defined in the callback method, the callback method is not called and the event is not handled as desired.</span></span>

<span data-ttu-id="88041-106">下面的代码示例尝试将 MyNewInspector 回调方法连接到 [NewInspector](https://msdn.microsoft.com/library/bb612750\(v=office.15\)) 事件。</span><span class="sxs-lookup"><span data-stu-id="88041-106">The following example attempts to connect the   callback method to the NewInspector event.</span></span> <span data-ttu-id="88041-107">但是，回调方法在代码示例中挂接到了其作用域局限于 Connect 函数的 [Inspectors](https://msdn.microsoft.com/library/bb623458\(v=office.15\)) 对象的 NewInspector 事件。</span><span class="sxs-lookup"><span data-stu-id="88041-107">However, the callback method is hooked up in the code sample to the NewInspector event of an [Inspectors](https://msdn.microsoft.com/library/bb623458\(v=office.15\)) object that has a scope limited to the Connect function.</span></span> <span data-ttu-id="88041-108">当回调方法最终获调用时，此示例已退出 Connect 函数，并且已对 Inspectors 对象进行了垃圾回收，因此永远不会调用 MyNewInspector。</span><span class="sxs-lookup"><span data-stu-id="88041-108">When the callback method is eventually called, the Connect function has already exited, the Inspectors object has already been garbage collected, and so   is never called.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;

class MyClass
{
    private Outlook.Application MyApp;

    public MyClass(Outlook.Application appOutlook)
    {
        MyApp = appOutlook;
    }

    // Connects the NewInspector event to my callback method
    public void Connect()
    {
        MyApp.Inspectors.NewInspector += new Outlook.
            InspectorsEvents_NewInspectorEventHandler(
            MyNewInspector);
    }

    public void MyNewInspector(Outlook.Inspector inspector)
    {
        MessageBox.Show("
            My event handler caught a NewInspector event");
    }
}
```

<br/>

<span data-ttu-id="88041-p103">在本例中要执行的正确操作是将 Inspectors 对象存储在其生存期跨越整个 MyClass（包括 MyNewInspector 回调方法）的更永久的变量中。在下面的示例中，MyInspectors 的作用域为整个 MyClass，并确保在该类的生存期内连接了回调方法。</span><span class="sxs-lookup"><span data-stu-id="88041-p103">The correct thing to do in this case is to store the Inspectors object in a more permanent variable whose lifetime spans over the entire MyClass, including the MyNewInspector callback method. In the following example, MyInspectors has a scope of the entire MyClass and ensures that the callback method is connected for the lifetime of the class.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;

class MyClass
{
    private Outlook.Application MyApp;
    private Outlook.Inspectors MyInspectors;

    public MyClass(Outlook.Application appOutlook)
    {
        MyApp = appOutlook;
    }

    // Connects the NewInspector event to my callback method
    public void Connect()
    {
        MyInspectors = MyApp.Inspectors;
        MyInspectors.NewInspector += new Outlook.
            InspectorsEvents_NewInspectorEventHandler(
            MyNewInspector);
    }

    public void MyNewInspector(Outlook.Inspector inspector)
    {
        MessageBox.Show("
            My event handler caught a NewInspector event");
    }
}
```

<br/>

<span data-ttu-id="88041-111">由于各种语言连接事件处理程序的方式存在语法差异，此问题在诸如 Visual Basic 之类的语言中并不多见，在这些语言中，可以连接指定父对象实例的事件，并同时定义回调方法。</span><span class="sxs-lookup"><span data-stu-id="88041-111">By virtue of the syntactic differences in how various languages connect event handlers, this issue is less common in languages such as Visual Basic where you can connect an event specifying an instance of the parent object, and define the callback method at the same time.</span></span> <span data-ttu-id="88041-112">下面的示例在 Visual Basic 中使用 Handles 关键字，将 Region\_Expanded 回调方法连接到 [Expanded](https://msdn.microsoft.com/library/bb609515\(v=office.15\)) 事件。</span><span class="sxs-lookup"><span data-stu-id="88041-112">The following example in Visual Basic uses the Handles keyword to connect the   callback method to the Expanded event.</span></span> <span data-ttu-id="88041-113">父对象实例 Region 的作用范围横跨 MyClass，其中包括 Region\_Expanded 回调方法。</span><span class="sxs-lookup"><span data-stu-id="88041-113">An instance of the parent object,  , has a scope that spans   including the   callback method.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook

Public Class MyClass
    ' The Region object has a lifetime spanning the class 
    ' including the callback method Region_Expanded
    Private WithEvents Region As Outlook.FormRegion
    ...
    Private Sub Region_Expanded() Handles Region.Expanded
        MsgBox("My EventHandler caught an Expanded event.")
    End Sub
End Class
```

<span data-ttu-id="88041-114">在此代码示例中，因为 Region\_Expanded 回调方法在类的生存期内连接到了 Expanded 事件，所以回调方法相应获得调用。</span><span class="sxs-lookup"><span data-stu-id="88041-114">In this example, because the Region_Expanded callback method is connected to the Expanded event for the lifetime of the class, the callback method is called as appropriate.</span></span>

## <a name="see-also"></a><span data-ttu-id="88041-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88041-115">See also</span></span>

- [<span data-ttu-id="88041-116">连接到自定义事件处理程序</span><span class="sxs-lookup"><span data-stu-id="88041-116">Connecting to Custom Event Handlers</span></span>](connecting-to-custom-event-handlers.md)

