---
title: CursorDriverEnum 枚举 (DAO)
TOCTitle: CursorDriverEnum enumeration
ms:assetid: d0312ece-c30a-7d61-d5f3-75edf0d0afc8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834707(v=office.15)
ms:contentKeyID: 48547832
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2f2bf52943a84d6f2e60891d63810bc0bbb6ecb3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295245"
---
# <a name="cursordriverenum-enumeration-dao"></a>CursorDriverEnum 枚举 (DAO)

**适用于**：Access 2013、Office 2013

指定游标驱动程序的类型。

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
<td><p>dbUseClientBatchCursor</p></td>
<td><p>第三章</p></td>
<td><p>总是使用 FoxPro 游标库。执行批更新需要此选项。</p></td>
</tr>
<tr class="even">
<td><p>dbUseDefaultCursor</p></td>
<td><p>-1</p></td>
<td><p>（默认值）如果服务器支持，则使用服务器端游标；否则使用 ODBC 游标库。</p></td>
</tr>
<tr class="odd">
<td><p>dbUseNoCursor</p></td>
<td><p>4</p></td>
<td><p>将所有游标 (即<strong>Recordset</strong>对象) 作为仅向前类型打开, 并且为行集大小为1的只读。 也称为&quot;是无游标查询。&quot;</p></td>
</tr>
<tr class="even">
<td><p>dbUseODBCCursor</p></td>
<td><p>1</p></td>
<td><p>总是使用 ODBC 游标库。对于小型结果集，此选项可提供更好的性能，但对于较大的结果集，性能会快速下降。</p></td>
</tr>
<tr class="odd">
<td><p>dbUseServerCursor</p></td>
<td><p>双面</p></td>
<td><p>总是使用服务器端游标。对于大多数大型操作，此选项可提供更好的性能，但可能造成网络拥塞。</p></td>
</tr>
</tbody>
</table>

