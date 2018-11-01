---
title: ImportExportData 宏操作
TOCTitle: ImportExportData Macro Action
ms:assetid: 2cbde873-8a3d-b15c-4aab-405cddf44cea
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192107(v=office.15)
ms:contentKeyID: 48543961
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm51789
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 62a496867852afb89d5b556f6be793f3f8c3739e
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25887780"
---
# <a name="importexportdata-macro-action"></a><span data-ttu-id="221fa-102">ImportExportData 宏操作</span><span class="sxs-lookup"><span data-stu-id="221fa-102">ImportExportData Macro Action</span></span>

<span data-ttu-id="221fa-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="221fa-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="221fa-p101">可以使用 **ImportExportData** 操作在当前 Access 数据库（.mdb 或 .accdb）或 Microsoft Access 项目 (.adp) 与其他数据库之间导入或导出数据。对于 Microsoft Access 数据库，还可以从其他数据库通过链接表与当前 Access 数据库建立关联。通过链接表，在表本身仍位于其他数据库中时可以访问该表中的数据。</span><span class="sxs-lookup"><span data-stu-id="221fa-p101">You can use the **ImportExportData** action to import or export data between the current Access database (.mdb or .accdb) or Access project (.adp) and another database. For Microsoft Access databases, you can also link a table to the current Access database from another database. With a linked table, you have access to the table's data while the table itself remains in the other database.</span></span>

> [!NOTE]
> <span data-ttu-id="221fa-p102">[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</span><span class="sxs-lookup"><span data-stu-id="221fa-p102">This action will not be allowed if the database is not trusted. For more information about enabling macros, see the links in the See Also section of this article.</span></span>

## <a name="settings"></a><span data-ttu-id="221fa-109">设置</span><span class="sxs-lookup"><span data-stu-id="221fa-109">Settings</span></span>

<span data-ttu-id="221fa-110">**ImportExportData** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="221fa-110">The **ImportExportData** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="221fa-111">操作参数</span><span class="sxs-lookup"><span data-stu-id="221fa-111">Action argument</span></span></p></th>
<th><p><span data-ttu-id="221fa-112">说明</span><span class="sxs-lookup"><span data-stu-id="221fa-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="221fa-113"><strong>迁移类型</strong></span><span class="sxs-lookup"><span data-stu-id="221fa-113"><strong>Transfer Type</strong></span></span></p></td>
<td><p><span data-ttu-id="221fa-p103">要进行的迁移的类型。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“迁移类型”</strong>框中选择<strong>“导入”</strong>、<strong>“导出”</strong>或<strong>“链接”</strong>。默认值为<strong>“导入”</strong>。 

</span><span class="sxs-lookup"><span data-stu-id="221fa-p103">The type of transfer you want to make. Select <strong>Import</strong>, <strong>Export</strong>, or <strong>Link</strong> in the <strong>Transfer Type</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. The default is <strong>Import</strong>.</span></span></p>

> [!NOTE]
> <span data-ttu-id="221fa-117">Access 项目 (.adp) 不支持 **“链接”** 迁移类型。</span><span class="sxs-lookup"><span data-stu-id="221fa-117">The **Link** transfer type is not supported for Access projects (.adp).</span></span>


<p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="221fa-118"><strong>数据库类型</strong></span><span class="sxs-lookup"><span data-stu-id="221fa-118"><strong>Database Type</strong></span></span></p></td>
<td><p><span data-ttu-id="221fa-p104">作为导入来源、导出目标或链接目标的数据库的类型。在<strong>“数据库类型”</strong>框中，可以选择<strong>“Microsoft Access”</strong>或其他众多数据库类型中的某一个。默认值为<strong>“Microsoft Access”</strong>。</span><span class="sxs-lookup"><span data-stu-id="221fa-p104">The type of database to import from, export to, or link to. You can select <strong>Microsoft Access</strong> or one of a number of other database types in the <strong>Database Type</strong> box. The default is <strong>Microsoft Access</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="221fa-122"><strong>数据库名称</strong></span><span class="sxs-lookup"><span data-stu-id="221fa-122"><strong>Database Name</strong></span></span></p></td>
<td><p><span data-ttu-id="221fa-123">要从导入、 导出到或链接到的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="221fa-123">The name of the database to import from, export to, or link to.</span></span> <span data-ttu-id="221fa-124">包括的完整路径。</span><span class="sxs-lookup"><span data-stu-id="221fa-124">Include the full path.</span></span> <span data-ttu-id="221fa-125">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="221fa-125">This is a required argument.</span></span> <span data-ttu-id="221fa-126">对于类型为每个表，如 FoxPro、 Paradox 和 dBASE，使用单独的文件的数据库的输入包含该文件的目录。</span><span class="sxs-lookup"><span data-stu-id="221fa-126">For types of databases that use separate files for each table, such as FoxPro, Paradox, and dBASE, enter the directory containing the file.</span></span> <span data-ttu-id="221fa-127">在<strong>源</strong>参数 （用于导入或链接） 或<strong>Destination</strong>参数 （用于导出） 中输入文件名。</span><span class="sxs-lookup"><span data-stu-id="221fa-127">Enter the file name in the <strong>Source</strong> argument (to import or link) or the <strong>Destination</strong> argument (to export).</span></span> <span data-ttu-id="221fa-128">对于 ODBC 数据库，请键入完整的开放式数据库连接 (ODBC) 连接字符串。</span><span class="sxs-lookup"><span data-stu-id="221fa-128">For ODBC databases, type the full Open Database Connectivity (ODBC) connection string.</span></span></p>
<p><span data-ttu-id="221fa-129">要查看连接字符串的示例，请将外部表链接到 Access：</span><span class="sxs-lookup"><span data-stu-id="221fa-129">To see an example of a connection string, link an external table to Access:</span></span></p>
<ol>
<li><p><span data-ttu-id="221fa-130">在<strong>获取外部数据</strong>对话框中，输入<strong>文件名</strong>框中将源数据库的路径。</span><span class="sxs-lookup"><span data-stu-id="221fa-130">In the <strong>Get External Data</strong> dialog box, enter the path of your source database in the <strong>File name</strong> box.</span></span></p></li>
<li><p><span data-ttu-id="221fa-131">单击<strong>“通过创建链接表来链接到数据源”</strong>，然后单击<strong>“确定”</strong>。</span><span class="sxs-lookup"><span data-stu-id="221fa-131">Click <strong>Link to the data source by creating a linked table</strong>, and click <strong>OK</strong>.</span></span></p></li>
<li><p><span data-ttu-id="221fa-132">在<strong>“链接表”</strong>对话框中选择表，然后单击<strong>“确定”</strong>。</span><span class="sxs-lookup"><span data-stu-id="221fa-132">Select a table in the <strong>Link Tables</strong> dialog box, and click <strong>OK</strong>.</span></span></p></li>
</ol>
<p><span data-ttu-id="221fa-p106">在设计视图中打开新链接的表，然后在<strong>“工具”</strong>下的<strong>“设计”</strong>选项卡上单击<strong>“属性表”</strong>，查看表属性。<strong>“说明”</strong>属性设置中的文本是此表的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="221fa-p106">Open the newly linked table in Design view and view the table properties by clicking <strong>Property Sheet</strong> on the <strong>Design</strong> tab, under <strong>Tools</strong>. The text in the <strong>Description</strong> property setting is the connection string for this table.</span></span></p>
<p><span data-ttu-id="221fa-135">有关 ODBC 连接字符串的详细信息，请参阅帮助文件或其他文档的这种 ODBC 数据库的 ODBC 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="221fa-135">For more information about ODBC connection strings, see the Help file or other documentation for the ODBC driver of this type of ODBC database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="221fa-136"><strong>对象类型</strong></span><span class="sxs-lookup"><span data-stu-id="221fa-136"><strong>Object Type</strong></span></span></p></td>
<td><p><span data-ttu-id="221fa-137">要导入或导出的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="221fa-137">The type of object to import or export.</span></span> <span data-ttu-id="221fa-138">如果您选择<strong>Microsoft Access</strong> <strong>数据库类型</strong>参数，则可以选择<strong>表</strong>、<strong>查询</strong>、<strong>窗体</strong>、<strong>报表</strong>、<strong>宏</strong>、<strong>模块</strong>、<strong>数据访问页</strong>、<strong>服务器视图</strong>、 <strong>图</strong>，<strong>存储过程</strong>或在<strong>对象类型</strong>框中的<strong>函数</strong>。</span><span class="sxs-lookup"><span data-stu-id="221fa-138">If you select <strong>Microsoft Access</strong> for the <strong>Database Type</strong> argument, you can select <strong>Table</strong>, <strong>Query</strong>, <strong>Form</strong>, <strong>Report</strong>, <strong>Macro</strong>, <strong>Module</strong>, <strong>Data Access Page</strong>, <strong>Server View</strong>, <strong>Diagram</strong>, <strong>Stored Procedure</strong>, or <strong>Function</strong> in the <strong>Object Type</strong> box.</span></span> <span data-ttu-id="221fa-139">默认值是<strong>表</strong>。</span><span class="sxs-lookup"><span data-stu-id="221fa-139">The default is <strong>Table</strong>.</span></span> <span data-ttu-id="221fa-140">如果选择任何其他类型的数据库，或者如果您选择<strong>链接</strong><strong>迁移类型</strong>框中，此参数被忽略。</span><span class="sxs-lookup"><span data-stu-id="221fa-140">If you select any other type of database, or if you select <strong>Link</strong> in the <strong>Transfer Type</strong> box, this argument is ignored.</span></span> <span data-ttu-id="221fa-141">如果将选择查询导出到 Access 数据库，此参数来导出查询的结果集并选择要导出查询本身的<strong>查询</strong>中选择<strong>表</strong>。</span><span class="sxs-lookup"><span data-stu-id="221fa-141">If you are exporting a select query to an Access database, select <strong>Table</strong> in this argument to export the result set of the query, and select <strong>Query</strong> to export the query itself.</span></span> <span data-ttu-id="221fa-142">如果您选择查询导出到其他类型的数据库，则忽略此参数，并导出查询的结果集。</span><span class="sxs-lookup"><span data-stu-id="221fa-142">If you are exporting a select query to another type of database, this argument is ignored and the result set of the query is exported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="221fa-143"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="221fa-143"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="221fa-p108">要导入、导出或链接的表、选择查询或 Access 对象的名称。对于某些类型的数据库（例如 FoxPro、Paradox 或 dBASE）而言，这是文件名。请在文件名中包含文件扩展名（如 .dbf）。这是一个必选参数。</span><span class="sxs-lookup"><span data-stu-id="221fa-p108">The name of the table, select query, or Access object that you want to import, export, or link. For some types of databases, such as FoxPro, Paradox, or dBASE, this is a file name. Include the file name extension (such as .dbf) in the file name. This is a required argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="221fa-148"><strong>Destination</strong></span><span class="sxs-lookup"><span data-stu-id="221fa-148"><strong>Destination</strong></span></span></p></td>
<td><p><span data-ttu-id="221fa-149">导入、 导出，或链接表、 选择查询或目标数据库中的 Access 对象的名称。</span><span class="sxs-lookup"><span data-stu-id="221fa-149">The name of the imported, exported, or linked table, select query, or Access object in the destination database.</span></span> <span data-ttu-id="221fa-150">对于某些类型的数据库，如 FoxPro、 Paradox 或 dBASE，这是一个文件名。</span><span class="sxs-lookup"><span data-stu-id="221fa-150">For some types of databases, such as FoxPro, Paradox, or dBASE, this is a file name.</span></span> <span data-ttu-id="221fa-151">在文件名中包含文件扩展名 （例如.dbf)。</span><span class="sxs-lookup"><span data-stu-id="221fa-151">Include the file name extension (such as .dbf) in the file name.</span></span> <span data-ttu-id="221fa-152">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="221fa-152">This is a required argument.</span></span> <span data-ttu-id="221fa-153">如果选择<strong>导</strong>入的<strong>迁移类型</strong>参数和<strong>表</strong><strong>对象类型</strong>参数中，Access 将创建一个包含导入表中的数据的新表。</span><span class="sxs-lookup"><span data-stu-id="221fa-153">If you select <strong>Import</strong> in the <strong>Transfer Type</strong> argument and <strong>Table</strong> in the <strong>Object Type</strong> argument, Access creates a new table containing the data in the imported table.</span></span> <span data-ttu-id="221fa-154">如果您导入表或其他对象，请访问添加为名称数，如果它与现有的名称冲突。</span><span class="sxs-lookup"><span data-stu-id="221fa-154">If you import a table or other object, Access adds a number to the name if it conflicts with an existing name.</span></span> <span data-ttu-id="221fa-155">例如，如果您导入员工和员工已存在，则重命名访问，导入的表或其他对象雇员 1。</span><span class="sxs-lookup"><span data-stu-id="221fa-155">For example, if you import Employees and Employees already exists, Access renames the imported table or other object Employees1.</span></span> <span data-ttu-id="221fa-156">如果导出到 Access 数据库或其他数据库，则 Access 将自动替换任何同名的现有表或其他对象。</span><span class="sxs-lookup"><span data-stu-id="221fa-156">If you export to an Access database or another database, Access automatically replaces any existing table or other object that has the same name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="221fa-157"><strong>仅结构</strong></span><span class="sxs-lookup"><span data-stu-id="221fa-157"><strong>Structure Only</strong></span></span></p></td>
<td><p><span data-ttu-id="221fa-p110">指定是否只导入或导出数据库表的结构，而不涉及其中的任何数据。请选择<strong>“是”</strong>或<strong>“否”</strong>。默认值为<strong>“否”</strong>。</span><span class="sxs-lookup"><span data-stu-id="221fa-p110">Specifies whether to import or export only the structure of a database table without any of its data. Select <strong>Yes</strong> or <strong>No</strong>. The default is <strong>No</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="221fa-161">说明</span><span class="sxs-lookup"><span data-stu-id="221fa-161">Remarks</span></span>

<span data-ttu-id="221fa-p111">可以在 Access 和其他类型数据库之间导入或导出表。还可将 Access 选择查询导出到其他类型的数据库中。Access 可以以表的形式导出查询结果集。如果两个数据库均为 Access 数据库，则在两个数据库之间可以导入或导出所有的 Access 数据库对象。</span><span class="sxs-lookup"><span data-stu-id="221fa-p111">You can import and export tables between Access and other types of databases. You can also export Access select queries to other types of databases. Access exports the result set of the query in the form of a table. You can import and export any Access database object if both databases are Access databases.</span></span>

<span data-ttu-id="221fa-p112">如果从其他 Access 数据库（.mdb 或 .accdb）中导入表，而且此表是该数据库中的链接表，则此表在被导入后将仍处于链接状态。即导入的是链接而不是表本身。</span><span class="sxs-lookup"><span data-stu-id="221fa-p112">If you import a table from another Access database (.mdb or .accdb) that's a linked table in that database, it will still be linked after you import it. That is, the link is imported, not the table itself.</span></span>

<span data-ttu-id="221fa-p113">如果要访问的数据库需要密码，则当您运行宏时将显示一个对话框。请在此对话框中键入密码。</span><span class="sxs-lookup"><span data-stu-id="221fa-p113">If the database you're accessing requires a password, a dialog box appears when you run the macro. Type the password in this dialog box.</span></span>

<span data-ttu-id="221fa-p114">**ImportExportData** 操作类似于 **"外部数据"** 选项卡上的 **"导入"** 或 **"导出"** 下的命令。您可以使用这些命令选择一个数据源，例如 Access 数据库或其他类型的数据库、电子表格或文本文件。如果选择数据库，则将显示一个或多个对话框，您可以在其中根据作为导入来源、导出目标或链接目标的数据库选择要导入或导出的对象类型（针对 Access 数据库）、对象名称以及其他选项。 **ImportExportData** 操作的参数反映这些对话框中的选项。</span><span class="sxs-lookup"><span data-stu-id="221fa-p114">The **ImportExportData** action is similar to the commands on the **External Data** tab, under **Import** or **Export**. You can use these commands to select a source of data, such as an Access database or another type of database, a spreadsheet, or a text file. If you select a database, one or more dialog boxes appear in which you select the type of object to import or export (for Access databases), the name of the object, and other options, depending on the database you are importing from or exporting or linking to. The arguments for the **ImportExportData** action reflect the options in these dialog boxes.</span></span>

<span data-ttu-id="221fa-174">如果要为链接的 dBASE 表提供索引信息，请先链接该表：</span><span class="sxs-lookup"><span data-stu-id="221fa-174">If you want to supply index information for a linked dBASE table, first link the table:</span></span>

1.  <span data-ttu-id="221fa-175">单击 **"dBASE 文件"**。</span><span class="sxs-lookup"><span data-stu-id="221fa-175">Click **dBASE File**.</span></span>

2.  <span data-ttu-id="221fa-176">在 **"获取外部数据"** 对话框中的 **"文件名"** 框中输入 dBASE 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="221fa-176">In the **Get External Data** dialog box, enter the path for the dBASE file in the **File name** box.</span></span>

3.  <span data-ttu-id="221fa-177">单击 **"通过创建链接表来链接到数据源"**，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="221fa-177">Click **Link to the data source by creating a linked table**, then click **OK**.</span></span>

4.  <span data-ttu-id="221fa-p115">在此命令的对话框中指定索引。Access 将索引信息存储到位于 Microsoft Office 文件夹下的一个特殊信息 (.inf) 文件中。</span><span class="sxs-lookup"><span data-stu-id="221fa-p115">Specify the indexes in the dialog boxes for this command. Access stores the index information in a special information (.inf) file, located in the Microsoft Office folder.</span></span>

5.  <span data-ttu-id="221fa-180">然后，您可以删除指向链接表的链接。</span><span class="sxs-lookup"><span data-stu-id="221fa-180">You can then delete the link to the linked table.</span></span>

<span data-ttu-id="221fa-181">下次使用 **ImportExportData** 操作链接此 dBASE 表时，Access 将使用您指定的索引信息。</span><span class="sxs-lookup"><span data-stu-id="221fa-181">The next time you use the **ImportExportData** action to link this dBASE table, Access uses the index information that you've specified.</span></span>

> [!NOTE]
> <span data-ttu-id="221fa-182">[!注释] 如果查询或筛选链接表，则该查询或筛选将区分大小写。</span><span class="sxs-lookup"><span data-stu-id="221fa-182">If you query or filter a linked table, the query or filter is case-sensitive.</span></span>

<span data-ttu-id="221fa-183">若要在 Visual Basic for Applications (VBA) 模块中运行 **ImportExportData** 操作，请使用 **DoCmd** 对象的 **TransferDatabase** 方法。</span><span class="sxs-lookup"><span data-stu-id="221fa-183">To run the **ImportExportData** action in a Visual Basic for Applications (VBA) module, use the **TransferDatabase** method of the **DoCmd** object.</span></span>

