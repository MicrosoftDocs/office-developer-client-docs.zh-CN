---
title: 数据库成员 (DAO)
TOCTitle: Database Members
ms:assetid: 68b0c069-8ed9-64dc-ea68-0d323e24c79c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195257(v=office.15)
ms:contentKeyID: 48545392
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: aa627d7c44700041209b9884374e57f7e3fa6c28
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25937097"
---
# <a name="database-members-dao"></a>数据库成员 (DAO)


**适用于**： Access 2013、 Office 2013

Database 对象代表打开的数据库。

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
<td><p><strong><a href="database-close-method-dao.md">关闭</a></strong></p></td>
<td><p>关闭已打开的 <strong>Database</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="database-createproperty-method-dao.md">CreateProperty</a></strong></p></td>
<td><p>创建一个新的用户定义的 <strong><a href="property-object-dao.md">Property</a></strong> 对象（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="database-createquerydef-method-dao.md">CreateQueryDef</a></strong></p></td>
<td><p>创建新的 <strong><a href="querydef-object-dao.md">QueryDef</a></strong> 对象。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="database-createrelation-method-dao.md">CreateRelation</a></strong></p></td>
<td><p>创建一个新的 <strong><a href="relation-object-dao.md">Relation</a></strong> 对象（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="database-createtabledef-method-dao.md">CreateTableDef</a></strong></p></td>
<td><p>创建一个新的 <strong><a href="tabledef-object-dao.md">TableDef</a></strong> 对象（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="database-execute-method-dao.md">Execute</a></strong></p></td>
<td><p>对指定的对象运行动作查询，或执行 SQL 语句。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="database-makereplica-method-dao.md">MakeReplica</a></strong></p></td>
<td><p>根据另一个数据库副本制作一个新的副本（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="database-newpassword-method-dao.md">新密码</a></strong></p></td>
<td><p>更改现有 Microsoft Access 数据库引擎数据库的密码（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="database-openrecordset-method-dao.md">OpenRecordset</a></strong></p></td>
<td><p>创建一个新的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象，并将其追加到 <strong>Recordsets</strong> 集合。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="database-populatepartial-method-dao.md">PopulatePartial</a></strong></p></td>
<td><p>将部分副本中的任何更改与完全副本同步，清除部分副本中的所有记录，然后根据当前副本筛选器重新填充部分副本。（仅适用于 Microsoft Access 数据库引擎数据库。）</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="database-synchronize-method-dao.md">同步</a></strong></p></td>
<td><p>同步两个副本。（仅适用于 Microsoft Access 工作区）。</p></td>
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
<td><p><strong><a href="database-collatingorder-property-dao.md">CollatingOrder</a></strong></p></td>
<td><p>返回一个值，该值指定用于字符串比较或排序的文本中排序次序的序列（仅适用于 Microsoft Access 工作区）。只读 <strong>Long</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="database-connect-property-dao.md">Connect</a></strong></p></td>
<td><p>设置或返回一个值，该值提供与已打开数据库的源有关的信息。可读/写 <strong>String</strong> 类型。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="database-connection-property-dao.md">Connection</a></strong></p></td>
<td><p><strong>注意</strong>： Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</p>
<p>返回与数据库对应的 <strong><a href="connection-object-dao.md">Connection</a></strong> 对象（仅适用于 ODBCDirect 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="database-containers-property-dao.md">Containers</a></strong></p></td>
<td><p>返回一个 <strong>Containers</strong> 集合，该集合代表指定数据库中的所有 <strong>Container</strong> 对象。只读。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="database-designmasterid-property-dao.md">DesignMasterID</a></strong></p></td>
<td><p>设置或返回一个 16 字节值，该值唯一地标识副本集中的设计母版（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="database-name-property-dao.md">Name</a></strong></p></td>
<td><p>返回指定对象的名称。只读 <strong>String</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="database-properties-property-dao.md">属性</a></strong></p></td>
<td><p>返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。只读。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="database-querydefs-property-dao.md">QueryDefs</a></strong></p></td>
<td><p>返回一个 <strong>QueryDefs</strong> 集合，该集合包含指定数据库的所有 <strong>QueryDef</strong> 对象。只读。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="database-querytimeout-property-dao.md">QueryTimeout</a></strong></p></td>
<td><p>设置或返回一个值，该值指定对 ODBC 数据源执行查询时发生超时错误之前等待的秒数。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="database-recordsaffected-property-dao.md">RecordsAffected</a></strong></p></td>
<td><p>返回最近调用的 <strong><a href="connection-execute-method-dao.md">Execute</a></strong> 方法所影响的记录数。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="database-recordsets-property-dao.md">Recordsets</a></strong></p></td>
<td><p>返回一个 <strong>Recordsets</strong> 集合，该集合包含指定数据库的所有已打开的记录集。只读。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="database-relations-property-dao.md">Relations</a></strong></p></td>
<td><p>返回一个 <strong>Relations</strong> 集合，该集合包含指定数据库的所有存储的 <strong>Relation</strong> 对象。只读。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="database-replicaid-property-dao.md">ReplicaID</a></strong></p></td>
<td><p>返回一个 16 字节的值，该值唯一标识数据库副本（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="database-tabledefs-property-dao.md">TableDefs</a></strong></p></td>
<td><p>返回一个 <strong>TableDefs</strong> 集合，该集合包含指定数据库中存储的所有 <strong>TableDef</strong> 对象。只读。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="database-transactions-property-dao.md">事务</a></strong></p></td>
<td><p>返回一个值，该值指示对象是否支持事务。只读 <strong>Boolean</strong> 类型。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="database-updatable-property-dao.md">Updatable</a></strong></p></td>
<td><p>返回一个值，该值指示是否可以更改 DAO 对象。只读 <strong>Boolean</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="database-version-property-dao.md">版本</a></strong></p></td>
<td><p>在 Microsoft Access 工作区中，返回创建数据库的 Microsoft Jet 或 Microsoft Access 数据库引擎的版本。 <strong>String</strong> 类型，只读。</p></td>
</tr>
</tbody>
</table>

