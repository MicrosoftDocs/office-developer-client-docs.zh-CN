---
title: ImportExportSpreadsheet 宏操作
TOCTitle: ImportExportSpreadsheet macro action
ms:assetid: 526aef41-8329-5335-9d16-4d332542a297
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193927(v=office.15)
ms:contentKeyID: 48544846
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm31446
f1_categories:
- Office.Version=v15
ms.openlocfilehash: eaab9d43e85ee94c5e71d52399a92515cce94693
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25997131"
---
# <a name="importexportspreadsheet-macro-action"></a>ImportExportSpreadsheet 宏操作

**适用于**： Access 2013、 Office 2013

可以使用 **ImportExportSpreadsheet** 操作在当前的 Microsoft Access 数据库（.mdb 或 .accdb）或 Microsoft Access 项目 (.adp) 与电子表格文件之间导入或导出数据。还可以将 Microsoft Excel 电子表格中的数据链接到当前的 Microsoft Access 数据库。通过链接的电子表格，可以用 Access 查看和编辑电子表格数据，同时仍然可以从 Excel 电子表格程序中对这些数据进行完全访问。还可以链接到 Lotus 1-2-3 电子表格文件中的数据，但这些数据在 Access 中是只读的。

> [!NOTE]
> [!注释] 如果数据库不受信任，将不允许此操作。 

## <a name="setting"></a>设置

**TransferSpreadsheet** 操作具有下列参数。

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
<td><p>要进行的迁移的类型。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“迁移类型”</strong>框中选择<strong>“导入”</strong>、<strong>“导出”</strong>或<strong>“链接”</strong>。默认值为<strong>“导入”</strong>。 

</p><p><strong>注意</strong>： Access 项目 (.adp) 不支持<STRONG>链接</STRONG>传输类型。</p></td>
</tr>
<tr class="even">
<td><p><strong>电子表格类型</strong></p></td>
<td><p>要作为导入来源、导入目标或链接目标的电子表格的类型。可以选择框中多种电子表格类型中的一种。默认值为<strong>“Excel 工作簿”</strong>。</p><p><strong>注意</strong>： 您可以从导入并链接到 Lotus 的 （只读）。WK4 文件，但您无法将 Access 数据导出到电子表格格式。 Access 还不再支持导入、 导出或链接数据从 Lotus。WKS 或与此操作的 Excel 版本 2.0 电子表格。 如果您想要从中导入或链接到在 Excel 2.0 版或 Lotus 中的电子表格数据。WKS 格式、 电子表格数据转换为 Excel 或 Lotus 1-2-3 导入或将数据链接到 Access 前的更高版本。</p>
</td>
</tr>
<tr class="odd">
<td><p><strong>表名称</strong></p></td>
<td><p>要导入电子表格数据来，将从电子表格数据导出或链接到的电子表格数据的访问表的名称。 您还可以键入要从中导出数据的访问选择查询的名称。 这是必需参数。 如果选择<strong>迁移类型</strong>参数中的<strong>导入</strong>，Access 将在电子表格数据表已经存在追加到此表。 否则，Access 将创建一个包含电子表格数据的新表。 在 Access 中，不能使用的 SQL 语句中指定要使用<strong>ImportExportSpreadsheet</strong>操作时导出数据。 而不是使用的 SQL 语句中，您必须首先创建查询，然后在<strong>表名称</strong>参数中指定的查询的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>文件名</strong></p></td>
<td><p>要从导入、 导出到或链接到的电子表格文件的名称。 包括的完整路径。 这是必需参数。 从 Access 导出数据时，access 将创建新的电子表格。 如果现有的电子表格的名称相同的文件名，Access 将替换现有的电子表格，除非您要导出到 Excel 版本 5.0 或更高版本工作簿。 在这种情况下，Access 将导出的数据复制到下一个可用新工作表的工作簿中。 如果要从导入或链接到 Excel 5.0 版或更高版本的电子表格，您可以通过使用<strong>范围</strong>参数指定具体的工作表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>带有字段名称</strong></p></td>
<td><p>指定是否在电子表格的第一行包含的字段的名称。 如果选择<strong>是</strong>，Access 将使用名称此行中为 Access 表中的字段名称导入或链接的电子表格数据时。 如果选择<strong>否</strong>，Access 会将第一行视为普通数据行。 默认值为 <strong>"否"</strong>。 将 Access 表或选择查询导出到电子表格中时，无论您在此参数中做何选择，字段名称都将插入到电子表格的第一行中。</p></td>
</tr>
<tr class="even">
<td><p><strong>区域</strong></p></td>
<td><p>要导入或链接的单元格范围。将此参数留空可以导入或链接整个电子表格。可以键入电子表格内的范围名称或者指定要导入或链接的单元格范围，例如 A1:E25（注意，语法 A1..E25 在 Access 97 或更高版本中无效）。如果您从 Excel 5.0 版或更高版本的电子表格中导入数据或者链接到其中的数据，可以在范围前面附加工作表的名称和感叹号，例如 Budget!A1:C7。 

</p><p><strong>注意</strong>： 导出到电子表格时，您必须将此参数留空。 如果您输入范围，则导出将失败。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

可以将 Access 选择查询中的数据导出到电子表格中。Access 会导出查询的结果集，就像处理表一样处理它。

追加到现有的 Access 表中的电子表格数据必须与该表的结构兼容。

- 电子表格中的每个字段必须与表中的相应字段属于同一字段数据类型。

- 字段必须相同的顺序 （除非将**带有字段名称**参数设置为**是**，在这种情况下字段电子表格中的名称必须匹配表中的字段名称）。

此操作类似于以下两种操作：单击 **"外部数据"** 选项卡，然后单击 **"导入"** 或 **"导出"** 组中的 **"Excel"**；或者单击 **"导入"** 或 **"导出"** 组中的 **"其他"**，然后单击 **"Lotus 1-2-3 文件"**。可以使用这些命令来选择数据源，例如 Access 或一种数据库、电子表格或文本文件。如果选择电子表格，则会出现一系列对话框，或者 Access 向导将运行，在其中可以选择电子表格的名称及其他选项。 **ImportExportSpreadsheet** 操作的参数反映这些对话框或向导中的选项。

> [!NOTE]
> [!注释] 如果对链接电子表格进行查询或筛选，则该查询或筛选将区分大小写。

如果链接到在"编辑"模式下打开的 Excel 电子表格，Access 将一直等待，直到 Excel 电子表格退出"编辑"模式，然后才完成链接；不存在超时。

若要在 Visual Basic for Applications (VBA) 模块中运行 **ImportExportSpreadsheet** 操作，请使用 **DoCmd** 对象的 **TransferSpreadsheet** 方法。

