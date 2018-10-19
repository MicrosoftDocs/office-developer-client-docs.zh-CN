---
title: 向收件人分配任务
TOCTitle: Assign a task to a recipient
ms:assetid: c6be97a7-de3f-43e5-9111-534d0f04e986
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184639(v=office.15)
ms:contentKeyID: 55119929
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 55063cfd6c448fe32a9d4348069266b9e4a8b566
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406328"
---
# <a name="assign-a-task-to-a-recipient"></a>向收件人分配任务

此代码示例展示了如何创建任务，并将它分配给收件人。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。


在下面的代码示例中，AssignTaskExample 创建 [TaskItem](https://msdn.microsoft.com/library/bb624227\(v=office.15\)) 对象，并指定 [Subject](https://msdn.microsoft.com/library/bb624148\(v=office.15\))、[StartDate](https://msdn.microsoft.com/library/bb643988\(v=office.15\)) 和 [DueDate](https://msdn.microsoft.com/library/bb612307\(v=office.15\)) 属性的值。 [Assign()](https://msdn.microsoft.com/library/bb644565\(v=office.15\)) 方法指定任务为已分配任务。 当 [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) 对象通过 [Add(String)](https://msdn.microsoft.com/library/bb612668\(v=office.15\)) 方法添加到 **TaskItem** 后，[Send()](https://msdn.microsoft.com/library/bb646608\(v=office.15\)) 方法将任务发送给收件人。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void AssignTaskExample()
{
    Outlook.TaskItem task = Application.CreateItem(
        Outlook.OlItemType.olTaskItem) as Outlook.TaskItem;
    task.Subject = "Tax Preparation";
    task.StartDate = DateTime.Parse("4/1/2007 8:00 AM");
    task.DueDate = DateTime.Parse("4/15/2007 8:00 AM");
    Outlook.RecurrencePattern pattern =
        task.GetRecurrencePattern();
    pattern.RecurrenceType = Outlook.OlRecurrenceType.olRecursYearly;
    pattern.PatternStartDate = DateTime.Parse("4/1/2007");
    pattern.NoEndDate = true;
    task.ReminderSet = true;
    task.ReminderTime = DateTime.Parse("4/1/2007 8:00 AM");
    task.Assign();
    task.Recipients.Add("accountant@example.com");
    task.Recipients.ResolveAll();
    task.Send();
}
```

## <a name="see-also"></a>另请参阅

- [任务](tasks.md)

