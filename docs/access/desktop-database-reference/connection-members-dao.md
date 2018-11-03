---
title: 连接成员 (DAO)
TOCTitle: Connection Members
ms:assetid: 94fc60ee-b6f2-cf08-b008-ed51bf7e7f8c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197681(v=office.15)
ms:contentKeyID: 48546422
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 39c1366a182f1757abdcbf4b36a19b553eb2b680
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25936761"
---
# <a name="connection-members-dao"></a>连接成员 (DAO)

**适用于**： Access 2013、 Office 2013

> [!NOTE]
> Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。 Connection 对象代表与 ODBC 数据库的连接（仅适用于 ODBCDirect 工作区）。
 
## <a name="methods"></a>方法

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong><a href="connection-cancel-method-dao.md">Cancel</a></strong></p></td>
<td><p>取消执行待定的异步方法调用（仅适用于 ODBCDirect 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="connection-close-method-dao.md">关闭</a></strong></p></td>
<td><p>关闭已打开的 <strong>Connection</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="connection-createquerydef-method-dao.md">CreateQueryDef</a></strong></p></td>
<td><p>创建新的 <strong><a href="querydef-object-dao.md">QueryDef</a></strong> 对象。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="connection-execute-method-dao.md">Execute</a></strong></p></td>
<td><p>对指定的对象运行动作查询，或执行 SQL 语句。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="connection-openrecordset-method-dao.md">OpenRecordset</a></strong></p></td>
<td><p>创建一个新的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象，并将其追加到 <strong>Recordsets</strong> 集合。</p></td>
</tr>
</tbody>
</table>


## <a name="properties"></a>属性

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong><a href="connection-connect-property-dao.md">连接</a></strong></p></td>
<td><p>设置或返回一个值，该值提供与已打开连接的源有关的信息。可读/写 <strong>String</strong> 类型。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="connection-database-property-dao.md">Database</a></strong></p></td>
<td><p>返回对应于此连接的 <strong><a href="database-object-dao.md">Database</a></strong> 对象（仅适用于 ODBCDirect 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="connection-name-property-dao.md">Name</a></strong></p></td>
<td><p>返回 <strong><a href="connection-object-dao.md">Connection</a></strong> 的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="connection-querydefs-property-dao.md">QueryDefs</a></strong></p></td>
<td><p>返回一个 <strong>QueryDefs</strong> 集合，该集合包含指定连接的所有 <strong>QueryDef</strong> 对象。只读。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="connection-querytimeout-property-dao.md">QueryTimeout</a></strong></p></td>
<td><p>设置或返回一个值，该值指定对 ODBC 数据源执行查询时发生超时错误之前等待的秒数。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="connection-recordsaffected-property-dao.md">RecordsAffected</a></strong></p></td>
<td><p>返回最近调用的 <strong><a href="connection-execute-method-dao.md">Execute</a></strong> 方法所影响的记录数。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="connection-recordsets-property-dao.md">Recordsets</a></strong></p></td>
<td><p>返回一个 <strong>Recordsets</strong> 集合，该集合包含指定连接的所有已打开的记录集。只读。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="connection-stillexecuting-property-dao.md">StillExecuting</a></strong></p></td>
<td><p>指示异步操作（即用 <strong>dbRunAsync</strong> 选项调用的方法）是否已执行完毕（仅适用于 ODBCDirect 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="connection-transactions-property-dao.md">事务</a></strong></p></td>
<td><p>返回一个值，该值指示对象是否支持事务。只读 <strong>Boolean</strong> 类型。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="connection-updatable-property-dao.md">Updatable</a></strong></p></td>
<td><p>返回一个值，该值指示是否可以更改 DAO 对象。 <strong>Boolean</strong> 类型，只读。</p></td>
</tr>
</tbody>
</table>

