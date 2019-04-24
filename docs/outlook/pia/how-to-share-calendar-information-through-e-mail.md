---
title: 通过电子邮件共享日历信息
TOCTitle: Share calendar information through email
ms:assetid: 3382010c-0a16-4dca-a99e-669e9178354e
ms:mtpsurl: https://msdn.microsoft.com/library/Bb609881(v=office.15)
ms:contentKeyID: 55119817
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 48b299ad4d3afe5c0c9aaa05f5d8af3b92bf655d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332076"
---
# <a name="share-calendar-information-through-email"></a><span data-ttu-id="308c8-102">通过电子邮件共享日历信息</span><span class="sxs-lookup"><span data-stu-id="308c8-102">Share calendar information through email</span></span>

<span data-ttu-id="308c8-103">此代码示例展示了如何通过 iCalendar 格式的电子邮件共享日历信息。</span><span class="sxs-lookup"><span data-stu-id="308c8-103">This example shows how to share information from a calendar by email in the iCalendar format.</span></span>

## <a name="example"></a><span data-ttu-id="308c8-104">示例</span><span class="sxs-lookup"><span data-stu-id="308c8-104">Example</span></span>

<span data-ttu-id="308c8-p101">iCalendar 格式允许您通过标准 Internet 邮件格式和协议向其他 Outlook 或非 Outlook 客户端发送项目。该代码示例使用 [CalendarSharing](https://msdn.microsoft.com/library/bb624344\(v=office.15\)) 对象，该对象支持从日历文件夹中将信息导出为 iCalendar 格式。</span><span class="sxs-lookup"><span data-stu-id="308c8-p101">The iCalendar format allows you to send items to other Outlook or non-Outlook clients via standard Internet mail formats and protocols. The code sample uses the [CalendarSharing](https://msdn.microsoft.com/library/bb624344\(v=office.15\)) object that supports exporting information from a calendar folder to the iCalendar format.</span></span>

<span data-ttu-id="308c8-p102">该代码示例先对默认"日历"文件夹调用 [GetCalendarExporter](https://msdn.microsoft.com/library/bb610021\(v=office.15\)) ，以获取 **CalendarSharing** 对象。然后，该示例通过设置 **CalendarSharing** 对象的属性来指定导出条件，如日历信息的日期范围、是否包括附件以及标记为"私有"的约会的详细信息。</span><span class="sxs-lookup"><span data-stu-id="308c8-p102">The code sample first calls [GetCalendarExporter](https://msdn.microsoft.com/library/bb610021\(v=office.15\)) on the default Calendar folder to obtain a **CalendarSharing** object. Then it sets properties of the **CalendarSharing** object to specify criteria for the export, such as the date range of calendar information, whether to include attachments, and details of appointments that are marked "private."</span></span>

<span data-ttu-id="308c8-109">此代码示例调用 **CalendarSharing** 对象的 [ForwardAsICal](https://msdn.microsoft.com/library/bb652866\(v=office.15\)) 方法，以通过电子邮件发送日历信息。</span><span class="sxs-lookup"><span data-stu-id="308c8-109">To send the calendar information by email, the code sample calls the [ForwardAsICal](https://msdn.microsoft.com/library/bb652866\(v=office.15\)) method of the **CalendarSharing** object.</span></span>

<span data-ttu-id="308c8-110">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="308c8-110">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="308c8-111">不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="308c8-111">The **Imports** or **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="308c8-112">下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="308c8-112">The following lines of code show how to do the import and assignment in Visual Basic and C\#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```vb
Private Sub SendNextWeekToAddress(ByVal sendToAddresses As String)
    If String.IsNullOrEmpty(sendToAddresses) Then
        Throw New ArgumentException( _
            "Parameter must contain a value.", "sendToAddress")
    End If

    Dim calendar As Outlook.Folder = TryCast( _
        Application.Session.GetDefaultFolder( _
        Outlook.OlDefaultFolders.olFolderCalendar), Outlook.Folder)
    Dim exporter As Outlook.CalendarSharing = calendar.GetCalendarExporter()

    '' Set the properties for the export
    exporter.CalendarDetail = Outlook.OlCalendarDetail.olFullDetails
    exporter.IncludeAttachments = True
    exporter.IncludePrivateDetails = False
    exporter.RestrictToWorkingHours = False
    exporter.StartDate = DateTime.Today.Date
    exporter.EndDate = DateTime.Today.Date.AddDays(7)

    '' Create a new mail item
    Dim calendarMail As Outlook.MailItem = exporter.ForwardAsICal _
        (Outlook.OlCalendarMailFormat. _
        olCalendarMailFormatDailySchedule)
    calendarMail.To = sendToAddresses
    calendarMail.Send()
    calendarMail.Display()
End Sub
```

```csharp
private void SendNextWeekToAddress(string sendToAddresses)
{
    if (string.IsNullOrEmpty(sendToAddresses))
        throw new ArgumentException(
        "sendToAddress","Parameter must contain a value.");
    Outlook.Folder calendar = 
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderCalendar)
        as Outlook.Folder;
    Outlook.CalendarSharing exporter = calendar.GetCalendarExporter();

    // Set the properties for the export
    exporter.CalendarDetail = Outlook.OlCalendarDetail.olFullDetails;
    exporter.IncludeAttachments = true;
    exporter.IncludePrivateDetails = false;
    exporter.RestrictToWorkingHours = false;
    exporter.StartDate = DateTime.Today.Date;
    exporter.EndDate = DateTime.Today.Date.AddDays(7);

    // Create a new mail item
    Outlook.MailItem calendarMail = 
        exporter.ForwardAsICal(Outlook.OlCalendarMailFormat.
        olCalendarMailFormatDailySchedule);
    calendarMail.To = sendToAddresses;
    ((Outlook.MailItemClass)calendarMail).Send();
    ((Outlook.MailItemClass)calendarMail).Display(Type.Missing);
}
```

## <a name="see-also"></a><span data-ttu-id="308c8-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="308c8-113">See also</span></span>

- [<span data-ttu-id="308c8-114">日历</span><span class="sxs-lookup"><span data-stu-id="308c8-114">Calendar</span></span>](calendar.md)

