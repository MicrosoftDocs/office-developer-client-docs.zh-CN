---
title: ADCPROP_UPDATERESYNC_ENUM
TOCTitle: ADCPROP_UPDATERESYNC_ENUM
ms:assetid: 890210c4-2290-ddb2-8814-022093c318de
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249600(v=office.15)
ms:contentKeyID: 48546145
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 1952d473b51048a271a689498ae844cee761b001
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280437"
---
# <a name="adcpropupdateresyncenum"></a>ADCPROP\_UPDATERESYNC\_枚举

**适用于**：Access 2013、Office 2013

指定 [UpdateBatch](updatebatch-method-ado.md) 方法后面是否跟随隐式的 [Resync](resync-method-ado.md) 方法操作，如果跟随，则指定该操作的范围。

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>值</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>adResyncAll</strong></p></td>
<td><p>个</p></td>
<td><p>用所有其他 ADCPROP_UPDATERESYNC_ENUM 成员的组合值调用 <strong>Resync</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong>adResyncAutoIncrement</strong></p></td>
<td><p>1</p></td>
<td><p>默认值。尝试检索由数据源自动递增或生成的列（如 Microsoft Jet AutoNumber 字段或 Microsoft SQL Server Identity 列）的新标识值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adresyncconflicts 会</strong></p></td>
<td><p>双面</p></td>
<td><p>对于由于并发冲突而导致更新或删除操作失败的所有行，调用 <strong>Resync</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong>adResyncInserts</strong></p></td>
<td><p>utf-8</p></td>
<td><p>对于所有已成功插入的行调用 <strong>Resync</strong>。 但是，“自动递增”列的值不会重新同步。 相反，新插入行的内容将根据现有主键值重新同步。 如果主键是“自动递增”值，<strong>Resync</strong> 将不检索目标行的内容。 若要自动递增自动增量主键值, 请使用组合值<strong>adResyncAutoIncrement</strong> + <strong>adResyncInserts</strong>调用<strong>UpdateBatch</strong> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adResyncNone</strong></p></td>
<td><p>0</p></td>
<td><p>不调用 <strong>Resync</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong>adResyncUpdates</strong></p></td>
<td><p>4</p></td>
<td><p>对于所有已成功更新的行调用 <strong>Resync</strong>。</p></td>
</tr>
</tbody>
</table>

