---
title: 创建使用 YearNth 模式的每年一次定期约会
TOCTitle: Create an annual recurring appointment that uses a YearNth pattern
ms:assetid: 5fb2ad0b-248c-417d-8868-52e0550d970f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184611(v=office.15)
ms:contentKeyID: 55119811
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9fc50166674ee7b9699ef8e29c5ff1e54db705ad
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349502"
---
# <a name="create-an-annual-recurring-appointment-that-uses-a-yearnth-pattern"></a>创建使用 YearNth 模式的每年一次定期约会

本示例演示如何创建其年度定期模式是特定日期（如 6 月的第一个星期一）的约会。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

如果要创建在某个月的某一周的某一天定期发生的年度约会（例如，6 月的第一个星期一），您必须使用 YearNth 定期模式。 若要设置 YearNth 定期模式，必须先将 [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) 对象的 [RecurrenceType](https://msdn.microsoft.com/library/bb623463\(v=office.15\)) 属性设置为 olRecursYearNth。 然后，设置 [DayOfWeekMask](https://msdn.microsoft.com/library/bb609163\(v=office.15\)) 属性以指定约会应发生在星期几，并设置 [Instance](https://msdn.microsoft.com/library/bb645269\(v=office.15\)) 属性以指定年度模式下指定月份中的第 N 个星期几（例如，第三个星期二）。

当使用定期约会项目时，您应当先释放以前的所有引用，再获取对定期约会项目的新引用，然后才访问或修改项目，并在完成和保存更改后立即释放这些引用。 此做法适用于定期 **AppointmentItem** 对象，以及任何 [Exception](https://msdn.microsoft.com/library/bb610440\(v=office.15\)) 或 [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) 对象。 若要在 Visual Basic 中释放引用，请将现有对象设置为“Nothing”。 在 C\# 中，显式释放相应对象占用的内存。

请注意，即使是在您释放引用并尝试获取新引用之后，如果仍存在对以上对象之一的活动引用（由另一个加载项或 Outlook 保存），则新引用也仍将指向对象的过期副本。因此，在完成使用定期约会后立即释放引用非常重要。

在下面的代码示例中，RecurringYearNthAppointment 创建使用 YearNth 定期模式的约会。 首先，RecurringYearNthAppointment 通过创建 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象来创建定期约会。 接下来，它使用 [GetRecurrencePattern()](https://msdn.microsoft.com/library/bb652582\(v=office.15\)) 方法获取约会的定期模式。 然后，它设置以下 RecurrencePattern 属性：RecurrenceType、DayOfWeekMask、[MonthOfYear](https://msdn.microsoft.com/library/bb610515\(v=office.15\))、[Instance](https://msdn.microsoft.com/library/bb645269\(v=office.15\))、[Occurrences](https://msdn.microsoft.com/library/bb611303\(v=office.15\))、[Duration](https://msdn.microsoft.com/library/bb644889\(v=office.15\))、[PatternStartDate](https://msdn.microsoft.com/library/bb624492\(v=office.15\))、[StartTime](https://msdn.microsoft.com/library/bb646324\(v=office.15\)) 和 [EndTime](https://msdn.microsoft.com/library/bb644544\(v=office.15\))。 MonthOfYear 属性的可取数值介于 1 和 12 之间，其中每个数字都代表相应的月份。 在属性设置后，RecurringYearNthAppointment 便会保存约会，再显示模式为“发生于 6 月的第一个星期一，有效期为 2007 年 6 月 1 日至 2016 年 6 月 6 日，时间范围为下午 2:00 到下午 5:00”的约会。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。 下面几行代码展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void RecurringYearNthAppointment()
{
    Outlook.AppointmentItem appt = Application.CreateItem(
        Outlook.OlItemType.olAppointmentItem)
        as Outlook.AppointmentItem;
    appt.Subject = "Recurring YearNth Appointment";
    Outlook.RecurrencePattern pattern = appt.GetRecurrencePattern();
    pattern.RecurrenceType = Outlook.OlRecurrenceType.olRecursYearNth;
    pattern.DayOfWeekMask = Outlook.OlDaysOfWeek.olMonday;
    pattern.MonthOfYear = 6;
    pattern.Instance = 1;
    pattern.Occurrences = 10;
    pattern.Duration = 180;
    pattern.PatternStartDate = DateTime.Parse("6/1/2007");
    pattern.StartTime = DateTime.Parse("2:00:00 PM");
    pattern.EndTime = DateTime.Parse("5:00:00 PM");
    appt.Save();
    appt.Display(false);
}
```

## <a name="see-also"></a>另请参阅

- [约会](appointments.md)

