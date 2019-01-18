---
title: 标记来自经理的邮件项以供跟进
TOCTitle: Flag mail items from a manager for follow-up
ms:assetid: 5f7f3678-0f63-451e-ba08-cd973525aa1b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424470(v=office.15)
ms:contentKeyID: 55119898
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: fa3cf00a116b51f88f47ef48eab566155626dbbe
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28708597"
---
# <a name="flag-mail-items-from-a-manager-for-follow-up"></a>标记来自经理的邮件项以供跟进

此代码示例展示了如何标记来自用户的经理的电子邮件项以供跟进。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

Microsoft Outlook 提供了一个任务标记系统，在该系统中可以标记邮件项目或联系人项目等某些 Outlook 项目以进行跟踪。当标记某个 Outlook 项目以进行跟踪时，有关该 Outlook 项目的信息以及其他基于任务的信息将显示在 Outlook 用户界面中的“待办事项栏”**** 和“日历”导航模块上。“待办事项栏”**** 在 Outlook 资源管理器窗口的典型配置中显示为垂直窗格。它包含数据导航器控件、即将发生的约会和已加以标记进行跟踪的项目。“待办事项栏”**** 本身是不可扩展的，并且您只能通过 Outlook 用户界面为“待办事项栏”**** 设置配置选项。通过标记项目，您可以组织任务和待办事项并设置其优先级。

下面的代码示例标记一组项，以供在指定的时间间隔内跟进。 此代码示例使用 DAV 搜索和定位 (DASL) 查询，以筛选出使用经理姓名作为发件人的“IPM.NOTE”类型邮件，从而获取当前用户收件箱中来自当前用户的经理的所有项。 然后，此代码示例根据 [Importance](https://msdn.microsoft.com/library/bb611974\(v=office.15\)) 属性的 [OlImportance](https://msdn.microsoft.com/library/bb609592\(v=office.15\)) 值标记所有项。 此代码示例使用 [MarkAsTask(OlMarkInterval)](https://msdn.microsoft.com/library/bb609068\(v=office.15\)) 方法，将所有重要性高的项都标记为今天跟进，将所有重要性一般的项都标记为本周跟进。


> [!NOTE]
> **Importance** 属性和 **MarkAsTask** 方法是 **Item** 对象成员。


如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void DemoTaskFlagging()
{
    const string PR_SENT_REPRESENTING_NAME =
        "https://schemas.microsoft.com/mapi/proptag/0x0042001E";
    const string PR_MESSAGE_CLASS =
        "https://schemas.microsoft.com/mapi/proptag/0x001A001E";
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

## <a name="see-also"></a>另请参阅

- [任务](tasks.md)

