---
title: 为检查器实现包装并在每个检查器中跟踪项目级事件
TOCTitle: Implement a wrapper for inspectors and track item-level events in each inspector
ms:assetid: 8021dd2b-c36c-492b-b281-783e85140ad8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184620(v=office.15)
ms:contentKeyID: 55119854
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: d5fee97e27b616232f2f45eb42faf659eee52cda
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405768"
---
# <a name="implement-a-wrapper-for-inspectors-and-track-item-level-events-in-each-inspector"></a><span data-ttu-id="333b3-102">为检查器实现包装并在每个检查器中跟踪项目级事件</span><span class="sxs-lookup"><span data-stu-id="333b3-102">Implement a Wrapper for Inspectors and Track Item-Level Events in Each Inspector</span></span>

<span data-ttu-id="333b3-103">此主题包含两个代码示例，用来演示如何实现 [Inspectors](https://msdn.microsoft.com/library/bb623458\(v=office.15\)) 集合的包装，以及如何使用该包装跟踪集合中每个 [Inspector](https://msdn.microsoft.com/library/bb647744\(v=office.15\)) 对象中的项目级事件。</span><span class="sxs-lookup"><span data-stu-id="333b3-103">This topic contains two code examples that show how to implement a wrapper for an [Inspectors](https://msdn.microsoft.com/library/bb623458\(v=office.15\)) collection and to use that wrapper to track item-level events in each [Inspector](https://msdn.microsoft.com/library/bb647744\(v=office.15\)) object in the collection.</span></span>

## <a name="example"></a><span data-ttu-id="333b3-104">示例</span><span class="sxs-lookup"><span data-stu-id="333b3-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="333b3-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="333b3-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="333b3-106">下面的两个代码示例实现了 Connect 及 OutlookInspector 类。</span><span class="sxs-lookup"><span data-stu-id="333b3-106">The following two code examples implement the   and   classes.</span></span> <span data-ttu-id="333b3-107">第一个代码示例涉及你在 Connect 类中用来实现 **Inspectors** 集合包装的方法和事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="333b3-107">The first code example involves methods and event handlers you include in the   class to implement a wrapper for an Inspectors collection.</span></span> <span data-ttu-id="333b3-108">第二个代码示例涉及 **OutlookInspector** 类的一个简单实现。</span><span class="sxs-lookup"><span data-stu-id="333b3-108">The second code example involves a simple implementation of the  \*\*\*\* class.</span></span>

<span data-ttu-id="333b3-109">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="333b3-109">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="333b3-110">不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="333b3-110">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="333b3-111">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="333b3-111">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

<span data-ttu-id="333b3-112">在以下的代码示例中，在新检查器窗口创建之后、显示之前会发生 [NewInspector(Inspector)](https://msdn.microsoft.com/library/bb610594\(v=office.15\)) 事件。</span><span class="sxs-lookup"><span data-stu-id="333b3-112">In the following code example, a [NewInspector(Inspector)](https://msdn.microsoft.com/library/bb610594\(v=office.15\)) event occurs after a new inspector window has been created and before it is displayed.</span></span> <span data-ttu-id="333b3-113">用户操作也可以创建新的检查器窗口。</span><span class="sxs-lookup"><span data-stu-id="333b3-113">A user action may also create a new inspector window.</span></span> <span data-ttu-id="333b3-114">系统会声明 **Connect** 类中一个名为 inspectors 的类级实例变量，还将挂起 **NewInspector** 事件。</span><span class="sxs-lookup"><span data-stu-id="333b3-114">A class-level instance variable named   in the Connect class is declared, and a NewInspector event is hooked up.</span></span> 

<span data-ttu-id="333b3-115">在 inspectors\_NewInspector 方法中，**FindOutlookInspector** 方法会检查新的检查器窗口是否已在 inspectorWindows 列表中。</span><span class="sxs-lookup"><span data-stu-id="333b3-115">In the   method, the   method checks whether the new inspector window is already in the   list.</span></span> <span data-ttu-id="333b3-116">如果 FindOutlookInspector 没有在 inspectorWindows 中找到 **Inspector** 对象，**AddInspector** 方法会向 inspectorWindows 添加 **OutlookInspector** 类的一个实例。</span><span class="sxs-lookup"><span data-stu-id="333b3-116">If   does not find the Inspector object in  , the   method adds an instance of the   class to  .</span></span> <span data-ttu-id="333b3-117">可以使用 **OutlookInspector** 类来为此特定检查器窗口引发事件。</span><span class="sxs-lookup"><span data-stu-id="333b3-117">You can use the  \*\*\*\* class to raise events for this particular inspector window.</span></span> <span data-ttu-id="333b3-118">第二个代码示例演示了 **OutlookInspector** 类的实现。</span><span class="sxs-lookup"><span data-stu-id="333b3-118">The implementation of the  \*\*\*\* class is shown in the second code example.</span></span>

```csharp
class Connect
{
    // Connect class-level Instance Variables
    // Outlook inspectors collection
    private Outlook.Inspectors inspectors;

    // Collection of tracked inspector windows              
    private List<OutlookInspector> inspectorWindows;    

    // Hook up NewInspector event
    inspectors.NewInspector += new 
        Outlook.InspectorsEvents_NewInspectorEventHandler(
        inspectors_NewInspector);

    // NewInspector event creates new instance of OutlookInspector
    void inspectors_NewInspector(Outlook.Inspector Inspector)
    {
        // Check to see if this is a new window you don't
        // already track
        OutlookInspector existingWindow = 
            FindOutlookInspector(Inspector);
        if (existingWindow == null)
        {
            AddInspector(Inspector);
        }
    }

    // Adds an instance of **OutlookInspector** class
    private void AddInspector(Outlook.Inspector inspector)
    {
        OutlookInspector window = new OutlookInspector(inspector);
        window.Close +=
            new EventHandler(WrappedInspectorWindow_Close);
    }

    // Looks up the window wrapper for a given Inspector 
    // window object
    private OutlookInspector FindOutlookInspector(object window)
    {
        foreach (OutlookInspector inspector in inspectorWindows)
        {
            if (inspector.Window == window)
            {
                return inspector;
            }
        }
        return null;
    }
}
```

<span data-ttu-id="333b3-119">以下代码示例是 **OutlookInspector** 类的实现。</span><span class="sxs-lookup"><span data-stu-id="333b3-119">The following code example is an implementation of the  \*\*\*\* class.</span></span> <span data-ttu-id="333b3-120">此类用于为前面的代码示例中的检查器窗口引发事件。</span><span class="sxs-lookup"><span data-stu-id="333b3-120">This class is used to raise events for the inspector window from the preceding code example.</span></span> <span data-ttu-id="333b3-121">可以同时打开多个检查器窗口。</span><span class="sxs-lookup"><span data-stu-id="333b3-121">Multiple inspector windows can be open simultaneously.</span></span> <span data-ttu-id="333b3-122">通过在此类构造函数中挂起项目级事件（如 [Open](https://msdn.microsoft.com/library/bb644296\(v=office.15\))、[PropertyChange](https://msdn.microsoft.com/library/bb647794\(v=office.15\)) 和 [CustomPropertyChange](https://msdn.microsoft.com/library/bb645015\(v=office.15\)) 等），可跟踪这些事件。</span><span class="sxs-lookup"><span data-stu-id="333b3-122">Item-level events such as [Open](https://msdn.microsoft.com/library/bb644296\(v=office.15\)) , [PropertyChange](https://msdn.microsoft.com/library/bb647794\(v=office.15\)) , and [CustomPropertyChange](https://msdn.microsoft.com/library/bb645015\(v=office.15\)) are tracked by hooking them up in this class constructor.</span></span> <span data-ttu-id="333b3-123">[ContactItem](https://msdn.microsoft.com/library/bb644956\(v=office.15\)) 对象的 [Close](https://msdn.microsoft.com/library/bb645009\(v=office.15\)) 事件也可在此类构造函数中挂起。</span><span class="sxs-lookup"><span data-stu-id="333b3-123">A [Close](https://msdn.microsoft.com/library/bb645009\(v=office.15\)) event for a [ContactItem](https://msdn.microsoft.com/library/bb644956\(v=office.15\)) object is also hooked up in this class constructor.</span></span> <span data-ttu-id="333b3-124">你可以根据需要定义其他类级别的项目实例变量。</span><span class="sxs-lookup"><span data-stu-id="333b3-124">You can define other class-level item instance variables as needed.</span></span> <span data-ttu-id="333b3-125">原来在 OutlookInspector 构造函数中挂起的所有事件在 OutlookInspectorWindow\_Close 事件处理程序中均处于解除挂起状态。</span><span class="sxs-lookup"><span data-stu-id="333b3-125">All the events that were hooked up in the   constructor are unhooked in the   event handler.</span></span>

<span data-ttu-id="333b3-126">请注意，在对象模型级别，**Outlook inspector** 并不特别针对任何 Outlook 项目类型。</span><span class="sxs-lookup"><span data-stu-id="333b3-126">Note that at the object model level, an **Outlook inspector** object is not specific to any Outlook item type.</span></span> <span data-ttu-id="333b3-127">此代码示例利用[创建用于访问常见 Outlook 项成员的帮助程序类](how-to-create-a-helper-class-to-access-common-outlook-item-members.md)一文中定义的 OutlookItem 帮助程序类，便捷地调用 OutlookItem.Class 属性来验证检查器中当前项目的邮件类，而无需先假设该项目为联系人项目。</span><span class="sxs-lookup"><span data-stu-id="333b3-127">This code sample makes use of the OutlookItem helper class, defined in [Create a Helper Class to Access Common Outlook Item Members](how-to-create-a-helper-class-to-access-common-outlook-item-members.md), to conveniently call the OutlookItem.Class property to verify the message class of the current item in the inspector, before assuming the item is a contact item.</span></span>

```csharp
// This class tracks the state of an Outlook Inspector window 
// and ensures that what happens in this window is handled correctly.
class OutlookInspector
{
    // OutlookInspector class-level instance variables 
    // wrapped window object
    private Outlook.Inspector m_Window;             

    // Use these instance variables to handle item-level events
    // wrapped MailItem
    private Outlook.MailItem m_Mail;    
    // wrapped AppointmentItem        
    private Outlook.AppointmentItem m_Appointment;  
    // wrapped ContactItem
    private Outlook.ContactItem m_Contact;
    // wrapped TaskItem      
    private Outlook.ContactItem m_Task;             

    // OutlookInspector constructor
    public OutlookInspector(Outlook.Inspector inspector)
    {
        m_Window = inspector;

        // Hook up the close event
        ((Outlook.InspectorEvents_Event)inspector).Close +=
            new Outlook.InspectorEvents_CloseEventHandler(
            OutlookInspectorWindow_Close);

        // Hook up item-level events as needed
        OutlookItem olItem = new OutlookItem(inspector.CurrentItem);
        if(olItem.Class==Outlook.OlObjectClass.olContact)
        {
            m_Contact = olItem.InnerObject as Outlook.ContactItem;
            m_Contact.Open +=
                new Outlook.ItemEvents_10_OpenEventHandler(
                m_Contact_Open);
            m_Contact.PropertyChange +=
                new Outlook.ItemEvents_10_PropertyChangeEventHandler(
                m_Contact_PropertyChange);
            m_Contact.CustomPropertyChange +=
                new Outlook.ItemEvents_10_CustomPropertyChangeEventHandler(
                m_Contact_CustomPropertyChange);
        }
    }

    // Event Handler for the inspector close event.
    private void OutlookInspectorWindow_Close()
    {
        // Unhook events from any item-level instance variables
        m_Contact.Open -= 
            Outlook.ItemEvents_10_OpenEventHandler(
            m_Contact_Open);
        m_Contact.PropertyChange -= 
            Outlook.ItemEvents_10_PropertyChangeEventHandler(
            m_Contact_PropertyChange);
        m_Contact.CustomPropertyChange -= 
            Outlook.ItemEvents_10_CustomPropertyChangeEventHandler(
            m_Contact_CustomPropertyChange);
        ((Outlook.ItemEvents_Event)m_Contact).Close -= 
            Outlook.ItemEvents_CloseEventHandler(
            m_Contact_Close);

        // Unhook events from the window
        ((Outlook.InspectorEvents_Event)m_Window).Close -=
            new Outlook.InspectorEvents_CloseEventHandler(
            OutlookInspectorWindow_Close);

        // Raise the OutlookInspector close event
        if (Close != null)
        {
            Close(this, EventArgs.Empty);
        }
        // Release item-level instance variables
        m_Mail = null;
        m_Appointment = null;
        m_Contact = null;
        m_Task = null;
        m_Window = null;
    }
}
```

## <a name="see-also"></a><span data-ttu-id="333b3-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="333b3-128">See also</span></span>

- [<span data-ttu-id="333b3-129">使用 Outlook 事件的示例任务</span><span class="sxs-lookup"><span data-stu-id="333b3-129">Sample Tasks Using Outlook Events</span></span>](sample-tasks-using-outlook-events.md)

