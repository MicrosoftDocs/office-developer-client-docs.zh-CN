---
title: FindRecord 宏操作
TOCTitle: FindRecord macro action
ms:assetid: 379e3dda-cb7d-a294-29b1-c6ce9a62ba8a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192494(v=office.15)
ms:contentKeyID: 48544199
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm7496
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 086993095daef3ff4ad87aed9f572a09124a9d31
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292370"
---
# <a name="findrecord-macro-action"></a>FindRecord 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **FindRecord** 操作查找符合由 **FindRecord** 参数指定的条件的第一个数据实例。此数据可能在当前记录中，也可能在当前记录之前或之后的记录中，或者在第一条记录中。您可以在活动表数据表、查询数据表、窗体数据表或窗体中查找记录。

## <a name="setting"></a>Setting

**FindRecord** 操作具有下列参数。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>操作参数</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>查找内容</strong></p></td>
<td><p>指定要在记录中查找的数据。 在 "宏生成器" 窗格的 "<strong>操作参数</strong>" 部分的 "查找内容" 框中, 输入要查找的文本<strong>=</strong>、数字或日期, 或在 "<strong>查找内容</strong>" 框中键入一个以等号 () 开头的表达式。 可以使用通配符。 这是一个必选参数。</p></td>
</tr>
<tr class="even">
<td><p><strong>匹配</strong></p></td>
<td><p>指定数据在字段中的位置。可以指定搜索位于字段任何部分的数据（<strong>“字段任何部分”</strong>）、填充整个字段的数据（<strong>“整个字段”</strong>）或位于字段开头的数据（<strong>“字段开头”</strong>）。默认值为<strong>“整个字段”</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>区分大小写</strong></p></td>
<td><p>指定搜索是否区分大小写。请单击 <strong>"是"</strong>（执行区分大小写的搜索）或 <strong>"否"</strong>（进行搜索时不精确匹配大写和小写字母）。默认值为 <strong>"否"</strong>。  </p></td>
</tr>
<tr class="even">
<td><p><strong>搜索</strong></p></td>
<td><p>指定搜索方式：从当前记录开始向上搜索到记录开头（<strong>“向上”</strong>）；向下搜索到记录末尾（<strong>“向下”</strong>）；或者向下搜索到记录末尾，然后再从记录开头开始搜索到当前记录，从而搜索所有记录（<strong>“全部”</strong>）。默认值为<strong>“全部”</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>格式化搜索</strong></p></td>
<td><p>Specifies whether the search includes formatted data. Click <strong>Yes</strong> (Microsoft Office Access 2007 searches for the data as it is formatted and displayed in the field) or <strong>No</strong> (Access searches for the data as it is stored in the database, which isn't always the same as it's displayed). The default is <strong>No</strong>. You can use this feature to restrict the search to data in a particular format. For example, click <strong>Yes</strong> and type <strong>1,234</strong> in the <strong>Find What</strong> argument to find a value of 1,234 in a field formatted to include commas. Click <strong>No</strong> if you want to type <strong>1234</strong> to search for the data in this field. To search for dates, click <strong>Yes</strong> to find a date exactly as it is formatted, such as 08-July-2003. If you click <strong>No</strong>, enter the date for the <strong>Find What</strong> argument in the format that is set in the regional settings in Windows Control Panel. This format is shown in the <strong>Short date format</strong> box found on the <strong>Date</strong> tab in the regional settings. For example, if the <strong>Short date format</strong> box is set to <strong>M/d/yy</strong>, you can enter 7/8/03, and Access will find all entries in a Date field that correspond to July 8, 2003, regardless of how this field is formatted.  </p>
<p><strong>注意</strong>: 仅当当前字段是绑定控件、 <strong>Match</strong>参数设置为 "<strong>整个字段</strong>"、"<strong>仅当前字段</strong>" 参数设置为<strong>"是</strong>" 和 "匹配" 时, "<strong>按格式搜索</strong>" 参数才会生效。 <strong>Case</strong>参数设置为 "<strong>否</strong>"。</p>
<p>If you set <strong>Match Case</strong> to <strong>Yes</strong> or <strong>Only Current Field</strong> to <strong>No</strong>, you must also set <strong>Search As Formatted</strong> to <strong>Yes</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>只搜索当前字段</strong></p></td>
<td><p>指定是将搜索限制在每个记录内的当前字段，还是包括每个记录内的所有字段。在当前字段中进行搜索的速度更快。请单击 <strong>"是"</strong>（将搜索限制在当前字段）或 <strong>"否"</strong>（在每个记录内的所有字段中进行搜索）。默认值为 <strong>"是"</strong>。  </p></td>
</tr>
<tr class="odd">
<td><p><strong>查找第一个</strong></p></td>
<td><p>指定搜索是从第一条记录开始，还是从当前记录开始。请单击 <strong>"是"</strong>（从第一条记录开始）或 <strong>"否"</strong>（从当前记录开始）。默认值为 <strong>"是"</strong>。  </p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

When a macro runs the **FindRecord** action, Access searches for the specified data in the records (the order of the search is determined by the setting of the **Search** argument). When Access finds the specified data, the data is selected in the record.

**FindRecord** 操作等效于在 **"开始"** 选项卡上单击 **"查找"**，其参数与 **"查找和替换"** 对话框中的选项相同。如果在"宏生成器"窗格中设置了 **FindRecord** 参数，然后运行宏，则您将看到单击 **"查找"** 时 **"查找和替换"** 对话框中选择的相应选项。

在数据库会话过程中，Access 会保留最近的 **FindRecord** 参数，因而您在使用 **FindRecord** 操作执行后续操作时无需重复输入相同的条件。如果您将某个参数留空，Access 将使用该参数的最近设置，与在前一个 **FindRecord** 操作或 **"查找和替换"** 对话框中的设置相同。

当需要使用宏查找记录时，请使用 **FindRecord** 操作，而不是其参数设置为运行 **"查找"** 命令的 **RunMenuCommand** 操作。

> [!NOTE]
> [!注释] 针对表、查询和窗体的 **FindRecord** 操作对应于 **"开始"** 选项卡上的 **"查找"** 命令，而不对应于"代码"窗口的 **"编辑"** 菜单上的 **"查找"** 命令。不能使用 **FindRecord** 操作在模块中搜索文本。

在执行 **FindRecord** 操作时，如果当前选择的文本与搜索文本相同，则会从所选文本之后开始在包含该文本的同一字段和同一记录中进行搜索。否则将从当前记录的起始位置开始搜索。这样可以找到单个记录中可能出现的符合相同搜索条件的多个实例。

但请注意，如果使用命令按钮运行包含 **FindRecord** 操作的宏，则将重复找到搜索条件的第一个实例。出现这种情况的原因是，单击命令按钮会将焦点从包含匹配值的字段中移走。然后， **FindRecord** 操作将从记录开头开始搜索。为了避免此问题，请使用不更改焦点的技术（例如自定义工具栏按钮或在 AutoKeys 宏中定义的组合键）运行宏，或在执行 **FindRecord** 操作之前将宏中的焦点设置为包含搜索条件的字段。

<table>
<thead>
<tr class="header">
<th><img src="media/access-alert-security.gif" title="安全注释" alt="Security note" /><strong>安全说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>避免使用带敏感信息或机密信息的 <strong>SendKeys</strong> 语句或 AutoKeys 宏。恶意用户会截取键击，从而危及计算机和数据的安全性。</td>
</tr>
</tbody>
</table>

如果使用命令按钮运行包含 **FindNext** 操作的宏，也会出现同样的情况。

要在 Visual Basic for Applications (VBA) 模块中运行 **FindRecord** 操作，请使用 **DoCmd** 对象的 **FindRecord** 方法。

要进行更加复杂的搜索，您可能需要使用 **SearchForRecord** 宏操作。

