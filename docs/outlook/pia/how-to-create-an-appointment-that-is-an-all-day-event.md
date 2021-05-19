---
title: 创建属于全天事件的约会
TOCTitle: Create an appointment that is an all-day event
ms:assetid: a0d3baeb-6ed5-41b6-bef5-d6c1bb56fee3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184629(v=office.15)
ms:contentKeyID: 55119806
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b5065395afe39247f8113bc5223b0e3e403a02fa
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349474"
---
# <a name="create-an-appointment-that-is-an-all-day-event"></a>创建属于全天事件的约会

此代码示例展示了如何使用 [AllDayEvent](https://msdn.microsoft.com/library/bb610279\(v=office.15\)) 属性创建属于全天事件的约会。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

事件不同于常规约会，因为它是持续 24 小时或更长时间的活动。事件示例包括贸易展览、讨论会或节假日。事件和年度事件在用户日历中不显示为占用的时间段，而是显示为横幅。可在日历的天视图或周视图顶部看到横幅。对于全天约会，默认情况下，在其他人查看时，用户时间显示为忙碌；但对于事件或年度事件，用户时间显示为空闲。

若要以编程方式创建全天事件，请将 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象的 [AllDayEvent](https://msdn.microsoft.com/library/bb610279\(v=office.15\)) 属性设置为 true。 然后，设置 AppointmentItem 的 [Start](https://msdn.microsoft.com/library/bb647263\(v=office.15\)) 和 [End](https://msdn.microsoft.com/library/bb623715\(v=office.15\)) 属性。 如果将 AllDayEvent 属性设置为 true 而没有设置 Start 和 End 属性，则事件会在今天发生，并且它会成为约会，在日历上显示忙碌状态。 若要创建未来发生的事件，必须设置 Start 和 End 属性。

> [!NOTE]
> 若要创建属于全天事件的约会，必须将 Start 属性设置为所需事件开始日期当天的凌晨 12:00 （午夜），并将 End 属性设置为 所需事件结束日期后一天的凌晨 12:00。 如果你将 Start 或 End 时间设置为除凌晨 12:00 以外的其他日期和时间值，约会便成为多天约会，而不是全天事件。 
>
> 例如，如果事件持续时间只有一天，请将 Start 属性设置为所需事件开始日期当天的凌晨 12:00， 并将 End 属性设置为后一天的 凌晨 12:00。 应始终将 End 属性设置为 开始日期后一天的凌晨 12:00。

在下面的代码示例中，AllDayEventExample 创建 2007 年 6 月 11 日开始，2007 年 6 月 15 日结束的全天事件。请注意，约会的 End 属性设置为 2007 年 6 月 16 日的午夜 12:00。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void AllDayEventExample()
{
    Outlook.AppointmentItem appt = Application.CreateItem(
        Outlook.OlItemType.olAppointmentItem)
        as Outlook.AppointmentItem;
    appt.Subject = "Developer's Conference";
    appt.AllDayEvent = true;
    appt.Start = DateTime.Parse("6/11/2007 12:00 AM");
    appt.End = DateTime.Parse("6/16/2007 12:00 AM");
    appt.Display(false);
}
```

## <a name="see-also"></a>另请参阅

- [约会](appointments.md)

