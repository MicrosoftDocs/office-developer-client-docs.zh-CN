---
title: ImportExportData 宏操作
TOCTitle: ImportExportData macro action
ms:assetid: 2cbde873-8a3d-b15c-4aab-405cddf44cea
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192107(v=office.15)
ms:contentKeyID: 48543961
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm51789
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: e0cdf85461276d26005bc3066a387031a1086691
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291885"
---
# <a name="importexportdata-macro-action"></a>ImportExportData 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **ImportExportData** 操作在当前 Access 数据库（.mdb 或 .accdb）或 Microsoft Access 项目 (.adp) 与其他数据库之间导入或导出数据。对于 Microsoft Access 数据库，还可以从其他数据库通过链接表与当前 Access 数据库建立关联。通过链接表，在表本身仍位于其他数据库中时可以访问该表中的数据。

> [!NOTE]
> [!注释] 如果数据库不受信任，将不允许此操作。 

## <a name="settings"></a>设置

**ImportExportData** 操作具有下列参数。

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

</p><p><strong>注释</strong>：Access 项目 (.adp) 不支持 <strong>链接</strong>迁移类型。</p></td>
</tr>
<tr class="even">
<td><p><strong>数据库类型</strong></p></td>
<td><p>作为导入来源、导出目标或链接目标的数据库的类型。在<strong>“数据库类型”</strong>框中，可以选择<strong>“Microsoft Access”</strong>或其他众多数据库类型中的某一个。默认值为<strong>“Microsoft Access”</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>数据库名称</strong></p></td>
<td><p>作为导入来源、导出目标或链接目标的数据库的名称。 包括完整路径。 这是必需参数。 对于为每个表使用单独文件的数据库类型，例如 FoxPro、Paradox 和 dBASE，请输入包含文件的目录。 请在“源”<strong></strong>参数（用于导入或链接）或“目标”<strong></strong>参数（用于导出）中输入文件名。 对于 ODBC 数据库, 请键入完整的开放式数据库连接 (ODBC) 连接字符串。</p>
<p>要查看连接字符串的示例，请将外部表链接到 Access：</p>
<ol>
<li><p>在 "<strong>获取外部数据</strong>" 对话框中, 在 "文件名" 框中输入源<strong></strong>数据库的路径。</p></li>
<li><p>单击<strong>“通过创建链接表来链接到数据源”</strong>，然后单击<strong>“确定”</strong>。</p></li>
<li><p>在<strong>“链接表”</strong>对话框中选择表，然后单击<strong>“确定”</strong>。</p></li>
</ol>
<p>在设计视图中打开新链接的表，然后在<strong>“工具”</strong>下的<strong>“设计”</strong>选项卡上单击<strong>“属性表”</strong>，查看表属性。<strong>“说明”</strong>属性设置中的文本是此表的连接字符串。</p>
<p>有关 odbc 连接字符串的详细信息, 请参阅此类 odbc 数据库的 odbc 驱动程序的帮助文件或其他文档。</p></td>
</tr>
<tr class="even">
<td><p><strong>对象类型</strong></p></td>
<td><p>要导入或导出的对象的类型。 如果为“数据库类型”<strong></strong>参数选择了<strong>“Microsoft Access”</strong>，则可以在<strong>“对象类型”</strong>框中选择<strong>“表”</strong>、<strong>“查询”</strong>、<strong>“窗体”</strong>、<strong>“报表”</strong>、<strong>“宏”</strong>、<strong>“模块”</strong>、<strong>“数据访问页”</strong>、<strong>“服务器视图”</strong>、<strong>“图表”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。 默认值为<strong>“表”</strong>。 如果选择任何其他类型的数据库，或者在<strong>“迁移类型”</strong>框中选择<strong>“链接”</strong>，则将忽略此参数。 如果要将选择查询导出到 Access 数据库中，请在此参数中选择<strong>“表”</strong>以导出查询的结果集，然后选择<strong>“查询”</strong>导出查询本身。 如果要将选择查询导出到其他类型的数据库中，则将忽略此参数并导出查询的结果集。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Source</strong></p></td>
<td><p>要导入、导出或链接的表、选择查询或 Access 对象的名称。对于某些类型的数据库（例如 FoxPro、Paradox 或 dBASE）而言，这是文件名。请在文件名中包含文件扩展名（如 .dbf）。这是一个必选参数。</p></td>
</tr>
<tr class="even">
<td><p><strong>目标</strong></p></td>
<td><p>目标数据库中的导入表、导出表或链接表、选择查询或 Access 对象的名称。 对于某些类型的数据库（例如 FoxPro、Paradox 或 dBASE）而言，这是文件名。 请在文件名中包含文件扩展名（如 .dbf）。 这是一个必选参数。 如果在“迁移类型”<strong></strong>参数中选择<strong>“导入”</strong>，并在“对象类型”参数<strong></strong>中选择<strong>“表”</strong>，则 Access 将创建一个包含导入表中的数据的新表。 如果导入的表或其他对象的名称与现有名称冲突，则 Access 将向该名称中添加一个数字。 例如，如果导入 Employees，而 Employees 已经存在，则 Access 会将导入的表或其他对象重命名为 Employees1。 如果导出到 Access 数据库或其他数据库，则 Access 将自动替换任何同名的现有表或其他对象。</p></td>
</tr>
<tr class="odd">
<td><p><strong>仅结构</strong></p></td>
<td><p>指定是否只导入或导出数据库表的结构，而不涉及其中的任何数据。请选择<strong>“是”</strong>或<strong>“否”</strong>。默认值为<strong>“否”</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

可以在 Access 和其他类型数据库之间导入或导出表。还可将 Access 选择查询导出到其他类型的数据库中。Access 可以以表的形式导出查询结果集。如果两个数据库均为 Access 数据库，则在两个数据库之间可以导入或导出所有的 Access 数据库对象。

如果从其他 Access 数据库（.mdb 或 .accdb）中导入表，而且此表是该数据库中的链接表，则此表在被导入后将仍处于链接状态。即导入的是链接而不是表本身。

如果要访问的数据库需要密码，则当您运行宏时将显示一个对话框。请在此对话框中键入密码。

**ImportExportData** 操作类似于 **"外部数据"** 选项卡上的 **"导入"** 或 **"导出"** 下的命令。您可以使用这些命令选择一个数据源，例如 Access 数据库或其他类型的数据库、电子表格或文本文件。如果选择数据库，则将显示一个或多个对话框，您可以在其中根据作为导入来源、导出目标或链接目标的数据库选择要导入或导出的对象类型（针对 Access 数据库）、对象名称以及其他选项。 **ImportExportData** 操作的参数反映这些对话框中的选项。

如果要为链接的 dBASE 表提供索引信息，请先链接该表：

1.  单击 **"dBASE 文件"**。

2.  在 **"获取外部数据"** 对话框中的 **"文件名"** 框中输入 dBASE 文件的路径。

3.  单击 **"通过创建链接表来链接到数据源"**，然后单击 **"确定"**。

4.  在此命令的对话框中指定索引。Access 将索引信息存储到位于 Microsoft Office 文件夹下的一个特殊信息 (.inf) 文件中。

5.  然后，您可以删除指向链接表的链接。

下次使用 **ImportExportData** 操作链接此 dBASE 表时，Access 将使用您指定的索引信息。

> [!NOTE]
> [!注释] 如果查询或筛选链接表，则该查询或筛选将区分大小写。

若要在 Visual Basic for Applications (VBA) 模块中运行 **ImportExportData** 操作，请使用 **DoCmd** 对象的 **TransferDatabase** 方法。

