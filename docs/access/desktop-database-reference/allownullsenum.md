---
title: AllowNullsEnum （访问桌面数据库参考 （英文）
TOCTitle: AllowNullsEnum
ms:assetid: 7bb42b38-6b3b-5930-b1d7-16323a3bdf37
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249515(v=office.15)
ms:contentKeyID: 48545819
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 04e67584e0f0c2eeb5a12e34fdf98a84cc1da852
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467201"
---
# <a name="allownullsenum"></a>AllowNullsEnum


**适用于**： Access 2013 |Office 2013

指定是否对含有 null 值的记录进行索引。

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
<td><p><strong>adIndexNullsAllow</strong></p></td>
<td><p>0</p></td>
<td><p>索引允许键列为 null 的项。如果 null 值输入键列中，则该项插入索引中。</p></td>
</tr>
<tr class="even">
<td><p><strong>adIndexNullsDisallow</strong></p></td>
<td><p>1</p></td>
<td><p>默认值。索引不允许键列为 null 的项。如果 null 值输入键列中，则会发生错误。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adIndexNullsIgnore</strong></p></td>
<td><p>2</p></td>
<td><p>索引不插入包含 null 键的项。如果 null 值输入键列中，则该项被忽略并且不会发生错误。</p></td>
</tr>
<tr class="even">
<td><p><strong>adIndexNullsIgnoreAny</strong></p></td>
<td><p>4</p></td>
<td><p>索引不插入其中某个键列含有 null 值的项。对于带有多列键的索引，如果 null 值输入某个列中，则该项被忽略并且不会发生错误。</p></td>
</tr>
</tbody>
</table>

