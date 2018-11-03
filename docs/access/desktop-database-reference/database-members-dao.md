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
# <a name="database-members-dao"></a><span data-ttu-id="44ea7-102">数据库成员 (DAO)</span><span class="sxs-lookup"><span data-stu-id="44ea7-102">Database members (DAO)</span></span>


<span data-ttu-id="44ea7-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="44ea7-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="44ea7-104">Database 对象代表打开的数据库。</span><span class="sxs-lookup"><span data-stu-id="44ea7-104">A Database object represents an open database.</span></span>

## <a name="methods"></a><span data-ttu-id="44ea7-105">方法</span><span class="sxs-lookup"><span data-stu-id="44ea7-105">Methods</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="44ea7-106">名称</span><span class="sxs-lookup"><span data-stu-id="44ea7-106">Name</span></span></p></th>
<th><p><span data-ttu-id="44ea7-107">说明</span><span class="sxs-lookup"><span data-stu-id="44ea7-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44ea7-108"><strong><a href="database-close-method-dao.md">关闭</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-108"><strong><a href="database-close-method-dao.md">Close</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-109">关闭已打开的 <strong>Database</strong>。</span><span class="sxs-lookup"><span data-stu-id="44ea7-109">Closes an open <strong>Database</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44ea7-110"><strong><a href="database-createproperty-method-dao.md">CreateProperty</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-110"><strong><a href="database-createproperty-method-dao.md">CreateProperty</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-p101">创建一个新的用户定义的 <strong><a href="property-object-dao.md">Property</a></strong> 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="44ea7-p101">Creates a new user-defined <strong><a href="property-object-dao.md">Property</a></strong> object (Microsoft Access workspaces only). .</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44ea7-113"><strong><a href="database-createquerydef-method-dao.md">CreateQueryDef</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-113"><strong><a href="database-createquerydef-method-dao.md">CreateQueryDef</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-114">创建新的 <strong><a href="querydef-object-dao.md">QueryDef</a></strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="44ea7-114">Creates a new <strong><a href="querydef-object-dao.md">QueryDef</a></strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44ea7-115"><strong><a href="database-createrelation-method-dao.md">CreateRelation</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-115"><strong><a href="database-createrelation-method-dao.md">CreateRelation</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-p102">创建一个新的 <strong><a href="relation-object-dao.md">Relation</a></strong> 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="44ea7-p102">Creates a new <strong><a href="relation-object-dao.md">Relation</a></strong> object (Microsoft Access workspaces only). .</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44ea7-118"><strong><a href="database-createtabledef-method-dao.md">CreateTableDef</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-118"><strong><a href="database-createtabledef-method-dao.md">CreateTableDef</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-p103">创建一个新的 <strong><a href="tabledef-object-dao.md">TableDef</a></strong> 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="44ea7-p103">Creates a new <strong><a href="tabledef-object-dao.md">TableDef</a></strong> object (Microsoft Access workspaces only). .</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44ea7-121"><strong><a href="database-execute-method-dao.md">Execute</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-121"><strong><a href="database-execute-method-dao.md">Execute</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-122">对指定的对象运行动作查询，或执行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="44ea7-122">Runs an action query or executes an SQL statement on the specified object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44ea7-123"><strong><a href="database-makereplica-method-dao.md">MakeReplica</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-123"><strong><a href="database-makereplica-method-dao.md">MakeReplica</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-124">根据另一个数据库副本制作一个新的副本（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="44ea7-124">Makes a new replica from another database replica (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44ea7-125"><strong><a href="database-newpassword-method-dao.md">新密码</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-125"><strong><a href="database-newpassword-method-dao.md">NewPassword</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-126">更改现有 Microsoft Access 数据库引擎数据库的密码（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="44ea7-126">Changes the password of an existing Microsoft Access database engine database (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44ea7-127"><strong><a href="database-openrecordset-method-dao.md">OpenRecordset</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-127"><strong><a href="database-openrecordset-method-dao.md">OpenRecordset</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-128">创建一个新的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象，并将其追加到 <strong>Recordsets</strong> 集合。</span><span class="sxs-lookup"><span data-stu-id="44ea7-128">Creates a new <strong><a href="recordset-object-dao.md">Recordset</a></strong> object and appends it to the <strong>Recordsets</strong> collection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44ea7-129"><strong><a href="database-populatepartial-method-dao.md">PopulatePartial</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-129"><strong><a href="database-populatepartial-method-dao.md">PopulatePartial</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-p104">将部分副本中的任何更改与完全副本同步，清除部分副本中的所有记录，然后根据当前副本筛选器重新填充部分副本。（仅适用于 Microsoft Access 数据库引擎数据库。）</span><span class="sxs-lookup"><span data-stu-id="44ea7-p104">Synchronizes any changes in a partial replica with the full replica, clears all records in the partial replica, and then repopulates the partial replica based on the current replica filters. (Microsoft Access database engine databases only.).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44ea7-132"><strong><a href="database-synchronize-method-dao.md">同步</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-132"><strong><a href="database-synchronize-method-dao.md">Synchronize</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-p105">同步两个副本。（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="44ea7-p105">Synchronizes two replicas. (Microsoft Access workspaces only).</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="properties"></a><span data-ttu-id="44ea7-135">属性</span><span class="sxs-lookup"><span data-stu-id="44ea7-135">Properties</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="44ea7-136">名称</span><span class="sxs-lookup"><span data-stu-id="44ea7-136">Name</span></span></p></th>
<th><p><span data-ttu-id="44ea7-137">说明</span><span class="sxs-lookup"><span data-stu-id="44ea7-137">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44ea7-138"><strong><a href="database-collatingorder-property-dao.md">CollatingOrder</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-138"><strong><a href="database-collatingorder-property-dao.md">CollatingOrder</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-p106">返回一个值，该值指定用于字符串比较或排序的文本中排序次序的序列（仅适用于 Microsoft Access 工作区）。只读 <strong>Long</strong>。</span><span class="sxs-lookup"><span data-stu-id="44ea7-p106">Returns a value that specifies the sequence of the sort order in text for string comparison or sorting (Microsoft Access workspaces only). Read-only <strong>Long</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44ea7-141"><strong><a href="database-connect-property-dao.md">Connect</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-141"><strong><a href="database-connect-property-dao.md">Connect</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-p107">设置或返回一个值，该值提供与已打开数据库的源有关的信息。可读/写 <strong>String</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="44ea7-p107">Sets or returns a value that provides information about the source an open database. Read/write <strong>String</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44ea7-144"><strong><a href="database-connection-property-dao.md">Connection</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-144"><strong><a href="database-connection-property-dao.md">Connection</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-145"><strong>注意</strong>： Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="44ea7-145"><strong>NOTE</strong>: ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="44ea7-146">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="44ea7-146">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></p>
<p><span data-ttu-id="44ea7-147">返回与数据库对应的 <strong><a href="connection-object-dao.md">Connection</a></strong> 对象（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="44ea7-147">Returns the <strong><a href="connection-object-dao.md">Connection</a></strong> object that corresponds to the database (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44ea7-148"><strong><a href="database-containers-property-dao.md">Containers</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-148"><strong><a href="database-containers-property-dao.md">Containers</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-p109">返回一个 <strong>Containers</strong> 集合，该集合代表指定数据库中的所有 <strong>Container</strong> 对象。只读。</span><span class="sxs-lookup"><span data-stu-id="44ea7-p109">Returns a <strong>Containers</strong> collection that represents all of the <strong>Container</strong> objects in the specifed database. Read-only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44ea7-151"><strong><a href="database-designmasterid-property-dao.md">DesignMasterID</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-151"><strong><a href="database-designmasterid-property-dao.md">DesignMasterID</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-152">设置或返回一个 16 字节值，该值唯一地标识副本集中的设计母版（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="44ea7-152">Sets or returns a 16-byte value that uniquely identifies the Design Master in a replica set (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44ea7-153"><strong><a href="database-name-property-dao.md">Name</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-153"><strong><a href="database-name-property-dao.md">Name</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-p110">返回指定对象的名称。只读 <strong>String</strong>。</span><span class="sxs-lookup"><span data-stu-id="44ea7-p110">Returns the name of the specified object. Read-only <strong>String</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44ea7-156"><strong><a href="database-properties-property-dao.md">属性</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-156"><strong><a href="database-properties-property-dao.md">Properties</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-p111">返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。只读。</span><span class="sxs-lookup"><span data-stu-id="44ea7-p111">Returns the <strong><a href="properties-collection-dao.md">Properties</a></strong> collection of the specified object. Read-only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44ea7-159"><strong><a href="database-querydefs-property-dao.md">QueryDefs</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-159"><strong><a href="database-querydefs-property-dao.md">QueryDefs</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-p112">返回一个 <strong>QueryDefs</strong> 集合，该集合包含指定数据库的所有 <strong>QueryDef</strong> 对象。只读。</span><span class="sxs-lookup"><span data-stu-id="44ea7-p112">Returns a <strong>QueryDefs</strong> collection that contains all of the <strong>QueryDef</strong> objects of the specified database. Read-only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44ea7-162"><strong><a href="database-querytimeout-property-dao.md">QueryTimeout</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-162"><strong><a href="database-querytimeout-property-dao.md">QueryTimeout</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-163">设置或返回一个值，该值指定对 ODBC 数据源执行查询时发生超时错误之前等待的秒数。</span><span class="sxs-lookup"><span data-stu-id="44ea7-163">Sets or returns a value that specifies the number of seconds to wait before a timeout error occurs when a query is executed on an ODBC data source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44ea7-164"><strong><a href="database-recordsaffected-property-dao.md">RecordsAffected</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-164"><strong><a href="database-recordsaffected-property-dao.md">RecordsAffected</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-165">返回最近调用的 <strong><a href="connection-execute-method-dao.md">Execute</a></strong> 方法所影响的记录数。</span><span class="sxs-lookup"><span data-stu-id="44ea7-165">Returns the number of records affected by the most recently invoked <strong><a href="connection-execute-method-dao.md">Execute</a></strong> method.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44ea7-166"><strong><a href="database-recordsets-property-dao.md">Recordsets</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-166"><strong><a href="database-recordsets-property-dao.md">Recordsets</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-p113">返回一个 <strong>Recordsets</strong> 集合，该集合包含指定数据库的所有已打开的记录集。只读。</span><span class="sxs-lookup"><span data-stu-id="44ea7-p113">Returns a <strong>Recordsets</strong> collection that contains all of the open recordsets in the for the specified database. Read-only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44ea7-169"><strong><a href="database-relations-property-dao.md">Relations</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-169"><strong><a href="database-relations-property-dao.md">Relations</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-p114">返回一个 <strong>Relations</strong> 集合，该集合包含指定数据库的所有存储的 <strong>Relation</strong> 对象。只读。</span><span class="sxs-lookup"><span data-stu-id="44ea7-p114">Returns a <strong>Relations</strong> collection that contains all of the stored <strong>Relation</strong> objects for the specified database. Read-only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44ea7-172"><strong><a href="database-replicaid-property-dao.md">ReplicaID</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-172"><strong><a href="database-replicaid-property-dao.md">ReplicaID</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-173">返回一个 16 字节的值，该值唯一标识数据库副本（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="44ea7-173">Returns a 16-byte value that uniquely identifies a database replica (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44ea7-174"><strong><a href="database-tabledefs-property-dao.md">TableDefs</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-174"><strong><a href="database-tabledefs-property-dao.md">TableDefs</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-p115">返回一个 <strong>TableDefs</strong> 集合，该集合包含指定数据库中存储的所有 <strong>TableDef</strong> 对象。只读。</span><span class="sxs-lookup"><span data-stu-id="44ea7-p115">Returns a <strong>TableDefs</strong> collection that contains all of the <strong>TableDef</strong> objects stored in the specified database. Read-only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44ea7-177"><strong><a href="database-transactions-property-dao.md">事务</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-177"><strong><a href="database-transactions-property-dao.md">Transactions</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-p116">返回一个值，该值指示对象是否支持事务。只读 <strong>Boolean</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="44ea7-p116">Returns a value that indicates whether an object supports transactions. Read-only <strong>Boolean</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44ea7-180"><strong><a href="database-updatable-property-dao.md">Updatable</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-180"><strong><a href="database-updatable-property-dao.md">Updatable</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-p117">返回一个值，该值指示是否可以更改 DAO 对象。只读 <strong>Boolean</strong>。</span><span class="sxs-lookup"><span data-stu-id="44ea7-p117">Returns a value that indicates whether you can change a DAO object. Read-only <strong>Boolean</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44ea7-183"><strong><a href="database-version-property-dao.md">版本</a></strong></span><span class="sxs-lookup"><span data-stu-id="44ea7-183"><strong><a href="database-version-property-dao.md">Version</a></strong></span></span></p></td>
<td><p><span data-ttu-id="44ea7-p118">在 Microsoft Access 工作区中，返回创建数据库的 Microsoft Jet 或 Microsoft Access 数据库引擎的版本。 <strong>String</strong> 类型，只读。</span><span class="sxs-lookup"><span data-stu-id="44ea7-p118">In a Microsoft Access workspace, returns the vesion of the Microsoft Jet or Microsoft Access database engine that created the database. Read-only <strong>String</strong>.</span></span></p></td>
</tr>
</tbody>
</table>

