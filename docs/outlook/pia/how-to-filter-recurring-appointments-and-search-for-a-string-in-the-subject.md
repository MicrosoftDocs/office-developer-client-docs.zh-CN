---
title: 筛选定期约会并在主题中搜索某个字符串
TOCTitle: Filter recurring appointments and search for a string in the subject
ms:assetid: 997186aa-5264-4b19-bed6-51c38831c03d
ms:mtpsurl: https://msdn.microsoft.com/library/Bb611267(v=office.15)
ms:contentKeyID: 55119891
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 6bda9cc663af1d1b9167ec78da286fe1c1991d40
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320263"
---
# <a name="filter-recurring-appointments-and-search-for-a-string-in-the-subject"></a><span data-ttu-id="d928e-102">筛选定期约会并在主题中搜索某个字符串</span><span class="sxs-lookup"><span data-stu-id="d928e-102">Filter recurring appointments and search for a string in the subject</span></span>

<span data-ttu-id="d928e-103">该示例筛选“日历”文件夹中某一日期范围内的定期约会，然后以两种方式在主题中搜索字符串“office”。</span><span class="sxs-lookup"><span data-stu-id="d928e-103">This example filters recurring appointments that fall within a date range in a Calendar folder, and then searches in two ways for the string "office" in the subject.</span></span>

## <a name="example"></a><span data-ttu-id="d928e-104">示例</span><span class="sxs-lookup"><span data-stu-id="d928e-104">Example</span></span>

<span data-ttu-id="d928e-105">此代码示例使用 [Items](https://msdn.microsoft.com/library/bb645287\(v=office.15\)) 集合（而不是 [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象）筛选定期约会，因为 **Table** 对象仅返回主要系列约会，不包括文件夹中的定期项。</span><span class="sxs-lookup"><span data-stu-id="d928e-105">To filter recurring appointments, this code sample uses the [Items](https://msdn.microsoft.com/library/bb645287\(v=office.15\)) collection instead of the [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) object, because the **Table** object returns only the master series appointments and does not include recurring items in the folder.</span></span> <span data-ttu-id="d928e-106">为了在调用 [Find(String)](https://msdn.microsoft.com/library/bb646289\(v=office.15\)) 或 [Restrict(String)](https://msdn.microsoft.com/library/bb612531\(v=office.15\)) 方法时添加定期约会，此代码示例设置 **Items** 集合的 [IncludeRecurrences](https://msdn.microsoft.com/library/bb646522\(v=office.15\)) 属性，然后按 [Start](https://msdn.microsoft.com/library/bb647263\(v=office.15\)) 属性对文件夹中的约会进行排序。</span><span class="sxs-lookup"><span data-stu-id="d928e-106">To include recurring appointments when calling the [Find(String)](https://msdn.microsoft.com/library/bb646289\(v=office.15\)) or [Restrict(String)](https://msdn.microsoft.com/library/bb612531\(v=office.15\)) method, the code sample sets the [IncludeRecurrences](https://msdn.microsoft.com/library/bb646522\(v=office.15\)) property of the **Items** collection, and then sorts appointments in the folder by their [Start](https://msdn.microsoft.com/library/bb647263\(v=office.15\)) property.</span></span> <span data-ttu-id="d928e-107">然后，它使用 Jet 查询，指定定期约会的开始日期和结束日期。</span><span class="sxs-lookup"><span data-stu-id="d928e-107">It then uses a Jet query to specify start and end dates for the recurrences.</span></span>

<span data-ttu-id="d928e-108">获取指定日期范围内定期约会项的 **Items** 集合后，此代码示例使用 DAV 搜索和定位 (DASL) 查询执行其他两种搜索。</span><span class="sxs-lookup"><span data-stu-id="d928e-108">After obtaining an **Items** collection of recurring appointment items that fall within the specified range of dates, the code sample carries out two more searches using DAV Searching and Locating (DASL) queries.</span></span> <span data-ttu-id="d928e-109">第一种搜索使用 **Items.Find**、[FindNext](https://msdn.microsoft.com/library/bb623799\(v=office.15\)) 和 **like** 关键字，搜索主题中有“office”子字符串的项。</span><span class="sxs-lookup"><span data-stu-id="d928e-109">The first search uses **Items.Find**, [FindNext](https://msdn.microsoft.com/library/bb623799\(v=office.15\)), and the **like** keyword to search for items that have "office" as a substring in the subject.</span></span> <span data-ttu-id="d928e-110">第二种搜索使用 **Items.Restrict** 方法和 **ci\_startswith** 关键字，搜索主题以“office”开头的项。</span><span class="sxs-lookup"><span data-stu-id="d928e-110">The second search uses the **Items.Restrict** method and the **ci\_startswith** keyword to search for items that have subjects beginning with "office."</span></span>

<span data-ttu-id="d928e-111">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="d928e-111">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="d928e-112">不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="d928e-112">The **Imports** or **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="d928e-113">下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="d928e-113">The following lines of code show how to do the import and assignment in Visual Basic and C\#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub SearchRecurringAppointments()
    Dim appt As Outlook.AppointmentItem = Nothing
    Dim folder As Outlook.Folder = _
        CType(Application.Session.GetDefaultFolder( _
        Outlook.OlDefaultFolders.olFolderCalendar), _
        Outlook.Folder)
    ' Set start value
    Dim startTime As DateTime = New DateTime(2006, 8, 9, 0, 0, 0)
    ' Set end value
    Dim endTime As DateTime = New DateTime(2006, 12, 14, 0, 0, 0)
    ' Initial restriction is Jet query for date range
    Dim filter1 As String = "[Start] >= '" & startTime.ToString("g") _
        & "' AND [End] <= '" & endTime.ToString("g") & "'"
    Dim calendarItems As Outlook.Items = folder.Items.Restrict(filter1)
    calendarItems.IncludeRecurrences = True
    calendarItems.Sort("[Start]")
    ' Must use 'like' comparison for Find/FindNext
    Dim filter2 As String
    filter2 = "@SQL=" & _
        Chr(34) & "urn:schemas:httpmail:subject" & Chr(34) & _
        " like '%Office%'"
    ' Create DASL query for additional Restrict method
    Dim filter3 As String
    If (Application.Session.DefaultStore.IsInstantSearchEnabled) Then
        filter3 = "@SQL=" & _
            Chr(34) & "urn:schemas:httpmail:subject" & Chr(34) & " _
            ci_startswith 'Office'"
    Else
        filter3 = "@SQL=" & _
            Chr(34) & "urn:schemas:httpmail:subject" & Chr(34) & " _
            like '%Office%'"
    End If
    ' Use Find and FindNext methods
    appt = CType(calendarItems.Find(filter2), Outlook.AppointmentItem)
    While Not (appt Is Nothing)
        Dim sb As StringBuilder = New StringBuilder()
        sb.AppendLine(appt.Subject)
        sb.AppendLine("Start: " & appt.Start)
        sb.AppendLine("End: " & appt.End)
        Debug.WriteLine(sb.ToString())
        ' Find the next appointment
        appt = CType(calendarItems.FindNext(), Outlook.AppointmentItem)
    End While
    ' Restrict calendarItems with DASL query
    Dim restrictedItems As Outlook.Items = _
        calendarItems.Restrict(filter3)
    For Each apptItem As Outlook.AppointmentItem In restrictedItems
        Dim sb As StringBuilder = New StringBuilder()
        sb.AppendLine(apptItem.Subject)
        sb.AppendLine("Start: " & apptItem.Start)
        sb.AppendLine("End: " & apptItem.End)
        sb.AppendLine()
        Debug.WriteLine(sb.ToString())
    Next
End Sub
```


```csharp
private void SearchRecurringAppointments()
{
    Outlook.AppointmentItem appt = null;
    Outlook.Folder folder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderCalendar)
        as Outlook.Folder;
    // Set start value
    DateTime start =
        new DateTime(2006, 8, 9, 0, 0, 0);
    // Set end value
    DateTime end =
        new DateTime(2006, 12, 14, 0, 0, 0);
    // Initial restriction is Jet query for date range
    string filter1 = "[Start] >= '" +
        start.ToString("g")
        + "' AND [End] <= '" +
        end.ToString("g") + "'";
    Outlook.Items calendarItems = folder.Items.Restrict(filter1);
    calendarItems.IncludeRecurrences = true;
    calendarItems.Sort("[Start]", Type.Missing);
    // Must use 'like' comparison for Find/FindNext
    string filter2;
    filter2 = "@SQL="
        + "\"" + "urn:schemas:httpmail:subject" + "\""
        + " like '%Office%'";
    // Create DASL query for additional Restrict method
    string filter3;
    if (Application.Session.DefaultStore.IsInstantSearchEnabled)
    {
        filter3 = "@SQL="
            + "\"" + "urn:schemas:httpmail:subject" + "\""
            + " ci_startswith 'Office'";
    }
    else
    {
        filter3 = "@SQL="
            + "\"" + "urn:schemas:httpmail:subject" + "\""
            + " like '%Office%'";
    }
    // Use Find and FindNext methods
    appt = calendarItems.Find(filter2)
        as Outlook.AppointmentItem;
    while (appt != null)
    {
        StringBuilder sb = new StringBuilder();
        sb.AppendLine(appt.Subject);
        sb.AppendLine("Start: " + appt.Start);
        sb.AppendLine("End: " + appt.End);
        Debug.WriteLine(sb.ToString());
        // Find the next appointment
        appt = calendarItems.FindNext()
            as Outlook.AppointmentItem;
    }
    // Restrict calendarItems with DASL query
    Outlook.Items restrictedItems =
        calendarItems.Restrict(filter3);
    foreach (Outlook.AppointmentItem apptItem in restrictedItems)
    {
        StringBuilder sb = new StringBuilder();
        sb.AppendLine(apptItem.Subject);
        sb.AppendLine("Start: " + apptItem.Start);
        sb.AppendLine("End: " + apptItem.End);
        sb.AppendLine();
        Debug.WriteLine(sb.ToString());
    }
}
```

## <a name="see-also"></a><span data-ttu-id="d928e-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d928e-114">See also</span></span>

- [<span data-ttu-id="d928e-115">搜索和筛选</span><span class="sxs-lookup"><span data-stu-id="d928e-115">Search and filter</span></span>](search-and-filter.md)

