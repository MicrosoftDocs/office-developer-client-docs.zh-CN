---
title: 搜索并获取某个时间范围内的约会
TOCTitle: Search and obtain appointments in a time range
ms:assetid: ce5205ad-6967-4f21-8a9d-503b731dbd40
ms:mtpsurl: https://msdn.microsoft.com/library/Gg619398(v=office.15)
ms:contentKeyID: 55119927
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9088da5f2deb4b3d4ccb1c2bc5409e0ff280ed24
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316086"
---
# <a name="search-and-obtain-appointments-in-a-time-range"></a><span data-ttu-id="cbd8e-102">搜索并获取某个时间范围内的约会</span><span class="sxs-lookup"><span data-stu-id="cbd8e-102">Search and obtain appointments in a time range</span></span>

<span data-ttu-id="cbd8e-103">此示例会返回默认 Microsoft Outlook 日历中指定时间范围内的约会。</span><span class="sxs-lookup"><span data-stu-id="cbd8e-103">This example returns appointments in a specific time range in the default Microsoft Outlook calendar.</span></span>

## <a name="example"></a><span data-ttu-id="cbd8e-104">示例</span><span class="sxs-lookup"><span data-stu-id="cbd8e-104">Example</span></span>

<span data-ttu-id="cbd8e-105">此代码示例包含两个方法：DemoAppointmentsInRange 和 GetAppointmentsInRange。</span><span class="sxs-lookup"><span data-stu-id="cbd8e-105">This code example contains two methods: DemoAppointmentsInRange and GetAppointmentsInRange.</span></span> <span data-ttu-id="cbd8e-106">DemoAppointmentsInRange 会获取当前已登录的 Outlook 配置文件的默认日历，从当天凌晨 12:00 开始设置 5 天的日期范围，</span><span class="sxs-lookup"><span data-stu-id="cbd8e-106">DemoAppointmentsInRange obtains the default calendar for the current signed-in Outlook profile, sets a date range of 5 days from 12:00 A.M.</span></span> <span data-ttu-id="cbd8e-107">调用 GetAppointmentsInRange 来获取该时间范围内的约会并显示返回的每个约会的主题和开始时间。</span><span class="sxs-lookup"><span data-stu-id="cbd8e-107">today, calls GetAppointmentsInRange to obtain appointments that fall in that time range, and displays the subject and start time of each of the returned appointments.</span></span>

<span data-ttu-id="cbd8e-108">GetAppointmentsInRange 会接受 Outlook 文件夹以及相应时间范围的开始和结束 **DateTime** 值作为输入参数。</span><span class="sxs-lookup"><span data-stu-id="cbd8e-108">GetAppointmentsInRange accepts an Outlook folder, and the start and end **DateTime** values of the time range as input parameters.</span></span> <span data-ttu-id="cbd8e-109">此方法使用了 [Restrict(String)](https://msdn.microsoft.com/library/bb612531\(v=office.15\)) 方法以及一种 Jet 格式字符串筛选器，该筛选器将返回在指定时间范围内开始并结束的约会。</span><span class="sxs-lookup"><span data-stu-id="cbd8e-109">This method uses the [Restrict(String)](https://msdn.microsoft.com/library/bb612531\(v=office.15\)) method and a string filter in Jet format that returns appointments that start and end within the specified time range.</span></span> <span data-ttu-id="cbd8e-110">假定 \[Start\] 和 \[End\] 是约会的开始时间和结束时间，startTime 和 endTime 是指定时间范围的开始时间和结束时间，那么 GetAppointmentsInRange 会设置一个筛选器来寻找同时满足 `[Start]>=startTime` 和 `[End]<=endTime` 这两个条件的约会。</span><span class="sxs-lookup"><span data-stu-id="cbd8e-110">Assuming \[Start\] and \[End\] are the start time and end time of an appointment, and startTime and endTime are the beginning and end time of the specified time range, GetAppointmentsInRange sets up a filter  that looks for appointments with `[Start]>=startTime`, and `[End]<=endTime`.</span></span> <span data-ttu-id="cbd8e-111">以下代码展示了 C\# 形式的 Jet 筛选器。</span><span class="sxs-lookup"><span data-stu-id="cbd8e-111">The following code shows the Jet filter in C\#.</span></span>

```csharp
string filter = "[Start] >= '"
    + startTime.ToString("g")
    + "' AND [End] <= '"
    + endTime.ToString("g") + "'";
```

<span data-ttu-id="cbd8e-112">在调用 **Items.Restrict** 方法来搜索约会之前，GetAppointmentsInRange 会执行另外两个操作来包含会在指定时间范围内发生的定期约会：</span><span class="sxs-lookup"><span data-stu-id="cbd8e-112">Before calling the **Items.Restrict** method to search for appointments, GetAppointmentsInRange does two other things to include recurring appointments that occur in the specified time range:</span></span>

- <span data-ttu-id="cbd8e-113">设置 [Items](https://msdn.microsoft.com/library/bb645287\(v=office.15\)) 集合的 [IncludeRecurrences](https://msdn.microsoft.com/library/bb646522\(v=office.15\)) 属性。</span><span class="sxs-lookup"><span data-stu-id="cbd8e-113">Sets the [IncludeRecurrences](https://msdn.microsoft.com/library/bb646522\(v=office.15\)) property of the [Items](https://msdn.microsoft.com/library/bb645287\(v=office.15\)) collection.</span></span>

- <span data-ttu-id="cbd8e-114">根据 [Start](https://msdn.microsoft.com/library/bb647263\(v=office.15\)) 属性对指定日历文件夹中的约会项目进行排序。</span><span class="sxs-lookup"><span data-stu-id="cbd8e-114">Sorts the appointment items in the given calendar folder by the [Start](https://msdn.microsoft.com/library/bb647263\(v=office.15\)) property.</span></span>

<span data-ttu-id="cbd8e-115">或者，如果你还对与指定时间范围的部分或全部时间重叠的约会感兴趣，则可以指定一种不同的筛选器来返回其他类型的约会（如图 1 所示）：</span><span class="sxs-lookup"><span data-stu-id="cbd8e-115">Alternatively, if you are also interested in appointments that overlap partially or entirely with the specified time range, you would specify a different filter to return additional types of appointments (as shown in Figure 1):</span></span>

- <span data-ttu-id="cbd8e-116">开始和结束时间均在指定时间范围内的约会（例如约会 A）：</span><span class="sxs-lookup"><span data-stu-id="cbd8e-116">Appointments that start and end within the specified time range (for example, appointment A):</span></span><br/><br/>`[Start]>=startTime and [End]<=endTime`

- <span data-ttu-id="cbd8e-117">开始时间早于指定时间范围，但结束时间在该时间范围内的约会（例如约会 B）：</span><span class="sxs-lookup"><span data-stu-id="cbd8e-117">Appointments that start before the specified time range but end within the time range (for example, appointment B):</span></span><br/><br/>`[Start]<startTime and [End]<=endTime`

- <span data-ttu-id="cbd8e-118">开始时间在指定时间范围内，但结束时间晚于该时间范围的约会（例如约会 C）：</span><span class="sxs-lookup"><span data-stu-id="cbd8e-118">Appointments that start within the specified time range but end after the time range (for example, appointment C):</span></span><br/><br/>`[Start]>=startTime and [End]>endTime`

- <span data-ttu-id="cbd8e-119">开始时间早于指定时间范围，且结束时间晚于该时间范围的约会（例如约会 D）：</span><span class="sxs-lookup"><span data-stu-id="cbd8e-119">Appointments that start before the specified time range and end after the time range (for example, appointment D):</span></span><br/><br/>`[Start]<startTime and [End]>endTime`

<span data-ttu-id="cbd8e-120">**图 1. 在某个时间范围内的或与该时间范围重叠的约会的类型**</span><span class="sxs-lookup"><span data-stu-id="cbd8e-120">**Figure 1. Types of appointments that occur within a time range, or overlap with that time range**</span></span>

![在某个时间范围内的或与该时间范围重叠的约会的类型](media/pia-appointment-starttime-endtime.gif)
 

<span data-ttu-id="cbd8e-122">在任何时间范围内，`startTime<=endTime` 这一条件都成立，因此具有 `[Start]<=endTime` 和 `[End]>=startTime` 两个条件的筛选器将会捕捉该时间范围内的前述各种类型的约会。</span><span class="sxs-lookup"><span data-stu-id="cbd8e-122">Because in any time range `startTime<=endTime`, a filter with `[Start]<=endTime` and `[End]>=startTime` would capture the preceding types of appointments in that time range.</span></span>

<span data-ttu-id="cbd8e-123">在 C\# 中，可以将该 Jet 筛选器表示如下。</span><span class="sxs-lookup"><span data-stu-id="cbd8e-123">In C\#, you can express the Jet filter as follows.</span></span>

```csharp
string filter = "[Start] <= '"
    + endTime.ToString("g")
    + "' AND [End] >= '"
    + startTime.ToString("g") + "'";
```

<span data-ttu-id="cbd8e-124">以下代码展示了完整的示例。</span><span class="sxs-lookup"><span data-stu-id="cbd8e-124">The following code shows the complete example.</span></span> <span data-ttu-id="cbd8e-125">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="cbd8e-125">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="cbd8e-126">不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="cbd8e-126">The **Imports** or **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="cbd8e-127">下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="cbd8e-127">The following lines of code show how to do the import and assignment in Visual Basic and C\#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void DemoAppointmentsInRange()
{
    Outlook.Folder calFolder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderCalendar)
        as Outlook.Folder;
    DateTime start = DateTime.Now;
    DateTime end = start.AddDays(5);
    Outlook.Items rangeAppts = GetAppointmentsInRange(calFolder, start, end);
    if (rangeAppts != null)
    {
        foreach (Outlook.AppointmentItem appt in rangeAppts)
        {
            Debug.WriteLine("Subject: " + appt.Subject 
                + " Start: " + appt.Start.ToString("g"));
        }
    }
}

/// <summary>
/// Get recurring appointments in date range.
/// </summary>
/// <param name="folder"></param>
/// <param name="startTime"></param>
/// <param name="endTime"></param>
/// <returns>Outlook.Items</returns>
private Outlook.Items GetAppointmentsInRange(
    Outlook.Folder folder, DateTime startTime, DateTime endTime)
{
    string filter = "[Start] >= '"
        + startTime.ToString("g")
        + "' AND [End] <= '"
        + endTime.ToString("g") + "'";
    Debug.WriteLine(filter);
    try
    {
        Outlook.Items calItems = folder.Items;
        calItems.IncludeRecurrences = true;
        calItems.Sort("[Start]", Type.Missing);
        Outlook.Items restrictItems = calItems.Restrict(filter);
        if (restrictItems.Count > 0)
        {
            return restrictItems;
        }
        else
        {
            return null;
        }
    }
    catch { return null; }
}
```

## <a name="see-also"></a><span data-ttu-id="cbd8e-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cbd8e-128">See also</span></span>

- [<span data-ttu-id="cbd8e-129">搜索和筛选</span><span class="sxs-lookup"><span data-stu-id="cbd8e-129">Search and filter</span></span>](search-and-filter.md)

