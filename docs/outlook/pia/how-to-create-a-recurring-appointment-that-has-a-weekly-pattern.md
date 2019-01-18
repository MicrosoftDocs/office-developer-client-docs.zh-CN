---
title: 创建模式为每周一次的定期约会
TOCTitle: Create a recurring appointment that has a weekly pattern
ms:assetid: 20b46b26-e278-451b-9e35-36683205d164
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184595(v=office.15)
ms:contentKeyID: 55119810
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b326ad23f8cbe47e5141775eacdd2bc9302db3cd
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716416"
---
# <a name="create-a-recurring-appointment-that-has-a-weekly-pattern"></a><span data-ttu-id="8d210-102">创建模式为每周一次的定期约会</span><span class="sxs-lookup"><span data-stu-id="8d210-102">Create a recurring appointment that has a weekly pattern</span></span>

<span data-ttu-id="8d210-103">本示例演示如何创建具有每周模式的定期约会（例如，在每个星期一、星期三和星期五发生的约会）。</span><span class="sxs-lookup"><span data-stu-id="8d210-103">This example shows how to create a recurring appointment that has a weekly pattern (for example, an appointment that occurs every Monday, Wednesday, and Friday).</span></span>

## <a name="example"></a><span data-ttu-id="8d210-104">示例</span><span class="sxs-lookup"><span data-stu-id="8d210-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="8d210-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="8d210-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>


<span data-ttu-id="8d210-106">当你新建定期约会时，定期模式的依据为你在创建约会时指定的时间。</span><span class="sxs-lookup"><span data-stu-id="8d210-106">When you create a new recurring appointment, the recurrence pattern is based on the time you specify when you create the appointment.</span></span> <span data-ttu-id="8d210-107">例如，如果创建一个在每天的下午 1:00 定期发生的约会，则该约会将只在每天的下午 1:00 定期发生。</span><span class="sxs-lookup"><span data-stu-id="8d210-107">For example, if you create an appointment that recurs daily at 1:00 PM, the appointment will recur only at 1:00 PM on a daily basis.</span></span> <span data-ttu-id="8d210-108">若要更改约会的定期模式，请设置约会的 [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) 对象属性。</span><span class="sxs-lookup"><span data-stu-id="8d210-108">To change the recurrence pattern of an appointment, set the properties of the appointment’s [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) object.</span></span> <span data-ttu-id="8d210-109">在设置其他 RecurrencePattern 属性前，先设置 RecurrencePattern 对象的 [RecurrenceType](https://msdn.microsoft.com/library/bb623463\(v=office.15\)) 属性。</span><span class="sxs-lookup"><span data-stu-id="8d210-109">Set the [RecurrenceType](https://msdn.microsoft.com/library/bb623463\(v=office.15\)) property of the RecurrencePattern object before setting other RecurrencePattern properties.</span></span> <span data-ttu-id="8d210-110">下表列出了给定 RecurrenceType（由 [OlRecurrenceType](https://msdn.microsoft.com/library/bb647129\(v=office.15\)) 枚举指定）的有效 RecurrencePattern 属性。</span><span class="sxs-lookup"><span data-stu-id="8d210-110">The following table shows valid RecurrencePattern properties for a given RecurrenceType (specified by the [OlRecurrenceType](https://msdn.microsoft.com/library/bb647129\(v=office.15\)) enumeration).</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8d210-111">OlRecurrenceType 值</span><span class="sxs-lookup"><span data-stu-id="8d210-111">OlRecurrenceType value</span></span></p></th>
<th><p><span data-ttu-id="8d210-112">有效 RecurrencePattern 属性</span><span class="sxs-lookup"><span data-stu-id="8d210-112">Valid RecurrencePattern properties</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d210-113">olRecursDaily</span><span class="sxs-lookup"><span data-stu-id="8d210-113">olRecursDaily</span></span></p></td>
<td><p><span data-ttu-id="8d210-114"><a href="https://msdn.microsoft.com/library/bb644889(v=office.15)">Duration</a>、<a href="https://msdn.microsoft.com/library/bb644544(v=office.15)">EndTime</a>、<a href="https://msdn.microsoft.com/library/bb624287(v=office.15)">Interval</a>、<a href="https://msdn.microsoft.com/library/bb646849(v=office.15)">NoEndDate</a>、<a href="https://msdn.microsoft.com/library/bb611303(v=office.15)">Occurrences</a>、<a href="https://msdn.microsoft.com/library/bb624492(v=office.15)">PatternStartDate</a>、<a href="https://msdn.microsoft.com/library/bb609279(v=office.15)">PatternEndDate</a>、<a href="https://msdn.microsoft.com/library/bb646324(v=office.15)">StartTime</a></span><span class="sxs-lookup"><span data-stu-id="8d210-114"><a href="https://msdn.microsoft.com/library/bb644889(v=office.15)">Duration</a>, <a href="https://msdn.microsoft.com/library/bb644544(v=office.15)">EndTime</a>, <a href="https://msdn.microsoft.com/library/bb624287(v=office.15)">Interval</a>, <a href="https://msdn.microsoft.com/library/bb646849(v=office.15)">NoEndDate</a>, <a href="https://msdn.microsoft.com/library/bb611303(v=office.15)">Occurrences</a>, <a href="https://msdn.microsoft.com/library/bb624492(v=office.15)">PatternStartDate</a>, <a href="https://msdn.microsoft.com/library/bb609279(v=office.15)">PatternEndDate</a>, <a href="https://msdn.microsoft.com/library/bb646324(v=office.15)">StartTime</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d210-115">olRecursWeekly</span><span class="sxs-lookup"><span data-stu-id="8d210-115">olRecursWeekly</span></span></p></td>
<td><p><span data-ttu-id="8d210-116"><a href="https://msdn.microsoft.com/library/bb609163(v=office.15)">DayOfWeekMask</a>、Duration、EndTime、Interval、NoEndDate、Occurrences、PatternStartDate、PatternEndDate、StartTime</span><span class="sxs-lookup"><span data-stu-id="8d210-116"><a href="https://msdn.microsoft.com/library/bb609163(v=office.15)">DayOfWeekMask</a>, Duration, EndTime, Interval, NoEndDate, Occurrences, PatternStartDate, PatternEndDate, StartTime</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d210-117">olRecursMonthly</span><span class="sxs-lookup"><span data-stu-id="8d210-117">olRecursMonthly</span></span></p></td>
<td><p><span data-ttu-id="8d210-118"><a href="https://msdn.microsoft.com/library/bb622604(v=office.15)">DayOfMonth</a>、Duration、EndTime、Interval、NoEndDate、Occurrences、PatternStartDate、PatternEndDate、StartTime</span><span class="sxs-lookup"><span data-stu-id="8d210-118"><a href="https://msdn.microsoft.com/library/bb622604(v=office.15)">DayOfMonth</a>, Duration, EndTime, Interval, NoEndDate, Occurrences, PatternStartDate, PatternEndDate, StartTime</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d210-119">olRecursMonthNth</span><span class="sxs-lookup"><span data-stu-id="8d210-119">olRecursMonthNth</span></span></p></td>
<td><p><span data-ttu-id="8d210-120">DayOfWeekMask、Duration、EndTime、Interval、<a href="https://msdn.microsoft.com/library/bb645269(v=office.15)">Instance</a>、NoEndDate、Occurrences、PatternStartDate、PatternEndDate、StartTime</span><span class="sxs-lookup"><span data-stu-id="8d210-120">DayOfWeekMask, Duration, EndTime, Interval, <a href="https://msdn.microsoft.com/library/bb645269(v=office.15)">Instance</a>, NoEndDate, Occurrences, PatternStartDate, PatternEndDate, StartTime</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d210-121">olRecursYearly</span><span class="sxs-lookup"><span data-stu-id="8d210-121">olRecursYearly</span></span></p></td>
<td><p><span data-ttu-id="8d210-122">DayOfMonth、Duration、EndTime、Interval、<a href="https://msdn.microsoft.com/library/bb610515(v=office.15)">MonthOfYear</a>、NoEndDate、Occurrences、PatternStartDate、PatternEndDate、StartTime</span><span class="sxs-lookup"><span data-stu-id="8d210-122">DayOfMonth, Duration, EndTime, Interval, <a href="https://msdn.microsoft.com/library/bb610515(v=office.15)">MonthOfYear</a>, NoEndDate, Occurrences, PatternStartDate, PatternEndDate, StartTime</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d210-123">olRecursYearNth</span><span class="sxs-lookup"><span data-stu-id="8d210-123">olRecursYearNth</span></span></p></td>
<td><p><span data-ttu-id="8d210-124">DayOfWeekMask、Duration、EndTime、Interval、Instance、NoEndDate、Occurrences、PatternStartDate、PatternEndDate、StartTime</span><span class="sxs-lookup"><span data-stu-id="8d210-124">DayOfWeekMask, Duration, EndTime, Interval, Instance, NoEndDate, Occurrences, PatternStartDate, PatternEndDate, StartTime</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8d210-125">当使用定期约会项目时，您应当先释放以前的所有引用，再获取对定期约会项目的新引用，然后才访问或修改项目，并在完成和保存更改后立即释放这些引用。</span><span class="sxs-lookup"><span data-stu-id="8d210-125">When you work with recurring appointment items, you should release any prior references, obtain new references to the recurring appointment item before you access or modify the item, and release these references as soon as you are finished and have saved the changes.</span></span> <span data-ttu-id="8d210-126">此做法适用于定期 **AppointmentItem** 对象，以及任何 [Exception](https://msdn.microsoft.com/library/bb610440\(v=office.15\)) 或 [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="8d210-126">This practice applies to the recurring **AppointmentItem** object, and any [Exception](https://msdn.microsoft.com/library/bb610440\(v=office.15\)) or [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) object.</span></span> <span data-ttu-id="8d210-127">若要在 Visual Basic 中释放引用，请将现有对象设置为“Nothing”。</span><span class="sxs-lookup"><span data-stu-id="8d210-127">To release a reference in Visual Basic, set that existing object to Nothing.</span></span> <span data-ttu-id="8d210-128">在 C\# 中，显式释放相应对象占用的内存。</span><span class="sxs-lookup"><span data-stu-id="8d210-128">In C\#, explicitly release the memory for that object.</span></span>

<span data-ttu-id="8d210-p103">请注意，即使是在您释放引用并尝试获取新引用之后，如果仍存在对以上对象之一的活动引用（由另一个加载项或 Outlook 保存），则新引用也仍将指向对象的过期副本。因此，在完成使用定期约会后立即释放引用非常重要。</span><span class="sxs-lookup"><span data-stu-id="8d210-p103">Note that even after you release your reference and attempt to obtain a new reference, if there is still an active reference (held by another add-in or Outlook) to one of the above objects, your new reference will still point to an out-of-date copy of the object. Therefore, it is important that you release your references as soon as you are finished with the recurring appointment.</span></span>

<span data-ttu-id="8d210-131">在下面的代码示例中，RecurringAppointmentEveryMondayWednesdayFriday 先创建 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象，再调用 [GetRecurrencePattern()](https://msdn.microsoft.com/library/bb652582\(v=office.15\)) 来获取新建约会的 RecurrencePattern 对象。</span><span class="sxs-lookup"><span data-stu-id="8d210-131">In the following code example, RecurringAppointmentEveryMondayWednesdayFriday creates an [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) object, and then calls [GetRecurrencePattern()](https://msdn.microsoft.com/library/bb652582\(v=office.15\)) to get the newly created appointment’s RecurrencePattern object.</span></span> <span data-ttu-id="8d210-132">然后，RecurringAppointmentEveryMondayWednesdayFriday 设置 RecurrenceType、DayOfWeekMask、PatternStartDate、PatternEndDate、Duration、StartTime、EndTime 和 Subject 属性，并保存约会，最后显示模式为“每星期一、星期三和星期五发生一次，有效期为 2006 年 7 月 10 日至 2006 年 8 月 25 日，时间范围为下午 2:00 到下午 3:00”的约会。</span><span class="sxs-lookup"><span data-stu-id="8d210-132">RecurringAppointmentEveryMondayWednesdayFriday then sets the RecurrenceType, DayOfWeekMask, PatternStartDate, PatternEndDate, Duration, StartTime, EndTime, and Subject properties, saves the appointment, and finally displays the appointment with the pattern "Occurs every Monday, Wednesday, and Friday effective 7/10/2006 until 8/25/2006 from 2:00 PM to 3:00 PM."</span></span>

<span data-ttu-id="8d210-133">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="8d210-133">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="8d210-134">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="8d210-134">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="8d210-135">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="8d210-135">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void RecurringAppointmentEveryMondayWednesdayFriday()
{
    Outlook.AppointmentItem appt = Application.CreateItem(
        Outlook.OlItemType.olAppointmentItem)
        as Outlook.AppointmentItem;
    appt.Subject = "Recurring Appointment DaysOfWeekMask Example";
    Outlook.RecurrencePattern pattern = appt.GetRecurrencePattern();
    pattern.RecurrenceType = Outlook.OlRecurrenceType.olRecursWeekly;
    // Logical OR for DayOfWeekMask creates pattern
    pattern.DayOfWeekMask = Outlook.OlDaysOfWeek.olMonday |
        Outlook.OlDaysOfWeek.olWednesday |
        Outlook.OlDaysOfWeek.olFriday;
    pattern.PatternStartDate = DateTime.Parse("7/10/2006");
    pattern.PatternEndDate = DateTime.Parse("8/25/2006");
    pattern.Duration = 60;
    pattern.StartTime = DateTime.Parse("2:00:00 PM");
    pattern.EndTime = DateTime.Parse("3:00:00 PM");
    appt.Save();
    appt.Display(false);
}
```

## <a name="see-also"></a><span data-ttu-id="8d210-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d210-136">See also</span></span>

- [<span data-ttu-id="8d210-137">约会</span><span class="sxs-lookup"><span data-stu-id="8d210-137">Appointments</span></span>](appointments.md)

