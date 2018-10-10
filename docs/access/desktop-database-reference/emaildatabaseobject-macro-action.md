---
title: EMailDatabaseObject 宏操作
TOCTitle: EMailDatabaseObject Macro Action
ms:assetid: 7fd80596-5c08-dab9-5343-c0edc38a1af9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196469(v=office.15)
ms:contentKeyID: 48545915
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm24439
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 79b903f63ba0a9b8e6fd1adf9e5a29dab9de9edb
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465888"
---
# <a name="emaildatabaseobject-macro-action"></a>EMailDatabaseObject 宏操作

**适用于：** Access 2013 |Office 2013

可以使用 **EMailDatabaseObject** 操作在电子邮件中包含指定的 Microsoft Access 数据表、窗体、报表、模块或数据访问页，并且可以在电子邮件中查看和转发这些对象。

> [!NOTE]
> [!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。

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
<td><p>要在邮件中包含的对象类型。 单击 （对于表数据表） 的<strong>表</strong>、<strong>查询</strong>（用于查询数据表）、 （对于窗体或窗体数据表） 的<strong>窗体</strong>、<strong>报表</strong>、<strong>模块</strong>或<strong>数据访问页</strong>、<strong>服务器视图</strong>、<strong>存储过程</strong>或<strong>函数</strong>宏生成器窗格的<strong>操作参数</strong>部分的<strong>对象类型</strong>框中。 您不能发送宏。 如果您想要包括的活动对象，请选择与此参数，其类型，但将<strong>对象名称</strong>参数留空。</p></td>
</tr>
<tr class="even">
<td><p><strong>对象名称</strong></p></td>
<td><p>要在邮件中包含的对象的名称。 <strong>对象名称</strong>框中显示<strong>对象类型</strong>参数所选类型的数据库中的所有对象。 如果将<strong>对象类型</strong>和<strong>对象名称</strong>参数留空，Access 会向不带任何数据库对象的邮件应用程序发送一条消息。 如果在类库数据库中运行包含 <strong>EMailDatabaseObject</strong> 操作的宏，Access 将先在该类库数据库中查找具有此名称的对象，然后再在当前数据库中查找。</p></td>
</tr>
<tr class="odd">
<td><p><strong>输出格式</strong></p></td>
<td><p>您希望用于包含的对象的格式的类型。 可以从选择的格式的列表将根据您所选择的<strong>对象类型</strong>参数。 <strong>Excel 97-Excel 2003 工作簿 (*.xls)</strong>、 <strong>Excel 二进制工作簿 (*.xlsb)</strong>、 <strong>Excel 工作簿 (*.xlsx)</strong>，可能包括可用格式<strong>HTML (*.htm，*.html)</strong>， <strong>Microsoft Excel 5.0/95 工作簿 (*.xls)</strong>， <strong>PDF 格式</strong>，<strong>格式文本设置 (*.rtf)</strong>、<strong>文本文件 (*.txt)</strong>或<strong>XPS 格式 (*.xps)</strong>。 在<strong>输出格式</strong>框中。 可以仅以文本格式发送模块。 只能以 HTML 格式发送数据访问页。 如果将此参数留空，则 Access 将提示您为输出格式。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>您想要放在邮件中的<strong>到</strong>行上将其姓名的收件人。 如果将此参数留空，则 Access 将提示您的收件人的名称。 用分号 （;） 或 Microsoft 中的<strong>区域设置属性</strong>对话框<strong>编号</strong>选项卡上设置的列表分隔符指定此参数中 （以及<strong>Cc</strong>和<strong>Bcc</strong>参数） 的收件人的姓名Windows<strong>控制面板</strong>。 如果邮件应用程序无法识别的收件人的姓名，不发送消息和发生错误。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cc</strong></p></td>
<td><p>邮件的收件人，您想要置于<strong>抄送</strong>将其姓名 (&quot;抄送&quot;) 行中的邮件。 如果将此参数留空，邮件中的“抄送”<strong></strong>行为空。</p></td>
</tr>
<tr class="even">
<td><p><strong>Bcc</strong></p></td>
<td><p>邮件的收件人，您想要置于<strong>密件抄送</strong>将其姓名 (&quot;密件抄送副本&quot;) 行中的邮件。 如果将此参数留空，邮件中的“密件抄送”<strong></strong>行为空。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Subject</strong></p></td>
<td><p>邮件的主题。此文本出现在邮件的<strong>“主题”</strong>行。如果将此参数留空，则邮件的<strong>“主题”</strong>行为空。</p></td>
</tr>
<tr class="even">
<td><p><strong>邮件文本</strong></p></td>
<td><p>要在邮件中的数据库对象除了包含任何文本。 此文本的邮件正文中出现对象之后。 如果将此参数留空，则邮件中不包含任何其他文本。 如果将<strong>对象类型</strong>和<strong>对象名称</strong>参数留空，您可以使用此参数发送一封邮件没有数据库对象。</p></td>
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


## <a name="remarks"></a>说明

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

### <a name="about-the-contributor"></a>关于参与者

**通过提供的链接**Luke Chung、 [FMS，Inc.](https://www.fmsinc.com/)、 的创始人兼总裁 FMS，inc.，自定义数据库解决方案和开发人员工具的领先提供商。

  - [功能和使用 SendObject 方法发送到的限制](https://www.fmsinc.com/microsoftaccess/email/sendobject.html)





