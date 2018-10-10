---
title: ActiveX 数据对象 (ADO) 方法
TOCTitle: ADO Methods
ms:assetid: 1fd965a0-711c-e199-822c-b9575c5034bd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248984(v=office.15)
ms:contentKeyID: 48543651
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7b7a685352063c3c1dd4c9bbd62e9c1fc4cdfe11
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465770"
---
# <a name="ado-methods"></a><span data-ttu-id="91917-102">ADO 方法</span><span class="sxs-lookup"><span data-stu-id="91917-102">ADO Methods</span></span>


<span data-ttu-id="91917-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="91917-103">**Applies to**: Access 2013 | Office 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91917-104"><a href="addnew-method-ado.md">AddNew</a></span><span class="sxs-lookup"><span data-stu-id="91917-104"><a href="addnew-method-ado.md">AddNew</a></span></span></p></td>
<td><p><span data-ttu-id="91917-105">用于为可更新的 <strong>Recordset</strong> 对象创建新记录。</span><span class="sxs-lookup"><span data-stu-id="91917-105">Creates a new record for an updatable <strong>Recordset</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-106"><a href="append-method-ado.md">Append</a></span><span class="sxs-lookup"><span data-stu-id="91917-106"><a href="append-method-ado.md">Append</a></span></span></p></td>
<td><p><span data-ttu-id="91917-p101">用于将对象追加到集合。如果集合为 <strong>Fields</strong>，则在将对象追加到集合之前，可能会创建新的 <strong>Field</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="91917-p101">Appends an object to a collection. If the collection is <strong>Fields</strong>, a new <strong>Field</strong> object may be created before it is appended to the collection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-109"><a href="appendchunk-method-ado.md">AppendChunk</a></span><span class="sxs-lookup"><span data-stu-id="91917-109"><a href="appendchunk-method-ado.md">AppendChunk</a></span></span></p></td>
<td><p><span data-ttu-id="91917-110">用于将数据追加到大型文本或二进制数据 <strong>Field</strong> 或 <strong>Parameter</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="91917-110">Appends data to a large text or binary data <strong>Field</strong>, or to a <strong>Parameter</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-111"><a href="begintrans-committrans-and-rollbacktrans-methods-ado.md">BeginTrans、 CommitTrans 和 RollbackTrans</a></span><span class="sxs-lookup"><span data-stu-id="91917-111"><a href="begintrans-committrans-and-rollbacktrans-methods-ado.md">BeginTrans, CommitTrans, and RollbackTrans</a></span></span></p></td>
<td><p><span data-ttu-id="91917-112">管理中的事务处理<strong>Connection</strong>对象，如下所示： <strong>BeginTrans</strong> -开始新的事务。</span><span class="sxs-lookup"><span data-stu-id="91917-112">Manages transaction processing within a <strong>Connection</strong> object as follows: <strong>BeginTrans</strong> — Begins a new transaction.</span></span><br /><span data-ttu-id="91917-p102">
<strong>CommitTrans</strong> - 保存任何更改并结束当前事务。还可以开始一个新的事务。</span><span class="sxs-lookup"><span data-stu-id="91917-p102">
<strong>CommitTrans</strong> — Saves any changes and ends the current transaction. It may also start a new transaction.</span></span><br /><span data-ttu-id="91917-115">
<strong>RollbackTrans</strong> — 取消所有更改并结束当前事务。</span><span class="sxs-lookup"><span data-stu-id="91917-115">
<strong>RollbackTrans</strong> — Cancels any changes and ends the current transaction.</span></span> <span data-ttu-id="91917-116">还可以开始一个新的事务。</span><span class="sxs-lookup"><span data-stu-id="91917-116">It may also start a new transaction.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-117"><a href="cancel-method-ado.md">Cancel</a></span><span class="sxs-lookup"><span data-stu-id="91917-117"><a href="cancel-method-ado.md">Cancel</a></span></span></p></td>
<td><p><span data-ttu-id="91917-118">用于取消执行挂起的异步方法调用。</span><span class="sxs-lookup"><span data-stu-id="91917-118">Cancels execution of a pending, asynchronous method call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-119"><a href="cancelbatch-method-ado.md">CancelBatch</a></span><span class="sxs-lookup"><span data-stu-id="91917-119"><a href="cancelbatch-method-ado.md">CancelBatch</a></span></span></p></td>
<td><p><span data-ttu-id="91917-120">用于取消挂起的批更新。</span><span class="sxs-lookup"><span data-stu-id="91917-120">Cancels a pending batch update.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-121"><a href="cancelupdate-method-ado.md">CancelUpdate</a></span><span class="sxs-lookup"><span data-stu-id="91917-121"><a href="cancelupdate-method-ado.md">CancelUpdate</a></span></span></p></td>
<td><p><span data-ttu-id="91917-122">在调用 <strong>Update</strong> 方法之前，取消对 <strong>Recordset</strong> 对象的当前行或新行，或对 <strong>Record</strong> 对象的 <strong>Fields</strong> 集合所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="91917-122">Cancels any changes made to the current or new row of a <strong>Recordset</strong> object, or the <strong>Fields</strong> collection of a <strong>Record</strong> object, before calling the <strong>Update</strong> method.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-123"><a href="clear-method-ado.md">Clear</a></span><span class="sxs-lookup"><span data-stu-id="91917-123"><a href="clear-method-ado.md">Clear</a></span></span></p></td>
<td><p><span data-ttu-id="91917-124">用于从 <strong>Errors</strong> 集合中删除所有 <strong>Error</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="91917-124">Removes all the <strong>Error</strong> objects from the <strong>Errors</strong> collection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-125"><a href="clone-method-ado.md">Clone</a></span><span class="sxs-lookup"><span data-stu-id="91917-125"><a href="clone-method-ado.md">Clone</a></span></span></p></td>
<td><p><span data-ttu-id="91917-p104">用于从现有 <strong>Recordset</strong> 对象创建重复的 <strong>Recordset</strong> 对象。还可以指定克隆为只读状态。</span><span class="sxs-lookup"><span data-stu-id="91917-p104">Creates a duplicate <strong>Recordset</strong> object from an existing <strong>Recordset</strong> object. Optionally, specifies that the clone be read-only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-128"><a href="close-method-ado.md">Close</a></span><span class="sxs-lookup"><span data-stu-id="91917-128"><a href="close-method-ado.md">Close</a></span></span></p></td>
<td><p><span data-ttu-id="91917-129">用于关闭打开的对象和任何相关的对象。</span><span class="sxs-lookup"><span data-stu-id="91917-129">Closes an open object and any dependent objects.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-130"><a href="comparebookmarks-method-ado.md">CompareBookmarks</a></span><span class="sxs-lookup"><span data-stu-id="91917-130"><a href="comparebookmarks-method-ado.md">CompareBookmarks</a></span></span></p></td>
<td><p><span data-ttu-id="91917-131">用于比较两个书签，并返回其相对值的指示。</span><span class="sxs-lookup"><span data-stu-id="91917-131">Compares two bookmarks and returns an indication of their relative values.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-132"><a href="copyrecord-method-ado.md">CopyRecord</a></span><span class="sxs-lookup"><span data-stu-id="91917-132"><a href="copyrecord-method-ado.md">CopyRecord</a></span></span></p></td>
<td><p><span data-ttu-id="91917-133">用于将文件或目录及其内容复制到其他位置。</span><span class="sxs-lookup"><span data-stu-id="91917-133">Copies a file or directory, and its contents, to another location.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-134"><a href="copyto-method-ado.md">CopyTo</a></span><span class="sxs-lookup"><span data-stu-id="91917-134"><a href="copyto-method-ado.md">CopyTo</a></span></span></p></td>
<td><p><span data-ttu-id="91917-135">用于将 <strong>Stream</strong> 中指定数量的字符或字节（取决于 <strong>类型</strong>）复制到另一个 <strong>Stream</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="91917-135">Copies the specified number of characters or bytes (depending on <strong>Type</strong>) in the <strong>Stream</strong> to another <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-136"><a href="createparameter-method-ado.md">CreateParameter</a></span><span class="sxs-lookup"><span data-stu-id="91917-136"><a href="createparameter-method-ado.md">CreateParameter</a></span></span></p></td>
<td><p><span data-ttu-id="91917-137">用于创建具有指定属性的新 <strong>Parameter</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="91917-137">Creates a new <strong>Parameter</strong> object with the specified properties.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-138"><a href="delete-method-ado-parameters-collection.md">删除 （ADO Parameters 集合）</a></span><span class="sxs-lookup"><span data-stu-id="91917-138"><a href="delete-method-ado-parameters-collection.md">Delete (ADO Parameters Collection)</a></span></span></p></td>
<td><p><span data-ttu-id="91917-139">用于从 <strong>Parameters</strong> 集合中删除对象。</span><span class="sxs-lookup"><span data-stu-id="91917-139">Deletes an object from the <strong>Parameters</strong> collection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-140"><a href="delete-method-ado-fields-collection.md">删除 （ADO Fields 集合）</a></span><span class="sxs-lookup"><span data-stu-id="91917-140"><a href="delete-method-ado-fields-collection.md">Delete (ADO Fields Collection)</a></span></span></p></td>
<td><p><span data-ttu-id="91917-141">用于从 <strong>Fields</strong> 集合中删除对象。</span><span class="sxs-lookup"><span data-stu-id="91917-141">Deletes an object from the <strong>Fields</strong> collection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-142"><a href="delete-method-ado-recordset.md">删除 (ADO Recordset)</a></span><span class="sxs-lookup"><span data-stu-id="91917-142"><a href="delete-method-ado-recordset.md">Delete (ADO Recordset)</a></span></span></p></td>
<td><p><span data-ttu-id="91917-143">用于删除当前记录或一组记录。</span><span class="sxs-lookup"><span data-stu-id="91917-143">Deletes the current record or a group of records.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-144"><a href="deleterecord-method-ado.md">DeleteRecord</a></span><span class="sxs-lookup"><span data-stu-id="91917-144"><a href="deleterecord-method-ado.md">DeleteRecord</a></span></span></p></td>
<td><p><span data-ttu-id="91917-145">用于删除文件或目录及其所有子目录。</span><span class="sxs-lookup"><span data-stu-id="91917-145">Deletes a file or directory, and all its subdirectories.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-146"><a href="https://msdn.microsoft.com/library/jj248785(v=office.15)">执行 (ADO Command)</a></span><span class="sxs-lookup"><span data-stu-id="91917-146"><a href="https://msdn.microsoft.com/library/jj248785(v=office.15)">Execute (ADO Command)</a></span></span></p></td>
<td><p><span data-ttu-id="91917-147">用于执行在 <strong>CommandText</strong> 属性中指定的查询、SQL 语句或存储过程。</span><span class="sxs-lookup"><span data-stu-id="91917-147">Executes the query, SQL statement, or stored procedure specified in the <strong>CommandText</strong> property.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-148"><a href="https://msdn.microsoft.com/library/jj249832(v=office.15)">执行 (ADO Connection)</a></span><span class="sxs-lookup"><span data-stu-id="91917-148"><a href="https://msdn.microsoft.com/library/jj249832(v=office.15)">Execute (ADO Connection)</a></span></span></p></td>
<td><p><span data-ttu-id="91917-149">执行指定的查询、SQL 语句、存储过程或提供程序特定的文本。</span><span class="sxs-lookup"><span data-stu-id="91917-149">Executes the specified query, SQL statement, stored procedure, or provider-specific text.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-150"><a href="find-method-ado.md">Find</a></span><span class="sxs-lookup"><span data-stu-id="91917-150"><a href="find-method-ado.md">Find</a></span></span></p></td>
<td><p><span data-ttu-id="91917-151">用于在 <strong>Recordset</strong> 中搜索满足指定条件的行。</span><span class="sxs-lookup"><span data-stu-id="91917-151">Searches a <strong>Recordset</strong> for the row that satisfies the specified criteria.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-152"><a href="flush-method-ado.md">刷新</a></span><span class="sxs-lookup"><span data-stu-id="91917-152"><a href="flush-method-ado.md">Flush</a></span></span></p></td>
<td><p><span data-ttu-id="91917-153">用于将保留在 ADO 缓冲区中的 <strong>Stream</strong> 的内容强制转移到 <strong>Stream</strong> 所关联的基础对象中。</span><span class="sxs-lookup"><span data-stu-id="91917-153">Forces the contents of the <strong>Stream</strong> remaining in the ADO buffer to the underlying object with which the <strong>Stream</strong> is associated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-154"><a href="getchildren-method-ado.md">GetChildren</a></span><span class="sxs-lookup"><span data-stu-id="91917-154"><a href="getchildren-method-ado.md">GetChildren</a></span></span></p></td>
<td><p><span data-ttu-id="91917-155">返回一个<strong>Recordset</strong> ，其行表示的文件和此<strong>Record</strong>所表示的目录的子目录中。</span><span class="sxs-lookup"><span data-stu-id="91917-155">Returns a <strong>Recordset</strong> whose rows represent the files and subdirectories in the directory represented by this <strong>Record</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-156"><a href="getchunk-method-ado.md">GetChunk</a></span><span class="sxs-lookup"><span data-stu-id="91917-156"><a href="getchunk-method-ado.md">GetChunk</a></span></span></p></td>
<td><p><span data-ttu-id="91917-157">返回所有或大型文本或二进制数据<strong>Field</strong>对象的内容的一部分。</span><span class="sxs-lookup"><span data-stu-id="91917-157">Returns all, or a portion of, the contents of a large text or binary data <strong>Field</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-158"><a href="getrows-method-ado.md">GetRows</a></span><span class="sxs-lookup"><span data-stu-id="91917-158"><a href="getrows-method-ado.md">GetRows</a></span></span></p></td>
<td><p><span data-ttu-id="91917-159">用于将 <strong>Recordset</strong> 对象的多个记录检索到数组中。</span><span class="sxs-lookup"><span data-stu-id="91917-159">Retrieves multiple records of a <strong>Recordset</strong> object into an array.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-160"><a href="getstring-method-ado.md">GetString</a></span><span class="sxs-lookup"><span data-stu-id="91917-160"><a href="getstring-method-ado.md">GetString</a></span></span></p></td>
<td><p><span data-ttu-id="91917-161">将 <strong>Recordset</strong> 作为字符串返回。</span><span class="sxs-lookup"><span data-stu-id="91917-161">Returns the <strong>Recordset</strong> as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-162"><a href="loadfromfile-method-ado.md">LoadFromFile</a></span><span class="sxs-lookup"><span data-stu-id="91917-162"><a href="loadfromfile-method-ado.md">LoadFromFile</a></span></span></p></td>
<td><p><span data-ttu-id="91917-163">用于将现有文件的内容加载到 <strong>Stream</strong> 中。</span><span class="sxs-lookup"><span data-stu-id="91917-163">Loads the contents of an existing file into a <strong>Stream</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-164"><a href="move-method-ado.md">移动</a></span><span class="sxs-lookup"><span data-stu-id="91917-164"><a href="move-method-ado.md">Move</a></span></span></p></td>
<td><p><span data-ttu-id="91917-165">用于移动 <strong>Recordset</strong> 对象中当前记录的位置。</span><span class="sxs-lookup"><span data-stu-id="91917-165">Moves the position of the current record in a <strong>Recordset</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-166"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst、 MoveLast、 MoveNext 和 MovePrevious</a></span><span class="sxs-lookup"><span data-stu-id="91917-166"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst, MoveLast, MoveNext, and MovePrevious</a></span></span></p></td>
<td><p><span data-ttu-id="91917-167">用于移动到指定的 <strong>Recordset</strong> 对象中的第一个、最后一个、下一个或上一个记录，并使该记录成为当前记录。</span><span class="sxs-lookup"><span data-stu-id="91917-167">Moves to the first, last, next, or previous record in a specified <strong>Recordset</strong> object and makes that record the current record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-168"><a href="moverecord-method-ado.md">MoveRecord</a></span><span class="sxs-lookup"><span data-stu-id="91917-168"><a href="moverecord-method-ado.md">MoveRecord</a></span></span></p></td>
<td><p><span data-ttu-id="91917-169">用于将文件（或目录及其内容）移动到其他位置。</span><span class="sxs-lookup"><span data-stu-id="91917-169">Moves a file, or a directory and its contents, to another location.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-170"><a href="nextrecordset-method-ado.md">NextRecordset</a></span><span class="sxs-lookup"><span data-stu-id="91917-170"><a href="nextrecordset-method-ado.md">NextRecordset</a></span></span></p></td>
<td><p><span data-ttu-id="91917-171">用于通过执行一系列命令，清除当前 <strong>Recordset</strong> 对象并返回下一个 <strong>Recordset</strong> 。</span><span class="sxs-lookup"><span data-stu-id="91917-171">Clears the current <strong>Recordset</strong> object and returns the next <strong>Recordset</strong> by advancing through a series of commands.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-172"><a href="open-method-ado-connection.md">打开 (ADO Connection)</a></span><span class="sxs-lookup"><span data-stu-id="91917-172"><a href="open-method-ado-connection.md">Open (ADO Connection)</a></span></span></p></td>
<td><p><span data-ttu-id="91917-173">用于打开与数据源的连接。</span><span class="sxs-lookup"><span data-stu-id="91917-173">Opens a connection to a data source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-174"><a href="open-method-ado-record.md">打开 (ADO Record)</a></span><span class="sxs-lookup"><span data-stu-id="91917-174"><a href="open-method-ado-record.md">Open (ADO Record)</a></span></span></p></td>
<td><p><span data-ttu-id="91917-175">用于打开现有的 <strong>Record</strong> 对象，或创建新的文件或目录。</span><span class="sxs-lookup"><span data-stu-id="91917-175">Opens an existing <strong>Record</strong> object, or creates a new file or directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-176"><a href="open-method-ado-recordset.md">打开 (ADO Recordset)</a></span><span class="sxs-lookup"><span data-stu-id="91917-176"><a href="open-method-ado-recordset.md">Open (ADO Recordset)</a></span></span></p></td>
<td><p><span data-ttu-id="91917-177">打开游标。</span><span class="sxs-lookup"><span data-stu-id="91917-177">Opens a cursor.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-178"><a href="open-method-ado-stream.md">打开 (ADO Stream)</a></span><span class="sxs-lookup"><span data-stu-id="91917-178"><a href="open-method-ado-stream.md">Open (ADO Stream)</a></span></span></p></td>
<td><p><span data-ttu-id="91917-179">用于打开 <strong>Stream</strong> 对象，以操作二进制数据流或文本数据流。</span><span class="sxs-lookup"><span data-stu-id="91917-179">Opens a <strong>Stream</strong> object to manipulate streams of binary or text data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-180"><a href="openschema-method-ado.md">OpenSchema</a></span><span class="sxs-lookup"><span data-stu-id="91917-180"><a href="openschema-method-ado.md">OpenSchema</a></span></span></p></td>
<td><p><span data-ttu-id="91917-181">用于从提供程序获取数据库架构信息。</span><span class="sxs-lookup"><span data-stu-id="91917-181">Obtains database schema information from the provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-182"><a href="read-method-ado.md">Read</a></span><span class="sxs-lookup"><span data-stu-id="91917-182"><a href="read-method-ado.md">Read</a></span></span></p></td>
<td><p><span data-ttu-id="91917-183">用于从 <strong>Stream</strong> 对象读取指定的字节数。</span><span class="sxs-lookup"><span data-stu-id="91917-183">Reads a specified number of bytes from a <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-184"><a href="readtext-method-ado.md">ReadText</a></span><span class="sxs-lookup"><span data-stu-id="91917-184"><a href="readtext-method-ado.md">ReadText</a></span></span></p></td>
<td><p><span data-ttu-id="91917-185">用于从文本 <strong>Stream</strong> 对象读取指定的字符数。</span><span class="sxs-lookup"><span data-stu-id="91917-185">Reads a specified number of characters from a text <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-186"><a href="refresh-method-ado.md">Refresh</a></span><span class="sxs-lookup"><span data-stu-id="91917-186"><a href="refresh-method-ado.md">Refresh</a></span></span></p></td>
<td><p><span data-ttu-id="91917-187">更新集合中的对象，以反映提供程序特定的可用对象。</span><span class="sxs-lookup"><span data-stu-id="91917-187">Updates the objects in a collection to reflect objects available from, and specific to, the provider.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-188"><a href="requery-method-ado.md">Requery</a></span><span class="sxs-lookup"><span data-stu-id="91917-188"><a href="requery-method-ado.md">Requery</a></span></span></p></td>
<td><p><span data-ttu-id="91917-189">通过重新执行对象所基于的查询，更新 <strong>Recordset</strong> 对象中的数据。</span><span class="sxs-lookup"><span data-stu-id="91917-189">Updates the data in a <strong>Recordset</strong> object by re-executing the query on which the object is based.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-190"><a href="resync-method-ado.md">Resync</a></span><span class="sxs-lookup"><span data-stu-id="91917-190"><a href="resync-method-ado.md">Resync</a></span></span></p></td>
<td><p><span data-ttu-id="91917-191">用于从基础数据库刷新当前 <strong>Recordset</strong> 对象中的数据或刷新 <strong>Record</strong> 对象的 <strong>Fields</strong> 集合中的数据。</span><span class="sxs-lookup"><span data-stu-id="91917-191">Refreshes the data in the current <strong>Recordset</strong> object, or <strong>Fields</strong> collection of a <strong>Record</strong> object, from the underlying database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-192"><a href="save-method-ado.md">Save</a></span><span class="sxs-lookup"><span data-stu-id="91917-192"><a href="save-method-ado.md">Save</a></span></span></p></td>
<td><p><span data-ttu-id="91917-193">可将 <strong>Recordset</strong> 保存到文件或 <strong>Stream</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="91917-193">Saves the <strong>Recordset</strong> in a file or <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-194"><a href="savetofile-method-ado.md">SaveToFile</a></span><span class="sxs-lookup"><span data-stu-id="91917-194"><a href="savetofile-method-ado.md">SaveToFile</a></span></span></p></td>
<td><p><span data-ttu-id="91917-195">可将 <strong>Stream</strong> 的二进制内容保存到文件。</span><span class="sxs-lookup"><span data-stu-id="91917-195">Saves the binary contents of a <strong>Stream</strong> to a file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-196"><a href="seek-method-ado.md">Seek</a></span><span class="sxs-lookup"><span data-stu-id="91917-196"><a href="seek-method-ado.md">Seek</a></span></span></p></td>
<td><p><span data-ttu-id="91917-197">可搜索 <strong>Recordset</strong> 的索引，以快速找到与指定值匹配的行，并将当前行位置更改为该行。</span><span class="sxs-lookup"><span data-stu-id="91917-197">Searches the index of a <strong>Recordset</strong> to quickly locate the row that matches the specified values, and changes the current row position to that row.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-198"><a href="seteos-method-ado.md">SetEOS</a></span><span class="sxs-lookup"><span data-stu-id="91917-198"><a href="seteos-method-ado.md">SetEOS</a></span></span></p></td>
<td><p><span data-ttu-id="91917-199">用于设置流的结束位置。</span><span class="sxs-lookup"><span data-stu-id="91917-199">Sets the position that is the end of the stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-200"><a href="skipline-method-ado.md">SkipLine</a></span><span class="sxs-lookup"><span data-stu-id="91917-200"><a href="skipline-method-ado.md">SkipLine</a></span></span></p></td>
<td><p><span data-ttu-id="91917-201">用于在读取文本流时跳过一整行。</span><span class="sxs-lookup"><span data-stu-id="91917-201">Skips one entire line when reading a text stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-202"><a href="stat-method-ado.md">Stat</a></span><span class="sxs-lookup"><span data-stu-id="91917-202"><a href="stat-method-ado.md">Stat</a></span></span></p></td>
<td><p><span data-ttu-id="91917-203">用于获得有关打开的流的统计信息。</span><span class="sxs-lookup"><span data-stu-id="91917-203">Gets statistical information about an open stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-204"><a href="supports-method-ado.md">支持</a></span><span class="sxs-lookup"><span data-stu-id="91917-204"><a href="supports-method-ado.md">Supports</a></span></span></p></td>
<td><p><span data-ttu-id="91917-205">用于确定指定的 <strong>Recordset</strong> 对象是否支持特定类型的功能。</span><span class="sxs-lookup"><span data-stu-id="91917-205">Determines whether a specified <strong>Recordset</strong> object supports a particular type of functionality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-206"><a href="update-method-ado.md">更新</a></span><span class="sxs-lookup"><span data-stu-id="91917-206"><a href="update-method-ado.md">Update</a></span></span></p></td>
<td><p><span data-ttu-id="91917-207">可保存对 <strong>Recordset</strong> 对象的当前行或 <strong>Record</strong> 对象的 <strong>Fields</strong> 集合所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="91917-207">Saves any changes you make to the current row of a <strong>Recordset</strong> object, or the <strong>Fields</strong> collection of a <strong>Record</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-208"><a href="updatebatch-method-ado.md">UpdateBatch</a></span><span class="sxs-lookup"><span data-stu-id="91917-208"><a href="updatebatch-method-ado.md">UpdateBatch</a></span></span></p></td>
<td><p><span data-ttu-id="91917-209">用于将所有挂起的批更新写入磁盘。</span><span class="sxs-lookup"><span data-stu-id="91917-209">Writes all pending batch updates to disk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91917-210"><a href="write-method-ado.md">写入</a></span><span class="sxs-lookup"><span data-stu-id="91917-210"><a href="write-method-ado.md">Write</a></span></span></p></td>
<td><p><span data-ttu-id="91917-211">用于将二进制数据写入 <strong>Stream</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="91917-211">Writes binary data to a <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91917-212"><a href="writetext-method-ado.md">WriteText</a></span><span class="sxs-lookup"><span data-stu-id="91917-212"><a href="writetext-method-ado.md">WriteText</a></span></span></p></td>
<td><p><span data-ttu-id="91917-213">用于将指定的文本字符串写入 <strong>Stream</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="91917-213">Writes a specified text string to a <strong>Stream</strong> object.</span></span></p></td>
</tr>
</tbody>
</table>

