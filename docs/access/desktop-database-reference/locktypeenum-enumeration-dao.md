---
title: LockTypeEnum Enumeration (DAO)
TOCTitle: LockTypeEnum Enumeration
ms:assetid: d40f984c-b37f-72f7-7b05-752f106b6029
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834802(v=office.15)
ms:contentKeyID: 48547925
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 771ce7a5a7f0a6721703953029b7bc8de9f0f251
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25936572"
---
# <a name="locktypeenum-enumeration-dao"></a>LockTypeEnum Enumeration (DAO)


**适用于**： Access 2013、 Office 2013

指定在打开记录集时使用的记录锁定的类型。

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
<td><p>dbOptimistic</p></td>
<td><p>3</p></td>
<td><p>基于记录 ID 的开放式并发。游标对新旧记录中的记录 ID 进行比较，以确定自上次访问该记录以来是否进行过任何更改。</p></td>
</tr>
<tr class="even">
<td><p>dbOptimisticBatch</p></td>
<td><p>5</p></td>
<td><p>启用批处理开放式更新（仅适用于 ODBCDirect 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p>dbOptimisticValue</p></td>
<td><p>1</p></td>
<td><p>基于记录值的开放式并发。游标对新旧记录中的数据值进行比较，以确定自上次访问该记录以来是否进行过任何更改。（仅适用于 ODBCDirect 工作区）</p>

> [!NOTE]
> Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。


</td>
</tr>
<tr class="even">
<td><p>dbPessimistic</p></td>
<td><p>2</p></td>
<td><p>保守式并发。游标使用足以确保对记录进行更新的最低级别的锁定。</p></td>
</tr>
</tbody>
</table>

