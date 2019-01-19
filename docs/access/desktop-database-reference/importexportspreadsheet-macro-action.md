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
localization_priority: Priority
ms.openlocfilehash: f910393c6d7a64258e5afc7545641fc5c6778b03
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28726006"
---
# <a name="importexportspreadsheet-macro-action"></a><span data-ttu-id="7c657-102">ImportExportSpreadsheet 宏操作</span><span class="sxs-lookup"><span data-stu-id="7c657-102">ImportExportSpreadsheet macro action</span></span>

<span data-ttu-id="7c657-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="7c657-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7c657-p101">可以使用 **ImportExportSpreadsheet** 操作在当前的 Microsoft Access 数据库（.mdb 或 .accdb）或 Microsoft Access 项目 (.adp) 与电子表格文件之间导入或导出数据。还可以将 Microsoft Excel 电子表格中的数据链接到当前的 Microsoft Access 数据库。通过链接的电子表格，可以用 Access 查看和编辑电子表格数据，同时仍然可以从 Excel 电子表格程序中对这些数据进行完全访问。还可以链接到 Lotus 1-2-3 电子表格文件中的数据，但这些数据在 Access 中是只读的。</span><span class="sxs-lookup"><span data-stu-id="7c657-p101">You can use the **ImportExportSpreadsheet** action to import or export data between the current Access database (.mdb or .accdb) or Access project (.adp) and a spreadsheet file. You can also link the data in a Microsoft Excel spreadsheet to the current Microsoft Access database. With a linked spreadsheet, you can view and edit the spreadsheet data with Access while still allowing complete access to the data from your Excel spreadsheet program. You can also link to data in a Lotus 1-2-3 spreadsheet file, but this data is read-only in Access.</span></span>

> [!NOTE]
> <span data-ttu-id="7c657-108">如果数据库不受信任，则不允许执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7c657-108">This action will not be allowed if the database is not trusted.</span></span> 

## <a name="setting"></a><span data-ttu-id="7c657-109">设置</span><span class="sxs-lookup"><span data-stu-id="7c657-109">Setting</span></span>

<span data-ttu-id="7c657-110">**TransferSpreadsheet** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="7c657-110">The **TransferSpreadsheet** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7c657-111">操作参数</span><span class="sxs-lookup"><span data-stu-id="7c657-111">Action argument</span></span></p></th>
<th><p><span data-ttu-id="7c657-112">说明</span><span class="sxs-lookup"><span data-stu-id="7c657-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c657-113"><strong>迁移类型</strong></span><span class="sxs-lookup"><span data-stu-id="7c657-113"><strong>Transfer Type</strong></span></span></p></td>
<td><p><span data-ttu-id="7c657-p102">要进行的迁移的类型。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“迁移类型”</strong>框中选择<strong>“导入”</strong>、<strong>“导出”</strong>或<strong>“链接”</strong>。默认值为<strong>“导入”</strong>。 

</span><span class="sxs-lookup"><span data-stu-id="7c657-p102">The type of transfer you want to make. Select <strong>Import</strong>, <strong>Export</strong>, or <strong>Link</strong> in the <strong>Transfer Type</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. The default is <strong>Import</strong>.</span></span></p><p><span data-ttu-id="7c657-117"><strong>注释</strong>：Access 项目 (.adp) 不支持 <STRONG>链接</STRONG>迁移类型。</span><span class="sxs-lookup"><span data-stu-id="7c657-117">The <STRONG>Link</STRONG> transfer type is not supported for Access projects (.adp).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c657-118"><strong>电子表格类型</strong></span><span class="sxs-lookup"><span data-stu-id="7c657-118"><strong>Spreadsheet Type</strong></span></span></p></td>
<td><p><span data-ttu-id="7c657-p103">要作为导入来源、导入目标或链接目标的电子表格的类型。可以选择框中多种电子表格类型中的一种。默认值为<strong>“Excel 工作簿”</strong>。</span><span class="sxs-lookup"><span data-stu-id="7c657-p103">The type of spreadsheet to import from, export to, or link to. You can select one of a number of spreadsheet types in the box. The default is <strong>Excel Workbook</strong>.</span></span></p><p><span data-ttu-id="7c657-122"><strong>注释</strong>：可以从 Lotus .WK4 文件导入和链接（只读）至 Lotus .WK4 文件，但不能将 Access 数据导出为此电子表格格式。</span><span class="sxs-lookup"><span data-stu-id="7c657-122"><strong>NOTE</strong>: You can import from and link (read-only) to Lotus .WK4 files, but you can't export Access data to this spreadsheet format.</span></span> <span data-ttu-id="7c657-123">此外，Access 不再支持通过此操作导入、导出或链接 Lotus .WKS 或 Excel 版本 2.0 电子表格中的数据。</span><span class="sxs-lookup"><span data-stu-id="7c657-123">Access also no longer supports importing, exporting, or linking data from Lotus .WKS or Excel version 2.0 spreadsheets with this action.</span></span> <span data-ttu-id="7c657-124">如果想要导入或链接采用 Excel 版本 2.0 或 Lotus .WKS 格式的电子表格数据，请先将电子表格数据转换成更高版本的 Excel 或 Lotus 1-2-3，然后再将数据导入或链接到 Access。</span><span class="sxs-lookup"><span data-stu-id="7c657-124">You can import from and link (read-only) to Lotus .WK4 files, but you can't export Access data to this spreadsheet format. Access also no longer supports importing, exporting, or linking data from Lotus .WKS or Excel version 2.0 spreadsheets with this action. If you want to import from or link to spreadsheet data in Excel version 2.0 or Lotus .WKS format, convert the spreadsheet data to a later version of Excel or Lotus 1-2-3 before importing or linking the data into Access.</span></span></p>
</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c657-125"><strong>表格名称</strong></span><span class="sxs-lookup"><span data-stu-id="7c657-125"><strong>Table Name</strong></span></span></p></td>
<td><p><span data-ttu-id="7c657-126">用于指明所要从中导入、导出或链接电子表格数据的 Access 表的名称。</span><span class="sxs-lookup"><span data-stu-id="7c657-126">The name of the Access table to import spreadsheet data to, export spreadsheet data from, or link spreadsheet data to. You can also type the name of the Access select query you want to export data from. This is a required argument. 

</span></span> <span data-ttu-id="7c657-127">此外，还可以键入 Access 的名称，并选择想要导出其中的数据的查询。</span><span class="sxs-lookup"><span data-stu-id="7c657-127">You can also type the name of the Access select query you want to export data from.</span></span> <span data-ttu-id="7c657-128">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="7c657-128">This is a required argument.</span></span> <span data-ttu-id="7c657-129">在“<strong>迁移类型</strong>”参数中选择“<strong>导入</strong>”时，如果表格已存在，则 Access 会将电子表格数据附加到此表格中。</span><span class="sxs-lookup"><span data-stu-id="7c657-129">If you select <strong>Import</strong> in the <strong>Transfer Type</strong> argument, Access appends the spreadsheet data to this table if the table already exists. Otherwise, Access creates a new table containing the spreadsheet data.</span></span> <span data-ttu-id="7c657-130">否则，Access 将创建一个包含电子表格数据的新表格。</span><span class="sxs-lookup"><span data-stu-id="7c657-130">Otherwise, Access creates a new table containing the spreadsheet data.</span></span> <span data-ttu-id="7c657-131">在 Access 中使用 <strong>ImportExportSpreadsheet</strong> 时，无法使用 SQL 语句指定要导出的数据。</span><span class="sxs-lookup"><span data-stu-id="7c657-131">In Microsoft Access, you can't use a SQL statement to specify data to export when you're using the TransferText action or the TransferSpreadsheet action.</span></span> <span data-ttu-id="7c657-132">必须先创建查询，然后在“<strong>表格名称</strong>”参数中指定查询名称，而不是使用 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="7c657-132">Instead of using a SQL statement, you must first create a query and then specify the name of the query in the Table Name argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c657-133"><strong>文件名</strong></span><span class="sxs-lookup"><span data-stu-id="7c657-133"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="7c657-134">用于指明所要从中导入、导出到或链接到的电子表格的名称。</span><span class="sxs-lookup"><span data-stu-id="7c657-134">The name of the spreadsheet file to import from, export to, or link to. Include the full path. This is a required argument.

</span></span> <span data-ttu-id="7c657-135">包括完整路径。</span><span class="sxs-lookup"><span data-stu-id="7c657-135">Include the full path.</span></span> <span data-ttu-id="7c657-136">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="7c657-136">This is a required argument.</span></span> <span data-ttu-id="7c657-137">从 Access 导出数据时，Access 将会新建一个电子表格。</span><span class="sxs-lookup"><span data-stu-id="7c657-137">Access creates a new spreadsheet when you export data from Access.</span></span> <span data-ttu-id="7c657-138">如果文件名与现有电子表格的名称相同，则 Access 将会替换现有电子表格，除非导出至 Excel 版本 5.0 或更高版本的工作簿。</span><span class="sxs-lookup"><span data-stu-id="7c657-138">Access creates a new spreadsheet when you export data from Access. If the file name is the same as the name of an existing spreadsheet, Access replaces the existing spreadsheet, unless you're exporting to an Excel version 5.0 or later workbook. In that case, Access copies the exported data to the next available new worksheet in the workbook.</span></span> <span data-ttu-id="7c657-139">在此情况下，Access 会将导出的数据复制到工作簿中的下一个可用新工作表中。</span><span class="sxs-lookup"><span data-stu-id="7c657-139">In that case, Access copies the exported data to the next available new worksheet in the workbook.</span></span> <span data-ttu-id="7c657-140">如果导入或链接至 Excel 版本 5.0 或更高版本的电子表格，则可以使用“<strong>范围</strong>”参数指定特定工作表。</span><span class="sxs-lookup"><span data-stu-id="7c657-140">If you are importing from or linking to an Excel version 5.0 or later spreadsheet, you can specify a particular worksheet by using the <strong>Range</strong> argument.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c657-141"><strong>具有字段名称</strong></span><span class="sxs-lookup"><span data-stu-id="7c657-141"><strong>Has Field Names</strong></span></span></p></td>
<td><p><span data-ttu-id="7c657-142">指定电子表格的第一行是否包含字段名称。</span><span class="sxs-lookup"><span data-stu-id="7c657-142">Specifies whether the first row of the spreadsheet contains the names of the fields.</span></span> <span data-ttu-id="7c657-143">如果选择“<strong>是</strong>”，则在导入或链接电子表格数据时，Access 会将此行中的名称用作 Access 表格中的字段名称。</span><span class="sxs-lookup"><span data-stu-id="7c657-143">Specifies whether the first row of the spreadsheet contains the names of the fields. If you select <strong>Yes</strong>, Access uses the names in this row as field names in the Access table when you import or link the spreadsheet data. If you select No, Access treats the first row as a normal row of data. The default is No. 

</span></span> <span data-ttu-id="7c657-144">如果选择“<strong>否</strong>”，则 Access 会将第一行处理为一般的数据行。</span><span class="sxs-lookup"><span data-stu-id="7c657-144">If you select <strong>No</strong>, Access treats the first row as a normal row of data.</span></span> <span data-ttu-id="7c657-145">默认为“<strong>否</strong>”。</span><span class="sxs-lookup"><span data-stu-id="7c657-145">The default is <strong>No</strong>.</span></span> <span data-ttu-id="7c657-146">将 Access 表或选择查询导出到电子表格中时，无论您在此参数中做何选择，字段名称都将插入到电子表格的第一行中。</span><span class="sxs-lookup"><span data-stu-id="7c657-146">When you export an Access table or select query to a spreadsheet, the field names are inserted into the first row of the spreadsheet no matter what you select in this argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c657-147"><strong>范围</strong></span><span class="sxs-lookup"><span data-stu-id="7c657-147"><strong>Range</strong></span></span></p></td>
<td><p><span data-ttu-id="7c657-p108">要导入或链接的单元格范围。将此参数留空可以导入或链接整个电子表格。可以键入电子表格内的范围名称或者指定要导入或链接的单元格范围，例如 A1:E25（注意，语法 A1..E25 在 Access 97 或更高版本中无效）。如果您从 Excel 5.0 版或更高版本的电子表格中导入数据或者链接到其中的数据，可以在范围前面附加工作表的名称和感叹号，例如 Budget!A1:C7。 

</span><span class="sxs-lookup"><span data-stu-id="7c657-p108">The range of cells to import or link. Leave this argument blank to import or link the entire spreadsheet. You can type the name of a range in the spreadsheet or specify the range of cells to import or link, such as A1:E25 (note that the A1..E25 syntax does not work in Access 97 or later). If you are importing from or linking to an Excel version 5.0 or later spreadsheet, you can prefix the range with the name of the worksheet and an exclamation point; for example, Budget!A1:C7.</span></span></p><p><span data-ttu-id="7c657-152"><strong>注释</strong>：如果导出至电子表格，则必须将此参数留空。</span><span class="sxs-lookup"><span data-stu-id="7c657-152">When you export to a spreadsheet, you must leave this argument blank. If you enter a range, the export will fail.</span></span> <span data-ttu-id="7c657-153">如果输入范围，则导出将失败。</span><span class="sxs-lookup"><span data-stu-id="7c657-153">When you export to a spreadsheet, you must leave this argument blank. If you enter a range, the export will fail.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="7c657-154">备注</span><span class="sxs-lookup"><span data-stu-id="7c657-154">Remarks</span></span>

<span data-ttu-id="7c657-p110">可以将 Access 选择查询中的数据导出到电子表格中。Access 会导出查询的结果集，就像处理表一样处理它。</span><span class="sxs-lookup"><span data-stu-id="7c657-p110">You can export the data in Access select queries to spreadsheets. Access exports the result set of the query, treating it just like a table.</span></span>

<span data-ttu-id="7c657-157">追加到现有的 Access 表中的电子表格数据必须与该表的结构兼容。</span><span class="sxs-lookup"><span data-stu-id="7c657-157">Spreadsheet data that you append to an existing Access table must be compatible with the table's structure.</span></span>

- <span data-ttu-id="7c657-158">电子表格中的每个字段必须与表中的相应字段属于同一字段数据类型。</span><span class="sxs-lookup"><span data-stu-id="7c657-158">Each field in the spreadsheet must be of the same data type as the corresponding field in the table.</span></span>

- <span data-ttu-id="7c657-159">字段必须采用相同的顺序（除非将“**具有字段名称**”参数设为“**是**”，在此情况下，电子表格中的字段名称必须与表格中的字段名称匹配）。</span><span class="sxs-lookup"><span data-stu-id="7c657-159">The fields must be in the same order (unless you set the **Has Field Names** argument to **Yes**, in which case the field names in the spreadsheet must match the field names in the table).</span></span>

<span data-ttu-id="7c657-p111">此操作类似于以下两种操作：单击 **"外部数据"** 选项卡，然后单击 **"导入"** 或 **"导出"** 组中的 **"Excel"**；或者单击 **"导入"** 或 **"导出"** 组中的 **"其他"**，然后单击 **"Lotus 1-2-3 文件"**。可以使用这些命令来选择数据源，例如 Access 或一种数据库、电子表格或文本文件。如果选择电子表格，则会出现一系列对话框，或者 Access 向导将运行，在其中可以选择电子表格的名称及其他选项。 **ImportExportSpreadsheet** 操作的参数反映这些对话框或向导中的选项。</span><span class="sxs-lookup"><span data-stu-id="7c657-p111">This action is similar to clicking the **External Data** tab and clicking **Excel** in the **Import** or **Export** group, or clicking **More** in the **Import** or **Export** group and clicking **Lotus 1-2-3 File**. You can use these commands to select a source of data, such as Access or a type of database, spreadsheet, or text file. If you select a spreadsheet, a series of dialog boxes appear, or an Access wizard runs, in which you select the name of the spreadsheet and other options. The arguments of the **ImportExportSpreadsheet** action reflect the options in these dialog boxes or in the wizards.</span></span>

> [!NOTE]
> <span data-ttu-id="7c657-164">[!注释] 如果对链接电子表格进行查询或筛选，则该查询或筛选将区分大小写。</span><span class="sxs-lookup"><span data-stu-id="7c657-164">If you query or filter a linked spreadsheet, the query or filter is case-sensitive.</span></span>

<span data-ttu-id="7c657-165">如果链接到在"编辑"模式下打开的 Excel 电子表格，Access 将一直等待，直到 Excel 电子表格退出"编辑"模式，然后才完成链接；不存在超时。</span><span class="sxs-lookup"><span data-stu-id="7c657-165">If you link to an Excel spreadsheet that is open in Edit mode, Access will wait until the Excel spreadsheet is out of Edit mode before completing the link; there's no time-out.</span></span>

<span data-ttu-id="7c657-166">若要在 Visual Basic for Applications (VBA) 模块中运行 **ImportExportSpreadsheet** 操作，请使用 **DoCmd** 对象的 **TransferSpreadsheet** 方法。</span><span class="sxs-lookup"><span data-stu-id="7c657-166">To run the **ImportExportSpreadsheet** action in a Visual Basic for Applications (VBA) module, use the **TransferSpreadsheet** method of the **DoCmd** object.</span></span>

