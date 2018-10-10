---
title: ADCPROP_UPDATERESYNC_ENUM
TOCTitle: ADCPROP_UPDATERESYNC_ENUM
ms:assetid: 890210c4-2290-ddb2-8814-022093c318de
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249600(v=office.15)
ms:contentKeyID: 48546145
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ce8a0555e758cf2f3435de755720f312705ba374
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467375"
---
# <a name="adcpropupdateresyncenum"></a>ADCPROP\_UPDATERESYNC\_枚举

**适用于**： Access 2013 |Office 2013

指定 [UpdateBatch](updatebatch-method-ado.md) 方法后面是否跟随隐式的 [Resync](resync-method-ado.md) 方法操作，如果跟随，则指定该操作的范围。

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
<td><p>15</p></td>
<td><p>用所有其他 ADCPROP_UPDATERESYNC_ENUM 成员的组合值调用 <strong>Resync</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong>adResyncAutoIncrement</strong></p></td>
<td><p>1</p></td>
<td><p>默认值。尝试检索由数据源自动递增或生成的列（如 Microsoft Jet AutoNumber 字段或 Microsoft SQL Server Identity 列）的新标识值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adResyncConflicts</strong></p></td>
<td><p>2</p></td>
<td><p>对于由于并发冲突而导致更新或删除操作失败的所有行，调用 <strong>Resync</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong>adResyncInserts</strong></p></td>
<td><p>8</p></td>
<td><p>所有成功插入行中调用<strong>Resync</strong> 。 但是，不重新同步 AutoIncrement 列的值。 而是新插入行的内容是重新同步基于现有主关键字的值。 如果为主键为一个自动增量值，则<strong>Resync</strong>不会检索目标行的内容。 有关自动递增 AutoIncrement 主键值，与组合的值<strong>adResyncAutoIncrement</strong> + <strong>adResyncInserts</strong>调用<strong>UpdateBatch</strong> 。</p></td>
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

