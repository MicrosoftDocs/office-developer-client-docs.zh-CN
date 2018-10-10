---
title: Connection Members (DAO)
TOCTitle: Connection Members
ms:assetid: 94fc60ee-b6f2-cf08-b008-ed51bf7e7f8c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197681(v=office.15)
ms:contentKeyID: 48546422
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 001cb1372acf4a4a55b3841a3f4ca8d6598f55e8
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466302"
---
# <a name="connection-members-dao"></a><span data-ttu-id="f100c-102">Connection Members (DAO)</span><span class="sxs-lookup"><span data-stu-id="f100c-102">Connection Members (DAO)</span></span>


<span data-ttu-id="f100c-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="f100c-103">**Applies to**: Access 2013 | Office 2013</span></span>


> [!NOTE]
> <P><span data-ttu-id="f100c-104">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="f100c-104">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="f100c-105">如果您想要不使用 Microsoft Access 数据库引擎访问外部数据源，请使用 ADO。Connection 对象代表与 ODBC 数据库 （仅适用于 ODBCDirect 工作区） 的连接。</span><span class="sxs-lookup"><span data-stu-id="f100c-105">Use ADO if you want to access external data sources without using the Microsoft Access database engine.A Connection object represents a connection to an ODBC database (ODBCDirect workspaces only).</span></span></P>



## <a name="methods"></a><span data-ttu-id="f100c-106">方法</span><span class="sxs-lookup"><span data-stu-id="f100c-106">Methods</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f100c-107">名称</span><span class="sxs-lookup"><span data-stu-id="f100c-107">Name</span></span></p></th>
<th><p><span data-ttu-id="f100c-108">说明</span><span class="sxs-lookup"><span data-stu-id="f100c-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f100c-109"><strong><a href="connection-cancel-method-dao.md">Cancel</a></strong></span><span class="sxs-lookup"><span data-stu-id="f100c-109"><strong><a href="connection-cancel-method-dao.md">Cancel</a></strong></span></span></p></td>
<td><p></p>

> [!NOTE]
> <P><span data-ttu-id="f100c-110">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="f100c-110">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="f100c-111">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="f100c-111">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></P>


<p><span data-ttu-id="f100c-112">取消执行待定的异步方法调用（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="f100c-112">Cancels execution of a pending asynchronous method call (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f100c-113"><strong><a href="connection-close-method-dao.md">关闭</a></strong></span><span class="sxs-lookup"><span data-stu-id="f100c-113"><strong><a href="connection-close-method-dao.md">Close</a></strong></span></span></p></td>
<td><p><span data-ttu-id="f100c-114">关闭已打开的 <strong>Connection</strong>。</span><span class="sxs-lookup"><span data-stu-id="f100c-114">Closes an open <strong>Connection</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f100c-115"><strong><a href="connection-createquerydef-method-dao.md">CreateQueryDef</a></strong></span><span class="sxs-lookup"><span data-stu-id="f100c-115"><strong><a href="connection-createquerydef-method-dao.md">CreateQueryDef</a></strong></span></span></p></td>
<td><p><span data-ttu-id="f100c-116">创建新的 <strong><a href="querydef-object-dao.md">QueryDef</a></strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="f100c-116">Creates a new <strong><a href="querydef-object-dao.md">QueryDef</a></strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f100c-117"><strong><a href="connection-execute-method-dao.md">Execute</a></strong></span><span class="sxs-lookup"><span data-stu-id="f100c-117"><strong><a href="connection-execute-method-dao.md">Execute</a></strong></span></span></p></td>
<td><p><span data-ttu-id="f100c-118">对指定的对象运行动作查询，或执行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="f100c-118">Runs an action query or executes an SQL statement on the specified object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f100c-119"><strong><a href="connection-openrecordset-method-dao.md">OpenRecordset</a></strong></span><span class="sxs-lookup"><span data-stu-id="f100c-119"><strong><a href="connection-openrecordset-method-dao.md">OpenRecordset</a></strong></span></span></p></td>
<td><p><span data-ttu-id="f100c-120">创建一个新的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象，并将其追加到 <strong>Recordsets</strong> 集合。</span><span class="sxs-lookup"><span data-stu-id="f100c-120">Creates a new <strong><a href="recordset-object-dao.md">Recordset</a></strong> object and appends it to the <strong>Recordsets</strong> collection.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="properties"></a><span data-ttu-id="f100c-121">属性</span><span class="sxs-lookup"><span data-stu-id="f100c-121">Properties</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f100c-122">名称</span><span class="sxs-lookup"><span data-stu-id="f100c-122">Name</span></span></p></th>
<th><p><span data-ttu-id="f100c-123">说明</span><span class="sxs-lookup"><span data-stu-id="f100c-123">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f100c-124"><strong><a href="connection-connect-property-dao.md">连接</a></strong></span><span class="sxs-lookup"><span data-stu-id="f100c-124"><strong><a href="connection-connect-property-dao.md">Connect</a></strong></span></span></p></td>
<td><p><span data-ttu-id="f100c-p103">设置或返回一个值，该值提供与已打开连接的源有关的信息。可读/写 <strong>String</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="f100c-p103">Sets or returns a value that provides information about the source of an open connection. Read/write <strong>String</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f100c-127"><strong><a href="connection-database-property-dao.md">Database</a></strong></span><span class="sxs-lookup"><span data-stu-id="f100c-127"><strong><a href="connection-database-property-dao.md">Database</a></strong></span></span></p></td>
<td><p></p>

> [!NOTE]
> <P><span data-ttu-id="f100c-128">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="f100c-128">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="f100c-129">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="f100c-129">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></P>


<p><span data-ttu-id="f100c-130">返回对应于此连接的 <strong><a href="database-object-dao.md">Database</a></strong> 对象（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="f100c-130">Returns the <strong><a href="database-object-dao.md">Database</a></strong> object that corresponds to this connection (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f100c-131"><strong><a href="connection-name-property-dao.md">Name</a></strong></span><span class="sxs-lookup"><span data-stu-id="f100c-131"><strong><a href="connection-name-property-dao.md">Name</a></strong></span></span></p></td>
<td><p><span data-ttu-id="f100c-132">返回 <strong><a href="connection-object-dao.md">Connection</a></strong> 的名称。</span><span class="sxs-lookup"><span data-stu-id="f100c-132">Rreturns the name of a <strong><a href="connection-object-dao.md">Connection</a></strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f100c-133"><strong><a href="connection-querydefs-property-dao.md">QueryDefs</a></strong></span><span class="sxs-lookup"><span data-stu-id="f100c-133"><strong><a href="connection-querydefs-property-dao.md">QueryDefs</a></strong></span></span></p></td>
<td><p><span data-ttu-id="f100c-p105">返回一个 <strong>QueryDefs</strong> 集合，该集合包含指定连接的所有 <strong>QueryDef</strong> 对象。只读。</span><span class="sxs-lookup"><span data-stu-id="f100c-p105">Returns a <strong>QueryDefs</strong> collection that contains all of the <strong>QueryDef</strong> objects of the specified connection. Read-only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f100c-136"><strong><a href="connection-querytimeout-property-dao.md">QueryTimeout</a></strong></span><span class="sxs-lookup"><span data-stu-id="f100c-136"><strong><a href="connection-querytimeout-property-dao.md">QueryTimeout</a></strong></span></span></p></td>
<td><p><span data-ttu-id="f100c-137">设置或返回一个值，该值指定对 ODBC 数据源执行查询时发生超时错误之前等待的秒数。</span><span class="sxs-lookup"><span data-stu-id="f100c-137">Sets or returns a value that specifies the number of seconds to wait before a timeout error occurs when a query is executed on an ODBC data source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f100c-138"><strong><a href="connection-recordsaffected-property-dao.md">RecordsAffected</a></strong></span><span class="sxs-lookup"><span data-stu-id="f100c-138"><strong><a href="connection-recordsaffected-property-dao.md">RecordsAffected</a></strong></span></span></p></td>
<td><p><span data-ttu-id="f100c-139">返回最近调用的 <strong><a href="connection-execute-method-dao.md">Execute</a></strong> 方法所影响的记录数。</span><span class="sxs-lookup"><span data-stu-id="f100c-139">Returns the number of records affected by the most recently invoked <strong><a href="connection-execute-method-dao.md">Execute</a></strong> method.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f100c-140"><strong><a href="connection-recordsets-property-dao.md">Recordsets</a></strong></span><span class="sxs-lookup"><span data-stu-id="f100c-140"><strong><a href="connection-recordsets-property-dao.md">Recordsets</a></strong></span></span></p></td>
<td><p><span data-ttu-id="f100c-p106">返回一个 <strong>Recordsets</strong> 集合，该集合包含指定连接的所有已打开的记录集。只读。</span><span class="sxs-lookup"><span data-stu-id="f100c-p106">Returns a <strong>Recordsets</strong> collection that contains all of the open recordsets in the for the specified connection. Read-only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f100c-143"><strong><a href="connection-stillexecuting-property-dao.md">StillExecuting</a></strong></span><span class="sxs-lookup"><span data-stu-id="f100c-143"><strong><a href="connection-stillexecuting-property-dao.md">StillExecuting</a></strong></span></span></p></td>
<td><p></p>

> [!NOTE]
> <P><span data-ttu-id="f100c-144">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="f100c-144">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="f100c-145">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="f100c-145">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></P>


<p><span data-ttu-id="f100c-146">指示异步操作（即用 <strong>dbRunAsync</strong> 选项调用的方法）是否已执行完毕（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="f100c-146">Indicates whether or not an asynchronous operation (that is, a method called with the <strong>dbRunAsync</strong> option) has finished executing (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f100c-147"><strong><a href="connection-transactions-property-dao.md">事务</a></strong></span><span class="sxs-lookup"><span data-stu-id="f100c-147"><strong><a href="connection-transactions-property-dao.md">Transactions</a></strong></span></span></p></td>
<td><p><span data-ttu-id="f100c-p108">返回一个值，该值指示对象是否支持事务。只读 <strong>Boolean</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="f100c-p108">Returns a value that indicates whether an object supports transactions. Read-only <strong>Boolean</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f100c-150"><strong><a href="connection-updatable-property-dao.md">Updatable</a></strong></span><span class="sxs-lookup"><span data-stu-id="f100c-150"><strong><a href="connection-updatable-property-dao.md">Updatable</a></strong></span></span></p></td>
<td><p><span data-ttu-id="f100c-p109">返回一个值，该值指示是否可以更改 DAO 对象。 <strong>Boolean</strong> 类型，只读。</span><span class="sxs-lookup"><span data-stu-id="f100c-p109">Returns a value that indicates whether you can change a DAO object. Read-only <strong>Boolean</strong>.Read-only.</span></span></p></td>
</tr>
</tbody>
</table>

