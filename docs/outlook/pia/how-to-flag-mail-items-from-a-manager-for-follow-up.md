---
title: 标记来自经理的邮件项以供跟进
TOCTitle: Flag mail items from a manager for follow-up
ms:assetid: 5f7f3678-0f63-451e-ba08-cd973525aa1b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424470(v=office.15)
ms:contentKeyID: 55119898
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 06e6bdd91198cabeff689681f2999d6fd2cb725a
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542588"
---
# <a name="flag-mail-items-from-a-manager-for-follow-up"></a><span data-ttu-id="e0b48-102">标记来自经理的邮件项以供跟进</span><span class="sxs-lookup"><span data-stu-id="e0b48-102">Flag mail items from a manager for follow-up</span></span>

<span data-ttu-id="e0b48-103">此代码示例展示了如何标记来自用户的经理的电子邮件项以供跟进。</span><span class="sxs-lookup"><span data-stu-id="e0b48-103">This example shows how to flag email items that were received from the user’s manager for follow-up.</span></span>

## <a name="example"></a><span data-ttu-id="e0b48-104">示例</span><span class="sxs-lookup"><span data-stu-id="e0b48-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="e0b48-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="e0b48-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="e0b48-p101">Microsoft Outlook 提供了一个任务标记系统，在该系统中可以标记邮件项目或联系人项目等某些 Outlook 项目以进行跟踪。当标记某个 Outlook 项目以进行跟踪时，有关该 Outlook 项目的信息以及其他基于任务的信息将显示在 Outlook 用户界面中的“待办事项栏”和“日历”导航模块上。“待办事项栏”在 Outlook 资源管理器窗口的典型配置中显示为垂直窗格。它包含数据导航器控件、即将发生的约会和已加以标记进行跟踪的项目。“待办事项栏”本身是不可扩展的，并且您只能通过 Outlook 用户界面为“待办事项栏”设置配置选项。通过标记项目，您可以组织任务和待办事项并设置其优先级。</span><span class="sxs-lookup"><span data-stu-id="e0b48-p101">Microsoft Outlook provides a task flagging system in which certain Outlook items such as mail items or contact items can be flagged for follow-up. When you flag an Outlook item for follow-up, information about that Outlook item, along with other task-based information, is displayed on the **To-Do Bar** and Calendar navigation module in the Outlook user interface. The **To-Do Bar** is displayed as a vertical pane in a typical configuration of the Outlook explorer window. It contains a date navigator control, upcoming appointments, and items that have been flagged for follow-up. The **To-Do Bar** itself is not extensible, and you can set configuration options for the **To-Do Bar** only through the Outlook user interface. Flagging items allows to you organize and prioritize tasks and to-do items.</span></span>

<span data-ttu-id="e0b48-112">下面的代码示例标记一组项，以供在指定的时间间隔内跟进。</span><span class="sxs-lookup"><span data-stu-id="e0b48-112">The following code example marks a group of items for a specified follow-up interval.</span></span> <span data-ttu-id="e0b48-113">此代码示例使用 DAV 搜索和定位 (DASL) 查询，以筛选出使用经理姓名作为发件人的“IPM.NOTE”类型邮件，从而获取当前用户收件箱中来自当前用户的经理的所有项。</span><span class="sxs-lookup"><span data-stu-id="e0b48-113">The example gets all items in the current user’s Inbox that are from the current user’s manager by using a DAV Searching and Locating (DASL) query to filter for messages of type “IPM.NOTE” with the manager’s name as the sender.</span></span> <span data-ttu-id="e0b48-114">然后，此代码示例根据 [Importance](https://msdn.microsoft.com/library/bb611974\(v=office.15\)) 属性的 [OlImportance](https://msdn.microsoft.com/library/bb609592\(v=office.15\)) 值标记所有项。</span><span class="sxs-lookup"><span data-stu-id="e0b48-114">It then flags all items according to the [OlImportance](https://msdn.microsoft.com/library/bb609592\(v=office.15\)) value of the [Importance](https://msdn.microsoft.com/library/bb611974\(v=office.15\)) property.</span></span> <span data-ttu-id="e0b48-115">此代码示例使用 [MarkAsTask(OlMarkInterval)](https://msdn.microsoft.com/library/bb609068\(v=office.15\)) 方法，将所有重要性高的项都标记为今天跟进，将所有重要性一般的项都标记为本周跟进。</span><span class="sxs-lookup"><span data-stu-id="e0b48-115">All high-importance items are flagged for follow-up today and all normal-importance items are flagged for follow-up this week by using the [MarkAsTask(OlMarkInterval)](https://msdn.microsoft.com/library/bb609068\(v=office.15\)) method.</span></span>


> [!NOTE]
> <span data-ttu-id="e0b48-116">**Importance** 属性和 **MarkAsTask** 方法是 **Item** 对象成员。</span><span class="sxs-lookup"><span data-stu-id="e0b48-116">The **Importance** property and the **MarkAsTask** method are **Item** object members.</span></span>


<span data-ttu-id="e0b48-117">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="e0b48-117">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="e0b48-118">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="e0b48-118">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="e0b48-119">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="e0b48-119">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void DemoTaskFlagging()
{
    const string PR_SENT_REPRESENTING_NAME =
        "http://schemas.microsoft.com/mapi/proptag/0x0042001E";
    const string PR_MESSAGE_CLASS =
        "http://schemas.microsoft.com/mapi/proptag/0x001A001E";
    Outlook.AddressEntry currentUser =
        Application.Session.CurrentUser.AddressEntry;
    if (currentUser.Type == "EX")
    {
        Outlook.ExchangeUser manager;
        try
        {
            manager = currentUser.
                GetExchangeUser().GetExchangeUserManager();
        }
        catch
        {
            Debug.WriteLine("Could not obtain user's manager.");
            return;
        }
        if (manager != null)
        {
            string displayName = manager.Name;
            string filter = "@SQL=" + "\""
                + PR_SENT_REPRESENTING_NAME + "\""
                + " = '" + displayName + "'" + " AND " + "\""
                + PR_MESSAGE_CLASS + "\"" + " = 'IPM.NOTE'";
            Outlook.Items items =
                Application.Session.GetDefaultFolder(
                Outlook.OlDefaultFolders.olFolderInbox).
                Items.Restrict(filter);
            foreach (Outlook.MailItem mail in items)
            {
                if (mail.Importance ==
                    Outlook.OlImportance.olImportanceHigh)
                {
                    mail.MarkAsTask(Outlook.OlMarkInterval.olMarkToday);
                    mail.Save();
                }
                if (mail.Importance ==
                    Outlook.OlImportance.olImportanceNormal)
                {
                    mail.MarkAsTask(Outlook.OlMarkInterval.olMarkThisWeek);
                    mail.Save();
                }
            }
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="e0b48-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0b48-120">See also</span></span>

- [<span data-ttu-id="e0b48-121">任务</span><span class="sxs-lookup"><span data-stu-id="e0b48-121">Tasks</span></span>](tasks.md)

