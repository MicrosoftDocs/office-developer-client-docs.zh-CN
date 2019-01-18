---
title: RecordTypeEnum （访问桌面数据库参考 （英文）
TOCTitle: RecordTypeEnum
ms:assetid: 7edd6508-1507-4649-f1aa-03f1873ef09c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249534(v=office.15)
ms:contentKeyID: 48545890
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c95e4b78a3e2259c3dc5961e87b98ca65ea55692
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28704915"
---
# <a name="recordtypeenum"></a>RecordTypeEnum

**适用于**： Access 2013、 Office 2013

指定 [Record](record-object-ado.md) 对象的类型。

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


### <a name="adowfc-equivalent"></a>ADO/WFC 等效值

这些常量没有 ADO/WFC 等效值。

