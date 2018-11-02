---
title: QueryDef 成员 (DAO)
TOCTitle: QueryDef Members
ms:assetid: 3f914d23-aa63-3ebd-1d86-4f53da71131b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192855(v=office.15)
ms:contentKeyID: 48544403
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f73e01c11f62b8c9eaff874dc315be083474532a
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25919736"
---
# <a name="querydef-members-dao"></a><span data-ttu-id="e2d9c-102">QueryDef 成员 (DAO)</span><span class="sxs-lookup"><span data-stu-id="e2d9c-102">QueryDef members (DAO)</span></span>


<span data-ttu-id="e2d9c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e2d9c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e2d9c-104">QueryDef 对象是 Microsoft Access 数据库引擎数据库中某个查询的存储定义。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-104">A QueryDef object is a stored definition of a query in a Microsoft Access database engine database.</span></span>

## <a name="methods"></a><span data-ttu-id="e2d9c-105">方法</span><span class="sxs-lookup"><span data-stu-id="e2d9c-105">Methods</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e2d9c-106">名称</span><span class="sxs-lookup"><span data-stu-id="e2d9c-106">Name</span></span></p></th>
<th><p><span data-ttu-id="e2d9c-107">说明</span><span class="sxs-lookup"><span data-stu-id="e2d9c-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2d9c-108"><strong><a href="querydef-cancel-method-dao.md">Cancel</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-108"><strong><a href="querydef-cancel-method-dao.md">Cancel</a></strong></span></span></p></td>
<td><p></p>

> [!NOTE]
> <P><span data-ttu-id="e2d9c-109">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-109">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="e2d9c-110">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-110">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></P>


<p><span data-ttu-id="e2d9c-111">取消执行待定的异步方法调用（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-111">Cancels execution of a pending asynchronous method call (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d9c-112"><strong><a href="querydef-close-method-dao.md">关闭</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-112"><strong><a href="querydef-close-method-dao.md">Close</a></strong></span></span></p></td>
<td><p><span data-ttu-id="e2d9c-113">关闭已打开的 <strong>QueryDef</strong>。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-113">Closes an open <strong>QueryDef</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d9c-114"><strong><a href="querydef-createproperty-method-dao.md">CreateProperty</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-114"><strong><a href="querydef-createproperty-method-dao.md">CreateProperty</a></strong></span></span></p></td>
<td><p><span data-ttu-id="e2d9c-115">创建一个新的用户定义的 <strong><a href="property-object-dao.md">Property</a></strong> 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-115">Creates a new user-defined <strong><a href="property-object-dao.md">Property</a></strong> object (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d9c-116"><strong><a href="querydef-execute-method-dao.md">Execute</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-116"><strong><a href="querydef-execute-method-dao.md">Execute</a></strong></span></span></p></td>
<td><p><span data-ttu-id="e2d9c-117">对指定的对象执行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-117">Executes an SQL statement on the specified object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d9c-118"><strong><a href="querydef-openrecordset-method-dao.md">OpenRecordset</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-118"><strong><a href="querydef-openrecordset-method-dao.md">OpenRecordset</a></strong></span></span></p></td>
<td><p><span data-ttu-id="e2d9c-119">创建一个新的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象，并将其追加到 <strong>Recordsets</strong> 集合。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-119">Creates a new <strong><a href="recordset-object-dao.md">Recordset</a></strong> object and appends it to the <strong>Recordsets</strong> collection.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="properties"></a><span data-ttu-id="e2d9c-120">属性</span><span class="sxs-lookup"><span data-stu-id="e2d9c-120">Properties</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e2d9c-121">名称</span><span class="sxs-lookup"><span data-stu-id="e2d9c-121">Name</span></span></p></th>
<th><p><span data-ttu-id="e2d9c-122">说明</span><span class="sxs-lookup"><span data-stu-id="e2d9c-122">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2d9c-123"><strong><a href="querydef-cachesize-property-dao.md">CacheSize</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-123"><strong><a href="querydef-cachesize-property-dao.md">CacheSize</a></strong></span></span></p></td>
<td><p><span data-ttu-id="e2d9c-p102">设置或返回从 ODBC 数据源中检索的、需要本地缓存的记录数。可读/写 <strong>Long</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-p102">Sets or returns the number of records retrieved from an ODBC data source that will be cached locally. Read/write <strong>Long</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d9c-126"><strong><a href="querydef-connect-property-dao.md">Connect</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-126"><strong><a href="querydef-connect-property-dao.md">Connect</a></strong></span></span></p></td>
<td><p><span data-ttu-id="e2d9c-p103">设置或返回一个值，该值提供有关在传递查询中使用的数据库源的信息。只读 <strong>String</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-p103">Sets or returns a value that provides information about the source of database used in a pass-through query. Read-only <strong>String</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d9c-129"><strong><a href="querydef-datecreated-property-dao.md">DateCreated</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-129"><strong><a href="querydef-datecreated-property-dao.md">DateCreated</a></strong></span></span></p></td>
<td><p><span data-ttu-id="e2d9c-p104">返回对象的创建日期和时间（仅适用于 Microsoft Access 工作区）。只读 <strong>Variant</strong>。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-p104">Returns the date and time that an object was created (Microsoft Access workspaces only). Read-only <strong>Variant</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d9c-132"><strong><a href="querydef-fields-property-dao.md">字段</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-132"><strong><a href="querydef-fields-property-dao.md">Fields</a></strong></span></span></p></td>
<td><p><span data-ttu-id="e2d9c-p105">返回一个 <strong><a href="fields-collection-dao.md">Fields</a></strong> 集合，该集合表示指定对象的所有存储 <strong><a href="field-object-dao.md">Field</a></strong> 对象。只读。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-p105">Returns a <strong><a href="fields-collection-dao.md">Fields</a></strong> collection that represents all stored <strong><a href="field-object-dao.md">Field</a></strong> objects for the specified object. Read-only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d9c-135"><strong><a href="querydef-lastupdated-property-dao.md">LastUpdated</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-135"><strong><a href="querydef-lastupdated-property-dao.md">LastUpdated</a></strong></span></span></p></td>
<td><p><span data-ttu-id="e2d9c-p106">返回对象的最近更改日期和时间。只读 <strong>Variant</strong>。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-p106">Returns the date and time of the most recent change made to an object. Read-only <strong>Variant</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d9c-138"><strong><a href="querydef-maxrecords-property-dao.md">MaxRecords</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-138"><strong><a href="querydef-maxrecords-property-dao.md">MaxRecords</a></strong></span></span></p></td>
<td><p><span data-ttu-id="e2d9c-139">设置或返回针对 ODBC 数据源的查询所返回的最大记录数。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-139">Sets or returns the maximum number of records to return from a query against an ODBC data source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d9c-140"><strong><a href="querydef-name-property-dao.md">Name</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-140"><strong><a href="querydef-name-property-dao.md">Name</a></strong></span></span></p></td>
<td><p><span data-ttu-id="e2d9c-p107">返回或设置指定对象的名称。可读/写 <strong>String</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-p107">Returns or sets the name of the specified object. Read/write <strong>String</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d9c-143"><strong><a href="querydef-odbctimeout-property-dao.md">ODBCTimeout</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-143"><strong><a href="querydef-odbctimeout-property-dao.md">ODBCTimeout</a></strong></span></span></p></td>
<td><p><span data-ttu-id="e2d9c-144">指示在开放式数据库连接 (ODBC) 数据库上执行 <strong><a href="querydef-object-dao.md">QueryDef</a></strong> 时，发生超时错误之前等待的秒数。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-144">Indicates the number of seconds to wait before a timeout error occurs when a <strong><a href="querydef-object-dao.md">QueryDef</a></strong> is executed on an ODBC database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d9c-145"><strong><a href="querydef-parameters-property-dao.md">参数</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-145"><strong><a href="querydef-parameters-property-dao.md">Parameters</a></strong></span></span></p></td>
<td><p><span data-ttu-id="e2d9c-p108">返回一个 <strong><a href="parameters-collection-dao.md">Parameters</a></strong> 集合，该集合包含指定 <a href="parameter-object-dao.md">QueryDef</a> 的所有 <strong><strong>Parameter</strong></strong> 对象。只读。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-p108">Returns a <strong><a href="parameters-collection-dao.md">Parameters</a></strong> collection that contains all of the <strong><a href="parameter-object-dao.md">Parameter</a></strong> objects of the specified <strong>QueryDef</strong>. Read-only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d9c-148"><strong><a href="querydef-prepare-property-dao.md">Prepare</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-148"><strong><a href="querydef-prepare-property-dao.md">Prepare</a></strong></span></span></p></td>
<td><p></p>

> [!NOTE]
> <P><span data-ttu-id="e2d9c-149">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-149">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="e2d9c-150">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-150">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></P>


<p><span data-ttu-id="e2d9c-p110">设置或返回一个值，用于指示是应当在执行之前使用 ODBC <strong>SQLPrepare</strong> API 函数在服务器上将查询作为临时存储过程来准备，还是应当使用 ODBC <strong>SQLExecDirect</strong> API 函数（只适用于 ODBCDirect 工作区）来执行查询。可读写。 <strong><a href="querydefstateenum-enumeration-dao.md">QueryDefStateEnum</a></strong> 。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-p110">Sets or returns a value that indicates whether the query should be prepared on the server as a temporary stored procedure, using the ODBC <strong>SQLPrepare</strong> API function, prior to execution, or just executed using the ODBC <strong>SQLExecDirect</strong> API function (ODBCDirect workspaces only). Read/Write <strong><a href="querydefstateenum-enumeration-dao.md">QueryDefStateEnum</a></strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d9c-153"><strong><a href="querydef-properties-property-dao.md">属性</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-153"><strong><a href="querydef-properties-property-dao.md">Properties</a></strong></span></span></p></td>
<td><p><span data-ttu-id="e2d9c-p111">返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。只读。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-p111">Returns the <strong><a href="properties-collection-dao.md">Properties</a></strong> collection of the specified object. Read-only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d9c-156"><strong><a href="querydef-recordsaffected-property-dao.md">RecordsAffected</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-156"><strong><a href="querydef-recordsaffected-property-dao.md">RecordsAffected</a></strong></span></span></p></td>
<td><p><span data-ttu-id="e2d9c-157">返回最近调用的 <strong><a href="querydef-execute-method-dao.md">Execute</a></strong> 方法所影响的记录数。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-157">Returns the number of records affected by the most recently invoked <strong><a href="querydef-execute-method-dao.md">Execute</a></strong> method.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d9c-158"><strong><a href="querydef-returnsrecords-property-dao.md">ReturnsRecords</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-158"><strong><a href="querydef-returnsrecords-property-dao.md">ReturnsRecords</a></strong></span></span></p></td>
<td><p><span data-ttu-id="e2d9c-159">设置或返回一个值，该值指示针对外部数据库的 SQL 传递查询是否返回记录（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-159">Sets or returns a value that indicates whether an SQL pass-through query to an external database returns records (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d9c-160"><strong><a href="querydef-sql-property-dao.md">SQL</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-160"><strong><a href="querydef-sql-property-dao.md">SQL</a></strong></span></span></p></td>
<td><p><span data-ttu-id="e2d9c-161">设置或返回定义 <strong><a href="querydef-object-dao.md">QueryDef</a></strong> 对象所执行的查询的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-161">Sets or returns the SQL statement that defines the query executed by a <strong><a href="querydef-object-dao.md">QueryDef</a></strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d9c-162"><strong><a href="querydef-stillexecuting-property-dao.md">StillExecuting</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-162"><strong><a href="querydef-stillexecuting-property-dao.md">StillExecuting</a></strong></span></span></p></td>
<td><p></p>

> [!NOTE]
> <P><span data-ttu-id="e2d9c-163">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-163">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="e2d9c-164">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-164">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></P>


<p><span data-ttu-id="e2d9c-165">指示异步操作（即用 <a href="recordsetoptionenum-enumeration-dao.md">dbRunAsync</a> 选项调用的方法）是否已执行完毕（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-165">Indicates whether or not an asynchronous operation (that is, a method called with the <a href="recordsetoptionenum-enumeration-dao.md">dbRunAsync</a> option) has finished executing (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d9c-166"><strong><a href="querydef-type-property-dao.md">类型</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-166"><strong><a href="querydef-type-property-dao.md">Type</a></strong></span></span></p></td>
<td><p><span data-ttu-id="e2d9c-167">设置或返回一个值，该值指示对象的操作类型或数据类型。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-167">Sets or returns a value that indicates the operational type or data type of an object.</span></span> <span data-ttu-id="e2d9c-168">只读的<strong>整数</strong>。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-168">Read-only<strong>Integer</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d9c-169"><strong><a href="querydef-updatable-property-dao.md">Updatable</a></strong></span><span class="sxs-lookup"><span data-stu-id="e2d9c-169"><strong><a href="querydef-updatable-property-dao.md">Updatable</a></strong></span></span></p></td>
<td><p><span data-ttu-id="e2d9c-p114">返回一个值，该值指示是否可以更改 DAO 对象。只读 <strong>Boolean</strong>。</span><span class="sxs-lookup"><span data-stu-id="e2d9c-p114">Returns a value that indicates whether you can change a DAO object. Read-only <strong>Boolean</strong>.</span></span></p></td>
</tr>
</tbody>
</table>

