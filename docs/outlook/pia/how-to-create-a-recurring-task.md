---
title: 创建定期任务
TOCTitle: Create a recurring task
ms:assetid: bbca8527-79af-4c00-aae7-a1fd381e707c
ms:mtpsurl: https://msdn.microsoft.com/library/Bb623455(v=office.15)
ms:contentKeyID: 55119932
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 6a9308e42ebaea0bcd07066a31bab7eb7a768604
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405803"
---
# <a name="create-a-recurring-task"></a><span data-ttu-id="fd480-102">创建定期任务</span><span class="sxs-lookup"><span data-stu-id="fd480-102">Create a recurring task</span></span>

<span data-ttu-id="fd480-103">此代码示例创建定期任务。</span><span class="sxs-lookup"><span data-stu-id="fd480-103">This example creates a recurrent task.</span></span>

## <a name="example"></a><span data-ttu-id="fd480-104">示例</span><span class="sxs-lookup"><span data-stu-id="fd480-104">Example</span></span>

<span data-ttu-id="fd480-105">此代码示例创建 [TaskItem](https://msdn.microsoft.com/library/bb624227\(v=office.15\)) 对象，并使用 **TaskItem** 的 [GetRecurrencePattern](https://msdn.microsoft.com/library/bb647080\(v=office.15\)) 方法将任务设置为定期任务。</span><span class="sxs-lookup"><span data-stu-id="fd480-105">This code sample creates a [TaskItem](https://msdn.microsoft.com/library/bb624227\(v=office.15\)) object and uses the [GetRecurrencePattern](https://msdn.microsoft.com/library/bb647080\(v=office.15\)) method of the **TaskItem** to make the task a recurrent task.</span></span>

<span data-ttu-id="fd480-106">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="fd480-106">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="fd480-107">不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="fd480-107">The Imports or using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="fd480-108">下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="fd480-108">The following lines of code show how to do the import and assignment in Visual Basic and C#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub CreateRecurringTask()
    Dim task As Outlook.TaskItem = CType(Application.CreateItem( _
        Outlook.OlItemType.olTaskItem), Outlook.TaskItem)
    task.Subject = "Tax Preparation"
    task.StartDate = DateTime.Parse("4/1/2007 8:00 AM")
    task.DueDate = DateTime.Parse("4/15/2007 8:00 AM")
    Dim pattern As Outlook.RecurrencePattern = _
        task.GetRecurrencePattern()
    pattern.RecurrenceType = Outlook.OlRecurrenceType.olRecursYearly
    pattern.PatternStartDate = DateTime.Parse("4/1/2007")
    pattern.NoEndDate = True
    task.ReminderSet = True
    task.ReminderTime = DateTime.Parse("4/1/2007 8:00 AM")
    task.Save()
End Sub
```


```csharp
private void CreateRecurringTask()
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
    task.Save();
}
```

## <a name="see-also"></a><span data-ttu-id="fd480-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd480-109">See also</span></span>

- [<span data-ttu-id="fd480-110">任务</span><span class="sxs-lookup"><span data-stu-id="fd480-110">Tasks</span></span>](tasks.md)

