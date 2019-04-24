---
title: RecordStatusEnum (Access desktop database reference)
TOCTitle: RecordStatusEnum
ms:assetid: 302915b8-494d-0be2-6dce-eaf91a0ea8ae
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249080(v=office.15)
ms:contentKeyID: 48544022
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a83de7730224c5ecd5080c795d38cf2e9a3305a9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309378"
---
# <a name="recordstatusenum"></a>RecordStatusEnum

**适用于**：Access 2013、Office 2013

指定记录的批更新和其他批量操作的状态。

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
<td><p><strong>adRecCanceled</strong></p></td>
<td><p>0x100</p></td>
<td><p>指示由于操作被取消而未保存记录。</p></td>
</tr>
<tr class="even">
<td><p><strong>adRecCantRelease</strong></p></td>
<td><p>0x400</p></td>
<td><p>指示由于现有记录被锁定而未保存新记录。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRecConcurrencyViolation</strong></p></td>
<td><p>0x800</p></td>
<td><p>指示由于开放式并发正在使用中而未保存记录。</p></td>
</tr>
<tr class="even">
<td><p><strong>adRecDBDeleted</strong></p></td>
<td><p>0x40000</p></td>
<td><p>指示已经从数据源删除记录。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRecDeleted</strong></p></td>
<td><p>0x4</p></td>
<td><p>指示已删除记录。</p></td>
</tr>
<tr class="even">
<td><p><strong>adRecIntegrityViolation</strong></p></td>
<td><p>0x1000</p></td>
<td><p>指示由于用户违反了完整性约束而未保存记录。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRecInvalid</strong></p></td>
<td><p>0x10</p></td>
<td><p>指示由于记录的书签无效而未保存记录。</p></td>
</tr>
<tr class="even">
<td><p><strong>adRecMaxChangesExceeded</strong></p></td>
<td><p>0x2000</p></td>
<td><p>指示由于挂起更改过多而未保存记录。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRecModified</strong></p></td>
<td><p>0x2</p></td>
<td><p>指示已修改记录。</p></td>
</tr>
<tr class="even">
<td><p><strong>adRecMultipleChanges</strong></p></td>
<td><p>0x40</p></td>
<td><p>指示由于该记录会影响多个记录而未保存该记录。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRecNew</strong></p></td>
<td><p>0x1</p></td>
<td><p>指示该记录是新的。</p></td>
</tr>
<tr class="even">
<td><p><strong>adRecObjectOpen</strong></p></td>
<td><p>0x4000</p></td>
<td><p>指示由于与某个打开的存储对象发生冲突而未保存记录。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRecOK</strong></p></td>
<td><p>0</p></td>
<td><p>指示已成功更新记录。</p></td>
</tr>
<tr class="even">
<td><p><strong>adRecOutOfMemory</strong></p></td>
<td><p>0x8000</p></td>
<td><p>指示由于计算机耗尽内存而未保存记录。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRecPendingChanges</strong></p></td>
<td><p>0x80</p></td>
<td><p>指示记录由于引用了某个待定插入而未保存。</p></td>
</tr>
<tr class="even">
<td><p><strong>adRecPermissionDenied</strong></p></td>
<td><p>0x10000</p></td>
<td><p>指示由于用户权限不足而未保存记录。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRecSchemaViolation</strong></p></td>
<td><p>0x20000</p></td>
<td><p>指示记录由于违反了基础数据库的结构而未保存。</p></td>
</tr>
<tr class="even">
<td><p><strong>adRecUnmodified</strong></p></td>
<td><p>0x8</p></td>
<td><p>指示未修改记录。</p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a>ADO/WFC 等效项

AdoEnums. RecordStatus。

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
<td><p>AdoEnums。已取消 RecordStatus</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums RecordStatus</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums RecordStatus</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums RecordStatus</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums RecordStatus</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums RecordStatus</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums RecordStatus 无效</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums RecordStatus</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums 修改的 RecordStatus</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums RecordStatus</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums RecordStatus</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums RecordStatus</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums RecordStatus</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums RecordStatus</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums RecordStatus</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums RecordStatus</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums RecordStatus</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums 不修改的 RecordStatus</p></td>
</tr>
</tbody>
</table>

