---
title: 创建开始时采用太平洋时区且结束时采用东部时区的约会
TOCTitle: Create an appointment that starts in the Pacific Time Zone and ends in the Eastern Time Zone
ms:assetid: ba19532b-df31-4384-8816-e64e6eecbe53
ms:mtpsurl: https://msdn.microsoft.com/library/Bb623388(v=office.15)
ms:contentKeyID: 55119808
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e9a1b9d5f65d8683c08821d4cf0851f599f32030
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28698713"
---
# <a name="create-an-appointment-that-starts-in-the-pacific-time-zone-and-ends-in-the-eastern-time-zone"></a>创建开始时采用太平洋时区且结束时采用东部时区的约会

有时，约会可能跨越一个时间段，在此期间，用户可能出差到与约会开始时不同的时区。该示例创建在太平洋时区 (UTC-8) 开始、在东部时区 (UTC-5) 结束的约会。

## <a name="example"></a>示例

该代码示例使用表示 Microsoft Windows 中识别的所有时区的 [TimeZones](https://msdn.microsoft.com/library/bb611081\(v=office.15\)) 对象。它还使用 [TimeZone](https://msdn.microsoft.com/library/bb646259\(v=office.15\)) 对象来设置或获取 [AppointmentItem](https://msdn.microsoft.com/library/bb623657\(v=office.15\)) 对象上的 [StartTimeZone](https://msdn.microsoft.com/library/bb612198\(v=office.15\)) 属性和 [EndTimeZone](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 属性。

Outlook 采用本地时间显示所有日期，本地时间按用户的当前时区（由 Windows 控制面板中的用户设置控制）表示。 Outlook 也设置或获取采用本地时间的属性（如 [Start](https://msdn.microsoft.com/library/bb647263\(v=office.15\)) 和 [End](https://msdn.microsoft.com/library/bb623715\(v=office.15\))）。 不过，Outlook 将日期和时间值存储为协调世界时 (UTC)，而不是本地时间。 如果您使用 PropertyAccessor 对象检查 [Appointment.Start](https://msdn.microsoft.com/library/bb646034\(v=office.15\)) 的内部值，您会发现内部日期和时间值与转换为对应的 UTC 日期和时间值的本地日期和时间值相等。

Outlook 在保存约会时，使用时区信息将约会映射到正确的 UTC 时间；在日历中显示项目时，映射到正确的本地时间。 更改 StartTimeZone 会影响 Appointment.Start 值，此值始终采用本地时区（由 [TimeZones](https://msdn.microsoft.com/library/bb645170\(v=office.15\)) 返回的对象的 [CurrentTimeZone](https://msdn.microsoft.com/library/bb612024\(v=office.15\)) 属性表示）。 类似地，更改 EndTimeZone 会影响 Appointment.End 的值，该值总是采用本地时区表示，本地时区由 Application.TimeZones 返回的对象的 CurrentTimeZone 属性表示。

可以使用 Windows 注册表中与区域设置无关的时区键，检索 TimeZones 对象中的特定时区。 下列路径下列出了与区域设置无关的时区键：`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\TimeZones`。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。 下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。


```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```



```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```



```vb
Private Sub TimeZoneExample()
    Dim appt As Outlook.AppointmentItem = _
        CType(Application.CreateItem( _
        Outlook.OlItemType.olAppointmentItem), Outlook.AppointmentItem)
    Dim tzs As Outlook.TimeZones = Application.TimeZones
    ' Obtain timezone using indexer and locale-independent key
    Dim tzEastern As Outlook.TimeZone = tzs("Eastern Standard Time")
    Dim tzPacific As Outlook.TimeZone = tzs("Pacific Standard Time")
    appt.Subject = "SEA - JFK Flight"
    appt.Start = DateTime.Parse("8/9/2006 8:00 AM")
    appt.StartTimeZone = tzPacific
    appt.End = DateTime.Parse("8/9/2006 5:30 PM")
    appt.EndTimeZone = tzEastern
    appt.Display(False)
End Sub
```



```csharp
private void TimeZoneExample()
{
    Outlook.AppointmentItem appt = Application.CreateItem(
        Outlook.OlItemType.olAppointmentItem)
        as Outlook.AppointmentItem;
    Outlook.TimeZones tzs = Application.TimeZones;
    // Obtain timezone using indexer and locale-independent key
    Outlook.TimeZone tzEastern = tzs["Eastern Standard Time"];
    Outlook.TimeZone tzPacific = tzs["Pacific Standard Time"];
    appt.Subject = "SEA - JFK Flight";
    appt.Start = DateTime.Parse("8/9/2006 8:00 AM");
    appt.StartTimeZone = tzPacific;
    appt.End = DateTime.Parse("8/9/2006 5:30 PM");
    appt.EndTimeZone = tzEastern; 
    appt.Display(false);
}
```

## <a name="see-also"></a>另请参阅

- [约会](appointments.md)

