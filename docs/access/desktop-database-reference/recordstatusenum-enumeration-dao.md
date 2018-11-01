---
title: RecordStatusEnum Enumeration (DAO)
TOCTitle: RecordStatusEnum Enumeration
ms:assetid: bf4492f2-8d8f-f10f-7a3c-d6296d2ce96b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822784(v=office.15)
ms:contentKeyID: 48547483
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c2d96c359a913660c146f4850a1846554e3b6856
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25875117"
---
# <a name="recordstatusenum-enumeration-dao"></a>RecordStatusEnum Enumeration (DAO)


**适用于**： Access 2013、 Office 2013

与 **RecordStatus** 属性一起用来指示当前记录的更新状态（如果当前记录属于批更新的一部分）。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>值</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dbRecordDBDeleted</p></td>
<td><p>4</p></td>
<td><p>已在本地和数据库中删除该记录。</p></td>
</tr>
<tr class="even">
<td><p>dbRecordDeleted</p></td>
<td><p>3</p></td>
<td><p>已删除该记录，但是尚未在数据库中删除它。</p></td>
</tr>
<tr class="odd">
<td><p>dbRecordModified</p></td>
<td><p>1</p></td>
<td><p>已修改该记录，但是尚未在数据库中更新它。</p></td>
</tr>
<tr class="even">
<td><p>dbRecordNew</p></td>
<td><p>2</p></td>
<td><p>已经用 <strong>AddNew</strong> 方法插入了该记录，但是尚未将其插入到数据库中。</p></td>
</tr>
<tr class="odd">
<td><p>dbRecordUnmodified</p></td>
<td><p>0</p></td>
<td><p>（默认值）该记录尚未修改，或者已更新成功。</p></td>
</tr>
</tbody>
</table>

