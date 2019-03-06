---
title: 为检查器实现包装并在每个检查器中跟踪项目级事件
TOCTitle: Implement a wrapper for inspectors and track item-level events in each inspector
ms:assetid: 8021dd2b-c36c-492b-b281-783e85140ad8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184620(v=office.15)
ms:contentKeyID: 55119854
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a70aedf9a8803a2c990f07a77d4fc730f7263aae
ms.sourcegitcommit: 43cff5789e0a0a8cda11277c1a636c8b32d28cdb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "30413964"
---
# <a name="implement-a-wrapper-for-inspectors-and-track-item-level-events-in-each-inspector"></a>为检查器实现包装并在每个检查器中跟踪项目级事件

此主题包含两个代码示例，用来演示如何实现 [Inspectors](https://msdn.microsoft.com/library/bb623458\(v=office.15\)) 集合的包装，以及如何使用该包装跟踪集合中每个 [Inspector](https://msdn.microsoft.com/library/bb647744\(v=office.15\)) 对象中的项目级事件。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

下面的两个代码示例实现了 Connect 及 OutlookInspector 类。 第一个代码示例涉及你在 Connect 类中用来实现 **Inspectors** 集合包装的方法和事件处理程序。 第二个代码示例涉及 **OutlookInspector** 类的一个简单实现。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

在以下的代码示例中，在新检查器窗口创建之后、显示之前会发生 [NewInspector(Inspector)](https://msdn.microsoft.com/library/bb610594\(v=office.15\)) 事件。 用户操作也可以创建新的检查器窗口。 系统会声明 **Connect** 类中一个名为 inspectors 的类级实例变量，还将挂起 **NewInspector** 事件。 

在 inspectors\_NewInspector 方法中，**FindOutlookInspector** 方法会检查新的检查器窗口是否已在 inspectorWindows 列表中。 如果 FindOutlookInspector 没有在 inspectorWindows 中找到 **Inspector** 对象，**AddInspector** 方法会向 inspectorWindows 添加 **OutlookInspector** 类的一个实例。 可以使用 **OutlookInspector** 类来为此特定检查器窗口引发事件。 第二个代码示例演示了 **OutlookInspector** 类的实现。

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

以下代码示例是 **OutlookInspector** 类的实现。 此类用于为前面的代码示例中的检查器窗口引发事件。 可以同时打开多个检查器窗口。 通过在此类构造函数中挂起项目级事件（如 [Open](https://msdn.microsoft.com/library/bb644296\(v=office.15\))、[PropertyChange](https://msdn.microsoft.com/library/bb647794\(v=office.15\)) 和 [CustomPropertyChange](https://msdn.microsoft.com/library/bb645015\(v=office.15\)) 等），可跟踪这些事件。 [ContactItem](https://msdn.microsoft.com/library/bb644956\(v=office.15\)) 对象的 [Close](https://msdn.microsoft.com/library/bb645009\(v=office.15\)) 事件也可在此类构造函数中挂起。 你可以根据需要定义其他类级别的项目实例变量。 原来在 OutlookInspector 构造函数中挂起的所有事件在 OutlookInspectorWindow\_Close 事件处理程序中均处于解除挂起状态。

请注意，在对象模型级别，**Outlook inspector** 并不特别针对任何 Outlook 项目类型。 此代码示例利用[创建用于访问常见 Outlook 项成员的帮助程序类](how-to-create-a-helper-class-to-access-common-outlook-item-members.md)一文中定义的 OutlookItem 帮助程序类，便捷地调用 OutlookItem.Class 属性来验证检查器中当前项目的邮件类，而无需先假设该项目为联系人项目。

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
    private Outlook.TaskItem m_Task;             

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

## <a name="see-also"></a>另请参阅

- [使用 Outlook 事件的示例任务](sample-tasks-using-outlook-events.md)

