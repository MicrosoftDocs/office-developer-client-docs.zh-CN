---
title: 使用默认定期模式创建定期约会
TOCTitle: Create a recurring appointment by using the default recurrence pattern
ms:assetid: 157bf1ae-2efe-4783-99ea-606722dde204
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184589(v=office.15)
ms:contentKeyID: 55119809
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: de58523e663349c43cc358f5b76896987a0f23b3
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28722814"
---
# <a name="create-a-recurring-appointment-by-using-the-default-recurrence-pattern"></a>使用默认定期模式创建定期约会

此代码示例展示了如何使用默认定期模式创建定期约会。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。


在 Outlook 中创建约会时，创建的是 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象。 如果 AppointmentItem 的 [IsRecurring](https://msdn.microsoft.com/library/bb609491\(v=office.15\)) 属性设置为 true，约会就是定期约会。 无法直接设置 IsRecurring。 

不过，可使用 [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) 对象创建定期约会。 若要以编程方式创建定期约会，请创建 **AppointmentItem** 对象，调用 **AppointmentItem** 对象的 [GetRecurrencePattern()](https://msdn.microsoft.com/library/bb652582\(v=office.15\)) 方法，再保存 **AppointmentItem** 对象。 这会创建使用默认定期模式的约会，即约会在创建时设置的每周几发生一次，且没有结束日期。 借助 RecurrencePattern 对象，可以创建采用指定时间间隔的定期约会（即每日、每周、每月或每年发生一次）。 如果你没有指定 RecurrencePattern 对象的时间间隔，Outlook 便会使用默认定期模式。

当使用定期约会项目时，您应当先释放以前的所有引用，再获取对定期约会项目的新引用，然后才访问或修改项目，并在完成和保存更改后立即释放这些引用。 此做法适用于定期 **AppointmentItem** 对象，以及任何 [Exception](https://msdn.microsoft.com/library/bb610440\(v=office.15\)) 或 [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) 对象。 若要在 Visual Basic 中释放引用，请将现有对象设置为“Nothing”。 在 C\# 中，显式释放相应对象占用的内存。

请注意，即使是在您释放引用并尝试获取新引用之后，如果仍存在对以上对象之一的活动引用（由另一个加载项或 Outlook 保存），则新引用也仍将指向对象的过期副本。因此，在完成使用定期约会后立即释放引用非常重要。

在下面的代码示例中，CreateRecurringAppointment 创建 **AppointmentItem** 对象。 然后，它调用 GetRecurrencePattern。 GetRecurrencePattern 返回 RecurrencePattern 对象，并保存 AppointmentItem。 这会创建使用默认定期模式的定期约会。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void CreateRecurringAppointment()
{
    Outlook.AppointmentItem appt = Application.CreateItem(
        Outlook.OlItemType.olAppointmentItem)
        as Outlook.AppointmentItem;
    appt.Subject = "Weekly Extensibility Team Meeting";
    Outlook.RecurrencePattern pattern = appt.GetRecurrencePattern();
    appt.Save();
}
```

## <a name="see-also"></a>另请参阅

- [约会](appointments.md)

