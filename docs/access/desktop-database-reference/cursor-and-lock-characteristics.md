---
title: 游标和锁定特征
TOCTitle: Cursor and lock characteristics
ms:assetid: 5f8b6700-14f6-d342-42f6-cc8e89c71a1a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249347(v=office.15)
ms:contentKeyID: 48545164
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 41a42aa3b0c49a5d871fa7b079a26c7d8076116a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295287"
---
# <a name="cursor-and-lock-characteristics"></a>游标和锁定特征

**适用于**：Access 2013、Office 2013

尽管游标的特征依赖于提供程序的功能，但以下优点和缺点通常适用于各种游标和锁定。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>游标或锁定类型</p></th>
<th><p>优点</p></th>
<th><p>缺点</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>adOpenForwardOnly</strong></p></td>
<td><p></p>
<ul>
<li><p>资源要求低</p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p>不能向后滚动</p></li>
<li><p>没有数据并发</p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>adOpenStatic</strong></p></td>
<td><p></p>
<ul>
<li><p>可</p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p>没有数据并发</p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td><p><strong>adOpenKeyset</strong></p></td>
<td><p></p>
<ul>
<li><p>有数据并发</p></li>
<li><p>可</p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p>资源要求高</p></li>
<li><p>在连接中断的方案中不可用</p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>adOpenDynamic</strong></p></td>
<td><p></p>
<ul>
<li><p>高数据并发</p></li>
<li><p>可</p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p>资源要求最高</p></li>
<li><p>在连接中断的方案中不可用</p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td><p><strong>adLockReadOnly</strong></p></td>
<td><p></p>
<ul>
<li><p>资源要求低</p></li>
<li><p>可伸缩性高</p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p>无法通过游标更新数据</p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>adLockBatchOptimistic</strong></p></td>
<td><p></p>
<ul>
<li><p>批更新</p></li>
<li><p>允许连接中断的方案</p></li>
<li><p>其他用户可以访问数据</p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p>多个用户可以同时更改数据</p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td><p><strong>adLockPessimistic</strong></p></td>
<td><p></p>
<ul>
<li><p>锁定时其他用户不能更改数据</p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p>锁定时防止其他用户访问数据</p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>adLockOptimistic</strong></p></td>
<td><p></p>
<ul>
<li><p>其他用户可以访问数据</p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p>多个用户可以同时更改数据</p></li>
</ul>
<p></p></td>
</tr>
</tbody>
</table>

