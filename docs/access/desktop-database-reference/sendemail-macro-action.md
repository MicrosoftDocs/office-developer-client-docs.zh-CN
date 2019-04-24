---
title: SendEmail 宏操作
TOCTitle: SendEmail macro action
ms:assetid: 84ff6b46-d239-4716-9964-5b909656d347
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196780(v=office.15)
ms:contentKeyID: 48546046
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c0fa220b3088cde46b0e82631c06520afd839c64
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314649"
---
# <a name="sendemail-macro-action"></a>SendEmail 宏操作

**适用于**：Access 2013、Office 2013

**SendEmail**操作会发送一封电子邮件。

> [!NOTE]
> **SendEmail** 操作仅适用于数据宏。

## <a name="setting"></a>Setting

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
<th><p>必需</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>To</strong></p></td>
<td><p>是</p></td>
<td><p>要将其名称放在邮件的 "<strong>收件人</strong>" 行中的邮件的收件人。使用分号 (;) 将在此参数中指定的收件人姓名 (以及 " <em>Cc</em> " 和<em>"Bcc</em> " 参数) 隔开。</p></td>
</tr>
<tr class="even">
<td><p><strong>Cc</strong></p></td>
<td><p>否</p></td>
<td><p>要将其姓名置于邮件的 "抄送" (&quot;抄送&quot;) 行中的邮件收件人。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Bcc</strong></p></td>
<td><p>否</p></td>
<td><p>要将其姓名置于邮件的 "密件抄送" (&quot;密件抄送&quot;) 行中的邮件收件人。</p></td>
</tr>
<tr class="even">
<td><p><strong>Subject</strong></p></td>
<td><p>否</p></td>
<td><p>邮件的主题。此文本显示在邮件的“主题”<strong></strong>行中。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Body</strong></p></td>
<td><p>否</p></td>
<td><p>要在邮件的正文中包括的文本。如果将此参数留空，则邮件中不会包括其他文本。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

**SendEmail** 操作仅适用于 **[删除后](after-delete-macro-event.md)** 、 **[插入后](after-insert-macro-event.md)** 和 **[更新后](after-update-macro-event.md)** 宏事件。

**SendEmail** 操作不显示用于编辑的邮件。

