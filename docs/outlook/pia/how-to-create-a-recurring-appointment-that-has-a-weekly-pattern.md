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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359169"
---
# <a name="create-a-recurring-appointment-that-has-a-weekly-pattern"></a>创建模式为每周一次的定期约会

本示例演示如何创建具有每周模式的定期约会（例如，在每个星期一、星期三和星期五发生的约会）。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。


当你新建定期约会时，定期模式的依据为你在创建约会时指定的时间。 例如，如果创建一个在每天的下午 1:00 定期发生的约会，则该约会将只在每天的下午 1:00 定期发生。 若要更改约会的定期模式，请设置约会的 [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) 对象属性。 在设置其他 RecurrencePattern 属性前，先设置 RecurrencePattern 对象的 [RecurrenceType](https://msdn.microsoft.com/library/bb623463\(v=office.15\)) 属性。 下表列出了给定 RecurrenceType（由 [OlRecurrenceType](https://msdn.microsoft.com/library/bb647129\(v=office.15\)) 枚举指定）的有效 RecurrencePattern 属性。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>OlRecurrenceType 值</p></th>
<th><p>有效 RecurrencePattern 属性</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>olRecursDaily</p></td>
<td><p><a href="https://msdn.microsoft.com/library/bb644889(v=office.15)">Duration</a>、<a href="https://msdn.microsoft.com/library/bb644544(v=office.15)">EndTime</a>、<a href="https://msdn.microsoft.com/library/bb624287(v=office.15)">Interval</a>、<a href="https://msdn.microsoft.com/library/bb646849(v=office.15)">NoEndDate</a>、<a href="https://msdn.microsoft.com/library/bb611303(v=office.15)">Occurrences</a>、<a href="https://msdn.microsoft.com/library/bb624492(v=office.15)">PatternStartDate</a>、<a href="https://msdn.microsoft.com/library/bb609279(v=office.15)">PatternEndDate</a>、<a href="https://msdn.microsoft.com/library/bb646324(v=office.15)">StartTime</a></p></td>
</tr>
<tr class="even">
<td><p>olRecursWeekly</p></td>
<td><p><a href="https://msdn.microsoft.com/library/bb609163(v=office.15)">DayOfWeekMask</a>、Duration、EndTime、Interval、NoEndDate、Occurrences、PatternStartDate、PatternEndDate、StartTime</p></td>
</tr>
<tr class="odd">
<td><p>olRecursMonthly</p></td>
<td><p><a href="https://msdn.microsoft.com/library/bb622604(v=office.15)">DayOfMonth</a>、Duration、EndTime、Interval、NoEndDate、Occurrences、PatternStartDate、PatternEndDate、StartTime</p></td>
</tr>
<tr class="even">
<td><p>olRecursMonthNth</p></td>
<td><p>DayOfWeekMask、Duration、EndTime、Interval、<a href="https://msdn.microsoft.com/library/bb645269(v=office.15)">Instance</a>、NoEndDate、Occurrences、PatternStartDate、PatternEndDate、StartTime</p></td>
</tr>
<tr class="odd">
<td><p>olRecursYearly</p></td>
<td><p>DayOfMonth、Duration、EndTime、Interval、<a href="https://msdn.microsoft.com/library/bb610515(v=office.15)">MonthOfYear</a>、NoEndDate、Occurrences、PatternStartDate、PatternEndDate、StartTime</p></td>
</tr>
<tr class="even">
<td><p>olRecursYearNth</p></td>
<td><p>DayOfWeekMask、Duration、EndTime、Interval、Instance、NoEndDate、Occurrences、PatternStartDate、PatternEndDate、StartTime</p></td>
</tr>
</tbody>
</table>


当使用定期约会项目时，您应当先释放以前的所有引用，再获取对定期约会项目的新引用，然后才访问或修改项目，并在完成和保存更改后立即释放这些引用。 此做法适用于定期 **AppointmentItem** 对象，以及任何 [Exception](https://msdn.microsoft.com/library/bb610440\(v=office.15\)) 或 [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) 对象。 若要在 Visual Basic 中释放引用，请将现有对象设置为“Nothing”。 在 C\# 中，显式释放相应对象占用的内存。

请注意，即使是在您释放引用并尝试获取新引用之后，如果仍存在对以上对象之一的活动引用（由另一个加载项或 Outlook 保存），则新引用也仍将指向对象的过期副本。因此，在完成使用定期约会后立即释放引用非常重要。

在下面的代码示例中, RecurringAppointmentEveryMondayWednesdayFriday 创建一个[AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\))对象, 然后调用[GetRecurrencePattern ()](https://msdn.microsoft.com/library/bb652582\(v=office.15\))以获取新创建的约会的 RecurrencePattern 对象。 然后，RecurringAppointmentEveryMondayWednesdayFriday 设置 RecurrenceType、DayOfWeekMask、PatternStartDate、PatternEndDate, Duration、StartTime、EndTime 和 Subject 属性，保存约会，最后使用“每个星期一、星期三和星期五发生，生效日期是 2006 年 7 月 10 日，截至日期是 2006 年 8 月 25 日，从下午 2:00 到下午 3:00”模式显示约会。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。 下面几行代码展示了如何在 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [约会](appointments.md)

