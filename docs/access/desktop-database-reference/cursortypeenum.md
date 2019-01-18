---
title: CursorTypeEnum （访问桌面数据库参考 （英文）
TOCTitle: CursorTypeEnum
ms:assetid: 7c5fa8b2-85ea-a0a7-41f1-a78650aced3e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249519(v=office.15)
ms:contentKeyID: 48545835
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0bcaaa1298f12d72c5e836dcfe1e74cdcda68d19
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28710788"
---
# <a name="cursortypeenum"></a>CursorTypeEnum

**适用于**： Access 2013、 Office 2013

指定在 [Recordset](recordset-object-ado.md) 对象中使用的游标的类型。

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
<td><p><strong>adOpenDynamic</strong></p></td>
<td><p>2</p></td>
<td><p>使用动态游标。其他用户所做的添加、更改和删除均可见，且允许在 <strong>Recordset</strong> 中移动所有类型，但提供程序不支持的书签除外。</p></td>
</tr>
<tr class="even">
<td><p><strong>adOpenForwardOnly</strong></p></td>
<td><p>0</p></td>
<td><p>默认值。使用仅向前型游标。与静态游标相似，但您只能在记录中向前滚动。这样可以在您仅需要在 <strong>Recordset</strong> 中通过一次时提高性能。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adOpenKeyset</strong></p></td>
<td><p>1</p></td>
<td><p>使用键集游标。与动态游标相似，不同的是：尽管其他用户删除的记录从您的 <strong>Recordset</strong> 不可访问，但您无法看到其他用户添加的记录。由其他用户所作的数据更改仍然可见。</p></td>
</tr>
<tr class="even">
<td><p><strong>为 adOpenStatic</strong></p></td>
<td><p>3</p></td>
<td><p>使用静态游标。您可用于查找数据或生成报表的记录集的静态副本。其他用户所做的添加、更改或删除不可见。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adOpenUnspecified</strong></p></td>
<td><p>-1</p></td>
<td><p>不指定游标类型。</p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a>ADO/WFC 等效值

包： **com.ms.wfc.data**

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
<td><p>AdoEnums.CursorType.DYNAMIC</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.CursorType.FORWARDONLY</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.CursorType.KEYSET</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.CursorType.STATIC</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.CursorType.UNSPECIFIED</p></td>
</tr>
</tbody>
</table>

