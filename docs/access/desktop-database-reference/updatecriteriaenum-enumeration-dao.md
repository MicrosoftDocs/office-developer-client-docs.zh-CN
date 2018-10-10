---
title: UpdateCriteriaEnum Enumeration (DAO)
TOCTitle: UpdateCriteriaEnum Enumeration
ms:assetid: 1f83a0c6-bdc8-9c3e-380b-524f611f6476
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845853(v=office.15)
ms:contentKeyID: 48543644
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7dc671458d53f6e40e27ff2dd338f010c09dc5ba
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466623"
---
# <a name="updatecriteriaenum-enumeration-dao"></a>UpdateCriteriaEnum Enumeration (DAO)


**适用于**： Access 2013 |Office 2013

与 **UpdateOptions** 方法一起用来指定如何构造批更新。

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
<td><p>dbCriteriaAllCols</p></td>
<td><p>4</p></td>
<td><p>在 where 子句中使用键列和所有列。</p></td>
</tr>
<tr class="even">
<td><p>dbCriteriaDeleteInsert</p></td>
<td><p>16</p></td>
<td><p>对于每个已修改行都使用一对 DELETE 和 INSERT 语句。</p></td>
</tr>
<tr class="odd">
<td><p>dbCriteriaKey</p></td>
<td><p>1</p></td>
<td><p>仅在 where 子句中使用键列。</p></td>
</tr>
<tr class="even">
<td><p>dbCriteriaModValues</p></td>
<td><p>2</p></td>
<td><p>在 where 子句中使用键列和所有已更新列。</p></td>
</tr>
<tr class="odd">
<td><p>dbCriteriaTimestamp</p></td>
<td><p>8</p></td>
<td><p>仅使用可用的时间戳列（如果结果集内没有时间戳列，将生成运行时错误）。</p></td>
</tr>
<tr class="even">
<td><p>将使用 dbCriteriaUpdate</p></td>
<td><p>32</p></td>
<td><p>对于每个已修改行都使用一个 UPDATE 语句。</p></td>
</tr>
</tbody>
</table>

