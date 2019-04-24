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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291864"
---
# <a name="importexporttext-macro-action"></a>ImportExportText 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **ImportExportText** 操作在当前 Microsoft Access 数据库（.mdb 或 .accdb）或 Microsoft Access 项目 (.adp) 与文本文件之间导入或导出文本。 还可以将文本文件中的数据链接到当前的 Access 数据库。 使用链接的文本文件，您可以通过 Access 查看文本数据，同时仍然可从字处理程序中对这些数据进行完全访问。 您还可以在 html 文件 (\*.html) 中导入、导出到和链接到表或列表。

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
<td><p>传输的类型。 对带分隔符的文本文件或固定宽度的文本文件或 HTML 文件中的数据可以进行导入、导出或链接操作。 还可以将数据导出到 Microsoft Word 邮件合并数据文件中，随后结合使用 Word 邮件合并功能来创建合并文档，例如套用信函和邮件标签。 请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“迁移类型”</strong>框中选择<strong>“导入分隔符号”</strong>、<strong>“导入固定宽度”</strong>、<strong>“导入 HTML”</strong>、<strong>“导出分隔符号”</strong>、<strong>“导出固定宽度”</strong>、<strong>“导出 HTML”</strong>、<strong>“导出 Word for Windows 合并文件”</strong>、<strong>“链接分隔符号”</strong>、<strong>“链接固定宽度”</strong>或<strong>“链接 HTML”</strong>。 默认值为<strong>“导入分隔符号”</strong>。</p><p><strong>注意</strong>: Access 项目 (.adp) 仅支持 "<STRONG>导入</STRONG>"、"<STRONG>导入固定宽度</STRONG>"、"<STRONG>导出分隔符</STRONG>"、"导出<STRONG>固定宽度</STRONG>" 或 "<STRONG>导出 Word for Windows Merge</STRONG> " 传输类型。</p></td>
</tr>
<tr class="even">
<td><p><strong>规格名称</strong></p></td>
<td><p>用于确定文本文件导入或链接方式的选项集的规格名称。 对于固定宽度的文本文件，必须指定参数或使用架构文件，该文件必须与导入或链接的文本文件存储在同一个文件夹中。</p>
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
<p>然后，每当要导入或导出同一种文本文件时，可以在此参数中键入规格名称。 可以导入、导出或链接带分隔符的文本文件，而无需为此参数键入规格名称。 在这种情况下，Access 使用向导对话框中的默认设置。 Access 对邮件合并数据文件使用预先确定的格式，因此您在导出这些类型的文件时无需为此参数键入规格名称。 您可以将导入/导出规格用于 HTML 文件，但只应用有关数据类型格式的规格部分。</p></td>
</tr>
<tr class="odd">
<td><p><strong>表名称</strong></p></td>
<td><p>作为文本数据导入目标、导出来源或链接目标的 Access 表的名称。 还可以键入要从中导出数据的 Access 查询的名称。 这是一个必选参数。 如果在<strong>“迁移类型”</strong>框中单击<strong>“导入分隔符号”</strong>、<strong>“导入固定宽度”</strong>或<strong>“导入 HTML”</strong>，Access 会将文本数据追加到该表（如果该表已经存在）。 否则，Access 将创建一个包含文本数据的新表。 在使用<strong>ImportExportText</strong>操作时, 不能使用 SQL 语句指定要导出的数据。 必须先创建查询，然后在“<strong>表格名称</strong>”参数中指定查询名称，而不是使用 SQL 语句。</p></td>
</tr>
<tr class="even">
<td><p><strong>文件名</strong></p></td>
<td><p>作为导入来源、导出目标或链接目标的文本文件的名称。 包括完整路径。 这是必需参数。 从 Access 中导出数据时，Access 将创建一个新的文本文件。 如果该文件名与现有文本文件的名称相同，Access 将替换现有的文本文件。 如果要导入或链接 HTML 文件中的某个特定的表或列表，可以使用“HTML 表名称”<strong></strong>参数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>带有字段名称</strong></p></td>
<td><p>指定文本文件的第一行是否包含字段名称。 如果选择<strong>“是”</strong>，则当您导入或链接文本数据时，Access 就会将此行中的名称用作 Access 表中的字段名称。 如果选择<strong>“否”</strong>，Access 就会将第一行视为普通的数据行。 默认值为<strong>“否”</strong>。<br/><br/>由于第一行必须包含字段名称，因此 Access 对 Word for Windows 邮件合并数据文件忽略此参数。 如果您已经为此参数选择了<strong>“是”</strong>，则在您将 Access 表或选择查询导出到带分隔符的文本文件或固定宽度的文本文件中时，Access 会将表或选择查询的字段名称插入到文本文件的第一行中。<br/><br/>如果要导入或链接固定宽度的文本文件，并在此框中选择<strong>“是”</strong>，则包含字段名称的第一行必须使用在导入/导出规格中设置的字段分隔符来分隔字段名称。如果要导出到固定宽度的文本文件中，并为此参数选择<strong>“是”</strong>，Access 就会使用此分隔符将字段名称插入到文本文件的第一行中。</p></td>
</tr>
<tr class="even">
<td><p><strong>HTML 表名称</strong></p></td>
<td><p>要导入或链接的 HTML 文件中的表或列表的名称。 除非将“迁移类型”<strong></strong>参数设置为“导入 HTML”或“链接 HTML”，否则将忽略此参数。 如果将此参数留空，则将导入或链接 HTML 文件中的第一个表或列表。 <br/><br/>HTML 文件中的表格或列表名称&lt;由题注&gt;标签指定的文字 (如果有&lt;题注&gt;标签) 决定。 如果没有 &lt;CAPTION&gt; 标记，名称由 &lt;TITLE&gt; 标记指定的文本决定。 如果多个表或列表具有同一名称，Access 将通过向每个名称的未尾添加一个数字来对它们加以区分，例如 Employees1 和 Employees2。</p></td>
</tr>
<tr class="odd">
<td><p><strong>代码页</strong></p></td>
<td><p>用于代码页的字符集的名称。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

可以将 Access 选择查询中的数据导出到文本文件中。Access 会导出查询的结果集，就像处理表一样处理它。

追加到现有 Access 表的文本数据必须与表的结构兼容。

- 文本中的每个字段必须与表中的相应字段属于同一字段数据类型。

- The fields must be in the same order (unless you set the **Has Field Names** argument to **Yes**, in which case the field names in the text must match the field names in the table).

此操作类似于单击 **"外部数据"** 选项卡上的 **"导入"** 或 **"导出"** 组中的 **"文本文件"**。 **ImportExportText** 操作的参数反映由 **"文本文件"** 命令启动的向导中的选项。

> [!TIP]
> [!提示] 导入/导出规格用于存储 Access 导入、导出或链接文本文件所需的信息。您可以使用存储规格将文本数据导入或链接到类似的文本文件，或从类似的文本文件中导出文本数据。例如，您要从主机接收文本文件格式的周销售数据。您可以为这种类型的数据创建并保存一个规格，每次将此数据添加到 Access 数据库中时，都可以使用该规格。

> [!NOTE]
> [!注释] 如果查询或筛选链接的文本文件，则查询或筛选将区分大小写。

若要在 Visual Basic for Applications (VBA) 模块中运行 **ImportExportText** 操作，请使用 **DoCmd** 对象的 **TransferText** 方法。

