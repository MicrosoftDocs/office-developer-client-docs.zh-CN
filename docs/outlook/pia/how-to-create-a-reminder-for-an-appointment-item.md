---
title: 创建约会项提醒
TOCTitle: Create a reminder for an appointment item
ms:assetid: 85e772f0-65ac-4abc-8286-9099882a2400
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184623(v=office.15)
ms:contentKeyID: 55119814
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 1f5f31c480f31b01e53fec9651c8154765b581a3
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28722779"
---
# <a name="create-a-reminder-for-an-appointment-item"></a>创建约会项提醒

此代码示例展示了如何使用 [ReminderSet](https://msdn.microsoft.com/library/bb624262\(v=office.15\)) 属性创建约会项提醒。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。


借助 Outlook，可设置约会提醒，具体方法为使用 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象的 [ReminderSet](https://msdn.microsoft.com/library/bb624262\(v=office.15\)) 属性。 此属性指明是否已创建约会提醒。 将 ReminderSet 属性设置为 true 即可创建提醒，设置为 false 即可删除提醒。

在下面的代码示例中，ReminderExample 为在加利福尼亚州纳帕市举办的品酒会这一私人约会创建提醒，并设置为在约会开始前提前两小时发出提醒。 首先，ReminderExample 创建 Outlook **AppointmentItem** 对象。 然后，它将项的 [Sensitivity](https://msdn.microsoft.com/library/bb623503\(v=office.15\)) 属性设置为 [olPrivate](https://msdn.microsoft.com/library/bb645125\(v=office.15\))。 这表示约会为私人约会。 设置约会的其他属性（如 [Start](https://msdn.microsoft.com/library/bb647263\(v=office.15\)) 和 [End](https://msdn.microsoft.com/library/bb623715\(v=office.15\)) 时间）后，ReminderExample 设置 [ReminderMinutesBeforeStart](https://msdn.microsoft.com/library/bb644528\(v=office.15\)) 属性，指明在约会开始前提前多少分钟发出提醒。 在此代码示例中，ReminderMinutesBeforeStart 设置为 120 分钟（两小时）。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void ReminderExample()
{
    Outlook.AppointmentItem appt = Application.CreateItem(
        Outlook.OlItemType.olAppointmentItem)
        as Outlook.AppointmentItem;
    appt.Subject = "Wine Tasting";
    appt.Location = "Napa CA";
    appt.Sensitivity = Outlook.OlSensitivity.olPrivate;
    appt.Start = DateTime.Parse("10/21/2006 10:00 AM");
    appt.End = DateTime.Parse("10/21/2006 3:00 PM");
    appt.ReminderSet = true;
    appt.ReminderMinutesBeforeStart = 120;
    appt.Save();
}
```

## <a name="see-also"></a>另请参阅

- [约会](appointments.md)

