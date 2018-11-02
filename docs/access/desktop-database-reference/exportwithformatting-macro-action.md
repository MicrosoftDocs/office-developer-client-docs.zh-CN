---
title: ExportWithFormatting 宏操作
TOCTitle: ExportWithFormatting macro action
ms:assetid: 8926dfa3-bf11-30ab-0f85-46f0a4961784
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197066(v=office.15)
ms:contentKeyID: 48546152
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm159503
f1_categories:
- Office.Version=v15
ms.openlocfilehash: ae03262489b707257a4aee93e4380aa70329856a
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25924433"
---
# <a name="exportwithformatting-macro-action"></a><span data-ttu-id="7d93c-102">ExportWithFormatting 宏操作</span><span class="sxs-lookup"><span data-stu-id="7d93c-102">ExportWithFormatting macro action</span></span>


<span data-ttu-id="7d93c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="7d93c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7d93c-104">可以使用 **ExportWithFormatting** 操作将指定的 Microsoft Access 数据库对象（数据表、窗体、报表、模块或数据访问页）中的数据输出为若干种输出格式。</span><span class="sxs-lookup"><span data-stu-id="7d93c-104">You can use the **ExportWithFormatting** action to output the data in the specified Microsoft Access database object (a datasheet, form, report, module, or data access page) to several output formats.</span></span>

## <a name="settings"></a><span data-ttu-id="7d93c-105">设置</span><span class="sxs-lookup"><span data-stu-id="7d93c-105">Settings</span></span>

<span data-ttu-id="7d93c-106">**ExportWithFormatting** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="7d93c-106">The **ExportWithFormatting** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7d93c-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="7d93c-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="7d93c-108">说明</span><span class="sxs-lookup"><span data-stu-id="7d93c-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d93c-109"><strong>对象类型</strong></span><span class="sxs-lookup"><span data-stu-id="7d93c-109"><strong>Object Type</strong></span></span></p></td>
<td><p><span data-ttu-id="7d93c-110">包含的数据输出的对象类型。</span><span class="sxs-lookup"><span data-stu-id="7d93c-110">The type of object containing the data to output.</span></span> <span data-ttu-id="7d93c-111">单击<strong>对象中的<strong>表</strong>（表数据表）、<strong>查询</strong>（用于查询数据表）、 （对于窗体或窗体数据表） 的<strong>窗体</strong>、<strong>报表</strong>、<strong>模块</strong>、<strong>服务器视图</strong>、<strong>存储过程</strong>或<strong>函数</strong>类型</strong>框在宏生成器窗格的<strong>操作参数</strong>部分。</span><span class="sxs-lookup"><span data-stu-id="7d93c-111">Click <strong>Table</strong> (for a table datasheet), <strong>Query</strong> (for a query datasheet), <strong>Form</strong> (for a form or form datasheet), <strong>Report</strong>, <strong>Module</strong>, <strong>Server View</strong>, <strong>Stored Procedure</strong>, or <strong>Function</strong> in the <strong>Object Type</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane.</span></span> <span data-ttu-id="7d93c-112">不能输出宏。</span><span class="sxs-lookup"><span data-stu-id="7d93c-112">You can't output a macro.</span></span> <span data-ttu-id="7d93c-113">如果您想要输出活动对象，请选择与此参数，其类型，但将<strong>对象名称</strong>参数留空。</span><span class="sxs-lookup"><span data-stu-id="7d93c-113">If you want to output the active object, select its type with this argument, but leave the <strong>Object Name</strong> argument blank.</span></span> <span data-ttu-id="7d93c-114">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="7d93c-114">This is a required argument.</span></span> <span data-ttu-id="7d93c-115">默认值是<strong>表</strong>。</span><span class="sxs-lookup"><span data-stu-id="7d93c-115">The default is <strong>Table</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d93c-116"><strong>对象名称</strong></span><span class="sxs-lookup"><span data-stu-id="7d93c-116"><strong>Object Name</strong></span></span></p></td>
<td><p><span data-ttu-id="7d93c-117">包含要输出的数据对象的名称。</span><span class="sxs-lookup"><span data-stu-id="7d93c-117">The name of the object containing the data to output.</span></span> <span data-ttu-id="7d93c-118"><strong>对象名称</strong>框中显示<strong>对象类型</strong>参数所选类型的数据库中的所有对象。</span><span class="sxs-lookup"><span data-stu-id="7d93c-118">The <strong>Object Name</strong> box shows all objects in the database of the type selected by the <strong>Object Type</strong> argument.</span></span> <span data-ttu-id="7d93c-119">如果在类库数据库中运行包含 <strong>ExportWithFormatting</strong> 操作的宏，Access 将先在该类库数据库中查找具有此名称的对象，然后再在当前数据库中查找。</span><span class="sxs-lookup"><span data-stu-id="7d93c-119">If you run a macro containing the <strong>ExportWithFormatting</strong> action in a library database, Access first looks for the object with this name in the library database, and then in the current database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d93c-120"><strong>输出格式</strong></span><span class="sxs-lookup"><span data-stu-id="7d93c-120"><strong>Output Format</strong></span></span></p></td>
<td><p><span data-ttu-id="7d93c-p103">要用来输出数据的格式类型。可以选择<strong>“Excel 97 - Excel 2003 工作簿(*.xls)”</strong>、<strong>“Excel 二进制工作簿(*.xlsb)”</strong>、<strong>“Excel 工作簿(*.xlsx)”</strong>、<strong>“HTML (*.htm; *.html)”</strong>、<strong>“Microsoft Excel 5.0/95 工作簿(*.xls)”</strong>、<strong>“PDF 格式(*.pdf)”</strong>、<strong>“RTF 格式(*.rtf)”</strong>、<strong>“文本文件(*.txt)”</strong>或<strong>“XPS 格式(*.xps)”</strong>。如果将此参数留空，Access 将提示您提供输出格式。</span><span class="sxs-lookup"><span data-stu-id="7d93c-p103">The type of format you want to use to output the data. You can select <strong>Excel 97 - Excel 2003 Workbook (*.xls)</strong>, <strong>Excel Binary Workbook (*.xlsb)</strong>, <strong>Excel Workbook (*.xlsx)</strong>, <strong>HTML (*.htm; *.html)</strong>, <strong>Microsoft Excel 5.0/95 Workbook (*.xls)</strong>, <strong>PDF Format (*.pdf)</strong>, <strong>Rich Text Format (*.rtf)</strong>, <strong>Text Files (*.txt)</strong>, or <strong>XPS Format (*.xps)</strong>. If you leave this argument blank, Access prompts you for the output format.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d93c-124"><strong>输出文件</strong></span><span class="sxs-lookup"><span data-stu-id="7d93c-124"><strong>Output File</strong></span></span></p></td>
<td><p><span data-ttu-id="7d93c-125">所需的数据，包括完整路径输出文件。</span><span class="sxs-lookup"><span data-stu-id="7d93c-125">The file to which you want to output the data, including the full path.</span></span> <span data-ttu-id="7d93c-126">您可以包括标准的文件扩展名为您选择使用<strong>输出格式</strong>参数，输出格式，但不是必需的。</span><span class="sxs-lookup"><span data-stu-id="7d93c-126">You can include the standard file name extension for the output format you select with the <strong>Output Format</strong> argument, but it is not required.</span></span> <span data-ttu-id="7d93c-127">如果将<strong>输出文件</strong>参数留空，Access 将提示您进行了输出文件名称。</span><span class="sxs-lookup"><span data-stu-id="7d93c-127">If you leave the <strong>Output File</strong> argument blank, Access prompts you for an output file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d93c-128"><strong>自动启动</strong></span><span class="sxs-lookup"><span data-stu-id="7d93c-128"><strong>Auto Start</strong></span></span></p></td>
<td><p><span data-ttu-id="7d93c-129">指定是否希望相应的软件在<strong>ExportWithFormatting</strong>操作将运行后立即, 启动并打开<strong>输出文件</strong>参数指定的文件。</span><span class="sxs-lookup"><span data-stu-id="7d93c-129">Specifies whether you want the appropriate software to start immediately after the <strong>ExportWithFormatting</strong> action runs, with the file specified by the <strong>Output File</strong> argument opened.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d93c-130"><strong>模板文件</strong></span><span class="sxs-lookup"><span data-stu-id="7d93c-130"><strong>Template File</strong></span></span></p></td>
<td><p><span data-ttu-id="7d93c-p105">要作为 HTML 文件的模板的文件的路径和文件名。模板文件是包含 Access 独有的 HTML 标记和符号的文本文件。</span><span class="sxs-lookup"><span data-stu-id="7d93c-p105">The path and file name of a file you want to use as a template for HTML files. The template file is a text file that includes HTML tags and tokens that are unique to Access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d93c-133"><strong>Encoding</strong></span><span class="sxs-lookup"><span data-stu-id="7d93c-133"><strong>Encoding</strong></span></span></p></td>
<td><p><span data-ttu-id="7d93c-p106">要用于输出文本或 HTML 数据的字符编码格式的类型。可以选择<strong>“MS-DOS”</strong>、<strong>“Unicode”</strong>或<strong>“Unicode (UTF-8)”</strong>。<strong>“MS-DOS”</strong>参数设置仅适用于文本文件。如果将此参数留空，Access 则通过对文本文件使用 Windows 默认编码，对 HTML 文件使用默认系统编码来输出数据。</span><span class="sxs-lookup"><span data-stu-id="7d93c-p106">The type of character encoding format you want used to output the text or HTML data. You can select <strong>MS-DOS</strong>, <strong>Unicode</strong>, or <strong>Unicode (UTF-8)</strong>. The <strong>MS-DOS</strong> argument setting is available only for text files. If you leave this argument blank, Access outputs the data by using the Windows default encoding for text files and the default system encoding for HTML files.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d93c-138"><strong>输出质量</strong></span><span class="sxs-lookup"><span data-stu-id="7d93c-138"><strong>Output Quality</strong></span></span></p></td>
<td><p><span data-ttu-id="7d93c-139">选择<strong>“打印”</strong>优化打印输出，或者选择<strong>“屏幕”</strong>来优化屏幕上的显示输出。</span><span class="sxs-lookup"><span data-stu-id="7d93c-139">Select <strong>Print</strong> to optimize the output for printing, or <strong>Screen</strong> to optimize the output for display on a screen.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="7d93c-140">说明</span><span class="sxs-lookup"><span data-stu-id="7d93c-140">Remarks</span></span>

<span data-ttu-id="7d93c-p107">Access 数据将按所选的格式输出，并且可由使用相同格式的任何程序读取。例如，可将 Access 报表输出为 RTF 格式文档并保留其格式，然后用 Microsoft Word 打开该文档。</span><span class="sxs-lookup"><span data-stu-id="7d93c-p107">The Access data is output in the selected format and can be read by any program that uses the same format. For example, you can output an Access report with its formatting to a Rich Text Format document and then open the document in Microsoft Word.</span></span>

<span data-ttu-id="7d93c-143">如果输出为 HTML 格式的数据库对象，Access 将创建一个文件中包含的数据对象中的 HTML 格式。</span><span class="sxs-lookup"><span data-stu-id="7d93c-143">If you output the database object to HTML format, Access creates a file in HTML format containing the data from the object.</span></span> <span data-ttu-id="7d93c-144">**模板文件**参数用于指定要用作.html 文件模板的文件。</span><span class="sxs-lookup"><span data-stu-id="7d93c-144">You can use the **Template File** argument to specify a file to be used as a template for the .html file.</span></span>

<span data-ttu-id="7d93c-145">使用 **ExportWithFormatting** 操作将数据库对象输出为任意输出格式时，下列规则适用：</span><span class="sxs-lookup"><span data-stu-id="7d93c-145">The following rules apply when you use the **ExportWithFormatting** action to output a database object to any of the output formats:</span></span>

  - <span data-ttu-id="7d93c-p109">可以输出表、查询和窗体数据表中的数据。在输出文件中，数据表中所有字段的显示都与它们在 Access 中一样，但包含 OLE 对象的字段除外。OLE 对象字段的列包含在输出文件中，但这些字段为空。</span><span class="sxs-lookup"><span data-stu-id="7d93c-p109">You can output data in table, query, and form datasheets. In the output file, all fields in the datasheet appear as they do in Access, with the exception of fields containing OLE objects. The columns for OLE object fields are included in the output file, but the fields are blank.</span></span>

  - <span data-ttu-id="7d93c-149">控件绑定到字段是/否 （切换按钮、 选项按钮或复选框），输出文件将显示值-1 （是） 或 0 （无）。</span><span class="sxs-lookup"><span data-stu-id="7d93c-149">For a control that is bound to a Yes/No field (a toggle button, option button, or check box), the output file displays the value –1 (Yes) or 0 (No).</span></span>

  - <span data-ttu-id="7d93c-150">对于绑定到超链接字段的文本框，无论输出格式如何，输出文件都会显示超链接，只有 MS-DOS 文本除外，在此情况下，超链接显示为普通文本。</span><span class="sxs-lookup"><span data-stu-id="7d93c-150">For a text box bound to a Hyperlink field, the output file displays the hyperlink for all output formats with the exception of MS-DOS text (in this case, the hyperlink is displayed as normal text).</span></span>

  - <span data-ttu-id="7d93c-151">如果输出的是窗体视图中的窗体中的数据，则输出文件总是包含该窗体的数据表视图。</span><span class="sxs-lookup"><span data-stu-id="7d93c-151">If you output the data in a form in Form view, the output file always contains the form's Datasheet view.</span></span>

  - <span data-ttu-id="7d93c-p110">在以 HTML 格式输出数据表、窗体或数据访问页时，会创建一个 .html 文件。在以 HTML 格式输出报表时，会为报表中的每一页创建一个 .html 文件。</span><span class="sxs-lookup"><span data-stu-id="7d93c-p110">When you output a datasheet, form, or data access page in HTML format, one .html file is created. When you output a report in HTML format, one .html file is created for each page in the report.</span></span>

<span data-ttu-id="7d93c-154">**ExportWithFormatting** 操作的运行结果与单击 **"外部数据"** 选项卡上 **"导出"** 组中的某个选项类似。该操作的参数对应于 **"导出"** 对话框中的设置。</span><span class="sxs-lookup"><span data-stu-id="7d93c-154">The result of running the **ExportWithFormatting** action is similar to clicking one of the options in the **Export** group on the **External Data** tab. The action arguments correspond to the settings in the **Export** dialog box.</span></span>

<span data-ttu-id="7d93c-155">若要在 Visual Basic for Applications (VBA) 模块中运行 **ExportWithFormatting** 操作，请使用 **DoCmd** 对象的 **OutputTo** 方法。</span><span class="sxs-lookup"><span data-stu-id="7d93c-155">To run the **ExportWithFormatting** action in a Visual Basic for Applications (VBA) module, use the **OutputTo** method of the **DoCmd** object.</span></span>

