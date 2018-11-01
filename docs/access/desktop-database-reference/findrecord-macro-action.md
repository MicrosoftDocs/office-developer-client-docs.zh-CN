---
title: FindRecord 宏操作
TOCTitle: FindRecord Macro Action
ms:assetid: 379e3dda-cb7d-a294-29b1-c6ce9a62ba8a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192494(v=office.15)
ms:contentKeyID: 48544199
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm7496
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 60f0b30574bd97572739664ca37c44e69258d544
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25881347"
---
# <a name="findrecord-macro-action"></a>FindRecord 宏操作


**适用于**： Access 2013、 Office 2013

可以使用 **FindRecord** 操作查找符合由 **FindRecord** 参数指定的条件的第一个数据实例。此数据可能在当前记录中，也可能在当前记录之前或之后的记录中，或者在第一条记录中。您可以在活动表数据表、查询数据表、窗体数据表或窗体中查找记录。

## <a name="setting"></a>设置

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
<td><p>指定要在记录中查找的数据。 输入文本、 数字或日期您想要查找或键入一个表达式，前面带有等号 (<strong>=</strong>)，在宏生成器窗格的<strong>操作参数</strong>部分的<strong>查找内容</strong>框中。 可以使用通配符。 这是一个必选参数。</p></td>
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
<td><p>指定搜索是否包括带格式的数据。 单击<strong>是</strong>（Microsoft Office Access 2007 将按其格式并显示在字段中搜索数据） 或<strong>否</strong>（存储在数据库中，这并不总是相同显示时，访问数据的搜索）。 默认值为 <strong>"否"</strong>。 此功能可用于将搜索限制为特定格式的数据。 例如，单击<strong>是</strong>，并在<strong>查找内容</strong>参数来查找格式设置为包含逗号分隔的字段的值为 1234 键入<strong>1234</strong> 。 如果您想要键入<strong>1234年</strong>以搜索此字段中的数据，请单击<strong>否</strong>。 要搜索日期，请单击<strong>是</strong>以查找完全按照它的格式设置，如 2003 年 7 月-08-的日期。 如果您单击<strong>否</strong>，在 Windows 控制面板中的区域设置中设置的格式输入<strong>查找内容</strong>参数的日期。 在区域设置中的<strong>日期</strong>选项卡上找到的<strong>短日期格式</strong>框中显示此格式。 例如，如果<strong>短日期格式</strong>框设置为<strong>d/yy</strong>，可以输入 7/8/03，并对应于 2003 年 7 月 8 日，无论该字段的格式的日期字段中，Access 将查找的所有条目。</p>

> [!NOTE]
> <P><STRONG>格式搜索</STRONG>参数才会生效，只有当前字段是绑定的控件、<STRONG>匹配</STRONG>参数设置为<STRONG>整个字段</STRONG><STRONG>只搜索当前字段</STRONG>参数设置为<STRONG>是</STRONG>，和<STRONG>区分大小写</STRONG>参数设置为<STRONG>No</STRONG>。</P>


<p>如果您设置为<strong>是</strong>或<strong>只搜索当前字段</strong>为<strong>否</strong><strong>区分大小写</strong>，还必须设置<strong>格式搜索</strong>为<strong>是</strong>。</p></td>
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


## <a name="remarks"></a>说明

当宏运行**FindRecord**操作时，访问搜索 （由**搜索**参数的设置确定的顺序搜索） 的记录中指定的数据。 当访问找到指定的数据时，记录中选定的数据。

**FindRecord** 操作等效于在 **"开始"** 选项卡上单击 **"查找"**，其参数与 **"查找和替换"** 对话框中的选项相同。如果在"宏生成器"窗格中设置了 **FindRecord** 参数，然后运行宏，则您将看到单击 **"查找"** 时 **"查找和替换"** 对话框中选择的相应选项。

在数据库会话过程中，Access 会保留最近的 **FindRecord** 参数，因而您在使用 **FindRecord** 操作执行后续操作时无需重复输入相同的条件。如果您将某个参数留空，Access 将使用该参数的最近设置，与在前一个 **FindRecord** 操作或 **"查找和替换"** 对话框中的设置相同。

当需要使用宏查找记录时，请使用 **FindRecord** 操作，而不是其参数设置为运行 **"查找"** 命令的 **RunMenuCommand** 操作。


> [!NOTE]
> <P>[!注释] 针对表、查询和窗体的 <STRONG>FindRecord</STRONG> 操作对应于 <STRONG>"开始"</STRONG>选项卡上的 <STRONG>"查找"</STRONG>命令，而不对应于"代码"窗口的 <STRONG>"编辑"</STRONG>菜单上的 <STRONG>"查找"</STRONG>命令。不能使用 <STRONG>FindRecord</STRONG> 操作在模块中搜索文本。</P>



在执行 **FindRecord** 操作时，如果当前选择的文本与搜索文本相同，则会从所选文本之后开始在包含该文本的同一字段和同一记录中进行搜索。否则将从当前记录的起始位置开始搜索。这样可以找到单个记录中可能出现的符合相同搜索条件的多个实例。

但请注意，如果使用命令按钮运行包含 **FindRecord** 操作的宏，则将重复找到搜索条件的第一个实例。出现这种情况的原因是，单击命令按钮会将焦点从包含匹配值的字段中移走。然后， **FindRecord** 操作将从记录开头开始搜索。为了避免此问题，请使用不更改焦点的技术（例如自定义工具栏按钮或在 AutoKeys 宏中定义的组合键）运行宏，或在执行 **FindRecord** 操作之前将宏中的焦点设置为包含搜索条件的字段。

<table>
<thead>
<tr class="header">
<th><img src="media/access-alert-security.gif" title="安全说明" alt="Security note" /><strong>安全注释</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>
      避免使用 <strong>SendKeys</strong> 语句或带敏感或机密信息的 AutoKeys 宏。恶意用户可能会拦截键击并损害您的计算机和数据的安全性。
</td>
</tr>
</tbody>
</table>


如果使用命令按钮运行包含 **FindNext** 操作的宏，也会出现同样的情况。

要在 Visual Basic for Applications (VBA) 模块中运行 **FindRecord** 操作，请使用 **DoCmd** 对象的 **FindRecord** 方法。

要进行更加复杂的搜索，您可能需要使用 **SearchForRecord** 宏操作。

