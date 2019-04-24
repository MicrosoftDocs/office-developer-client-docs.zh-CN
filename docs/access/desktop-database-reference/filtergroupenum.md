---
title: FilterGroupEnum (Access desktop database reference)
TOCTitle: FilterGroupEnum
ms:assetid: 141f8f9a-c188-5937-91cc-3155eaebebd2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248912(v=office.15)
ms:contentKeyID: 48543381
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: be2ce54fe743c46468850abc5dc16520e208ec9e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292417"
---
# <a name="filtergroupenum"></a>FilterGroupEnum

**适用于**：Access 2013、Office 2013

指定要从 [Recordset](recordset-object-ado.md) 中筛选的记录组。

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
<td><p><strong>adFilterAffectedRecords</strong></p></td>
<td><p>双面</p></td>
<td><p>用于仅查看受上一次 <a href="delete-method-ado-recordset.md">Delete</a>、<a href="resync-method-ado.md">Resync</a>、<a href="updatebatch-method-ado.md">UpdateBatch</a> 或 <a href="cancelbatch-method-ado.md">CancelBatch</a> 调用影响的记录的筛选器。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFilterConflictingRecords</strong></p></td>
<td><p>5</p></td>
<td><p>用于查看使上一次批更新失败的记录的筛选器。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFilterFetchedRecords</strong></p></td>
<td><p>第三章</p></td>
<td><p>用于查看当前缓存中的记录（即，上一次从数据库检索记录的调用的结果）的筛选器。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFilterNone</strong></p></td>
<td><p>0</p></td>
<td><p>删除当前的筛选并还原所有的记录以进行查看。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFilterPendingRecords</strong></p></td>
<td><p>1</p></td>
<td><p>用于仅查看已更改但尚未发送到服务器的记录的筛选器。仅适用于批更新模式。</p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a>ADO/WFC 等效项

包：**com.ms.wfc.data**

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AdoEnums FilterGroup</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums FilterGroup</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums FilterGroup</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums FilterGroup</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums FilterGroup</p></td>
</tr>
</tbody>
</table>

