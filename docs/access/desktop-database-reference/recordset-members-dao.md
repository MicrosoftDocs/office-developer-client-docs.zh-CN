---
title: Recordset 成员 (DAO)
TOCTitle: Recordset Members
ms:assetid: cfaae9ec-1b88-4285-1ebe-637564e99dc8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834683(v=office.15)
ms:contentKeyID: 48547815
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: c36187eef0b55681b2ba426d979f42ee8a6efea8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32284804"
---
# <a name="recordset-members-dao"></a><span data-ttu-id="1234c-102">Recordset 成员 (DAO)</span><span class="sxs-lookup"><span data-stu-id="1234c-102">Recordset members (DAO)</span></span>


<span data-ttu-id="1234c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="1234c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1234c-104">Recordset 对象表示基表中记录或运行查询所生成的结果记录。</span><span class="sxs-lookup"><span data-stu-id="1234c-104">A Recordset object represents the records in a base table or the records that result from running a query.</span></span>

## <a name="methods"></a><span data-ttu-id="1234c-105">方法</span><span class="sxs-lookup"><span data-stu-id="1234c-105">Methods</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1234c-106">名称</span><span class="sxs-lookup"><span data-stu-id="1234c-106">Name</span></span></p></th>
<th><p><span data-ttu-id="1234c-107">说明</span><span class="sxs-lookup"><span data-stu-id="1234c-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1234c-108"><strong><a href="recordset-addnew-method-dao.md">AddNew</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-108"><a href="recordset-addnew-method-dao.md">expression</a>  . <strong>AddNew</strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-109">为可更新的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象创建一条新记录。</span><span class="sxs-lookup"><span data-stu-id="1234c-109">Creates a new record for an updatable <strong><a href="recordset-object-dao.md">Recordset</a></strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-110"><strong><a href="recordset-cancel-method-dao.md">Cancel</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-110"><strong><a href="recordset-cancel-method-dao.md">Cancel</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-111"><strong>注释</strong>：Microsoft Access 2013 中不支持 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="1234c-111">ODBCDirect workspaces are not supported in Microsoft Access 2010.</span></span> <span data-ttu-id="1234c-112">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="1234c-112">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></p>
<p><span data-ttu-id="1234c-113">取消执行待定的异步方法调用（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="1234c-113">Cancels execution of a pending asynchronous method call (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-114"><strong><a href="recordset-cancelupdate-method-dao.md">CancelUpdate</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-114"><strong><a href="recordset-cancelupdate-method-dao.md">CancelUpdate</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-115">取消 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象的任意待定更新。</span><span class="sxs-lookup"><span data-stu-id="1234c-115">Cancels any pending updates for a <strong><a href="recordset-object-dao.md">Recordset</a></strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-116"><strong><a href="recordset-clone-method-dao.md">Clone</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-116"><strong><a href="recordset-clone-method-dao.md">Clone</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-117">创建一个引用原始 <strong>Recordset</strong> 对象的复制 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="1234c-117">Creates a duplicate <a href="recordset-object-dao.md"><strong>Recordset</strong></a> object that refers to the original <strong>Recordset</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-118"><strong><a href="recordset-close-method-dao.md">Close</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-118"><strong><a href="recordset-close-method-dao.md">Close</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-119">关闭一个打开的 <strong>Recordset</strong>。</span><span class="sxs-lookup"><span data-stu-id="1234c-119">Closes an open <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-120"><strong><a href="recordset-copyquerydef-method-dao.md">CopyQueryDef</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-120"><a href="recordset-copyquerydef-method-dao.md">expression</a>  . <strong>CopyQueryDef</strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-121">返回一个 <strong><a href="querydef-object-dao.md">QueryDef</a></strong> 对象，该对象是 <strong>QueryDef</strong> 的副本，用于创建由记录集占位符表示的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="1234c-121">Returns a <a href="querydef-object-dao.md"><strong>QueryDef</strong></a> object that is a copy of the <strong>QueryDef</strong> used to create the <strong><a href="recordset-object-dao.md">Recordset</a></strong> object represented by the recordset placeholder (Microsoft Access workspaces only).
.</span></span> <span data-ttu-id="1234c-122">。</span><span class="sxs-lookup"><span data-stu-id="1234c-122"></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-123"><strong><a href="recordset-delete-method-dao.md">Delete</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-123"><strong><a href="recordset-delete-method-dao.md">Delete</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-124">不支持此对象。</span><span class="sxs-lookup"><span data-stu-id="1234c-124">Not supported for this object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-125"><strong><a href="recordset-edit-method-dao.md">Edit</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-125"><strong><a href="recordset-edit-method-dao.md">Edit</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-126">将当前记录从可更新的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象复制到后续编辑复制缓冲区。</span><span class="sxs-lookup"><span data-stu-id="1234c-126">Copies the current record from an updatable <strong><a href="recordset-object-dao.md">Recordset</a></strong> object to the copy buffer for subsequent editing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-127"><strong><a href="recordset-fillcache-method-dao.md">FillCache</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-127"><strong><a href="recordset-fillcache-method-dao.md">FillCache</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-128">为某个 <strong>Recordset</strong> 对象填充所有或一部分本地缓存，该对象包含来自 Microsoft Access 数据库引擎连接的 ODBC 数据源中的数据（仅适用于 Microsoft Access 数据库引擎连接的 ODBC 数据库）。</span><span class="sxs-lookup"><span data-stu-id="1234c-128">Fills all or a part of a local cache for a <strong>Recordset</strong> object that contains data from a Microsoft Access database engine-connected ODBC data source (Microsoft Access database engine-connected ODBC databases only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-129"><strong><a href="recordset-findfirst-method-dao.md">FindFirst</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-129"><strong><a href="recordset-findfirst-method-dao.md">FindFirst</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-130">在动态集类型或快照类型的 <strong>Recordset</strong> 对象中查找符合指定条件的第一条记录，并使该记录成为当前记录（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="1234c-130">Locates the first record in a dynaset- or snapshot-type <strong>Recordset</strong> object that satisfies the specified criteria and makes that record the current record (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-131"><strong><a href="recordset-findlast-method-dao.md">FindLast</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-131"><strong><a href="recordset-findlast-method-dao.md">FindLast</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-132">在动态集类型或快照类型的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象中查找符合指定条件的最后一条记录，并且使该记录成为当前记录（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="1234c-132">Locates the last record in a dynaset- or snapshot-type <strong><a href="recordset-object-dao.md">Recordset</a></strong> object that satisfies the specified criteria and makes that record the current record (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-133"><strong><a href="recordset-findnext-method-dao.md">FindNext</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-133"><strong><a href="recordset-findnext-method-dao.md">FindNext</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-p103">在动态集类型或快照类型的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象中查找符合指定条件的下一条记录，并且使该记录成为当前记录（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="1234c-p103">Locates the next record in a dynaset- or snapshot-type <strong><a href="recordset-object-dao.md">Recordset</a></strong> object that satisfies the specified criteria and makes that record the current record (Microsoft Access workspaces only). .</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-136"><strong><a href="recordset-findprevious-method-dao.md">FindPrevious</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-136"><strong><a href="recordset-findprevious-method-dao.md">FindPrevious</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-p104">在动态集类型或快照类型的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象中查找符合指定条件的上一条记录，并且使该记录成为当前记录（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="1234c-p104">Locates the previous record in a dynaset- or snapshot-type <strong><a href="recordset-object-dao.md">Recordset</a></strong> object that satisfies the specified criteria and makes that record the current record (Microsoft Access workspaces only). .</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-139"><strong><a href="recordset-getrows-method-dao.md">GetRows</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-139"><strong><a href="recordset-getrows-method-dao.md">GetRows</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-140">检索来自 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象的多个行。</span><span class="sxs-lookup"><span data-stu-id="1234c-140">Retrieves multiple rows from a <strong><a href="recordset-object-dao.md">Recordset</a></strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-141"><strong><a href="recordset-move-method-dao.md">Move</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-141"><strong><a href="recordset-move-method-dao.md">Move</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-142">移动 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象中当前记录的位置。</span><span class="sxs-lookup"><span data-stu-id="1234c-142">Moves the position of the current record in a <strong><a href="recordset-object-dao.md">Recordset</a></strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-143"><strong><a href="recordset-movefirst-method-dao.md">MoveFirst</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-143"><a href="recordset-movefirst-method-dao.md">expression</a>  . <strong>MoveFirst</strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-144">移动至指定 <strong>Recordset</strong> 对象中的第一条记录，然后将该记录作为当前记录。</span><span class="sxs-lookup"><span data-stu-id="1234c-144">Moves to the first record in a specified <strong>Recordset</strong> object and make that record the current record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-145"><strong><a href="recordset-movelast-method-dao.md">MoveLast</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-145"><strong><a href="recordset-movelast-method-dao.md">MoveLast</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-146">移动至指定 <strong>Recordset</strong> 对象中的最后一条记录，然后将该记录作为当前记录。</span><span class="sxs-lookup"><span data-stu-id="1234c-146">Moves to the last record in a specified <strong>Recordset</strong> object and make that record the current record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-147"><strong><a href="recordset-movenext-method-dao.md">MoveNext</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-147"><a href="recordset-movenext-method-dao.md">expression</a>  . <strong>MoveNext</strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-148">移动至指定 <strong>Recordset</strong> 对象中的下一条记录，然后将该记录作为当前记录。</span><span class="sxs-lookup"><span data-stu-id="1234c-148">Moves to the next record in a specified <strong>Recordset</strong> object and make that record the current record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-149"><strong><a href="recordset-moveprevious-method-dao.md">MovePrevious</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-149"><a href="recordset-moveprevious-method-dao.md">expression</a>  . <strong>MovePrevious</strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-150">移动至指定 <strong>Recordset</strong> 对象中的上一条记录，然后将该记录作为当前记录。</span><span class="sxs-lookup"><span data-stu-id="1234c-150">Moves to the previous record in a specified <strong>Recordset</strong> object and make that record the current record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-151"><strong><a href="recordset-nextrecordset-method-dao.md">NextRecordset</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-151"><a href="recordset-nextrecordset-method-dao.md">expression</a>  . <strong>NextRecordset</strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-152"><strong>注释</strong>：Microsoft Access 2013 中不支持 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="1234c-152">ODBCDirect workspaces are not supported in Microsoft Access 2010.</span></span> <span data-ttu-id="1234c-153">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="1234c-153">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></p>
<p><span data-ttu-id="1234c-154">获取 <strong><a href="connection-openrecordset-method-dao.md">OpenRecordset</a></strong> 调用中多部分选择查询返回的下一个记录集（如果有的话），并且返回一个 <strong>Boolean</strong> 值，用于指示是有一个还是有多个附加记录处于待定状态（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="1234c-154">Gets the next set of records, if any, returned by a multi-part select query in an <strong><a href="connection-openrecordset-method-dao.md">OpenRecordset</a></strong> call, and returns a <strong>Boolean</strong> value indicating whether one or more additional records are pending (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-155"><strong><a href="recordset-openrecordset-method-dao.md">OpenRecordset</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-155"><strong><a href="recordset-openrecordset-method-dao.md">OpenRecordset</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-156">创建一个新的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象，并将其追加到 <strong>Recordsets</strong> 集合。</span><span class="sxs-lookup"><span data-stu-id="1234c-156">Creates a new <strong><a href="recordset-object-dao.md">Recordset</a></strong> object and appends it to the <strong>Recordsets</strong> collection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-157"><strong><a href="recordset-requery-method-dao.md">Requery</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-157"><strong><a href="recordset-requery-method-dao.md">Requery</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-158">通过重新执行该对象所基于的查询来更新 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象中的数据。</span><span class="sxs-lookup"><span data-stu-id="1234c-158">Updates the data in a <strong><a href="recordset-object-dao.md">Recordset</a></strong> object by re-executing the query on which the object is based.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-159"><strong><a href="recordset-seek-method-dao.md">Seek</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-159"><strong><a href="recordset-seek-method-dao.md">Seek</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-160">在已建立索引的表类型 <strong>Recordset</strong> 对象中查找符合当前索引的指定条件的记录，并使该记录成为当前记录（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="1234c-160">Locates the record in an indexed table-type <strong>Recordset</strong> object that satisfies the specified criteria for the current index and makes that record the current record (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-161"><strong><a href="recordset-update-method-dao.md">Update</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-161"><strong><a href="recordset-update-method-dao.md">Update</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-162"><strong>注释</strong>：Microsoft Access 2013 中不支持 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="1234c-162">ODBCDirect workspaces are not supported in Microsoft Access 2010.</span></span> <span data-ttu-id="1234c-163">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="1234c-163">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></p>
<p><span data-ttu-id="1234c-164">将复制缓冲区的内容保存到可更新的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="1234c-164">Saves the contents of the copy buffer to an updatable <strong><a href="recordset-object-dao.md">Recordset</a></strong> object.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="properties"></a><span data-ttu-id="1234c-165">属性</span><span class="sxs-lookup"><span data-stu-id="1234c-165">Properties</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1234c-166">名称</span><span class="sxs-lookup"><span data-stu-id="1234c-166">Name</span></span></p></th>
<th><p><span data-ttu-id="1234c-167">说明</span><span class="sxs-lookup"><span data-stu-id="1234c-167">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1234c-168"><strong><a href="recordset-absoluteposition-property-dao.md">AbsolutePosition</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-168"><a href="recordset-absoluteposition-property-dao.md">expression</a>  . <strong>AbsolutePosition</strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-169">设置或返回 <strong>Recordset</strong> 对象当前记录的相应记录编号。</span><span class="sxs-lookup"><span data-stu-id="1234c-169">Sets or returns the relative record number of a <strong>Recordset</strong> object's current record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-170"><strong><a href="recordset-batchcollisioncount-property-dao.md">BatchCollisionCount</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-170"><a href="recordset-batchcollisioncount-property-dao.md">expression</a>  . <strong>BatchCollisionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-171"><strong>注释</strong>：Microsoft Access 2013 中不支持 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="1234c-171">ODBCDirect workspaces are not supported in Microsoft Access 2010.</span></span> <span data-ttu-id="1234c-172">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="1234c-172">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></p>
<p><span data-ttu-id="1234c-173">返回未完成上一批更新的记录数（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="1234c-173">Returns the number of records that did not complete the last batch update (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-174"><strong><a href="recordset-batchcollisions-property-dao.md">BatchCollisions</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-174"><a href="recordset-batchcollisions-property-dao.md">expression</a>  . <strong>BatchCollisions</strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-175"><strong>注释</strong>：Microsoft Access 2013 中不支持 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="1234c-175">ODBCDirect workspaces are not supported in Microsoft Access 2010.</span></span> <span data-ttu-id="1234c-176">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="1234c-176">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></p>
<p><span data-ttu-id="1234c-177">返回一个书签数组，用于指示在上次批更新操作中产生冲突的行（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="1234c-177">Returns an array of bookmarks indicating the rows that generated collisions in the last batch update operation (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-178"><strong><a href="recordset-batchsize-property-dao.md">BatchSize</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-178"><a href="recordset-batchsize-property-dao.md">expression</a>  . <strong>BatchSize</strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-179"><strong>注释</strong>：Microsoft Access 2013 中不支持 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="1234c-179">ODBCDirect workspaces are not supported in Microsoft Access 2010.</span></span> <span data-ttu-id="1234c-180">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="1234c-180">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></p>
<p><span data-ttu-id="1234c-181">设置或返回每次批处理中发送回服务器的语句数（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="1234c-181">Sets or returns the number of statements sent back to the server in each batch (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-182"><strong><a href="recordset-bof-property-dao.md">BOF</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-182"><strong><a href="recordset-bof-property-dao.md">BOF</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-183">返回一个值，该值指示当前记录的位置是否在 <strong>Recordset</strong> 对象中的第一条记录之前。</span><span class="sxs-lookup"><span data-stu-id="1234c-183">Returns a value that indicates whether the current record position is before the first record in a <strong>Recordset</strong> object.</span></span> <span data-ttu-id="1234c-184">只读 <strong>Boolean</strong>。</span><span class="sxs-lookup"><span data-stu-id="1234c-184">Read-only <strong>Boolean</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-185"><strong><a href="recordset-bookmark-property-dao.md">Bookmark</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-185"><strong><a href="recordset-bookmark-property-dao.md">Bookmark</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-186">设置或返回唯一标识 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象当前记录的一个书签。</span><span class="sxs-lookup"><span data-stu-id="1234c-186">Sets or returns a bookmark that uniquely identifies the current record in a <strong><a href="recordset-object-dao.md">Recordset</a></strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-187"><strong><a href="recordset-bookmarkable-property-dao.md">Bookmarkable</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-187"><strong><a href="recordset-bookmarkable-property-dao.md">Bookmarkable</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-188">返回一个值，指示 <strong>Recordset</strong> 对象是否支持可使用 <strong><a href="recordset-bookmark-property-dao.md">Bookmark</a></strong> 属性来设置的书签。</span><span class="sxs-lookup"><span data-stu-id="1234c-188">Returns a value that indicates whether a <strong>Recordset</strong> object supports bookmarks, which you can set by using the <strong><a href="recordset-bookmark-property-dao.md">Bookmark</a></strong> property.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-189"><strong><a href="recordset-cachesize-property-dao.md">CacheSize</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-189"><a href="recordset-cachesize-property-dao.md">expression</a>  . <strong>CacheSize</strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-190">设置或返回从 ODBC 数据源中检索的、需要本地缓存的记录数。</span><span class="sxs-lookup"><span data-stu-id="1234c-190">Sets or returns the number of records retrieved from an ODBC data source that will be cached locally.</span></span> <span data-ttu-id="1234c-191">读/写 <strong>Long</strong>。</span><span class="sxs-lookup"><span data-stu-id="1234c-191">Read/write <strong>Long</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-192"><strong><a href="recordset-cachestart-property-dao.md">CacheStart</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-192">CacheStart Property</span></span></p></td>
<td><p><span data-ttu-id="1234c-193">设置或返回一个值，该值指定动态集类型 Recordset 对象（包含从 ODBC 数据源本地缓存的数据）中的第一条记录的书签（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="1234c-193">Sets or returns a value that specifies the bookmark of the first record in a dynaset-type Recordset object containing data to be locally cached from an ODBC data source (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-194"><strong><a href="recordset-connection-property-dao.md">Connection</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-194"><strong><a href="recordset-connection-property-dao.md">Connection</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-195">返回与数据库对应的 <strong><a href="connection-object-dao.md">Connection</a></strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="1234c-195">Returns the <strong><a href="connection-object-dao.md">Connection</a></strong> object that corresponds to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-196"><strong><a href="recordset-datecreated-property-dao.md">DateCreated</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-196"><strong><a href="recordset-datecreated-property-dao.md">DateCreated</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-197">返回基表的创建日期和时间（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="1234c-197">Returns the date and time a base table was created (Microsoft Access workspaces only).</span></span> <span data-ttu-id="1234c-198">只读<strong>变体</strong>。</span><span class="sxs-lookup"><span data-stu-id="1234c-198">Read-only <strong>Variant</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-199"><strong><a href="recordset-editmode-property-dao.md">EditMode</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-199"><a href="recordset-editmode-property-dao.md">expression</a>  . <strong>EditMode</strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-200">返回指示当前记录编辑状态的一个值。</span><span class="sxs-lookup"><span data-stu-id="1234c-200">Returns a value that indicates the state of editing for the current record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-201"><strong><a href="recordset-eof-property-dao.md">EOF</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-201"><strong><a href="recordset-eof-property-dao.md">EOF</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-202">返回一个值，该值指示当前记录位置是否位于 <strong>Recordset</strong> 对象的最后一条记录之后。</span><span class="sxs-lookup"><span data-stu-id="1234c-202">Returns a value that indicates whether the current record position is after the last record in a <strong>Recordset</strong> object.</span></span> <span data-ttu-id="1234c-203">只读 <strong>Boolean</strong>。</span><span class="sxs-lookup"><span data-stu-id="1234c-203">Read-only <strong>Boolean</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-204"><strong><a href="recordset-fields-property-dao.md">Fields</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-204"><strong><a href="recordset-fields-property-dao.md">Fields</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-205">返回一个 <strong>Fields</strong> 集合，该集合表示指定对象的所有存储 <strong>Field</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="1234c-205">Returns a <strong>Fields</strong> collection that represents all stored <strong>Field</strong> objects for the specified object.</span></span> <span data-ttu-id="1234c-206">只读。</span><span class="sxs-lookup"><span data-stu-id="1234c-206">Read-only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-207"><strong><a href="recordset-filter-property-dao.md">Filter</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-207"><strong><a href="recordset-filter-property-dao.md">Filter</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-208">设置或返回一个值，该值确定在随后打开的 <strong>Recordset</strong> 对象中包括的记录（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="1234c-208">Sets or returns a value that determines the records included in a subsequently opened <strong>Recordset</strong> object (Microsoft Access workspaces only).</span></span> <span data-ttu-id="1234c-209">读/写 <strong>String</strong>。</span><span class="sxs-lookup"><span data-stu-id="1234c-209">Read/write <strong>String</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-210"><strong><a href="recordset-index-property-dao.md">Index</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-210"><strong><a href="recordset-index-property-dao.md">Index</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-211">设置或返回在表类型 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象（仅 Microsoft Access 工作区）中指示当前 <strong><a href="index-object-dao.md">Index</a></strong> 对象名称的一个值。</span><span class="sxs-lookup"><span data-stu-id="1234c-211">Sets or returns a value that indicates the name of the current <strong><a href="index-object-dao.md">Index</a></strong> object in a table-type <strong><a href="recordset-object-dao.md">Recordset</a></strong> object (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-212"><strong><a href="recordset-lastmodified-property-dao.md">LastModified</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-212">LastModified Property</span></span></p></td>
<td><p><span data-ttu-id="1234c-213">返回一个指示最近添加或更改记录的书签。</span><span class="sxs-lookup"><span data-stu-id="1234c-213">Returns a ookmark indicating the most recently added or changed record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-214"><strong><a href="recordset-lastupdated-property-dao.md">LastUpdated</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-214">LastUpdated Property</span></span></p></td>
<td><p><span data-ttu-id="1234c-215">返回基表的最近更改日期和时间。</span><span class="sxs-lookup"><span data-stu-id="1234c-215">Returns the date and time of the most recent change made to a base table.</span></span> <span data-ttu-id="1234c-216">只读<strong>变体</strong>。</span><span class="sxs-lookup"><span data-stu-id="1234c-216">Read-only <strong>Variant</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-217"><strong><a href="recordset-lockedits-property-dao.md">LockEdits</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-217"><a href="recordset-lockedits-property-dao.md">expression</a>  . <strong>LockEdits</strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-218">设置或返回指示编辑时有效的锁定类型的一个值。</span><span class="sxs-lookup"><span data-stu-id="1234c-218">Sets or returns a value indicating the type of locking that is in effect while editing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-219"><strong><a href="recordset-name-property-dao.md">Name</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-219"><strong><a href="recordset-name-property-dao.md">Name</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-220">返回指定对象的名称。</span><span class="sxs-lookup"><span data-stu-id="1234c-220">Returns the name of the specified object.</span></span> <span data-ttu-id="1234c-221">只读 <strong>String</strong>。</span><span class="sxs-lookup"><span data-stu-id="1234c-221">Read-only <strong>String</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-222"><strong><a href="recordset-nomatch-property-dao.md">NoMatch</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-222"><a href="recordset-nomatch-property-dao.md">expression</a>  . <strong>NoMatch</strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-223">指示是否能通过使用 <strong><a href="recordset-seek-method-dao.md">Seek</a></strong> 方法或 <strong><a href="recordset-findfirst-method-dao.md">Find</a></strong> 方法之一（仅 Microsoft Access 工作区）找到特定记录。</span><span class="sxs-lookup"><span data-stu-id="1234c-223">Indicates whether a particular record was found by using the <strong><a href="recordset-seek-method-dao.md">Seek</a></strong> method or one of the <strong><a href="recordset-findfirst-method-dao.md">Find</a></strong> methods (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-224"><strong><a href="recordset-percentposition-property-dao.md">PercentPosition</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-224">PercentPosition Property</span></span></p></td>
<td><p><span data-ttu-id="1234c-225">设置或返回一个值，用于根据 <strong>Recordset</strong> 中的记录百分比指示 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象中当前记录的大概位置。</span><span class="sxs-lookup"><span data-stu-id="1234c-225">Sets or returns a value indicating the approximate location of the current record in the <a href="recordset-object-dao.md"><strong>Recordset</strong></a> object based on a percentage of the records in the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-226"><strong><a href="recordset-properties-property-dao.md">Properties</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-226"><strong><a href="recordset-properties-property-dao.md">Properties</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-227">返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。</span><span class="sxs-lookup"><span data-stu-id="1234c-227">Returns the <strong><a href="properties-collection-dao.md">Properties</a></strong> collection of the specified object.</span></span> <span data-ttu-id="1234c-228">只读。</span><span class="sxs-lookup"><span data-stu-id="1234c-228">Read-only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-229"><strong><a href="recordset-recordcount-property-dao.md">RecordCount</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-229"><strong><a href="recordset-recordcount-property-dao.md">RecordCount</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-p119">返回在 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象中访问的记录数，或者返回表类型 <strong>Recordset</strong> 对象或 <strong><a href="tabledef-object-dao.md">TableDef</a></strong> 对象中的记录总数。只读 <strong>Long</strong>。</span><span class="sxs-lookup"><span data-stu-id="1234c-p119">Returns the number of records accessed in a <strong><a href="recordset-object-dao.md">Recordset</a></strong> object, or the total number of records in a table-type <strong>Recordset</strong> object. or <strong><a href="tabledef-object-dao.md">TableDef</a></strong> object. Read-only <strong>Long</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-233"><strong><a href="recordset-recordstatus-property-dao.md">RecordStatus</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-233"><a href="recordset-recordstatus-property-dao.md">expression</a>  . <strong>RecordStatus</strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-234"><strong>注释</strong>：Microsoft Access 2013 中不支持 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="1234c-234">ODBCDirect workspaces are not supported in Microsoft Access 2010.</span></span> <span data-ttu-id="1234c-235">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="1234c-235">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></p>
<p><span data-ttu-id="1234c-p121">返回一个值，如果当前记录是批更新的一部分，该值将指示当前记录的更新状态（仅适用于 ODBCDirect 工作区）。只读 <strong><a href="recordstatusenum-enumeration-dao.md">RecordStatusEnum</a></strong> 。</span><span class="sxs-lookup"><span data-stu-id="1234c-p121">Returns a value indicating the update status of the current record if it is part of a batch update (ODBCDirect workspaces only). Read-only <strong><a href="recordstatusenum-enumeration-dao.md">RecordStatusEnum</a></strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-238"><strong><a href="recordset-restartable-property-dao.md">Restartable</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-238"><strong><a href="recordset-restartable-property-dao.md">Restartable</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-239">返回一个值，该值表示 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象是否支持 <strong><a href="recordset-requery-method-dao.md">Requery</a></strong> 方法，该方法重新执行 <strong>Recordset</strong> 对象所基于的查询。</span><span class="sxs-lookup"><span data-stu-id="1234c-239">Returns a value that indicates whether a <strong><a href="recordset-object-dao.md">Recordset</a></strong> object supports the <strong><a href="recordset-requery-method-dao.md">Requery</a></strong> method, which re-executes the query on which the <strong>Recordset</strong> object is based.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-240"><strong><a href="recordset-sort-property-dao.md">Sort</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-240"><strong><a href="recordset-sort-property-dao.md">Sort</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-241">设置或返回 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象中记录的排序顺序（仅 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="1234c-241">Sets or returns the sort order for records in a <strong><a href="recordset-object-dao.md">Recordset</a></strong> object (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-242"><strong><a href="recordset-stillexecuting-property-dao.md">StillExecuting</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-242"><a href="recordset-stillexecuting-property-dao.md">expression</a>  . <strong>StillExecuting</strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-243"><strong>注释</strong>：Microsoft Access 2013 中不支持 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="1234c-243">ODBCDirect workspaces are not supported in Microsoft Access 2010.</span></span> <span data-ttu-id="1234c-244">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="1234c-244">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></p>
<p><span data-ttu-id="1234c-245">指示异步操作（即用 <strong>dbRunAsync</strong> 选项调用的方法）是否已执行完毕（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="1234c-245">Indicates whether or not an asynchronous operation (that is, a method called with the <strong>dbRunAsync</strong> option) has finished executing (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-246"><strong><a href="recordset-transactions-property-dao.md">Transactions</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-246"><strong><a href="recordset-transactions-property-dao.md">Transactions</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-247">返回一个值，该值指示对象是否支持事务。</span><span class="sxs-lookup"><span data-stu-id="1234c-247">Returns a value that indicates whether an object supports transactions.</span></span> <span data-ttu-id="1234c-248">只读 <strong>Boolean</strong>。</span><span class="sxs-lookup"><span data-stu-id="1234c-248">Read-only <strong>Boolean</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-249"><strong>Type</strong></span><span class="sxs-lookup"><span data-stu-id="1234c-249"><strong>Type</strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-250">将在 Office 14 最终版本中显示此成员说明。</span><span class="sxs-lookup"><span data-stu-id="1234c-250">The description for this member will appear in the final release of Office 14.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-251"><strong><a href="recordset-updatable-property-dao.md">Updatable</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-251"><strong><a href="recordset-updatable-property-dao.md">Updatable</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-252">返回一个值，该值指示是否可以更改 DAO 对象。</span><span class="sxs-lookup"><span data-stu-id="1234c-252">Returns a value that indicates whether you can change a DAO object.</span></span> <span data-ttu-id="1234c-253">只读 <strong>Boolean</strong>。</span><span class="sxs-lookup"><span data-stu-id="1234c-253">Read-only <strong>Boolean</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-254"><strong><a href="recordset-updateoptions-property-dao.md">UpdateOptions</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-254"><strong><a href="recordset-updateoptions-property-dao.md">UpdateOptions</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-255"><strong>注释</strong>：Microsoft Access 2013 中不支持 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="1234c-255">ODBCDirect workspaces are not supported in Microsoft Access 2010.</span></span> <span data-ttu-id="1234c-256">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="1234c-256">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></p>
<p><span data-ttu-id="1234c-p126">设置或返回一个值，该值指示在批更新过程中如何为每条记录构建 WHERE 子句，以及批更新是应当使用 UPDATE 语句，还是应当使用后跟 INSERT 的 DELETE（仅适用于 ODBCDirect 工作区）。读/写 <strong><a href="updatecriteriaenum-enumeration-dao.md">UpdateCriteriaEnum</a></strong> 。</span><span class="sxs-lookup"><span data-stu-id="1234c-p126">Sets or returns a value that indicates how the WHERE clause is constructed for each record during a batch update, and whether the batch update should use an UPDATE statement or a DELETE followed by an INSERT (ODBCDirect workspaces only). Read/write <strong><a href="updatecriteriaenum-enumeration-dao.md">UpdateCriteriaEnum</a></strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1234c-259"><strong><a href="recordset-validationrule-property-dao.md">ValidationRule</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-259"><strong><a href="recordset-validationrule-property-dao.md">ValidationRule</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-260">设置或返回一个值，当字段中的数据更改或添加到表中时，该值对这些数据进行验证（仅适用于 Microsoft Access 工作区）。读/写 <strong>String</strong>。</span><span class="sxs-lookup"><span data-stu-id="1234c-260">Sets or returns a value that validates the data in a field as it's changed or added to a table (Microsoft Access workspaces only).Read/write <strong>String</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1234c-261"><strong><a href="recordset-validationtext-property-dao.md">ValidationText</a></strong></span><span class="sxs-lookup"><span data-stu-id="1234c-261"><strong><a href="recordset-validationtext-property-dao.md">ValidationText</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1234c-p127">设置或返回一个值，该值指定在 <strong>Field</strong> 对象的值不满足 <strong>ValidationRule</strong> 属性设置所指定的验证规则时应用程序显示的消息文本（仅适用于 Microsoft Access 工作区）。只读 <strong>String</strong>。</span><span class="sxs-lookup"><span data-stu-id="1234c-p127">Sets or returns a value that specifies the text of the message that your application displays if the value of a <strong>Field</strong> object doesn't satisfy the validation rule specified by the <strong>ValidationRule</strong> property setting (Microsoft Access workspaces only). Read-only <strong>String</strong>.</span></span></p></td>
</tr>
</tbody>
</table>

