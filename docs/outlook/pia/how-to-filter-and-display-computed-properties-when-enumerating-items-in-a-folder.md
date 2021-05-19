---
title: 在枚举文件夹中的项目时筛选并显示计算属性
TOCTitle: Filter and display computed properties when enumerating items in a folder
ms:assetid: b068e625-ff12-444d-a30d-51a3acba3043
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184632(v=office.15)
ms:contentKeyID: 55119922
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 1c1702ce816714b21da860aea3e49db8a3511701
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542637"
---
# <a name="filter-and-display-computed-properties-when-enumerating-items-in-a-folder"></a><span data-ttu-id="d5973-102">在枚举文件夹中的项目时筛选并显示计算属性</span><span class="sxs-lookup"><span data-stu-id="d5973-102">Filter and display computed properties when enumerating items in a folder</span></span>

<span data-ttu-id="d5973-103">此示例演示如何在枚举文件夹中的项目时筛选和显示计算属性。</span><span class="sxs-lookup"><span data-stu-id="d5973-103">This example shows how to filter and display computed properties when enumerating items in a folder.</span></span>

## <a name="example"></a><span data-ttu-id="d5973-104">示例</span><span class="sxs-lookup"><span data-stu-id="d5973-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="d5973-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="d5973-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>


<span data-ttu-id="d5973-p101">[Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象表示 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 或 [Search](https://msdn.microsoft.com/library/bb612611\(v=office.15\)) 对象中的一组项目数据。 [Row](https://msdn.microsoft.com/library/bb610126\(v=office.15\)) 对象表示 **Table** 中的数据行。 [Columns](https://msdn.microsoft.com/library/bb646214\(v=office.15\)) 对象表示 **Table** 的属性。您可以通过使用 **Columns** 对象的 [Add(String)](https://msdn.microsoft.com/library/bb652865\(v=office.15\)) 方法将某些属性添加到 **Table** 对象中。可以通过使用 [Table](https://msdn.microsoft.com/library/bb612178\(v=office.15\)) 对象的 **Restrict(String)** 方法对某些属性进行筛选。但是，有些属性既无法通过使用 **Columns.Add** 添加到 **Table** 对象中，也无法通过使用 **Restrict** 方法进行筛选。下表描述在使用 **Columns.Add** 或 **Restrict** 方法时 **Table** 对象对属性的支持性。</span><span class="sxs-lookup"><span data-stu-id="d5973-p101">The [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) object represents a set of item data from a [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) or [Search](https://msdn.microsoft.com/library/bb612611\(v=office.15\)) object. The [Row](https://msdn.microsoft.com/library/bb610126\(v=office.15\)) object represents rows of data in a **Table**. The [Columns](https://msdn.microsoft.com/library/bb646214\(v=office.15\)) object represents properties of the **Table**. You can add certain properties to the **Table** object by using the [Add(String)](https://msdn.microsoft.com/library/bb652865\(v=office.15\)) method of the **Columns** object. You can filter certain properties by using the [Restrict(String)](https://msdn.microsoft.com/library/bb612178\(v=office.15\)) method of the **Table** object. However, some properties cannot be added to the **Table** object by using **Columns.Add**, nor can they be filtered by using the **Restrict** method. The following table describes whether properties are supported for the **Table** object when you use the **Columns.Add** or **Restrict** method.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="d5973-113">属性</span><span class="sxs-lookup"><span data-stu-id="d5973-113">Property</span></span></p></th>
<th><p><span data-ttu-id="d5973-114">使用 Columns.Add 时</span><span class="sxs-lookup"><span data-stu-id="d5973-114">For Columns.Add</span></span></p></th>
<th><p><span data-ttu-id="d5973-115">使用 Restrict 时</span><span class="sxs-lookup"><span data-stu-id="d5973-115">For Restrict</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5973-116">二进制属性，如 <b>EntryID</b>。</span><span class="sxs-lookup"><span data-stu-id="d5973-116">Binary properties such as <b>EntryID</b>.</span></span></p></td>
<td><p><span data-ttu-id="d5973-117">通过内置或命名空间属性提供支持。</span><span class="sxs-lookup"><span data-stu-id="d5973-117">Supported via built-in or namespace property.</span></span></p></td>
<td><p><span data-ttu-id="d5973-p102">不支持。Outlook 将发生错误。</span><span class="sxs-lookup"><span data-stu-id="d5973-p102">Not supported. Outlook will raise an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5973-120">正文属性，包括 <b>Body</b> 和 <b>HTMLBody</b> 以及这些属性的命名空间表示形式（包括 <b>PR_RTF_COMPRESSED</b>）。</span><span class="sxs-lookup"><span data-stu-id="d5973-120">Body properties, including <b>Body</b> and <b>HTMLBody</b>, and namespace representation of those properties, including <b>PR_RTF_COMPRESSED</b>.</span></span></p></td>
<td><p><span data-ttu-id="d5973-121">满足以下条件时支持 <b>Body</b> 属性：只有相应值的前 255 个字节存储在 <b>Table</b> 对象中。</span><span class="sxs-lookup"><span data-stu-id="d5973-121">The <b>Body</b> property is supported with a condition that only the first 255 bytes of the value are stored in a <b>Table</b> object.</span></span> <span data-ttu-id="d5973-122">不支持以 HTML 或 RTF 格式表示正文内容的其他属性。</span><span class="sxs-lookup"><span data-stu-id="d5973-122">Other properties that represent the body content in HTML or RTF are not supported.</span></span> <span data-ttu-id="d5973-123">因为系统将仅返回 <b>Body</b> 的前 255 个字节，如果你想以文本或 HTML 格式获取某个项目的全部正文内容，请在 <a href="https://msdn.microsoft.com/library/bb644121(v=office.15)">GetItemFromID(String, Object)</a> 方法中使用该项目的 <b>EntryID</b> 来获取项目对象。</span><span class="sxs-lookup"><span data-stu-id="d5973-123">Because only the first 255 bytes of <b>Body</b> are returned, if you want to obtain the full body content of an item in text or HTML, use the item’s <b>EntryID</b> in the <a href="https://msdn.microsoft.com/library/bb644121(v=office.15)">GetItemFromID(String, Object)</a> method to obtain the item object.</span></span> <span data-ttu-id="d5973-124">然后，在整个项目对象中检索 <b>Body</b> 的完整值。</span><span class="sxs-lookup"><span data-stu-id="d5973-124">Then retrieve the full value of <b>Body</b> through the item object.</span></span></p></td>
<td><p><span data-ttu-id="d5973-p104">筛选器中仅支持文本表示形式的 <b>Body</b> 属性。这意味着在 DAV 搜索和定位 (DASL) 筛选器中必须将该属性作为 <em>urn:schemas:http-mail:textdescription</em> 进行引用，而且您无法对正文中的任何 HTML 标记进行筛选。为了提高性能，请在筛选器中使用内容索引器关键字来匹配正文中的字符串。</span><span class="sxs-lookup"><span data-stu-id="d5973-p104">Only the <b>Body</b> property represented in text is supported in a filter. This means that the property must be referenced in a DAV Searching and Locating (DASL) filter as <em>urn:schemas:http-mail:textdescription</em>, and you cannot filter on any HTML tags in the body. To improve performance, use context indexer keywords in the filter to match strings in the body.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5973-128">计算机属性，如 <b>AutoResolvedWinner</b> 和 <b>BodyFormat</b>。</span><span class="sxs-lookup"><span data-stu-id="d5973-128">Computer properties, such as <b>AutoResolvedWinner</b> and <b>BodyFormat</b>.</span></span></p></td>
<td><p><span data-ttu-id="d5973-129">不支持。</span><span class="sxs-lookup"><span data-stu-id="d5973-129">Not supported.</span></span></p></td>
<td><p><span data-ttu-id="d5973-130">不支持。</span><span class="sxs-lookup"><span data-stu-id="d5973-130">Not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5973-131">多值属性，如 <b>Categories</b>、<b>Children</b>、<b>Companies</b> 和 <b>VotingOptions</b>。</span><span class="sxs-lookup"><span data-stu-id="d5973-131">Multivalued properties, such as <b>Categories</b>, <b>Children</b>, <b>Companies</b>, and <b>VotingOptions</b>.</span></span></p></td>
<td><p><span data-ttu-id="d5973-132">支持。</span><span class="sxs-lookup"><span data-stu-id="d5973-132">Supported.</span></span></p></td>
<td><p><span data-ttu-id="d5973-133">支持，前提是你能够使用命名空间表示形式创建 DASL 查询。</span><span class="sxs-lookup"><span data-stu-id="d5973-133">Supported, provided that you can create a DASL query by using the namespace representation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5973-134">用于返回某个对象的属性，如 <b>Attachments</b>、<b>Parent</b>、<b>Recipients</b>、<b>RecurrencePattern</b> 和 <b>UserProperties</b>。</span><span class="sxs-lookup"><span data-stu-id="d5973-134">Properties that return an object, such as <b>Attachments</b>, <b>Parent</b>, <b>Recipients</b>, <b>RecurrencePattern</b>, and <b>UserProperties</b>.</span></span></p></td>
<td><p><span data-ttu-id="d5973-135">不支持。</span><span class="sxs-lookup"><span data-stu-id="d5973-135">Not supported.</span></span></p></td>
<td><p><span data-ttu-id="d5973-136">不支持。</span><span class="sxs-lookup"><span data-stu-id="d5973-136">Not supported.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d5973-p105">下表列出了无法通过使用 **Columns.Add** 添加到 **Table** 对象中的已知无效属性。如果尝试从此列表中添加属性，则 Outlook 将引发错误。</span><span class="sxs-lookup"><span data-stu-id="d5973-p105">The following table lists known invalid properties that cannot be added to the **Table** object by using **Columns.Add**. If you attempt to add a property from this list, Outlook will raise an error.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5973-139">AutoResolvedWinner</span><span class="sxs-lookup"><span data-stu-id="d5973-139">AutoResolvedWinner</span></span></p></td>
<td><p><span data-ttu-id="d5973-140">BodyFormat</span><span class="sxs-lookup"><span data-stu-id="d5973-140">BodyFormat</span></span></p></td>
<td><p><span data-ttu-id="d5973-141">类</span><span class="sxs-lookup"><span data-stu-id="d5973-141">Class</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5973-142">Companies</span><span class="sxs-lookup"><span data-stu-id="d5973-142">Companies</span></span></p></td>
<td><p><span data-ttu-id="d5973-143">ContactNames</span><span class="sxs-lookup"><span data-stu-id="d5973-143">ContactNames</span></span></p></td>
<td><p><span data-ttu-id="d5973-144">DLName</span><span class="sxs-lookup"><span data-stu-id="d5973-144">DLName</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5973-145">DownloadState</span><span class="sxs-lookup"><span data-stu-id="d5973-145">DownloadState</span></span></p></td>
<td><p><span data-ttu-id="d5973-146">FlagIcon</span><span class="sxs-lookup"><span data-stu-id="d5973-146">FlagIcon</span></span></p></td>
<td><p><span data-ttu-id="d5973-147">HtmlBody</span><span class="sxs-lookup"><span data-stu-id="d5973-147">HtmlBody</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5973-148">InternetCodePage</span><span class="sxs-lookup"><span data-stu-id="d5973-148">InternetCodePage</span></span></p></td>
<td><p><span data-ttu-id="d5973-149">IsConflict</span><span class="sxs-lookup"><span data-stu-id="d5973-149">IsConflict</span></span></p></td>
<td><p><span data-ttu-id="d5973-150">IsMarkedAsTask</span><span class="sxs-lookup"><span data-stu-id="d5973-150">IsMarkedAsTask</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5973-151">MeetingWorkspaceURL</span><span class="sxs-lookup"><span data-stu-id="d5973-151">MeetingWorkspaceURL</span></span></p></td>
<td><p><span data-ttu-id="d5973-152">MemberCount</span><span class="sxs-lookup"><span data-stu-id="d5973-152">MemberCount</span></span></p></td>
<td><p><span data-ttu-id="d5973-153">Permission</span><span class="sxs-lookup"><span data-stu-id="d5973-153">Permission</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5973-154">PermissionService</span><span class="sxs-lookup"><span data-stu-id="d5973-154">PermissionService</span></span></p></td>
<td><p><span data-ttu-id="d5973-155">RecurrenceState</span><span class="sxs-lookup"><span data-stu-id="d5973-155">RecurrenceState</span></span></p></td>
<td><p><span data-ttu-id="d5973-156">ResponseState</span><span class="sxs-lookup"><span data-stu-id="d5973-156">ResponseState</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5973-157">Saved</span><span class="sxs-lookup"><span data-stu-id="d5973-157">Saved</span></span></p></td>
<td><p><span data-ttu-id="d5973-158">发件箱</span><span class="sxs-lookup"><span data-stu-id="d5973-158">Sent</span></span></p></td>
<td><p><span data-ttu-id="d5973-159">已提交</span><span class="sxs-lookup"><span data-stu-id="d5973-159">Submitted</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5973-160">TaskSubject</span><span class="sxs-lookup"><span data-stu-id="d5973-160">TaskSubject</span></span></p></td>
<td><p><span data-ttu-id="d5973-161">未读</span><span class="sxs-lookup"><span data-stu-id="d5973-161">Unread</span></span></p></td>
<td><p><span data-ttu-id="d5973-162">VotingOptions</span><span class="sxs-lookup"><span data-stu-id="d5973-162">VotingOptions</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d5973-163">虽然一些计算属性无法添加到为表格设置的列，但是下面的代码示例可以克服这个限制。</span><span class="sxs-lookup"><span data-stu-id="d5973-163">Although some computed properties cannot be added to the column set for a table, the following code example works around this limitation.</span></span> <span data-ttu-id="d5973-164">GetToDoItems 使用 DASL 查询来限制出现在 **Table** 中的项目。</span><span class="sxs-lookup"><span data-stu-id="d5973-164">GetToDoItems uses a DASL query to restrict the items that appear in the **Table**.</span></span> <span data-ttu-id="d5973-165">如果计算属性采用命名空间表示形式，则命名空间表示形式将用于创建 DASL 查询，该查询将 **Table** 对象限制为返回计算属性的指定值所在的行。</span><span class="sxs-lookup"><span data-stu-id="d5973-165">If the computed property has a namespace representation, the namespace representation is used to create a DASL query that restricts the **Table** object to return rows for a specified value of the computed property.</span></span> <span data-ttu-id="d5973-166">GetToDoItem 获取收件箱中 [IsMarkedAsTask](https://msdn.microsoft.com/library/bb623631\(v=office.15\)) 属性值等于 **true** 的项目，然后将这些值分配给特定的任务属性，如 [TaskSubject](https://msdn.microsoft.com/library/bb643880\(v=office.15\))、[TaskDueDate](https://msdn.microsoft.com/library/bb623035\(v=office.15\))、[TaskStartDate](https://msdn.microsoft.com/library/bb610832\(v=office.15\)) 和 [TaskCompletedDate](https://msdn.microsoft.com/library/bb624055\(v=office.15\))。</span><span class="sxs-lookup"><span data-stu-id="d5973-166">GetToDoItems gets items in the Inbox where the value of the [IsMarkedAsTask](https://msdn.microsoft.com/library/bb623631\(v=office.15\)) property is equal to **true**, and then assigns values to certain task properties such as [TaskSubject](https://msdn.microsoft.com/library/bb643880\(v=office.15\)), [TaskDueDate](https://msdn.microsoft.com/library/bb623035\(v=office.15\)), [TaskStartDate](https://msdn.microsoft.com/library/bb610832\(v=office.15\)), and [TaskCompletedDate](https://msdn.microsoft.com/library/bb624055\(v=office.15\)).</span></span> <span data-ttu-id="d5973-167">最后，这些属性都将被写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器中。</span><span class="sxs-lookup"><span data-stu-id="d5973-167">Finally, those properties are written to the trace listeners of the [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) collection.</span></span>

<span data-ttu-id="d5973-168">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="d5973-168">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="d5973-169">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="d5973-169">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="d5973-170">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="d5973-170">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void GetToDoItems()
{
    // Obtain Inbox
    Outlook.Folder folder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox)
        as Outlook.Folder;
    // DASL filter for IsMarkedAsTask
    string filter = "@SQL=" + "\"" +
        "http://schemas.microsoft.com/mapi/proptag/0x0E2B0003"
        + "\"" + " = 1";
    Outlook.Table table =
        folder.GetTable(filter,
        Outlook.OlTableContents.olUserItems);
    table.Columns.Add("TaskStartDate");
    table.Columns.Add("TaskDueDate");
    table.Columns.Add("TaskCompletedDate");
    // Use GUID/ID to represent TaskSubject
    table.Columns.Add(
        "http://schemas.microsoft.com/mapi/id/" +
        "{00062008-0000-0000-C000-000000000046}/85A4001E");
    while (!table.EndOfTable)
    {
        Outlook.Row nextRow = table.GetNextRow();
        StringBuilder sb = new StringBuilder();
        sb.AppendLine("Task Subject: " + nextRow[9]);
        sb.AppendLine("Start Date: "
            + nextRow["TaskStartDate"]);
        sb.AppendLine("Due Date: "
            + nextRow["TaskDueDate"]);
        sb.AppendLine("Completed Date: "
            + nextRow["TaskCompletedDate"]);
        sb.AppendLine();
        Debug.WriteLine(sb.ToString());
    }
}
```

## <a name="see-also"></a><span data-ttu-id="d5973-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5973-171">See also</span></span>

- [<span data-ttu-id="d5973-172">搜索和筛选</span><span class="sxs-lookup"><span data-stu-id="d5973-172">Search and filter</span></span>](search-and-filter.md)

