---
title: Connection Members (DAO)
TOCTitle: Connection Members
ms:assetid: 94fc60ee-b6f2-cf08-b008-ed51bf7e7f8c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197681(v=office.15)
ms:contentKeyID: 48546422
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d797852512becee7f076298750495205cd09bf86
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25861497"
---
# <a name="connection-members-dao"></a><span data-ttu-id="a5643-102">Connection Members (DAO)</span><span class="sxs-lookup"><span data-stu-id="a5643-102">Connection Members (DAO)</span></span>

<span data-ttu-id="a5643-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="a5643-103">**Applies to**: Access 2013 | Office 2013</span></span>

> [!NOTE]
> <span data-ttu-id="a5643-104">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="a5643-104">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="a5643-105">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="a5643-105">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span> <span data-ttu-id="a5643-106">Connection 对象代表与 ODBC 数据库的连接（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="a5643-106">A Connection object represents a connection to an ODBC database (ODBCDirect workspaces only).</span></span>
 

## <a name="methods"></a><span data-ttu-id="a5643-107">方法</span><span class="sxs-lookup"><span data-stu-id="a5643-107">Methods</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="a5643-108">名称</span><span class="sxs-lookup"><span data-stu-id="a5643-108">Name</span></span></p></th>
<th><p><span data-ttu-id="a5643-109">说明</span><span class="sxs-lookup"><span data-stu-id="a5643-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5643-110"><strong><a href="connection-cancel-method-dao.md">Cancel</a></strong></span><span class="sxs-lookup"><span data-stu-id="a5643-110"><strong><a href="connection-cancel-method-dao.md">Cancel</a></strong></span></span></p></td>
<td><p></p>

<br/>


<p><span data-ttu-id="a5643-111">取消执行待定的异步方法调用（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="a5643-111">Cancels execution of a pending asynchronous method call (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5643-112"><strong><a href="connection-close-method-dao.md">关闭</a></strong></span><span class="sxs-lookup"><span data-stu-id="a5643-112"><strong><a href="connection-close-method-dao.md">Close</a></strong></span></span></p></td>
<td><p><span data-ttu-id="a5643-113">关闭已打开的 <strong>Connection</strong>。</span><span class="sxs-lookup"><span data-stu-id="a5643-113">Closes an open <strong>Connection</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5643-114"><strong><a href="connection-createquerydef-method-dao.md">CreateQueryDef</a></strong></span><span class="sxs-lookup"><span data-stu-id="a5643-114"><strong><a href="connection-createquerydef-method-dao.md">CreateQueryDef</a></strong></span></span></p></td>
<td><p><span data-ttu-id="a5643-115">创建新的 <strong><a href="querydef-object-dao.md">QueryDef</a></strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="a5643-115">Creates a new <strong><a href="querydef-object-dao.md">QueryDef</a></strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5643-116"><strong><a href="connection-execute-method-dao.md">Execute</a></strong></span><span class="sxs-lookup"><span data-stu-id="a5643-116"><strong><a href="connection-execute-method-dao.md">Execute</a></strong></span></span></p></td>
<td><p><span data-ttu-id="a5643-117">对指定的对象运行动作查询，或执行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="a5643-117">Runs an action query or executes an SQL statement on the specified object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5643-118"><strong><a href="connection-openrecordset-method-dao.md">OpenRecordset</a></strong></span><span class="sxs-lookup"><span data-stu-id="a5643-118"><strong><a href="connection-openrecordset-method-dao.md">OpenRecordset</a></strong></span></span></p></td>
<td><p><span data-ttu-id="a5643-119">创建一个新的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象，并将其追加到 <strong>Recordsets</strong> 集合。</span><span class="sxs-lookup"><span data-stu-id="a5643-119">Creates a new <strong><a href="recordset-object-dao.md">Recordset</a></strong> object and appends it to the <strong>Recordsets</strong> collection.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="properties"></a><span data-ttu-id="a5643-120">属性</span><span class="sxs-lookup"><span data-stu-id="a5643-120">Properties</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="a5643-121">名称</span><span class="sxs-lookup"><span data-stu-id="a5643-121">Name</span></span></p></th>
<th><p><span data-ttu-id="a5643-122">说明</span><span class="sxs-lookup"><span data-stu-id="a5643-122">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5643-123"><strong><a href="connection-connect-property-dao.md">连接</a></strong></span><span class="sxs-lookup"><span data-stu-id="a5643-123"><strong><a href="connection-connect-property-dao.md">Connect</a></strong></span></span></p></td>
<td><p><span data-ttu-id="a5643-p102">设置或返回一个值，该值提供与已打开连接的源有关的信息。可读/写 <strong>String</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="a5643-p102">Sets or returns a value that provides information about the source of an open connection. Read/write <strong>String</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5643-126"><strong><a href="connection-database-property-dao.md">Database</a></strong></span><span class="sxs-lookup"><span data-stu-id="a5643-126"><strong><a href="connection-database-property-dao.md">Database</a></strong></span></span></p></td>
<td><p></p>

<br/>


<p><span data-ttu-id="a5643-127">返回对应于此连接的 <strong><a href="database-object-dao.md">Database</a></strong> 对象（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="a5643-127">Returns the <strong><a href="database-object-dao.md">Database</a></strong> object that corresponds to this connection (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5643-128"><strong><a href="connection-name-property-dao.md">Name</a></strong></span><span class="sxs-lookup"><span data-stu-id="a5643-128"><strong><a href="connection-name-property-dao.md">Name</a></strong></span></span></p></td>
<td><p><span data-ttu-id="a5643-129">返回 <strong><a href="connection-object-dao.md">Connection</a></strong> 的名称。</span><span class="sxs-lookup"><span data-stu-id="a5643-129">Rreturns the name of a <strong><a href="connection-object-dao.md">Connection</a></strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5643-130"><strong><a href="connection-querydefs-property-dao.md">QueryDefs</a></strong></span><span class="sxs-lookup"><span data-stu-id="a5643-130"><strong><a href="connection-querydefs-property-dao.md">QueryDefs</a></strong></span></span></p></td>
<td><p><span data-ttu-id="a5643-p103">返回一个 <strong>QueryDefs</strong> 集合，该集合包含指定连接的所有 <strong>QueryDef</strong> 对象。只读。</span><span class="sxs-lookup"><span data-stu-id="a5643-p103">Returns a <strong>QueryDefs</strong> collection that contains all of the <strong>QueryDef</strong> objects of the specified connection. Read-only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5643-133"><strong><a href="connection-querytimeout-property-dao.md">QueryTimeout</a></strong></span><span class="sxs-lookup"><span data-stu-id="a5643-133"><strong><a href="connection-querytimeout-property-dao.md">QueryTimeout</a></strong></span></span></p></td>
<td><p><span data-ttu-id="a5643-134">设置或返回一个值，该值指定对 ODBC 数据源执行查询时发生超时错误之前等待的秒数。</span><span class="sxs-lookup"><span data-stu-id="a5643-134">Sets or returns a value that specifies the number of seconds to wait before a timeout error occurs when a query is executed on an ODBC data source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5643-135"><strong><a href="connection-recordsaffected-property-dao.md">RecordsAffected</a></strong></span><span class="sxs-lookup"><span data-stu-id="a5643-135"><strong><a href="connection-recordsaffected-property-dao.md">RecordsAffected</a></strong></span></span></p></td>
<td><p><span data-ttu-id="a5643-136">返回最近调用的 <strong><a href="connection-execute-method-dao.md">Execute</a></strong> 方法所影响的记录数。</span><span class="sxs-lookup"><span data-stu-id="a5643-136">Returns the number of records affected by the most recently invoked <strong><a href="connection-execute-method-dao.md">Execute</a></strong> method.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5643-137"><strong><a href="connection-recordsets-property-dao.md">Recordsets</a></strong></span><span class="sxs-lookup"><span data-stu-id="a5643-137"><strong><a href="connection-recordsets-property-dao.md">Recordsets</a></strong></span></span></p></td>
<td><p><span data-ttu-id="a5643-p104">返回一个 <strong>Recordsets</strong> 集合，该集合包含指定连接的所有已打开的记录集。只读。</span><span class="sxs-lookup"><span data-stu-id="a5643-p104">Returns a <strong>Recordsets</strong> collection that contains all of the open recordsets in the for the specified connection. Read-only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5643-140"><strong><a href="connection-stillexecuting-property-dao.md">StillExecuting</a></strong></span><span class="sxs-lookup"><span data-stu-id="a5643-140"><strong><a href="connection-stillexecuting-property-dao.md">StillExecuting</a></strong></span></span></p></td>
<td><p></p>

<br/>


<p><span data-ttu-id="a5643-141">指示异步操作（即用 <strong>dbRunAsync</strong> 选项调用的方法）是否已执行完毕（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="a5643-141">Indicates whether or not an asynchronous operation (that is, a method called with the <strong>dbRunAsync</strong> option) has finished executing (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5643-142"><strong><a href="connection-transactions-property-dao.md">事务</a></strong></span><span class="sxs-lookup"><span data-stu-id="a5643-142"><strong><a href="connection-transactions-property-dao.md">Transactions</a></strong></span></span></p></td>
<td><p><span data-ttu-id="a5643-p105">返回一个值，该值指示对象是否支持事务。只读 <strong>Boolean</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="a5643-p105">Returns a value that indicates whether an object supports transactions. Read-only <strong>Boolean</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5643-145"><strong><a href="connection-updatable-property-dao.md">Updatable</a></strong></span><span class="sxs-lookup"><span data-stu-id="a5643-145"><strong><a href="connection-updatable-property-dao.md">Updatable</a></strong></span></span></p></td>
<td><p><span data-ttu-id="a5643-p106">返回一个值，该值指示是否可以更改 DAO 对象。 <strong>Boolean</strong> 类型，只读。</span><span class="sxs-lookup"><span data-stu-id="a5643-p106">Returns a value that indicates whether you can change a DAO object. Read-only <strong>Boolean</strong>.Read-only.</span></span></p></td>
</tr>
</tbody>
</table>

