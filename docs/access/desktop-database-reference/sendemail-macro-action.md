---
title: SendEmail 宏操作
TOCTitle: SendEmail macro action
ms:assetid: 84ff6b46-d239-4716-9964-5b909656d347
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196780(v=office.15)
ms:contentKeyID: 48546046
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: aa783dcc7ad02cc36b14ef9ef97436cb1ad88e4a
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25924685"
---
# <a name="sendemail-macro-action"></a>SendEmail 宏操作


**适用于**： Access 2013、 Office 2013

**SendEmail** 操作可发送电子邮件。


> [!NOTE]
> <P>[!注释] <STRONG>SendEmail</STRONG> 操作仅适用于数据宏。</P>



## <a name="setting"></a>设置

**SendEmail** 操作具有以下参数。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>是否必需</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>To</strong></p></td>
<td><p>是</p></td>
<td><p>您想要放在邮件中的<strong>到</strong>行上将其姓名的收件人。分隔用分号 （;） 指定此参数中 （以及<em>Cc</em>和<em>Bcc</em>参数） 的收件人姓名。</p></td>
</tr>
<tr class="even">
<td><p><strong>Cc</strong></p></td>
<td><p>否</p></td>
<td><p>邮件的收件人，您想要置于抄送将其姓名 (&quot;抄送&quot;) 邮件行中的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Bcc</strong></p></td>
<td><p>否</p></td>
<td><p>邮件的收件人，您想要置于密件抄送将其姓名 (&quot;密件抄送副本&quot;) 邮件行中的。</p></td>
</tr>
<tr class="even">
<td><p><strong>Subject</strong></p></td>
<td><p>否</p></td>
<td><p>邮件的主题。 此文本出现在邮件中的<strong>主题</strong>行上。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Body</strong></p></td>
<td><p>否</p></td>
<td><p>要在邮件的正文中包括的文本。如果将此参数留空，则邮件中不会包括其他文本。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注释

**SendEmail** 操作仅适用于 **[删除后](after-delete-macro-event.md)** 、 **[插入后](after-insert-macro-event.md)** 和 **[更新后](after-update-macro-event.md)** 宏事件。

**SendEmail** 操作不显示用于编辑的邮件。

