---
title: ImportExportText 宏操作
TOCTitle: ImportExportText macro action
ms:assetid: 366fa095-6f09-7c22-e734-bfa585cfe79e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192475(v=office.15)
ms:contentKeyID: 48544171
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm168097
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: a26b370e14dba68b0cbe686f4b23ae0db3fc1fea
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28707862"
---
# <a name="importexporttext-macro-action"></a>ImportExportText 宏操作

**适用于**： Access 2013、 Office 2013

可以使用 **ImportExportText** 操作在当前 Microsoft Access 数据库（.mdb 或 .accdb）或 Microsoft Access 项目 (.adp) 与文本文件之间导入或导出文本。 还可以将文本文件中的数据链接到当前的 Access 数据库。 使用链接的文本文件，您可以通过 Access 查看文本数据，同时仍然可从字处理程序中对这些数据进行完全访问。 此外可以从导入、 导出到并链接到的表或 HTML 文件中的列表 (\*.html)。

> [!NOTE]
> [!注释] 如果链接到文本文件或 HTML 文件中的数据，则该数据在 Access 中是只读的。 [!注释] 如果数据库不受信任，将不允许此操作。 

## <a name="setting"></a>设置

**ImportExportText** 操作具有下列参数。

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
<td><p><strong>迁移类型</strong></p></td>
<td><p>传输的类型。 您可以从，将数据导出到，导入数据或链接到分隔符或固定宽度的文本文件或 HTML 文件中的数据。 您还可以将数据导出到一个 Microsoft Word 的邮件合并数据文件，它可然后用于 Word 邮件合并功能以创建合并的文档套用信函等邮件标签。 选择<strong>导入分隔符号</strong>、<strong>导入固定宽度</strong>、<strong>导入 HTML</strong>、<strong>导出分隔</strong>、<strong>导出固定的宽度</strong>、<strong>导出 HTML</strong>、<strong>导出 Word for Windows 合并</strong>、<strong>链接分隔</strong>，<strong>链接固定宽度</strong>，或<strong>链接 HTML</strong>宏生成器窗格的<strong>操作参数</strong>部分的<strong>迁移类型</strong>框中。 默认为<strong>导入分隔符号</strong>。</p><p><strong>注意</strong>： 在 Access 项目 (.adp) 支持仅<STRONG>导入分隔符号</STRONG>、<STRONG>导入固定宽度</STRONG>、<STRONG>导出分隔符号</STRONG>、<STRONG>导出固定宽度</STRONG>或<STRONG>导出 Word for Windows 合并</STRONG>传输类型。</p></td>
</tr>
<tr class="even">
<td><p><strong>规格名称</strong></p></td>
<td><p>用于确定文本文件导入或链接方式的选项集的规格名称。对于固定宽度的文本文件，必须指定参数或使用架构文件，该文件必须与导入或链接的文本文件存储在同一个文件夹中。

</p>
<p>要创建文本文件的导入或链接规格，请执行下列操作：</p>
<ol>
<li><p>在<strong>“获取外部数据”</strong>对话框中的<strong>“文件名”</strong>框中输入源文本文件的路径。</p></li>
<li><p>单击所需的用于存储数据的选项（导入、追加或链接），然后单击<strong>“确定”</strong>。</p></li>
<li><p>在<strong>“导入文本向导”</strong>对话框中，单击<strong>“高级”</strong>。</p></li>
<li><p>指定此规格所需的选项，然后单击<strong>“另存为”</strong>。</p></li>
<li><p>输入该规格要使用的名称，然后单击<strong>“确定”</strong>。</p></li>
<li><p>可以通过在规格对话框中单击<strong>“规格”</strong>来管理现有规格。</p></li>
<li><p>单击<strong>“确定”</strong>关闭规格对话框。</p></li>
</ol>
<p></p>
<p>然后，每当要导入或导出同一种文本文件时，可以在此参数中键入规格名称。 可以导入、 导出或链接带分隔符的文本文件，而无需键入规格名称为此参数。 在这种情况下，Access 将使用默认设置，从向导对话框。 访问对邮件合并数据文件中使用预先确定的格式，因此您不需要导出这些类型的文件时，键入此参数的规范名称。 您可以使用 HTML 文件导入/导出规范，但的规范的适用的唯一部分是格式的数据类型的规范。</p></td>
</tr>
<tr class="odd">
<td><p><strong>表名称</strong></p></td>
<td><p>要导入文本数据来，将从，文本数据导出或链接到的文本数据的访问表的名称。 您还可以键入要从中导出数据的访问查询的名称。 这是必需参数。 如果您单击<strong>导入分隔符号</strong>、<strong>导入固定宽度</strong>或<strong>导入 HTML</strong> <strong>迁移类型</strong>框中，访问文本将数据追加到该表表已存在。 否则，Access 将创建一个包含文本数据的新表。 SQL 语句不能用于指定要导出使用<strong>ImportExportText</strong>操作时的数据。 而不是使用的 SQL 语句中，您必须首先创建查询，然后在<strong>表名称</strong>参数中指定的查询的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>文件名</strong></p></td>
<td><p>从导入、 导出到或链接到文本文件的名称。 包括的完整路径。 这是必需参数。 从 Access 导出数据时，access 将创建一个新文本文件。 如果现有文本文件的名称相同的文件名，Access 将替换现有的文本文件。 如果您想要导入或链接的特定表或 HTML 文件中的列表，您可以使用<strong>HTML 表名称</strong>参数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>带有字段名称</strong></p></td>
<td><p>指定文本文件的第一行是否包含字段名称。如果选择<strong>“是”</strong>，则当您导入或链接文本数据时，Access 就会将此行中的名称用作 Access 表中的字段名称。如果选择<strong>“否”</strong>，Access 就会将第一行视为普通的数据行。默认值为<strong>“否”</strong>。 

<br/><br/>由于第一行必须包含字段名称，因此 Access 对 Word for Windows 邮件合并数据文件忽略此参数。 如果您已经为此参数选择了<strong>“是”</strong>，则在您将 Access 表或选择查询导出到带分隔符的文本文件或固定宽度的文本文件中时，Access 会将表或选择查询的字段名称插入到文本文件的第一行中。<br/><br/>如果要导入或链接固定宽度的文本文件，并在此框中选择<strong>“是”</strong>，则包含字段名称的第一行必须使用在导入/导出规格中设置的字段分隔符来分隔字段名称。如果要导出到固定宽度的文本文件中，并为此参数选择<strong>“是”</strong>，Access 就会使用此分隔符将字段名称插入到文本文件的第一行中。</p></td>
</tr>
<tr class="even">
<td><p><strong>HTML 表名称</strong></p></td>
<td><p>您想要导入或链接的 HTML 文件中的列表的表的名称。 除非<strong>传输类型</strong>参数设置为导入 HTML 或链接 HTML，则忽略此参数。 如果将此参数留空，将导入或链接 HTML 文件中的第一个表格或列表。 <br/><br/>HTML 文件中的表或列表的名称由指定的文本&lt;标题&gt;标记中，如果没有，则&lt;标题&gt;标记。 如果没有 &lt;CAPTION&gt; 标记，名称由 &lt;TITLE&gt; 标记指定的文本决定。 如果多个表或列表具有相同名称，访问到的每个名称; 末尾添加一个编号中区分例如，雇员 1 和 Employees2。</p></td>
</tr>
<tr class="odd">
<td><p><strong>代码页</strong></p></td>
<td><p>用于代码页的字符集的名称。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

可以将 Access 选择查询中的数据导出到文本文件中。Access 会导出查询的结果集，就像处理表一样处理它。

追加到现有 Access 表的文本数据必须与表的结构兼容。

- 文本中的每个字段必须与表中的相应字段属于同一字段数据类型。

- 字段必须相同的顺序 （除非将**带有字段名称**参数设置为**是**，在这种情况下该字段的文本中的名称必须匹配表中的字段名称）。

此操作类似于单击 **"外部数据"** 选项卡上的 **"导入"** 或 **"导出"** 组中的 **"文本文件"**。 **ImportExportText** 操作的参数反映由 **"文本文件"** 命令启动的向导中的选项。

> [!TIP]
> [!提示] 导入/导出规格用于存储 Access 导入、导出或链接文本文件所需的信息。您可以使用存储规格将文本数据导入或链接到类似的文本文件，或从类似的文本文件中导出文本数据。例如，您要从主机接收文本文件格式的周销售数据。您可以为这种类型的数据创建并保存一个规格，每次将此数据添加到 Access 数据库中时，都可以使用该规格。

> [!NOTE]
> [!注释] 如果查询或筛选链接的文本文件，则查询或筛选将区分大小写。

若要在 Visual Basic for Applications (VBA) 模块中运行 **ImportExportText** 操作，请使用 **DoCmd** 对象的 **TransferText** 方法。

