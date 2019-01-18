---
title: 创建任务项
TOCTitle: Create a task item
ms:assetid: d458dd31-2771-4a3c-a713-13c7e4e02a74
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184644(v=office.15)
ms:contentKeyID: 55119894
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c4f9a8f156ec43f446f27c94b2cb061de181b7d4
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28698440"
---
# <a name="create-a-task-item"></a>创建任务项

此代码示例展示了如何使用 [MarkAsTask(OlMarkInterval)](https://msdn.microsoft.com/library/bb609068\(v=office.15\)) 方法创建任务项。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。


在下面的代码示例中，CreateToDoItemExample 创建待办事项，具体方法为对项调用 **MarkAsTask** 方法并保存项。 此示例标记项以供明天跟进，并设置明天上午 10:00 的提醒 （具体是使用 [ReminderSet](https://msdn.microsoft.com/library/bb622600\(v=office.15\)) 和 [ReminderTime](https://msdn.microsoft.com/library/bb622803\(v=office.15\)) 属性）。 然后，此代码示例使用 [Save()](https://msdn.microsoft.com/library/bb645518\(v=office.15\)) 方法保存项。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void CreateToDoItemExample()
{
    // Date operations
    DateTime today = DateTime.Parse("10:00 AM");
    TimeSpan duration = TimeSpan.FromDays(1);
    DateTime tomorrow = today.Add(duration);
    Outlook.MailItem mail = Application.Session.
        GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox).Items.Find(
        "[MessageClass]='IPM.Note'") as Outlook.MailItem;
    mail.MarkAsTask(Outlook.OlMarkInterval.olMarkTomorrow);
    mail.TaskStartDate = today;
    mail.ReminderSet = true;
    mail.ReminderTime = tomorrow;
    mail.Save();
}
```

## <a name="see-also"></a>另请参阅

- [任务](tasks.md)

