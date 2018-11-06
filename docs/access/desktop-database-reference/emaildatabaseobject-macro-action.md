---
title: EMailDatabaseObject 宏操作
TOCTitle: EMailDatabaseObject macro action
ms:assetid: 7fd80596-5c08-dab9-5343-c0edc38a1af9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196469(v=office.15)
ms:contentKeyID: 48545915
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm24439
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 84d5b9c5f65e032523be8c646cdea18890744367
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25997446"
---
# <a name="emaildatabaseobject-macro-action"></a><span data-ttu-id="d615a-102">EMailDatabaseObject 宏操作</span><span class="sxs-lookup"><span data-stu-id="d615a-102">EMailDatabaseObject macro action</span></span>

<span data-ttu-id="d615a-103">**适用于：** Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="d615a-103">**Applies to:** Access 2013 | Office 2013</span></span>

<span data-ttu-id="d615a-104">可以使用 **EMailDatabaseObject** 操作在电子邮件中包含指定的 Microsoft Access 数据表、窗体、报表、模块或数据访问页，并且可以在电子邮件中查看和转发这些对象。</span><span class="sxs-lookup"><span data-stu-id="d615a-104">You can use the **EMailDatabaseObject** action to include the specified Microsoft Access datasheet, form, report, module, or data access page in an electronic mail message, where it can be viewed and forwarded.</span></span>

> [!NOTE]
> <span data-ttu-id="d615a-105">[!注释] 如果数据库不受信任，将不允许此操作。</span><span class="sxs-lookup"><span data-stu-id="d615a-105">This action will not be allowed if the database is not trusted.</span></span> 

## <a name="settings"></a><span data-ttu-id="d615a-106">设置</span><span class="sxs-lookup"><span data-stu-id="d615a-106">Settings</span></span>

<span data-ttu-id="d615a-107">**EMailDatabaseObject** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="d615a-107">The **EMailDatabaseObject** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="d615a-108">操作参数</span><span class="sxs-lookup"><span data-stu-id="d615a-108">Action argument</span></span></p></th>
<th><p><span data-ttu-id="d615a-109">说明</span><span class="sxs-lookup"><span data-stu-id="d615a-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d615a-110"><strong>对象类型</strong></span><span class="sxs-lookup"><span data-stu-id="d615a-110"><strong>Object Type</strong></span></span></p></td>
<td><p><span data-ttu-id="d615a-111">要在邮件中包含的对象类型。</span><span class="sxs-lookup"><span data-stu-id="d615a-111">The type of object to include in the mail message.</span></span> <span data-ttu-id="d615a-112">单击 （对于表数据表） 的<strong>表</strong>、<strong>查询</strong>（用于查询数据表）、 （对于窗体或窗体数据表） 的<strong>窗体</strong>、<strong>报表</strong>、<strong>模块</strong>或<strong>数据访问页</strong>、<strong>服务器视图</strong>、<strong>存储过程</strong>或<strong>函数</strong>宏生成器窗格的<strong>操作参数</strong>部分的<strong>对象类型</strong>框中。</span><span class="sxs-lookup"><span data-stu-id="d615a-112">Click <strong>Table</strong> (for a table datasheet), <strong>Query</strong> (for a query datasheet), <strong>Form</strong> (for a form or form datasheet), <strong>Report</strong>, <strong>Module</strong>, or <strong>Data Access Page</strong>, <strong>Server View</strong>, <strong>Stored Procedures</strong>, or <strong>Function</strong> in the <strong>Object Type</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane.</span></span> <span data-ttu-id="d615a-113">您不能发送宏。</span><span class="sxs-lookup"><span data-stu-id="d615a-113">You can't send a macro.</span></span> <span data-ttu-id="d615a-114">如果您想要包括的活动对象，请选择与此参数，其类型，但将<strong>对象名称</strong>参数留空。</span><span class="sxs-lookup"><span data-stu-id="d615a-114">If you want to include the active object, select its type with this argument, but leave the <strong>Object Name</strong> argument blank.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d615a-115"><strong>对象名称</strong></span><span class="sxs-lookup"><span data-stu-id="d615a-115"><strong>Object Name</strong></span></span></p></td>
<td><p><span data-ttu-id="d615a-116">要在邮件中包含的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="d615a-116">The name of the object to include in the mail message.</span></span> <span data-ttu-id="d615a-117"><strong>对象名称</strong>框中显示<strong>对象类型</strong>参数所选类型的数据库中的所有对象。</span><span class="sxs-lookup"><span data-stu-id="d615a-117">The <strong>Object Name</strong> box shows all objects in the database of the type selected by the <strong>Object Type</strong> argument.</span></span> <span data-ttu-id="d615a-118">如果将<strong>对象类型</strong>和<strong>对象名称</strong>参数留空，Access 会向不带任何数据库对象的邮件应用程序发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="d615a-118">If you leave both the <strong>Object Type</strong> and <strong>Object Name</strong> arguments blank, Access sends a message to the mail application without any database object.</span></span> <span data-ttu-id="d615a-119">如果在类库数据库中运行包含 <strong>EMailDatabaseObject</strong> 操作的宏，Access 将先在该类库数据库中查找具有此名称的对象，然后再在当前数据库中查找。</span><span class="sxs-lookup"><span data-stu-id="d615a-119">If you run a macro containing the <strong>EMailDatabaseObject</strong> action in a library database, Access looks for the object with this name first in the library database, then in the current database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d615a-120"><strong>输出格式</strong></span><span class="sxs-lookup"><span data-stu-id="d615a-120"><strong>Output Format</strong></span></span></p></td>
<td><p><span data-ttu-id="d615a-121">您希望用于包含的对象的格式的类型。</span><span class="sxs-lookup"><span data-stu-id="d615a-121">The type of format you want used for the included object.</span></span> <span data-ttu-id="d615a-122">可以从选择的格式的列表将根据您所选择的<strong>对象类型</strong>参数。</span><span class="sxs-lookup"><span data-stu-id="d615a-122">The list of formats you can select from will change depending on what you select for the <strong>Object Type</strong> argument.</span></span> <span data-ttu-id="d615a-123"><strong>Excel 97-Excel 2003 工作簿 (*.xls)</strong>、 <strong>Excel 二进制工作簿 (*.xlsb)</strong>、 <strong>Excel 工作簿 (*.xlsx)</strong>，可能包括可用格式<strong>HTML (*.htm，*.html)</strong>， <strong>Microsoft Excel 5.0/95 工作簿 (*.xls)</strong>， <strong>PDF 格式</strong>，<strong>格式文本设置 (*.rtf)</strong>、<strong>文本文件 (*.txt)</strong>或<strong>XPS 格式 (\*.xps)</strong>。</span><span class="sxs-lookup"><span data-stu-id="d615a-123">Available formats may include <strong>Excel 97 - Excel 2003 Workbook (*.xls)</strong>, <strong>Excel Binary Workbook (*.xlsb)</strong>, <strong>Excel Workbook (*.xlsx)</strong>, <strong>HTML (*.htm, *.html)</strong>, <strong>Microsoft Excel 5.0/95 Workbook (*.xls)</strong>, <strong>PDF Format</strong>, <strong>Rich Text Fomat (*.rtf)</strong>, <strong>Text Files (*.txt)</strong>, or <strong>XPS Format (\*.xps)</strong>.</span></span> <span data-ttu-id="d615a-124">在<strong>输出格式</strong>框中。</span><span class="sxs-lookup"><span data-stu-id="d615a-124">in the <strong>Output Format</strong> box.</span></span> <span data-ttu-id="d615a-125">可以仅以文本格式发送模块。</span><span class="sxs-lookup"><span data-stu-id="d615a-125">Modules can be sent only in text format.</span></span> <span data-ttu-id="d615a-126">只能以 HTML 格式发送数据访问页。</span><span class="sxs-lookup"><span data-stu-id="d615a-126">Data access pages can only be sent in HTML format.</span></span> <span data-ttu-id="d615a-127">如果将此参数留空，则 Access 将提示您为输出格式。</span><span class="sxs-lookup"><span data-stu-id="d615a-127">If you leave this argument blank, Access prompts you for the output format.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d615a-128"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="d615a-128"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="d615a-129">您想要放在邮件中的<strong>到</strong>行上将其姓名的收件人。</span><span class="sxs-lookup"><span data-stu-id="d615a-129">The recipients of the message whose names you want to put on the <strong>To</strong> line in the mail message.</span></span> <span data-ttu-id="d615a-130">如果将此参数留空，则 Access 将提示您的收件人的名称。</span><span class="sxs-lookup"><span data-stu-id="d615a-130">If you leave this argument blank, Access prompts you for the recipients' names.</span></span> <span data-ttu-id="d615a-131">用分号 （;） 或 Microsoft 中的<strong>区域设置属性</strong>对话框<strong>编号</strong>选项卡上设置的列表分隔符指定此参数中 （以及<strong>Cc</strong>和<strong>Bcc</strong>参数） 的收件人的姓名Windows<strong>控制面板</strong>。</span><span class="sxs-lookup"><span data-stu-id="d615a-131">Separate the recipients' names you specify in this argument (and in the <strong>Cc</strong> and <strong>Bcc</strong> arguments) with a semicolon (;) or with the list separator set on the <strong>Number</strong> tab of the <strong>Regional Settings Properties</strong> dialog box in Microsoft Windows <strong>Control Panel</strong>.</span></span> <span data-ttu-id="d615a-132">如果邮件应用程序无法识别的收件人的姓名，不发送消息和发生错误。</span><span class="sxs-lookup"><span data-stu-id="d615a-132">If the mail application can't identify the recipients' names, the message isn't sent and an error occurs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d615a-133"><strong>Cc</strong></span><span class="sxs-lookup"><span data-stu-id="d615a-133"><strong>Cc</strong></span></span></p></td>
<td><p><span data-ttu-id="d615a-134">邮件的收件人，您想要置于<strong>抄送</strong>将其姓名 (&quot;抄送&quot;) 行中的邮件。</span><span class="sxs-lookup"><span data-stu-id="d615a-134">The message recipients whose names you want to put on the <strong>Cc</strong> (&quot;carbon copy&quot;) line in the mail message.</span></span> <span data-ttu-id="d615a-135">如果将此参数留空，邮件中的“抄送”<strong></strong>行为空。</span><span class="sxs-lookup"><span data-stu-id="d615a-135">If you leave this argument blank, the <strong>Cc</strong> line in the mail message is blank.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d615a-136"><strong>Bcc</strong></span><span class="sxs-lookup"><span data-stu-id="d615a-136"><strong>Bcc</strong></span></span></p></td>
<td><p><span data-ttu-id="d615a-137">邮件的收件人，您想要置于<strong>密件抄送</strong>将其姓名 (&quot;密件抄送副本&quot;) 行中的邮件。</span><span class="sxs-lookup"><span data-stu-id="d615a-137">The message recipients whose names you want to put on the <strong>Bcc</strong> (&quot;blind carbon copy&quot;) line in the mail message.</span></span> <span data-ttu-id="d615a-138">如果将此参数留空，邮件中的“密件抄送”<strong></strong>行为空。</span><span class="sxs-lookup"><span data-stu-id="d615a-138">If you leave this argument blank, the <strong>Bcc</strong> line in the mail message is blank.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d615a-139"><strong>Subject</strong></span><span class="sxs-lookup"><span data-stu-id="d615a-139"><strong>Subject</strong></span></span></p></td>
<td><p><span data-ttu-id="d615a-p107">邮件的主题。此文本出现在邮件的<strong>“主题”</strong>行。如果将此参数留空，则邮件的<strong>“主题”</strong>行为空。</span><span class="sxs-lookup"><span data-stu-id="d615a-p107">The subject of the message. This text appears on the <strong>Subject</strong> line in the mail message. If you leave this argument blank, the <strong>Subject</strong> line in the mail message is blank.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d615a-143"><strong>消息文本</strong></span><span class="sxs-lookup"><span data-stu-id="d615a-143"><strong>Message Text</strong></span></span></p></td>
<td><p><span data-ttu-id="d615a-144">要在邮件中的数据库对象除了包含任何文本。</span><span class="sxs-lookup"><span data-stu-id="d615a-144">Any text you want to include in the message in addition to the database object.</span></span> <span data-ttu-id="d615a-145">此文本的邮件正文中出现对象之后。</span><span class="sxs-lookup"><span data-stu-id="d615a-145">This text appears in the main body of the mail message, after the object.</span></span> <span data-ttu-id="d615a-146">如果将此参数留空，则邮件中不包含任何其他文本。</span><span class="sxs-lookup"><span data-stu-id="d615a-146">If you leave this argument blank, no additional text is included in the mail message.</span></span> <span data-ttu-id="d615a-147">如果将<strong>对象类型</strong>和<strong>对象名称</strong>参数留空，您可以使用此参数发送一封邮件没有数据库对象。</span><span class="sxs-lookup"><span data-stu-id="d615a-147">If you leave the <strong>Object Type</strong> and <strong>Object Name</strong> arguments blank, you can use this argument to send a mail message without a database object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d615a-148"><strong>编辑邮件</strong></span><span class="sxs-lookup"><span data-stu-id="d615a-148"><strong>Edit Message</strong></span></span></p></td>
<td><p><span data-ttu-id="d615a-p109">指定邮件在发送前是否可以编辑。如果选择<strong>“是”</strong>，电子邮件应用程序将自动启动，而且您可以编辑邮件。如果选择<strong>“否”</strong>，邮件将直接发送，用户没有机会编辑邮件。默认值为<strong>“是”</strong>。</span><span class="sxs-lookup"><span data-stu-id="d615a-p109">Specifies whether the message can be edited before it's sent. If you select <strong>Yes</strong>, the electronic mail application starts automatically, and the message can be edited. If you select <strong>No</strong>, the message is sent without the user having a chance to edit the message. The default is <strong>Yes</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d615a-153"><strong>模板文件</strong></span><span class="sxs-lookup"><span data-stu-id="d615a-153"><strong>Template File</strong></span></span></p></td>
<td><p><span data-ttu-id="d615a-p110">要作为 HTML 文件的模板的文件的路径和文件名。模板文件是一种包含 HTML 标记的文件。</span><span class="sxs-lookup"><span data-stu-id="d615a-p110">The path and file name of a file you want to use as a template for an HTML file. The template file is a file containing HTML tags.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="d615a-156">说明</span><span class="sxs-lookup"><span data-stu-id="d615a-156">Remarks</span></span>

<span data-ttu-id="d615a-p111">邮件中的对象采用所选的输出格式。双击该对象时，相应的软件启动并且该对象打开。</span><span class="sxs-lookup"><span data-stu-id="d615a-p111">The object in the mail message is in the selected output format. When you double-click the object, the appropriate software starts with the object opened.</span></span>

<span data-ttu-id="d615a-159">使用 **EMailDatabaseObject** 操作将数据库对象包括在邮件中时，下列规则适用：</span><span class="sxs-lookup"><span data-stu-id="d615a-159">The following rules apply when you use the **EMailDatabaseObject** action to include a database object in a mail message:</span></span>

- <span data-ttu-id="d615a-p112">可以发送表、查询和窗体数据表。在所包括的对象中，数据表中的所有字段的外观都将与它们在 Access 中的相同，只有包含 OLE 对象的字段例外。这些字段的列将包括在对象中，但字段是空的。</span><span class="sxs-lookup"><span data-stu-id="d615a-p112">You can send table, query, and form datasheets. In the included object, all fields in the datasheet look as they do in Access, except fields containing OLE objects. The columns for these fields are included in the object, but the fields are blank.</span></span>

- <span data-ttu-id="d615a-163">对于绑定到“是/否”字段的控件（切换按钮、选项按钮或复选框），输出文件将显示值 -1（是）或 0（否）。</span><span class="sxs-lookup"><span data-stu-id="d615a-163">For a control bound to a Yes/No field (a toggle button, option button, or check box), the output file displays the value –1 (Yes) or 0 (No).</span></span>

- <span data-ttu-id="d615a-164">对于绑定到超链接字段的文本框，输出文件将显示所有输出格式的超链接，但 MS-DOS 文本除外（在这种情况下，超链接只显示为常规文本）。</span><span class="sxs-lookup"><span data-stu-id="d615a-164">For a text box bound to a Hyperlink field, the output file displays the hyperlink for all output formats except MS-DOS text (in this case, the hyperlink is just displayed as normal text).</span></span>

- <span data-ttu-id="d615a-165">如果发送窗体视图中的窗体，则所包括的对象将始终包含该窗体的数据表视图。</span><span class="sxs-lookup"><span data-stu-id="d615a-165">If you send a form in Form view, the included object always contains the form's Datasheet view.</span></span>

- <span data-ttu-id="d615a-p113">如果发送报表，包括在对象中的唯一控件只有文本框，在某些情况下，还可以包括标签。所有其他控件均被忽略。页眉和页脚信息也不会包括在其中。唯一的例外是，当发送 Excel 格式的报表时，组页脚中的文本框将被包括在对象中，但该文本框包含的表达式中要有 **Sum** 函数。页眉或页脚中的其他控件（以及除了 **"Sum"** 以外的其他聚合函数）将不会包括在对象中。</span><span class="sxs-lookup"><span data-stu-id="d615a-p113">If you send a report, the only controls that are included in the object are text boxes and (in some cases) labels. All other controls are ignored. Header and footer information is also not included. The only exception to this is that when you send a report in Excel format, a text box in a group footer containing an expression with the **Sum** function is included in the object. No other control in a header or footer (and no aggregate function other than **Sum**) is included in the object.</span></span>

- <span data-ttu-id="d615a-171">子报表将包括在对象中。</span><span class="sxs-lookup"><span data-stu-id="d615a-171">Subreports are included in the object.</span></span>

- <span data-ttu-id="d615a-p114">发送 HTML 格式的数据表、窗体或数据访问页时，将创建一个 .html 文件。发送 HTML 格式的报表时，将为报表中的每一页创建一个 .html 文件。</span><span class="sxs-lookup"><span data-stu-id="d615a-p114">When you send a datasheet, form, or data access page in HTML format, one .html file is created. When you send a report in HTML format, one .html file is created for each page in the report.</span></span>

<span data-ttu-id="d615a-174">若要在 Visual Basic for Applications (VBA) 模块中运行 **EMailDatabaseObject** 操作，请使用 **DoCmd** 对象的 **SendObject** 方法。</span><span class="sxs-lookup"><span data-stu-id="d615a-174">To run the **EMailDatabaseObject** action in a Visual Basic for Applications (VBA) module, use the **SendObject** method of the **DoCmd** object.</span></span>

### <a name="about-the-contributor"></a><span data-ttu-id="d615a-175">关于参与者</span><span class="sxs-lookup"><span data-stu-id="d615a-175">About the contributor</span></span>

<span data-ttu-id="d615a-176">**通过提供的链接**Luke Chung、 [FMS，Inc.](https://www.fmsinc.com/)、 的创始人兼总裁 FMS，inc.，自定义数据库解决方案和开发人员工具的领先提供商。</span><span class="sxs-lookup"><span data-stu-id="d615a-176">**Link provided by** Luke Chung, [FMS, Inc.](https://www.fmsinc.com/), the founder and president of FMS, Inc., a leading provider of custom database solutions and developer tools.</span></span>

- [<span data-ttu-id="d615a-177">功能和使用 SendObject 方法发送到的限制</span><span class="sxs-lookup"><span data-stu-id="d615a-177">Features and Limits of Using the SendObject Method to Send</span></span>](https://www.fmsinc.com/microsoftaccess/email/sendobject.html)





