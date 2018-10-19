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
# <a name="assign-a-task-to-a-recipient"></a><span data-ttu-id="54679-102">向收件人分配任务</span><span class="sxs-lookup"><span data-stu-id="54679-102">Assign a task to a recipient</span></span>

<span data-ttu-id="54679-103">此代码示例展示了如何创建任务，并将它分配给收件人。</span><span class="sxs-lookup"><span data-stu-id="54679-103">This example shows how to create a task and assign it to a recipient.</span></span>

## <a name="example"></a><span data-ttu-id="54679-104">示例</span><span class="sxs-lookup"><span data-stu-id="54679-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="54679-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="54679-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>


<span data-ttu-id="54679-106">在下面的代码示例中，AssignTaskExample 创建 [TaskItem](https://msdn.microsoft.com/library/bb624227\(v=office.15\)) 对象，并指定 [Subject](https://msdn.microsoft.com/library/bb624148\(v=office.15\))、[StartDate](https://msdn.microsoft.com/library/bb643988\(v=office.15\)) 和 [DueDate](https://msdn.microsoft.com/library/bb612307\(v=office.15\)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="54679-106">In the following code example, AssignTaskExample creates a [TaskItem](https://msdn.microsoft.com/library/bb624227\(v=office.15\)) object and specifies values for the [Subject](https://msdn.microsoft.com/library/bb624148\(v=office.15\)), [StartDate](https://msdn.microsoft.com/library/bb643988\(v=office.15\)), and [DueDate](https://msdn.microsoft.com/library/bb612307\(v=office.15\)) properties.</span></span> <span data-ttu-id="54679-107">[Assign()](https://msdn.microsoft.com/library/bb644565\(v=office.15\)) 方法指定任务为已分配任务。</span><span class="sxs-lookup"><span data-stu-id="54679-107">The [Assign()](https://msdn.microsoft.com/library/bb644565\(v=office.15\)) method specifies that the task is an assigned task.</span></span> <span data-ttu-id="54679-108">当 [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) 对象通过 [Add(String)](https://msdn.microsoft.com/library/bb612668\(v=office.15\)) 方法添加到 **TaskItem** 后，[Send()](https://msdn.microsoft.com/library/bb646608\(v=office.15\)) 方法将任务发送给收件人。</span><span class="sxs-lookup"><span data-stu-id="54679-108">After a [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) object is added to the **TaskItem** by using the [Add(String)](https://msdn.microsoft.com/library/bb612668\(v=office.15\)) method, the [Send()](https://msdn.microsoft.com/library/bb646608\(v=office.15\)) method sends the task to the recipient.</span></span>

<span data-ttu-id="54679-109">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="54679-109">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="54679-110">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="54679-110">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="54679-111">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="54679-111">The following line of code shows how to do the import and assignment in C#.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="54679-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54679-112">See also</span></span>

- [<span data-ttu-id="54679-113">任务</span><span class="sxs-lookup"><span data-stu-id="54679-113">Tasks</span></span>](tasks.md)

