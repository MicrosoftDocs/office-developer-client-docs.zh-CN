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
# <a name="create-an-appointment-that-starts-in-the-pacific-time-zone-and-ends-in-the-eastern-time-zone"></a><span data-ttu-id="c86b8-102">创建开始时采用太平洋时区且结束时采用东部时区的约会</span><span class="sxs-lookup"><span data-stu-id="c86b8-102">Create an appointment that starts in the Pacific Time Zone and ends in the Eastern Time Zone</span></span>

<span data-ttu-id="c86b8-p101">有时，约会可能跨越一个时间段，在此期间，用户可能出差到与约会开始时不同的时区。该示例创建在太平洋时区 (UTC-8) 开始、在东部时区 (UTC-5) 结束的约会。</span><span class="sxs-lookup"><span data-stu-id="c86b8-p101">Occasionally, an appointment may span over a period of time during which the user may have traveled to a different time zone than when the appointment starts. This example creates an appointment that begins in the Pacific Time Zone (UTC-8) and ends in the Eastern Time Zone (UTC-5).</span></span>

## <a name="example"></a><span data-ttu-id="c86b8-105">示例</span><span class="sxs-lookup"><span data-stu-id="c86b8-105">Example</span></span>

<span data-ttu-id="c86b8-p102">该代码示例使用表示 Microsoft Windows 中识别的所有时区的 [TimeZones](https://msdn.microsoft.com/library/bb611081\(v=office.15\)) 对象。它还使用 [TimeZone](https://msdn.microsoft.com/library/bb646259\(v=office.15\)) 对象来设置或获取 [AppointmentItem](https://msdn.microsoft.com/library/bb623657\(v=office.15\)) 对象上的 [StartTimeZone](https://msdn.microsoft.com/library/bb612198\(v=office.15\)) 属性和 [EndTimeZone](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 属性。</span><span class="sxs-lookup"><span data-stu-id="c86b8-p102">This code sample uses the [TimeZones](https://msdn.microsoft.com/library/bb611081\(v=office.15\)) object that represents all the time zones recognized in Microsoft Windows. It also uses the [TimeZone](https://msdn.microsoft.com/library/bb646259\(v=office.15\)) object to set or get the [StartTimeZone](https://msdn.microsoft.com/library/bb623657\(v=office.15\)) property and the [EndTimeZone](https://msdn.microsoft.com/library/bb612198\(v=office.15\)) property on the [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) object.</span></span>

<span data-ttu-id="c86b8-108">Outlook 采用本地时间显示所有日期，本地时间按用户的当前时区（由 Windows 控制面板中的用户设置控制）表示。</span><span class="sxs-lookup"><span data-stu-id="c86b8-108">Outlook displays all dates in local time, which is expressed in the user's current time zone, controlled by the user's settings in the Windows Control Panel.</span></span> <span data-ttu-id="c86b8-109">Outlook 也设置或获取采用本地时间的属性（如 [Start](https://msdn.microsoft.com/library/bb647263\(v=office.15\)) 和 [End](https://msdn.microsoft.com/library/bb623715\(v=office.15\))）。</span><span class="sxs-lookup"><span data-stu-id="c86b8-109">Outlook also sets or gets properties, such as [Start](https://msdn.microsoft.com/library/bb647263\(v=office.15\)) and [End](https://msdn.microsoft.com/library/bb623715\(v=office.15\)), in local time.</span></span> <span data-ttu-id="c86b8-110">不过，Outlook 将日期和时间值存储为协调世界时 (UTC)，而不是本地时间。</span><span class="sxs-lookup"><span data-stu-id="c86b8-110">However, Outlook stores date and time values as Coordinated Universal Time (UTC) rather than local time.</span></span> <span data-ttu-id="c86b8-111">如果您使用 PropertyAccessor 对象检查 [Appointment.Start](https://msdn.microsoft.com/library/bb646034\(v=office.15\)) 的内部值，您会发现内部日期和时间值与转换为对应的 UTC 日期和时间值的本地日期和时间值相等。</span><span class="sxs-lookup"><span data-stu-id="c86b8-111">If you examine the internal value of Appointment.Start by using the [PropertyAccessor](https://msdn.microsoft.com/library/bb646034\(v=office.15\)) object, you would find the internal date and time value is equal to the local date and time value converted to the equivalent UTC date and time value.</span></span>

<span data-ttu-id="c86b8-112">Outlook 在保存约会时，使用时区信息将约会映射到正确的 UTC 时间；在日历中显示项目时，映射到正确的本地时间。</span><span class="sxs-lookup"><span data-stu-id="c86b8-112">Outlook uses the time zone information to map the appointment to the correct UTC time when it saves an appointment, and into the correct local time when it displays the item in the calendar.</span></span> <span data-ttu-id="c86b8-113">更改 StartTimeZone 会影响 Appointment.Start 值，此值始终采用本地时区（由 [TimeZones](https://msdn.microsoft.com/library/bb645170\(v=office.15\)) 返回的对象的 [CurrentTimeZone](https://msdn.microsoft.com/library/bb612024\(v=office.15\)) 属性表示）。</span><span class="sxs-lookup"><span data-stu-id="c86b8-113">Changing StartTimeZone affects the value of Appointment.Start, which is always expressed in the local time zone, represented by the [CurrentTimeZone](https://msdn.microsoft.com/library/bb612024\(v=office.15\)) property of the object returned by [TimeZones](https://msdn.microsoft.com/library/bb645170\(v=office.15\)).</span></span> <span data-ttu-id="c86b8-114">类似地，更改 EndTimeZone 会影响 Appointment.End 的值，该值总是采用本地时区表示，本地时区由 Application.TimeZones 返回的对象的 CurrentTimeZone 属性表示。</span><span class="sxs-lookup"><span data-stu-id="c86b8-114">Similarly, changing EndTimeZone affects the value of Appointment.End, which is always expressed in the local time zone, represented by the CurrentTimeZone property of the object returned by Application.TimeZones.</span></span>

<span data-ttu-id="c86b8-115">可以使用 Windows 注册表中与区域设置无关的时区键，检索 TimeZones 对象中的特定时区。</span><span class="sxs-lookup"><span data-stu-id="c86b8-115">You can retrieve a specific TimeZone from the TimeZones object by using the locale-independent key for the TimeZone in the Windows registry.</span></span> <span data-ttu-id="c86b8-116">下列路径下列出了与区域设置无关的时区键：`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\TimeZones`。</span><span class="sxs-lookup"><span data-stu-id="c86b8-116">Locale-independent TimeZone keys are listed under the following key: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\TimeZones`.</span></span>

<span data-ttu-id="c86b8-117">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="c86b8-117">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="c86b8-118">不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="c86b8-118">The **Imports** or **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="c86b8-119">下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="c86b8-119">The following lines of code show how to do the import and assignment in Visual Basic and C\#.</span></span>


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

## <a name="see-also"></a><span data-ttu-id="c86b8-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c86b8-120">See also</span></span>

- [<span data-ttu-id="c86b8-121">约会</span><span class="sxs-lookup"><span data-stu-id="c86b8-121">Appointments</span></span>](appointments.md)

