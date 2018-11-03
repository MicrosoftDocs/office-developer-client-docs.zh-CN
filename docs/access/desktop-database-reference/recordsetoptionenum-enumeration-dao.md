---
title: RecordsetOptionEnum 枚举 (DAO)
TOCTitle: RecordsetOptionEnum Enumeration
ms:assetid: 3a9d8664-dcb6-cb60-7cf6-e229eb699ef1
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192649(v=office.15)
ms:contentKeyID: 48544266
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 75b69adbe8c3851afa33f729a108ac579f84c683
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25947138"
---
# <a name="recordsetoptionenum-enumeration-dao"></a>RecordsetOptionEnum 枚举 (DAO)


**适用于**： Access 2013、 Office 2013

与 **OpenRecordset** 方法一起用来指定新 **Recordset** 对象的特征。

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
<td><p>dbAppendOnly</p></td>
<td><p>8</p></td>
<td><p>允许用户向动态集内添加新记录，但是禁止用户读取现有记录。</p></td>
</tr>
<tr class="even">
<td><p>dbConsistent</p></td>
<td><p>32</p></td>
<td><p>仅向那些将不影响动态集内其他记录的字段应用更新（仅适用于动态集类型和快照类型）。</p></td>
</tr>
<tr class="odd">
<td><p>dbDenyRead</p></td>
<td><p>2</p></td>
<td><p>防止其他用户读取记录集记录 （仅限表类型）。</p></td>
</tr>
<tr class="even">
<td><p>dbDenyWrite</p></td>
<td><p>1</p></td>
<td><p>禁止其他用户更改记录集记录。</p></td>
</tr>
<tr class="odd">
<td><p>一设置</p></td>
<td><p>2048</p></td>
<td><p>在不首先调用 SQLPrepare ODBC 函数的情况下执行查询。</p></td>
</tr>
<tr class="even">
<td><p>dbFailOnError</p></td>
<td><p>128</p></td>
<td><p>在出错时回滚更新。</p></td>
</tr>
<tr class="odd">
<td><p>dbForwardOnly</p></td>
<td><p>256</p></td>
<td><p>创建仅向前型滚动快照类型的记录集（仅适用于快照类型）。</p></td>
</tr>
<tr class="even">
<td><p>dbInconsistent</p></td>
<td><p>16</p></td>
<td><p>向所有的动态集字段应用更新，即使其他记录受到影响也是如此（仅适用于动态集类型和快照类型）。</p></td>
</tr>
<tr class="odd">
<td><p>dbReadOnly</p></td>
<td><p>4</p></td>
<td><p>以只读方式打开记录集。</p></td>
</tr>
<tr class="even">
<td><p>dbRunAsync</p></td>
<td><p>1024</p></td>
<td><p>异步执行查询。</p></td>
</tr>
<tr class="odd">
<td><p>dbSeeChanges</p></td>
<td><p>512</p></td>
<td><p>如果其他用户更改您正编辑的数据，则生成运行时错误（仅适用于动态集类型）。</p></td>
</tr>
<tr class="even">
<td><p>dbSQLPassThrough</p></td>
<td><p>64</p></td>
<td><p>向 ODBC 数据库发送 SQL 语句（仅适用于快照类型）。</p></td>
</tr>
</tbody>
</table>

