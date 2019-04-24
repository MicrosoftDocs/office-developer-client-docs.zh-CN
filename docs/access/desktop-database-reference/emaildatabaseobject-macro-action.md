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
localization_priority: Normal
ms.openlocfilehash: 15cb7d6c422a9d7b0fae17ab649b6cfbc1b497a4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293565"
---
# <a name="emaildatabaseobject-macro-action"></a>EMailDatabaseObject 宏操作

**适用于:** Access 2013 |Office 2013

可以使用 **EMailDatabaseObject** 操作在电子邮件中包含指定的 Microsoft Access 数据表、窗体、报表、模块或数据访问页，并且可以在电子邮件中查看和转发这些对象。

> [!NOTE]
> [!注释] 如果数据库不受信任，将不允许此操作。 

## <a name="settings"></a>设置

**EMailDatabaseObject** 操作具有下列参数。

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
<td><p><strong>对象类型</strong></p></td>
<td><p>要包含在邮件中的对象的类型。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“对象类型”</strong>框中单击<strong>“表”</strong>（对于表数据表）、<strong>“查询”</strong>（对于查询数据表）、<strong>“窗体”</strong>（对于窗体或窗体数据表）、<strong>“报表”</strong>、<strong>“模块”</strong>、<strong>“数据访问页”</strong>、<strong>“服务器视图”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。不能发送宏。如果想包含活动对象，请使用此参数选择其类型，但要将“对象名称”<strong></strong>参数留空。</p></td>
</tr>
<tr class="even">
<td><p><strong>对象名称</strong></p></td>
<td><p>要包含在邮件中的对象的名称。 <strong>“对象名称”</strong>框会显示数据库中属于“对象类型”<strong></strong>参数所选的类型的所有对象。 如果将“对象类型”<strong></strong>和“对象名称”<strong></strong>参数都留空，Access 会向邮件应用程序发送一封邮件但其中不包含任何数据库对象。 如果在类库数据库中运行包含 <strong>EMailDatabaseObject</strong> 操作的宏，Access 将先在该类库数据库中查找具有此名称的对象，然后再在当前数据库中查找。</p></td>
</tr>
<tr class="odd">
<td><p><strong>输出格式</strong></p></td>
<td><p>要用于所包含对象的格式的类型。 您可以从中进行选择的格式列表将根据您为<strong>对象类型</strong>参数选择的内容而变化。 可用格式可能包括<strong>excel 97-excel 2003 工作簿 (* .xls)</strong>、 <strong>excel 二进制工作簿 (* xlsb)</strong>、 <strong>Excel 工作簿 (* .xlsx</strong>)、 <strong>HTML (* .htm、* .html</strong>)、 <strong>Microsoft Excel 5.0/95 工作簿 (* .xls)</strong>、 <strong>PDF 格式</strong>、<strong>格式文本设置 (* .rtf)</strong>、<strong>文本文件 (* .txt)</strong>或<strong>XPS 格式 (* .xps)</strong>。 在 "<strong>输出格式</strong>" 框中。 模块只能以文本格式发送。 只有 HTML 格式的数据访问页才能发送。 如果将此参数留空，Access 将提示您提供输出格式。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>邮件的收件人，您要将其姓名放在邮件的<strong>“收件人”</strong>行。 如果将此参数留空，Access 会提示您输入收件人的姓名。 用分号 (;) 将在此参数中（以及在<strong>“抄送”</strong>和<strong>“密件抄送”</strong>参数中）指定的收件人姓名隔开，或者使用在 Microsoft Windows<strong>“控制面板”</strong>的<strong>“区域设置属性”</strong>对话框的<strong>“数字”</strong>选项卡上设置的列表分隔符将它们隔开。 如果邮件应用程序无法识别收件人姓名，该邮件将不会被发送，而且会发生错误。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cc</strong></p></td>
<td><p>要将其姓名放在邮件的<strong>"抄送</strong>" (&quot;抄送&quot;) 行中的邮件收件人。 如果将此参数留空，邮件中的“抄送”<strong></strong>行为空。</p></td>
</tr>
<tr class="even">
<td><p><strong>Bcc</strong></p></td>
<td><p>要将其姓名置于邮件的<strong>"密件抄送</strong>" (&quot;密件抄送&quot;) 行中的邮件收件人。 如果将此参数留空，邮件中的“密件抄送”<strong></strong>行为空。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Subject</strong></p></td>
<td><p>邮件的主题。此文本出现在邮件的<strong>“主题”</strong>行。如果将此参数留空，则邮件的<strong>“主题”</strong>行为空。</p></td>
</tr>
<tr class="even">
<td><p><strong>消息文本</strong></p></td>
<td><p>除数据库对象之外，您要包含在邮件中的任意文本。此文本出现在邮件正文中，位于对象之后。如果将此参数留空，则邮件中不包含任何其他文本。如果将“对象类型”<strong></strong>和“对象名称”<strong></strong>参数留空，则可以使用此参数发送不含数据库对象的邮件。</p></td>
</tr>
<tr class="odd">
<td><p><strong>编辑邮件</strong></p></td>
<td><p>指定邮件在发送前是否可以编辑。如果选择<strong>“是”</strong>，电子邮件应用程序将自动启动，而且您可以编辑邮件。如果选择<strong>“否”</strong>，邮件将直接发送，用户没有机会编辑邮件。默认值为<strong>“是”</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong>模板文件</strong></p></td>
<td><p>要作为 HTML 文件的模板的文件的路径和文件名。模板文件是一种包含 HTML 标记的文件。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

邮件中的对象采用所选的输出格式。双击该对象时，相应的软件启动并且该对象打开。

使用 **EMailDatabaseObject** 操作将数据库对象包括在邮件中时，下列规则适用：

- 可以发送表、查询和窗体数据表。在所包括的对象中，数据表中的所有字段的外观都将与它们在 Access 中的相同，只有包含 OLE 对象的字段例外。这些字段的列将包括在对象中，但字段是空的。

- 对于绑定到“是/否”字段的控件（切换按钮、选项按钮或复选框），输出文件将显示值 -1（是）或 0（否）。

- 对于绑定到超链接字段的文本框，输出文件将显示所有输出格式的超链接，但 MS-DOS 文本除外（在这种情况下，超链接只显示为常规文本）。

- 如果发送窗体视图中的窗体，则所包括的对象将始终包含该窗体的数据表视图。

- 如果发送报表，包括在对象中的唯一控件只有文本框，在某些情况下，还可以包括标签。所有其他控件均被忽略。页眉和页脚信息也不会包括在其中。唯一的例外是，当发送 Excel 格式的报表时，组页脚中的文本框将被包括在对象中，但该文本框包含的表达式中要有 **Sum** 函数。页眉或页脚中的其他控件（以及除了 **"Sum"** 以外的其他聚合函数）将不会包括在对象中。

- 子报表将包括在对象中。

- 发送 HTML 格式的数据表、窗体或数据访问页时，将创建一个 .html 文件。发送 HTML 格式的报表时，将为报表中的每一页创建一个 .html 文件。

若要在 Visual Basic for Applications (VBA) 模块中运行 **EMailDatabaseObject** 操作，请使用 **DoCmd** 对象的 **SendObject** 方法。

### <a name="about-the-contributor"></a>参与者简介

**链接提供者**Luke Chung, [FMS, inc.](https://www.fmsinc.com/), FMS, inc. 的创始人和总统, 是自定义数据库解决方案和开发人员工具的领先提供商。

- [使用 SendObject 方法发送的功能和限制](https://www.fmsinc.com/microsoftaccess/email/sendobject.html)





