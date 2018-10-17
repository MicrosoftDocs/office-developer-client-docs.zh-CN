---
title: 将日历保存到磁盘中
TOCTitle: Save a calendar to disk
ms:assetid: f1b57bd0-c972-4b86-8870-f26290f28050
ms:mtpsurl: https://msdn.microsoft.com/library/Bb647583(v=office.15)
ms:contentKeyID: 55119827
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 2f9a71d2743896ca6257e30efc7260ed11086ca5
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405642"
---
# <a name="save-a-calendar-to-disk"></a><span data-ttu-id="5351e-102">将日历保存到磁盘中</span><span class="sxs-lookup"><span data-stu-id="5351e-102">Save a calendar to disk</span></span>

<span data-ttu-id="5351e-103">此代码示例展示了如何以 iCalendar (.ics) 文件格式将整个日历保存到磁盘中。</span><span class="sxs-lookup"><span data-stu-id="5351e-103">This example shows how to save an entire calendar to disk in the iCalendar (.ics) file format.</span></span>

## <a name="example"></a><span data-ttu-id="5351e-104">示例</span><span class="sxs-lookup"><span data-stu-id="5351e-104">Example</span></span>

<span data-ttu-id="5351e-p101">该代码示例使用 [CalendarSharing](https://msdn.microsoft.com/library/bb624344\(v=office.15\)) 对象，该对象支持将整个日历或日历中的一组约会保存到磁盘上。Outlook 会自动优化 .ics 文件，以便定期约会在 .ics 文件中不会另存为单个约会。根据要保存的日历的大小，将日历保存到磁盘上可能需要很长时间。在保存日历时，Outlook 窗口似乎对用户为无响应。</span><span class="sxs-lookup"><span data-stu-id="5351e-p101">This code sample uses the [CalendarSharing](https://msdn.microsoft.com/library/bb624344\(v=office.15\)) object that supports saving a whole calendar or a range of appointments from the calendar to disk. Outlook automatically optimizes an .ics file so that recurring appointments are not saved as individual appointments in the .ics file. Depending on the size of the calendar being saved, saving a calendar to disk can take a significant amount of time. While saving the calendar, the Outlook window appears unresponsive to the user.</span></span>

<span data-ttu-id="5351e-p102">该代码示例先对默认"日历"文件夹调用 [GetCalendarExporter](https://msdn.microsoft.com/library/bb610021\(v=office.15\)) ，以获取 **CalendarSharing** 对象。然后它设置 **CalendarSharing** 对象的属性来指定导出条件，例如是否保存整个日历并包括标记为"个人"的约会的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5351e-p102">The code sample first calls [GetCalendarExporter](https://msdn.microsoft.com/library/bb610021\(v=office.15\)) on the default Calendar folder to obtain a **CalendarSharing** object. Then it sets properties of the **CalendarSharing** object to specify criteria for the export, such as whether to save the entire calendar and include details of appointments that are marked "private".</span></span>

<span data-ttu-id="5351e-111">此代码示例调用 **CalendarSharing** 对象的 [SaveAsICal](https://msdn.microsoft.com/library/bb644844\(v=office.15\)) 方法，以 .ics 文件格式保存日历。</span><span class="sxs-lookup"><span data-stu-id="5351e-111">To save the calendar information in .ics file format, the code sample calls the [SaveAsICal](https://msdn.microsoft.com/library/bb644844\(v=office.15\)) method of the **CalendarSharing** object.</span></span>

<span data-ttu-id="5351e-112">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="5351e-112">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="5351e-113">不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="5351e-113">The Imports or using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="5351e-114">下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="5351e-114">The following lines of code show how to do the import and assignment in Visual Basic and C#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub SaveCalendarToDisk(ByVal calendarFileName As String)
    If String.IsNullOrEmpty(calendarFileName) Then
        Throw New ArgumentException( _
        "Parameter must contain a value.", "calendarFileName")
    End If

    Dim calendar As Outlook.Folder = TryCast( _
        Application.Session.GetDefaultFolder(_
        Outlook.OlDefaultFolders.olFolderCalendar), Outlook.Folder)
    Dim exporter As Outlook.CalendarSharing = _
        calendar.GetCalendarExporter()

    '' Set the properties for the export
    exporter.CalendarDetail = Outlook.OlCalendarDetail.olFullDetails
    exporter.IncludeAttachments = True
    exporter.IncludePrivateDetails = True
    exporter.RestrictToWorkingHours = False
    exporter.IncludeWholeCalendar = True

    '' Save the calendar to disk
    exporter.SaveAsICal(calendarFileName)
End Sub
```


```csharp
private void SaveCalendarToDisk(string calendarFileName)
{
    if (string.IsNullOrEmpty(calendarFileName))
        throw new ArgumentException("calendarFileName", 
        "Parameter must contain a value.");

    Outlook.Folder calendar = Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderCalendar) as Outlook.Folder;
    Outlook.CalendarSharing exporter = calendar.GetCalendarExporter();

    // Set the properties for the export
    exporter.CalendarDetail = Outlook.OlCalendarDetail.olFullDetails;
    exporter.IncludeAttachments = true;
    exporter.IncludePrivateDetails = true;
    exporter.RestrictToWorkingHours = false;
    exporter.IncludeWholeCalendar = true;

    // Save the calendar to disk
    exporter.SaveAsICal(calendarFileName);
}
```

## <a name="see-also"></a><span data-ttu-id="5351e-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5351e-115">See also</span></span>

- [<span data-ttu-id="5351e-116">日历</span><span class="sxs-lookup"><span data-stu-id="5351e-116">Calendar</span></span>](calendar.md)

