---
title: CursorDriverEnum Enumeration (DAO)
TOCTitle: CursorDriverEnum Enumeration
ms:assetid: d0312ece-c30a-7d61-d5f3-75edf0d0afc8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834707(v=office.15)
ms:contentKeyID: 48547832
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 25d264c1e91982231e025f17c00db79e47a1d5c6
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25880738"
---
# <a name="cursordriverenum-enumeration-dao"></a>CursorDriverEnum Enumeration (DAO)


**适用于**： Access 2013、 Office 2013

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
<td><p>3</p></td>
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
<td><p>打开所有游标 （即， <strong>Recordset</strong>对象） 作为仅向前类型，只读的行集大小为 1。 也称为&quot;是无游标查询。&quot;</p></td>
</tr>
<tr class="even">
<td><p>dbUseODBCCursor</p></td>
<td><p>1</p></td>
<td><p>总是使用 ODBC 游标库。对于小型结果集，此选项可提供更好的性能，但对于较大的结果集，性能会快速下降。</p></td>
</tr>
<tr class="odd">
<td><p>dbUseServerCursor</p></td>
<td><p>2</p></td>
<td><p>总是使用服务器端游标。对于大多数大型操作，此选项可提供更好的性能，但可能造成网络拥塞。</p></td>
</tr>
</tbody>
</table>

