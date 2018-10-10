---
title: RecordTypeEnum （访问桌面数据库参考 （英文）
TOCTitle: RecordTypeEnum
ms:assetid: 7edd6508-1507-4649-f1aa-03f1873ef09c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249534(v=office.15)
ms:contentKeyID: 48545890
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4eedd04b630e0cc1cf855eefe09bd071dfbbbb50
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468132"
---
# <a name="recordtypeenum"></a>RecordTypeEnum


**适用于**： Access 2013 |Office 2013

指定 [Record](record-object-ado.md) 对象的类型。

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
<td><p><strong>为 adSimpleRecord</strong></p></td>
<td><p>0</p></td>
<td><p>指示一个<em>简单</em>记录（不包含子节点）。</p></td>
</tr>
<tr class="even">
<td><p><strong>adCollectionRecord</strong></p></td>
<td><p>1</p></td>
<td><p>指示一个<em>集合</em>记录（包含子节点）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRecordUnknown</strong></p></td>
<td><p>-1</p></td>
<td><p>指示此 <strong>Record</strong> 的类型未知。</p></td>
</tr>
<tr class="even">
<td><p><strong>为 adStructDoc</strong></p></td>
<td><p>2</p></td>
<td><p>指示代表 COM 结构化文档的特殊种类的<em>集合</em>记录。</p></td>
</tr>
</tbody>
</table>


**ADO/WFC 等效值**

这些常量没有 ADO/WFC 等效值。

