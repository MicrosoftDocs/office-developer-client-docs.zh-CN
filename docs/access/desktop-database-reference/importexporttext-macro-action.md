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
# <a name="importexporttext-macro-action"></a><span data-ttu-id="ce790-102">ImportExportText 宏操作</span><span class="sxs-lookup"><span data-stu-id="ce790-102">ImportExportText macro action</span></span>

<span data-ttu-id="ce790-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="ce790-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ce790-104">可以使用 **ImportExportText** 操作在当前 Microsoft Access 数据库（.mdb 或 .accdb）或 Microsoft Access 项目 (.adp) 与文本文件之间导入或导出文本。</span><span class="sxs-lookup"><span data-stu-id="ce790-104">You can use the **ImportExportText** action to import or export text between the current Microsoft Access database (.mdb or .accdb) or Access project (.adp) and a text file.</span></span> <span data-ttu-id="ce790-105">还可以将文本文件中的数据链接到当前的 Access 数据库。</span><span class="sxs-lookup"><span data-stu-id="ce790-105">You can also link the data in a text file to the current Access database.</span></span> <span data-ttu-id="ce790-106">使用链接的文本文件，您可以通过 Access 查看文本数据，同时仍然可从字处理程序中对这些数据进行完全访问。</span><span class="sxs-lookup"><span data-stu-id="ce790-106">With a linked text file, you can view the text data with Access while still allowing complete access to the data from your word processing program.</span></span> <span data-ttu-id="ce790-107">您还可以在 html 文件 (\*.html) 中导入、导出到和链接到表或列表。</span><span class="sxs-lookup"><span data-stu-id="ce790-107">You can also import from, export to, and link to a table or list in an HTML file (\*.html).</span></span>

> [!NOTE]
> <span data-ttu-id="ce790-108">[!注释] 如果链接到文本文件或 HTML 文件中的数据，则该数据在 Access 中是只读的。</span><span class="sxs-lookup"><span data-stu-id="ce790-108">If you link to data in a text file or an HTML file, the data is read-only in Access.</span></span> <span data-ttu-id="ce790-109">[!注释] 如果数据库不受信任，将不允许此操作。</span><span class="sxs-lookup"><span data-stu-id="ce790-109">This action will not be allowed if the database is not trusted.</span></span> 

## <a name="setting"></a><span data-ttu-id="ce790-110">设置</span><span class="sxs-lookup"><span data-stu-id="ce790-110">Setting</span></span>

<span data-ttu-id="ce790-111">**ImportExportText** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="ce790-111">The **ImportExportText** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ce790-112">操作参数</span><span class="sxs-lookup"><span data-stu-id="ce790-112">Action argument</span></span></p></th>
<th><p><span data-ttu-id="ce790-113">说明</span><span class="sxs-lookup"><span data-stu-id="ce790-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce790-114"><strong>迁移类型</strong></span><span class="sxs-lookup"><span data-stu-id="ce790-114"><strong>Transfer Type</strong></span></span></p></td>
<td><p><span data-ttu-id="ce790-115">传输的类型。</span><span class="sxs-lookup"><span data-stu-id="ce790-115">The type of transfer you want to make.</span></span> <span data-ttu-id="ce790-116">对带分隔符的文本文件或固定宽度的文本文件或 HTML 文件中的数据可以进行导入、导出或链接操作。</span><span class="sxs-lookup"><span data-stu-id="ce790-116">You can import data from, export data to, or link to data in delimited or fixed-width text files or HTML files.</span></span> <span data-ttu-id="ce790-117">还可以将数据导出到 Microsoft Word 邮件合并数据文件中，随后结合使用 Word 邮件合并功能来创建合并文档，例如套用信函和邮件标签。</span><span class="sxs-lookup"><span data-stu-id="ce790-117">You can also export data to a Microsoft Word mail merge data file, which you can then use with the Word mail merge feature to create merged documents such as form letters and mailing labels.</span></span> <span data-ttu-id="ce790-118">请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“迁移类型”</strong>框中选择<strong>“导入分隔符号”</strong>、<strong>“导入固定宽度”</strong>、<strong>“导入 HTML”</strong>、<strong>“导出分隔符号”</strong>、<strong>“导出固定宽度”</strong>、<strong>“导出 HTML”</strong>、<strong>“导出 Word for Windows 合并文件”</strong>、<strong>“链接分隔符号”</strong>、<strong>“链接固定宽度”</strong>或<strong>“链接 HTML”</strong>。</span><span class="sxs-lookup"><span data-stu-id="ce790-118">Select <strong>Import Delimited</strong>, <strong>Import Fixed Width</strong>, <strong>Import HTML</strong>, <strong>Export Delimited</strong>, <strong>Export Fixed Width</strong>, <strong>Export HTML</strong>, <strong>Export Word for Windows Merge</strong>, <strong>Link Delimited</strong>, <strong>Link Fixed Width</strong>, or <strong>Link HTML</strong> in the <strong>Transfer Type</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane.</span></span> <span data-ttu-id="ce790-119">默认值为<strong>“导入分隔符号”</strong>。</span><span class="sxs-lookup"><span data-stu-id="ce790-119">The default is <strong>Import Delimited</strong>.</span></span></p><p><span data-ttu-id="ce790-120"><strong>注意</strong>: Access 项目 (.adp) 仅支持 "<STRONG>导入</STRONG>"、"<STRONG>导入固定宽度</STRONG>"、"<STRONG>导出分隔符</STRONG>"、"导出<STRONG>固定宽度</STRONG>" 或 "<STRONG>导出 Word for Windows Merge</STRONG> " 传输类型。</span><span class="sxs-lookup"><span data-stu-id="ce790-120"><strong>NOTE</strong>: Only <STRONG>Import Delimited</STRONG>, <STRONG>Import Fixed Width</STRONG>, <STRONG>Export Delimited</STRONG>, <STRONG>Export Fixed Width</STRONG>, or <STRONG>Export Word for Windows Merge</STRONG> transfer types are supported in an Access project (.adp).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce790-121"><strong>规格名称</strong></span><span class="sxs-lookup"><span data-stu-id="ce790-121"><strong>Specification Name</strong></span></span></p></td>
<td><p><span data-ttu-id="ce790-122">用于确定文本文件导入或链接方式的选项集的规格名称。</span><span class="sxs-lookup"><span data-stu-id="ce790-122">The specification name for the set of options that determines how a text file is imported or linked.</span></span> <span data-ttu-id="ce790-123">对于固定宽度的文本文件，必须指定参数或使用架构文件，该文件必须与导入或链接的文本文件存储在同一个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ce790-123">For a fixed-width text file, you must either specify an argument or use a schema.ini file, which must be stored in the same folder as the imported or linked text file.</span></span></p>
<p><span data-ttu-id="ce790-124">要创建文本文件的导入或链接规格，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ce790-124">To create a specification for importing or linking a text file:</span></span></p>
<ol>
<li><p><span data-ttu-id="ce790-125">在<strong>“获取外部数据”</strong>对话框中的<strong>“文件名”</strong>框中输入源文本文件的路径。</span><span class="sxs-lookup"><span data-stu-id="ce790-125">In the <strong>Get External Data</strong> dialog box, enter the path of the source text file in the <strong>File name</strong> box.</span></span></p></li>
<li><p><span data-ttu-id="ce790-126">单击所需的用于存储数据的选项（导入、追加或链接），然后单击<strong>“确定”</strong>。</span><span class="sxs-lookup"><span data-stu-id="ce790-126">Click the option you want for storing the data (import, append, or link), and click <strong>OK</strong>.</span></span></p></li>
<li><p><span data-ttu-id="ce790-127">在<strong>“导入文本向导”</strong>对话框中，单击<strong>“高级”</strong>。</span><span class="sxs-lookup"><span data-stu-id="ce790-127">In the <strong>Import Text Wizard</strong> dialog box, click <strong>Advanced</strong>.</span></span></p></li>
<li><p><span data-ttu-id="ce790-128">指定此规格所需的选项，然后单击<strong>“另存为”</strong>。</span><span class="sxs-lookup"><span data-stu-id="ce790-128">Specify the options you want for this specification, then click <strong>Save As</strong>.</span></span></p></li>
<li><p><span data-ttu-id="ce790-129">输入该规格要使用的名称，然后单击<strong>“确定”</strong>。</span><span class="sxs-lookup"><span data-stu-id="ce790-129">Enter the name you want for the specification, then click <strong>OK</strong>.</span></span></p></li>
<li><p><span data-ttu-id="ce790-130">可以通过在规格对话框中单击<strong>“规格”</strong>来管理现有规格。</span><span class="sxs-lookup"><span data-stu-id="ce790-130">You can manage existing specifications by clicking <strong>Specs</strong> in the specification dialog box.</span></span></p></li>
<li><p><span data-ttu-id="ce790-131">单击<strong>“确定”</strong>关闭规格对话框。</span><span class="sxs-lookup"><span data-stu-id="ce790-131">Click <strong>OK</strong> to close the specification dialog box.</span></span></p></li>
</ol>
<p></p>
<p><span data-ttu-id="ce790-132">然后，每当要导入或导出同一种文本文件时，可以在此参数中键入规格名称。</span><span class="sxs-lookup"><span data-stu-id="ce790-132">You can then type the specification name in this argument whenever you want to import or export the same type of text file.</span></span> <span data-ttu-id="ce790-133">可以导入、导出或链接带分隔符的文本文件，而无需为此参数键入规格名称。</span><span class="sxs-lookup"><span data-stu-id="ce790-133">You can import, export, or link delimited text files without typing a specification name for this argument.</span></span> <span data-ttu-id="ce790-134">在这种情况下，Access 使用向导对话框中的默认设置。</span><span class="sxs-lookup"><span data-stu-id="ce790-134">In this case, Access uses the defaults from the wizard dialog box.</span></span> <span data-ttu-id="ce790-135">Access 对邮件合并数据文件使用预先确定的格式，因此您在导出这些类型的文件时无需为此参数键入规格名称。</span><span class="sxs-lookup"><span data-stu-id="ce790-135">Access uses a predetermined format for mail merge data files, so you don't ever need to type a specification name for this argument when you export these types of files.</span></span> <span data-ttu-id="ce790-136">您可以将导入/导出规格用于 HTML 文件，但只应用有关数据类型格式的规格部分。</span><span class="sxs-lookup"><span data-stu-id="ce790-136">You can use import/export specifications with HTML files, but the only part of the specification that applies is the specification for data type formatting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce790-137"><strong>表名称</strong></span><span class="sxs-lookup"><span data-stu-id="ce790-137"><strong>Table Name</strong></span></span></p></td>
<td><p><span data-ttu-id="ce790-138">作为文本数据导入目标、导出来源或链接目标的 Access 表的名称。</span><span class="sxs-lookup"><span data-stu-id="ce790-138">The name of the Access table to import text data to, export text data from, or link text data to.</span></span> <span data-ttu-id="ce790-139">还可以键入要从中导出数据的 Access 查询的名称。</span><span class="sxs-lookup"><span data-stu-id="ce790-139">You can also type the name of the Access query you want to export data from.</span></span> <span data-ttu-id="ce790-140">这是一个必选参数。</span><span class="sxs-lookup"><span data-stu-id="ce790-140">This is a required argument.</span></span> <span data-ttu-id="ce790-141">如果在<strong>“迁移类型”</strong>框中单击<strong>“导入分隔符号”</strong>、<strong>“导入固定宽度”</strong>或<strong>“导入 HTML”</strong>，Access 会将文本数据追加到该表（如果该表已经存在）。</span><span class="sxs-lookup"><span data-stu-id="ce790-141">If you click <strong>Import Delimited</strong>, <strong>Import Fixed Width</strong>, or <strong>Import HTML</strong> in the <strong>Transfer Type</strong> box, Access appends the text data to this table if the table already exists.</span></span> <span data-ttu-id="ce790-142">否则，Access 将创建一个包含文本数据的新表。</span><span class="sxs-lookup"><span data-stu-id="ce790-142">Otherwise, Access creates a new table containing the text data.</span></span> <span data-ttu-id="ce790-143">在使用<strong>ImportExportText</strong>操作时, 不能使用 SQL 语句指定要导出的数据。</span><span class="sxs-lookup"><span data-stu-id="ce790-143">You can't use an SQL statement to specify data to export when you are using the <strong>ImportExportText</strong> action.</span></span> <span data-ttu-id="ce790-144">必须先创建查询，然后在“<strong>表格名称</strong>”参数中指定查询名称，而不是使用 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="ce790-144">Instead of using an SQL statement, you must first create a query and then specify the name of the query in the <strong>Table Name</strong> argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce790-145"><strong>文件名</strong></span><span class="sxs-lookup"><span data-stu-id="ce790-145"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="ce790-146">作为导入来源、导出目标或链接目标的文本文件的名称。</span><span class="sxs-lookup"><span data-stu-id="ce790-146">The name of the text file to import from, export to, or link to.</span></span> <span data-ttu-id="ce790-147">包括完整路径。</span><span class="sxs-lookup"><span data-stu-id="ce790-147">Include the full path.</span></span> <span data-ttu-id="ce790-148">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="ce790-148">This is a required argument.</span></span> <span data-ttu-id="ce790-149">从 Access 中导出数据时，Access 将创建一个新的文本文件。</span><span class="sxs-lookup"><span data-stu-id="ce790-149">Access creates a new text file when you export data from Access.</span></span> <span data-ttu-id="ce790-150">如果该文件名与现有文本文件的名称相同，Access 将替换现有的文本文件。</span><span class="sxs-lookup"><span data-stu-id="ce790-150">If the file name is the same as the name of an existing text file, Access replaces the existing text file.</span></span> <span data-ttu-id="ce790-151">如果要导入或链接 HTML 文件中的某个特定的表或列表，可以使用“HTML 表名称”<strong></strong>参数。</span><span class="sxs-lookup"><span data-stu-id="ce790-151">If you want to import or link a particular table or list in an HTML file, you can use the <strong>HTML Table Name</strong> argument.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce790-152"><strong>带有字段名称</strong></span><span class="sxs-lookup"><span data-stu-id="ce790-152"><strong>Has Field Names</strong></span></span></p></td>
<td><p><span data-ttu-id="ce790-153">指定文本文件的第一行是否包含字段名称。</span><span class="sxs-lookup"><span data-stu-id="ce790-153">Specifies whether the first row of the text file contains the names of the fields.</span></span> <span data-ttu-id="ce790-154">如果选择<strong>“是”</strong>，则当您导入或链接文本数据时，Access 就会将此行中的名称用作 Access 表中的字段名称。</span><span class="sxs-lookup"><span data-stu-id="ce790-154">If you select <strong>Yes</strong>, Access uses the names in this row as field names in the Access table when you import or link the text data.</span></span> <span data-ttu-id="ce790-155">如果选择<strong>“否”</strong>，Access 就会将第一行视为普通的数据行。</span><span class="sxs-lookup"><span data-stu-id="ce790-155">If you select <strong>No</strong>, Access treats the first row as a normal row of data.</span></span> <span data-ttu-id="ce790-156">默认值为<strong>“否”</strong>。</span><span class="sxs-lookup"><span data-stu-id="ce790-156">The default is <strong>No</strong>.</span></span><br/><br/><span data-ttu-id="ce790-157">由于第一行必须包含字段名称，因此 Access 对 Word for Windows 邮件合并数据文件忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="ce790-157">Access ignores this argument for Word for Windows mail merge data files because the first row must contain the field names.</span></span> <span data-ttu-id="ce790-158">如果您已经为此参数选择了<strong>“是”</strong>，则在您将 Access 表或选择查询导出到带分隔符的文本文件或固定宽度的文本文件中时，Access 会将表或选择查询的字段名称插入到文本文件的第一行中。</span><span class="sxs-lookup"><span data-stu-id="ce790-158">When you export an Access table or select query to a delimited or fixed-width text file, Access inserts the field names of your table or select query into the first row of the text file if you've selected <strong>Yes</strong> for this argument.</span></span><br/><br/><span data-ttu-id="ce790-p110">如果要导入或链接固定宽度的文本文件，并在此框中选择<strong>“是”</strong>，则包含字段名称的第一行必须使用在导入/导出规格中设置的字段分隔符来分隔字段名称。如果要导出到固定宽度的文本文件中，并为此参数选择<strong>“是”</strong>，Access 就会使用此分隔符将字段名称插入到文本文件的第一行中。</span><span class="sxs-lookup"><span data-stu-id="ce790-p110">If you are importing or linking a fixed-width text file and select <strong>Yes</strong> in this box, the first row containing the field names must use the field delimiter set in the import/export specification to separate the field names. If you are exporting to a fixed-width text file and select <strong>Yes</strong> for this argument, Access inserts the field names into the first row of the text file with this delimiter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce790-161"><strong>HTML 表名称</strong></span><span class="sxs-lookup"><span data-stu-id="ce790-161"><strong>HTML Table Name</strong></span></span></p></td>
<td><p><span data-ttu-id="ce790-162">要导入或链接的 HTML 文件中的表或列表的名称。</span><span class="sxs-lookup"><span data-stu-id="ce790-162">The name of the table or list in the HTML file that you want to import or link.</span></span> <span data-ttu-id="ce790-163">除非将“迁移类型”<strong></strong>参数设置为“导入 HTML”或“链接 HTML”，否则将忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="ce790-163">This argument is ignored unless the <strong>Transfer Type</strong> argument is set to Import HTML or Link HTML.</span></span> <span data-ttu-id="ce790-164">如果将此参数留空，则将导入或链接 HTML 文件中的第一个表或列表。</span><span class="sxs-lookup"><span data-stu-id="ce790-164">If you leave this argument blank, the first table or list in the HTML file is imported or linked.</span></span> <br/><br/><span data-ttu-id="ce790-165">HTML 文件中的表格或列表名称&lt;由题注&gt;标签指定的文字 (如果有&lt;题注&gt;标签) 决定。</span><span class="sxs-lookup"><span data-stu-id="ce790-165">The table or list name in the HTML file is determined by the text specified by the &lt;CAPTION&gt; tag, if there's a &lt;CAPTION&gt; tag.</span></span> <span data-ttu-id="ce790-166">如果没有 &lt;CAPTION&gt; 标记，名称由 &lt;TITLE&gt; 标记指定的文本决定。</span><span class="sxs-lookup"><span data-stu-id="ce790-166">If there's no &lt;CAPTION&gt; tag, the name is determined by the text specified by the &lt;TITLE&gt; tag.</span></span> <span data-ttu-id="ce790-167">如果多个表或列表具有同一名称，Access 将通过向每个名称的未尾添加一个数字来对它们加以区分，例如 Employees1 和 Employees2。</span><span class="sxs-lookup"><span data-stu-id="ce790-167">If more than one table or list has the same name, Access distinguishes them by adding a number to the end of each name; for example, Employees1 and Employees2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce790-168"><strong>代码页</strong></span><span class="sxs-lookup"><span data-stu-id="ce790-168"><strong>Code Page</strong></span></span></p></td>
<td><p><span data-ttu-id="ce790-169">用于代码页的字符集的名称。</span><span class="sxs-lookup"><span data-stu-id="ce790-169">The name of the character set used with the code page.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="ce790-170">注解</span><span class="sxs-lookup"><span data-stu-id="ce790-170">Remarks</span></span>

<span data-ttu-id="ce790-p113">可以将 Access 选择查询中的数据导出到文本文件中。Access 会导出查询的结果集，就像处理表一样处理它。</span><span class="sxs-lookup"><span data-stu-id="ce790-p113">You can export the data in Access select queries to text files. Access exports the result set of the query, treating it just like a table.</span></span>

<span data-ttu-id="ce790-173">追加到现有 Access 表的文本数据必须与表的结构兼容。</span><span class="sxs-lookup"><span data-stu-id="ce790-173">Text data that you append to an existing Access table must be compatible with the table's structure.</span></span>

- <span data-ttu-id="ce790-174">文本中的每个字段必须与表中的相应字段属于同一字段数据类型。</span><span class="sxs-lookup"><span data-stu-id="ce790-174">Each field in the text must be of the same data type as the corresponding field in the table.</span></span>

- <span data-ttu-id="ce790-175">The fields must be in the same order (unless you set the **Has Field Names** argument to **Yes**, in which case the field names in the text must match the field names in the table).</span><span class="sxs-lookup"><span data-stu-id="ce790-175">The fields must be in the same order (unless you set the **Has Field Names** argument to **Yes**, in which case the field names in the text must match the field names in the table).</span></span>

<span data-ttu-id="ce790-176">此操作类似于单击 **"外部数据"** 选项卡上的 **"导入"** 或 **"导出"** 组中的 **"文本文件"**。 **ImportExportText** 操作的参数反映由 **"文本文件"** 命令启动的向导中的选项。</span><span class="sxs-lookup"><span data-stu-id="ce790-176">This action is similar to clicking **Text File** in the **Import** or **Export** group on the **External Data** tab. The arguments of the **ImportExportText** action reflect the options in the wizard started by the **Text File** command.</span></span>

> [!TIP]
> <span data-ttu-id="ce790-p114">[!提示] 导入/导出规格用于存储 Access 导入、导出或链接文本文件所需的信息。您可以使用存储规格将文本数据导入或链接到类似的文本文件，或从类似的文本文件中导出文本数据。例如，您要从主机接收文本文件格式的周销售数据。您可以为这种类型的数据创建并保存一个规格，每次将此数据添加到 Access 数据库中时，都可以使用该规格。</span><span class="sxs-lookup"><span data-stu-id="ce790-p114">An import/export specification stores the information Access needs to import, export, or link a text file. You can use stored specifications to import, export, or link text data from or to similar text files. For example, you might receive weekly sales figures in a text file from a mainframe computer. You can create and save a specification for this type of data and then use the specification whenever you add this data to your Access database.</span></span>

> [!NOTE]
> <span data-ttu-id="ce790-181">[!注释] 如果查询或筛选链接的文本文件，则查询或筛选将区分大小写。</span><span class="sxs-lookup"><span data-stu-id="ce790-181">If you query or filter a linked text file, the query or filter is case-sensitive.</span></span>

<span data-ttu-id="ce790-182">若要在 Visual Basic for Applications (VBA) 模块中运行 **ImportExportText** 操作，请使用 **DoCmd** 对象的 **TransferText** 方法。</span><span class="sxs-lookup"><span data-stu-id="ce790-182">To run the **ImportExportText** action in a Visual Basic for Applications (VBA) module, use the **TransferText** method of the **DoCmd** object.</span></span>

