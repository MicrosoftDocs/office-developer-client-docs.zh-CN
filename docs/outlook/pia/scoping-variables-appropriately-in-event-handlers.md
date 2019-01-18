---
title: 在事件处理程序中适当设定变量作用范围
TOCTitle: Scoping variables appropriately in event handlers
ms:assetid: 95b71535-abfd-43f1-a471-2026b522eac1
ms:mtpsurl: https://msdn.microsoft.com/library/office/bb646475(v=office.15)
ms:contentKeyID: 55119788
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c8a1a418a315167cc96be5b9b5f65a0f4cd9ce44
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28708135"
---
# <a name="scoping-variables-appropriately-in-event-handlers"></a>在事件处理程序中适当设定变量作用范围

对事件处理程序进行编程时常见的一个错误是将事件处理程序连接到已声明的其作用域对于处理事件来说过于有限的对象。对象的生命不仅必须跨越将回调方法作为对象的事件处理程序来连接的函数，还必须跨越实际处理事件的回调方法本身。否则，如果对象在作用域外，不再在回调方法中定义，则不会调用回调方法，并且不会按需处理事件。

下面的代码示例尝试将 MyNewInspector 回调方法连接到 [NewInspector](https://msdn.microsoft.com/library/bb612750\(v=office.15\)) 事件。 但是，回调方法在代码示例中挂接到了其作用域局限于 Connect 函数的 [Inspectors](https://msdn.microsoft.com/library/bb623458\(v=office.15\)) 对象的 NewInspector 事件。 当回调方法最终获调用时，此示例已退出 Connect 函数，并且已对 Inspectors 对象进行了垃圾回收，因此永远不会调用 MyNewInspector。

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

在本例中要执行的正确操作是将 Inspectors 对象存储在其生存期跨越整个 MyClass（包括 MyNewInspector 回调方法）的更永久的变量中。在下面的示例中，MyInspectors 的作用域为整个 MyClass，并确保在该类的生存期内连接了回调方法。

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

由于各种语言连接事件处理程序的方式存在语法差异，此问题在诸如 Visual Basic 之类的语言中并不多见，在这些语言中，可以连接指定父对象实例的事件，并同时定义回调方法。 下面的示例在 Visual Basic 中使用 Handles 关键字，将 Region\_Expanded 回调方法连接到 [Expanded](https://msdn.microsoft.com/library/bb609515\(v=office.15\)) 事件。 父对象实例 Region 的作用范围横跨 MyClass，其中包括 Region\_Expanded 回调方法。

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

在此代码示例中，因为 Region\_Expanded 回调方法在类的生存期内连接到了 Expanded 事件，所以回调方法相应获得调用。

## <a name="see-also"></a>另请参阅

- [连接到自定义事件处理程序](connecting-to-custom-event-handlers.md)

