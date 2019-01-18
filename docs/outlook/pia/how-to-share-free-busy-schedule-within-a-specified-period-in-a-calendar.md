---
title: 共享日历中指定时间段内闲/忙日程安排
TOCTitle: Share Free/Busy schedule within a specified period in a calendar
ms:assetid: 1d038f56-80dd-42fd-809b-f5b3a47cd5ee
ms:mtpsurl: https://msdn.microsoft.com/library/Bb609503(v=office.15)
ms:contentKeyID: 55119824
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 00cc252dd16212e812280db70d6b7c77c2c02693
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28708058"
---
# <a name="share-freebusy-schedule-within-a-specified-period-in-a-calendar"></a><span data-ttu-id="7c7f0-102">共享日历中指定时间段内闲/忙日程安排</span><span class="sxs-lookup"><span data-stu-id="7c7f0-102">Share Free/Busy schedule within a specified period in a calendar</span></span>

<span data-ttu-id="7c7f0-103">此代码示例获取日历中指定一周内的闲/忙日程安排，并向用户显示闲、忙和主题详细信息。</span><span class="sxs-lookup"><span data-stu-id="7c7f0-103">This example obtains the Free/Busy schedule within a specified week from a calendar and displays the free, busy, and subject details to the user.</span></span>

## <a name="example"></a><span data-ttu-id="7c7f0-104">示例</span><span class="sxs-lookup"><span data-stu-id="7c7f0-104">Example</span></span>

<span data-ttu-id="7c7f0-p101">该代码示例使用 [Folder](https://msdn.microsoft.com/library/bb610021\(v=office.15\)) 对象的 [GetCalendarExporter](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 方法为默认"日历"文件夹获取特定一周内的 [CalendarSharing](https://msdn.microsoft.com/library/bb624344\(v=office.15\)) 对象。然后，该示例对 [CalendarSharing](https://msdn.microsoft.com/library/bb652866\(v=office.15\)) 对象调用 **ForwardAsICal** 方法并显示包含 iCalendar 有效负载的消息。</span><span class="sxs-lookup"><span data-stu-id="7c7f0-p101">This code sample uses the [GetCalendarExporter](https://msdn.microsoft.com/library/bb610021\(v=office.15\)) method of the [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) object to obtain a [CalendarSharing](https://msdn.microsoft.com/library/bb624344\(v=office.15\)) object for the default Calendar folder for a specific one-week period. It then calls the [ForwardAsICal](https://msdn.microsoft.com/library/bb652866\(v=office.15\)) method on the **CalendarSharing** object and displays the message with an iCalendar payload.</span></span>

<span data-ttu-id="7c7f0-107">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="7c7f0-107">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="7c7f0-108">不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="7c7f0-108">The **Imports** or **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="7c7f0-109">下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="7c7f0-109">The following lines of code show how to do the import and assignment in Visual Basic and C\#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```vb
Private Sub DemoCalendarSharing()
    ' Get instance of CalendarSharing object
    Dim calShare As Outlook.CalendarSharing = _
        Application.Session.GetDefaultFolder( _
        Outlook.OlDefaultFolders.olFolderCalendar). _
        GetCalendarExporter()
    ' Free busy and subject details
    calShare.CalendarDetail = _
        Outlook.OlCalendarDetail.olFreeBusyAndSubject
    ' Set start and end dates
    calShare.StartDate = DateTime.Today
    calShare.EndDate = calShare.StartDate.AddDays(1)
    ' Call ForwardAsICal method
    Dim mail As Outlook.MailItem = _
        calShare.ForwardAsICal( _
        Outlook.OlCalendarMailFormat.olCalendarMailFormatDailySchedule)
    ' Add recipient
    mail.Recipients.Add("someone@example.com")
    mail.Recipients.ResolveAll()
    ' Set subject
    Dim CalName As String = _
    Application.Session.GetDefaultFolder( _
    Outlook.OlDefaultFolders.olFolderCalendar).Name
    mail.Subject = _
        Application.Session.CurrentUser.Name & _
        CalName.PadLeft(CalName.Length + 1)
    ' Display calendar sharing item
    mail.Display(False)
End Sub
```

```csharp
private void DemoCalendarSharing()
{
    // Get instance of CalendarSharing object
    Outlook.CalendarSharing calShare =
        Application.Session.GetDefaultFolder
        (Outlook.OlDefaultFolders.olFolderCalendar).
        GetCalendarExporter();
    // Free busy and subject details
    calShare.CalendarDetail =
        Outlook.OlCalendarDetail.olFreeBusyAndSubject;
    // Set start and end dates
    calShare.StartDate = DateTime.Today;
    calShare.EndDate = calShare.StartDate.AddDays(1);
    // Call ForwardAsICal method
    Outlook.MailItem mail =
        calShare.ForwardAsICal(Outlook.OlCalendarMailFormat
        .olCalendarMailFormatDailySchedule);
    // Add recipient
    mail.Recipients.Add("someone@example.com");
    mail.Recipients.ResolveAll();
    // Set subject
    string CalName =
        Application.Session.GetDefaultFolder
    (Outlook.OlDefaultFolders.olFolderCalendar).Name;
    mail.Subject =
        Application.Session.CurrentUser.Name +
        CalName.PadLeft(CalName.Length + 1);
    // Display calendar sharing item
    mail.Display(false);
}
```

## <a name="see-also"></a><span data-ttu-id="7c7f0-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c7f0-110">See also</span></span>

- [<span data-ttu-id="7c7f0-111">日历</span><span class="sxs-lookup"><span data-stu-id="7c7f0-111">Calendar</span></span>](calendar.md)

