---
title: 在枚举文件夹中的项时筛选并显示计算属性
TOCTitle: Filter and display computed properties when enumerating items in a folder
ms:assetid: b068e625-ff12-444d-a30d-51a3acba3043
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184632(v=office.15)
ms:contentKeyID: 55119922
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 946858221b649cd6189ddf44680b316554cab5de
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320333"
---
# <a name="filter-and-display-computed-properties-when-enumerating-items-in-a-folder"></a>在枚举文件夹中的项目时筛选并显示计算属性

此示例演示如何在枚举文件夹中的项目时筛选和显示计算属性。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。


[Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象表示 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 或 [Search](https://msdn.microsoft.com/library/bb612611\(v=office.15\)) 对象中的一组项目数据。 [Row](https://msdn.microsoft.com/library/bb610126\(v=office.15\)) 对象表示 **Table** 中的数据行。 [Columns](https://msdn.microsoft.com/library/bb646214\(v=office.15\)) 对象表示 **Table** 的属性。您可以通过使用 **Columns** 对象的 [Add(String)](https://msdn.microsoft.com/library/bb652865\(v=office.15\)) 方法将某些属性添加到 **Table** 对象中。可以通过使用 [Table](https://msdn.microsoft.com/library/bb612178\(v=office.15\)) 对象的 **Restrict(String)** 方法对某些属性进行筛选。但是，有些属性既无法通过使用 **Columns.Add** 添加到 **Table** 对象中，也无法通过使用 **Restrict** 方法进行筛选。下表描述在使用 **Columns.Add** 或 **Restrict** 方法时 **Table** 对象对属性的支持性。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>属性</p></th>
<th><p>使用 Columns.Add 时</p></th>
<th><p>使用 Restrict 时</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>二进制属性，如 <b>EntryID</b>。</p></td>
<td><p>通过内置或命名空间属性提供支持。</p></td>
<td><p>不支持。Outlook 将发生错误。</p></td>
</tr>
<tr class="even">
<td><p>正文属性，包括 <b>Body</b> 和 <b>HTMLBody</b> 以及这些属性的命名空间表示形式（包括 <b>PR_RTF_COMPRESSED</b>）。</p></td>
<td><p>满足以下条件时支持 <b>Body</b> 属性：只有相应值的前 255 个字节存储在 <b>Table</b> 对象中。 不支持以 HTML 或 RTF 格式表示正文内容的其他属性。 因为系统将仅返回 <b>Body</b> 的前 255 个字节，如果你想以文本或 HTML 格式获取某个项目的全部正文内容，请在 <a href="https://msdn.microsoft.com/library/bb644121(v=office.15)">GetItemFromID(String, Object)</a> 方法中使用该项目的 <b>EntryID</b> 来获取项目对象。 然后，在整个项目对象中检索 <b>Body</b> 的完整值。</p></td>
<td><p>筛选器中仅支持文本表示形式的 <b>Body</b> 属性。这意味着在 DAV 搜索和定位 (DASL) 筛选器中必须将该属性作为 <em>urn:schemas:http-mail:textdescription</em> 进行引用，而且您无法对正文中的任何 HTML 标记进行筛选。为了提高性能，请在筛选器中使用内容索引器关键字来匹配正文中的字符串。</p></td>
</tr>
<tr class="odd">
<td><p>计算机属性，如 <b>AutoResolvedWinner</b> 和 <b>BodyFormat</b>。</p></td>
<td><p>不支持。</p></td>
<td><p>不支持。</p></td>
</tr>
<tr class="even">
<td><p>多值属性，如 <b>Categories</b>、<b>Children</b>、<b>Companies</b> 和 <b>VotingOptions</b>。</p></td>
<td><p>支持。</p></td>
<td><p>支持，前提是你能够使用命名空间表示形式创建 DASL 查询。</p></td>
</tr>
<tr class="odd">
<td><p>用于返回某个对象的属性，如 <b>Attachments</b>、<b>Parent</b>、<b>Recipients</b>、<b>RecurrencePattern</b> 和 <b>UserProperties</b>。</p></td>
<td><p>不支持。</p></td>
<td><p>不支持。</p></td>
</tr>
</tbody>
</table>


下表列出了无法通过使用 **Columns.Add** 添加到 **Table** 对象中的已知无效属性。如果尝试从此列表中添加属性，则 Outlook 将引发错误。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>AutoResolvedWinner</p></td>
<td><p>BodyFormat</p></td>
<td><p>类</p></td>
</tr>
<tr class="even">
<td><p>Companies</p></td>
<td><p>ContactNames</p></td>
<td><p>DLName</p></td>
</tr>
<tr class="odd">
<td><p>DownloadState</p></td>
<td><p>FlagIcon</p></td>
<td><p>HtmlBody</p></td>
</tr>
<tr class="even">
<td><p>InternetCodePage</p></td>
<td><p>IsConflict</p></td>
<td><p>IsMarkedAsTask</p></td>
</tr>
<tr class="odd">
<td><p>MeetingWorkspaceURL</p></td>
<td><p>MemberCount</p></td>
<td><p>Permission</p></td>
</tr>
<tr class="even">
<td><p>PermissionService</p></td>
<td><p>RecurrenceState</p></td>
<td><p>ResponseState</p></td>
</tr>
<tr class="odd">
<td><p>Saved</p></td>
<td><p>发件箱</p></td>
<td><p>已提交</p></td>
</tr>
<tr class="even">
<td><p>TaskSubject</p></td>
<td><p>未读</p></td>
<td><p>VotingOptions</p></td>
</tr>
</tbody>
</table>


虽然一些计算属性无法添加到为表格设置的列，但是下面的代码示例可以克服这个限制。 GetToDoItems 使用 DASL 查询来限制出现在 **Table** 中的项目。 如果计算属性采用命名空间表示形式，则命名空间表示形式将用于创建 DASL 查询，该查询将 **Table** 对象限制为返回计算属性的指定值所在的行。 GetToDoItem 获取收件箱中 [IsMarkedAsTask](https://msdn.microsoft.com/library/bb623631\(v=office.15\)) 属性值等于 **true** 的项目，然后将这些值分配给特定的任务属性，如 [TaskSubject](https://msdn.microsoft.com/library/bb643880\(v=office.15\))、[TaskDueDate](https://msdn.microsoft.com/library/bb623035\(v=office.15\))、[TaskStartDate](https://msdn.microsoft.com/library/bb610832\(v=office.15\)) 和 [TaskCompletedDate](https://msdn.microsoft.com/library/bb624055\(v=office.15\))。 最后，这些属性都将被写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器中。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。 下面几行代码展示了如何在 C\# 中执行导入和分配操作。

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
        "https://schemas.microsoft.com/mapi/proptag/0x0E2B0003"
        + "\"" + " = 1";
    Outlook.Table table =
        folder.GetTable(filter,
        Outlook.OlTableContents.olUserItems);
    table.Columns.Add("TaskStartDate");
    table.Columns.Add("TaskDueDate");
    table.Columns.Add("TaskCompletedDate");
    // Use GUID/ID to represent TaskSubject
    table.Columns.Add(
        "https://schemas.microsoft.com/mapi/id/" +
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

## <a name="see-also"></a>另请参阅

- [搜索和筛选](search-and-filter.md)

