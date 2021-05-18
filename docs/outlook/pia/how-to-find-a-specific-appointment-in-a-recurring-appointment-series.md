---
title: 在定期约会系列中查找特定约会
TOCTitle: Find a specific appointment in a recurring appointment series
ms:assetid: 01f55f04-7245-4325-a354-50a6eb270a31
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184586(v=office.15)
ms:contentKeyID: 55119812
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 19502895996d4777f2d1a6887aa80883a5398a09
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320249"
---
# <a name="find-a-specific-appointment-in-a-recurring-appointment-series"></a>在定期约会系列中查找特定约会

此代码示例展示了如何返回代表定期约会系列中特定约会的 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

若要查找在指定日期和时间发生的定期约会的实例，请使用 [RecurrencePattern](https://msdn.microsoft.com/library/bb622806\(v=office.15\)) 对象的 [GetOccurrence(DateTime)](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) 方法返回 **AppointmentItem** 对象。

当使用定期约会项目时，您应当先释放以前的所有引用，再获取对定期约会项目的新引用，然后才访问或修改项目，并在完成和保存更改后立即释放这些引用。 此做法适用于定期 **AppointmentItem** 对象，以及任何 [Exception](https://msdn.microsoft.com/library/bb610440\(v=office.15\)) 或 [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) 对象。 若要在 Visual Basic 中释放引用，请将现有对象设置为“Nothing”。 在 C\# 中，显式释放相应对象占用的内存。

请注意，即使是在您释放引用并尝试获取新引用之后，如果仍存在对以上对象之一的活动引用（由另一个加载项或 Outlook 保存），则新引用也仍将指向对象的过期副本。因此，在完成使用定期约会后立即释放引用非常重要。

在下面的代码示例中，CheckOccurrenceExample 使用在[创建模式为每周一次的定期约会](how-to-create-a-recurring-appointment-that-has-a-weekly-pattern.md)的代码示例中创建的定期约会。 然后，它调用 GetOccurrence 方法，以确定定期约会的开始日期和时间是否为指定值。 为了确保过程在提供的信息与定期约会实例的开始日期和时间不匹配时仍可继续执行，此示例使用 try…catch 块。 对定期约会系列中的每个约会调用 GetOccurrence 方法后，CheckOccurrenceExample 测试 singleAppt 变量，以确定它是否设置为空引用（表明方法失败且未返回 **AppointmentItem** 对象）。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void CheckOccurrenceExample()
{
    Outlook.AppointmentItem appt = Application.Session.
        GetDefaultFolder(Outlook.OlDefaultFolders.olFolderCalendar).
        Items.Find(
        "[Subject]='Recurring Appointment DaysOfWeekMask Example'")
        as Outlook.AppointmentItem;
    if (appt != null)
    {
        try
        {
            Outlook.RecurrencePattern pattern =
                appt.GetRecurrencePattern();
            Outlook.AppointmentItem singleAppt =
                pattern.GetOccurrence(DateTime.Parse(
                "7/21/2006 2:00 PM"))
                as Outlook.AppointmentItem;
            if (singleAppt != null)
            {
                Debug.WriteLine("7/21/2006 2:00 PM occurrence found.");
            }
        }
        catch (Exception ex)
        {
            Debug.WriteLine(ex.Message);
        }
    }
}
```

## <a name="see-also"></a>另请参阅

- [约会](appointments.md)

