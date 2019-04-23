---
title: ActiveX 数据对象 (ADO) 方法
TOCTitle: ADO methods
ms:assetid: 1fd965a0-711c-e199-822c-b9575c5034bd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248984(v=office.15)
ms:contentKeyID: 48543651
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 3169b7eaab6ad290bfc385881f5de69edc80111f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283280"
---
# <a name="ado-methods"></a>ADO 方法

**适用于**：Access 2013、Office 2013

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="even">
<th>方法</th>
<th>说明</th>
</tr>
<tr class="odd">
<td><p><a href="addnew-method-ado.md">AddNew</a></p></td>
<td><p>为可更新的 <strong>Recordset</strong> 对象创建新记录。</p></td>
</tr>
<tr class="even">
<td><p><a href="append-method-ado.md">Append</a></p></td>
<td><p>用于将对象追加到集合。如果集合为 <strong>Fields</strong>，则在将对象追加到集合之前，可能会创建新的 <strong>Field</strong> 对象。</p></td>
</tr>
<tr class="odd">
<td><p><a href="appendchunk-method-ado.md">AppendChunk</a></p></td>
<td><p>用于将数据追加到大型文本或二进制数据 <strong>Field</strong> 或 <strong>Parameter</strong> 对象。</p></td>
</tr>
<tr class="even">
<td><p><a href="begintrans-committrans-and-rollbacktrans-methods-ado.md">BeginTrans、CommitTrans 和 RollbackTrans</a></p></td>
<td><p>用于管理 <strong>Connection</strong> 对象中的事务处理，如下所示：<br/><br/><strong>BeginTrans</strong> - 开始新的事务。<br/><br/>
<strong>CommitTrans</strong> - 保存任何更改并结束当前事务。还可以开始一个新的事务。<br/><br/>
<strong>RollbackTrans</strong> —取消所有更改并结束当前事务。 它也可能开始新事务。</p></td>
</tr>
<tr class="odd">
<td><p><a href="cancel-method-ado.md">Cancel</a></p></td>
<td><p>用于取消执行挂起的异步方法调用。</p></td>
</tr>
<tr class="even">
<td><p><a href="cancelbatch-method-ado.md">CancelBatch</a></p></td>
<td><p>用于取消挂起的批更新。</p></td>
</tr>
<tr class="odd">
<td><p><a href="cancelupdate-method-ado.md">CancelUpdate</a></p></td>
<td><p>在调用 <strong>Update</strong> 方法之前，取消对 <strong>Recordset</strong> 对象的当前行或新行，或对 <strong>Record</strong> 对象的 <strong>Fields</strong> 集合所做的任何更改。</p></td>
</tr>
<tr class="even">
<td><p><a href="clear-method-ado.md">Clear</a></p></td>
<td><p>用于从 <strong>Errors</strong> 集合中删除所有 <strong>Error</strong> 对象。</p></td>
</tr>
<tr class="odd">
<td><p><a href="clone-method-ado.md">Clone</a></p></td>
<td><p>用于从现有 <strong>Recordset</strong> 对象创建重复的 <strong>Recordset</strong> 对象。 还可以指定克隆为只读状态。</p></td>
</tr>
<tr class="even">
<td><p><a href="close-method-ado.md">Close</a></p></td>
<td><p>用于关闭打开的对象和任何相关的对象。</p></td>
</tr>
<tr class="odd">
<td><p><a href="comparebookmarks-method-ado.md">CompareBookmarks</a></p></td>
<td><p>用于比较两个书签，并返回其相对值的指示。</p></td>
</tr>
<tr class="even">
<td><p><a href="copyrecord-method-ado.md">CopyRecord</a></p></td>
<td><p>用于将文件或目录及其内容复制到其他位置。</p></td>
</tr>
<tr class="odd">
<td><p><a href="copyto-method-ado.md">CopyTo</a></p></td>
<td><p>用于将 <strong>Stream</strong> 中指定数量的字符或字节（取决于<strong>类型</strong>）复制到另一个 <strong>Stream</strong> 对象。</p></td>
</tr>
<tr class="even">
<td><p><a href="createparameter-method-ado.md">CreateParameter</a></p></td>
<td><p>用于创建具有指定属性的新 <strong>Parameter</strong> 对象。</p></td>
</tr>
<tr class="odd">
<td><p><a href="delete-method-ado-parameters-collection.md">Delete（ADO Parameters 集合）</a></p></td>
<td><p>用于从 <strong>Parameters</strong> 集合中删除对象。</p></td>
</tr>
<tr class="even">
<td><p><a href="delete-method-ado-fields-collection.md">Delete（ADO Fields 集合）</a></p></td>
<td><p>用于从 <strong>Fields</strong> 集合中删除对象。</p></td>
</tr>
<tr class="odd">
<td><p><a href="delete-method-ado-recordset.md">Delete (ADO Recordset)</a></p></td>
<td><p>用于删除当前记录或一组记录。</p></td>
</tr>
<tr class="even">
<td><p><a href="deleterecord-method-ado.md">DeleteRecord</a></p></td>
<td><p>用于删除文件或目录及其所有子目录。</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command">Execute (ADO Command)</a></p></td>
<td><p>用于执行在 <strong>CommandText</strong> 属性中指定的查询、SQL 语句或存储过程。</p></td>
</tr>
<tr class="even">
<td><p><a href="https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-connection">Execute (ADO Connection)</a></p></td>
<td><p>用于执行指定的查询、SQL 语句、存储过程或提供程序的特定文本。</p></td>
</tr>
<tr class="odd">
<td><p><a href="find-method-ado.md">查找</a></p></td>
<td><p>用于在 <strong>Recordset</strong> 中搜索符合指定条件的行。</p></td>
</tr>
<tr class="even">
<td><p><a href="flush-method-ado.md">对齐</a></p></td>
<td><p>用于将保留在 ADO 缓冲区中的 <strong>Stream</strong> 的内容强制转移到 <strong>Stream</strong> 所关联的基础对象中。</p></td>
</tr>
<tr class="odd">
<td><p><a href="getchildren-method-ado.md">GetChildren</a></p></td>
<td><p>用于返回一个 <strong>Recordset</strong>，其行表示此 <strong>Record</strong> 所表示的目录中的文件和子目录。</p></td>
</tr>
<tr class="even">
<td><p><a href="getchunk-method-ado.md">GetChunk</a></p></td>
<td><p>返回大型文本或二进制数据 <strong>Field</strong> 对象的所有（或部分）内容。</p></td>
</tr>
<tr class="odd">
<td><p><a href="getrows-method-ado.md">GetRows</a></p></td>
<td><p>用于将 <strong>Recordset</strong> 对象的多个记录检索到数组中。</p></td>
</tr>
<tr class="even">
<td><p><a href="getstring-method-ado.md">GetString</a></p></td>
<td><p>将 <strong>Recordset</strong> 作为字符串返回。</p></td>
</tr>
<tr class="odd">
<td><p><a href="loadfromfile-method-ado.md">LoadFromFile</a></p></td>
<td><p>用于将现有文件的内容加载到 <strong>Stream</strong> 中。</p></td>
</tr>
<tr class="even">
<td><p><a href="move-method-ado.md">Move</a></p></td>
<td><p>用于移动 <strong>Recordset</strong> 对象中当前记录的位置。</p></td>
</tr>
<tr class="odd">
<td><p><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst、MoveLast、MoveNext 和 MovePrevious</a></p></td>
<td><p>用于移动到指定的 <strong>Recordset</strong> 对象中的第一个、最后一个、下一个或上一个记录，并使该记录成为当前记录。</p></td>
</tr>
<tr class="even">
<td><p><a href="moverecord-method-ado.md">MoveRecord</a></p></td>
<td><p>用于将文件（或目录及其内容）移动到其他位置。</p></td>
</tr>
<tr class="odd">
<td><p><a href="nextrecordset-method-ado.md">NextRecordset</a></p></td>
<td><p>用于通过执行一系列命令，清除当前 <strong>Recordset</strong> 对象并返回下一个 <strong>Recordset</strong>。</p></td>
</tr>
<tr class="even">
<td><p><a href="open-method-ado-connection.md">Open (ADO Connection)</a></p></td>
<td><p>用于打开与数据源的连接。</p></td>
</tr>
<tr class="odd">
<td><p><a href="open-method-ado-record.md">Open (ADO Record)</a></p></td>
<td><p>用于打开现有的 <strong>Record</strong> 对象，或创建新的文件或目录。</p></td>
</tr>
<tr class="even">
<td><p><a href="open-method-ado-recordset.md">Open (ADO Recordset)</a></p></td>
<td><p>可打开游标。</p></td>
</tr>
<tr class="odd">
<td><p><a href="open-method-ado-stream.md">Open (ADO Stream)</a></p></td>
<td><p>用于打开 <strong>Stream</strong> 对象，以操作二进制数据流或文本数据流。</p></td>
</tr>
<tr class="even">
<td><p><a href="openschema-method-ado.md">OpenSchema</a></p></td>
<td><p>用于从提供程序获取数据库架构信息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="read-method-ado.md">Read</a></p></td>
<td><p>用于从 <strong>Stream</strong> 对象读取指定的字节数。</p></td>
</tr>
<tr class="even">
<td><p><a href="readtext-method-ado.md">ReadText</a></p></td>
<td><p>用于从文本 <strong>Stream</strong> 对象读取指定的字符数。</p></td>
</tr>
<tr class="odd">
<td><p><a href="refresh-method-ado.md">Refresh</a></p></td>
<td><p>用于更新集合中的对象，以反映提供程序的特定可用对象。</p></td>
</tr>
<tr class="even">
<td><p><a href="requery-method-ado.md">Requery</a></p></td>
<td><p>通过重新执行对象所基于的查询，更新 <strong>Recordset</strong> 对象中的数据。</p></td>
</tr>
<tr class="odd">
<td><p><a href="resync-method-ado.md">同步</a></p></td>
<td><p>用于从基础数据库刷新当前 <strong>Recordset</strong> 对象中的数据或刷新 <strong>Record</strong> 对象的 <strong>Fields</strong> 集合中的数据。</p></td>
</tr>
<tr class="even">
<td><p><a href="save-method-ado.md">Save</a></p></td>
<td><p>可将 <strong>Recordset</strong> 保存到文件或 <strong>Stream</strong> 对象。</p></td>
</tr>
<tr class="odd">
<td><p><a href="savetofile-method-ado.md">SaveToFile</a></p></td>
<td><p>可将 <strong>Stream</strong> 的二进制内容保存到文件。</p></td>
</tr>
<tr class="even">
<td><p><a href="seek-method-ado.md">Seek</a></p></td>
<td><p>可搜索 <strong>Recordset</strong> 的索引，以快速找到与指定值匹配的行，并将当前行位置更改为该行。</p></td>
</tr>
<tr class="odd">
<td><p><a href="seteos-method-ado.md">SetEOS</a></p></td>
<td><p>用于设置流的结束位置。</p></td>
</tr>
<tr class="even">
<td><p><a href="skipline-method-ado.md">SkipLine</a></p></td>
<td><p>用于在读取文本流时跳过一整行。</p></td>
</tr>
<tr class="odd">
<td><p><a href="stat-method-ado.md">Stat</a></p></td>
<td><p>用于获得有关打开的流的统计信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="supports-method-ado.md">支持</a></p></td>
<td><p>用于确定指定的 <strong>Recordset</strong> 对象是否支持特定类型的功能。</p></td>
</tr>
<tr class="odd">
<td><p><a href="update-method-ado.md">Update</a></p></td>
<td><p>可保存对 <strong>Recordset</strong> 对象的当前行或 <strong>Record</strong> 对象的 <strong>Fields</strong> 集合所做的任何更改。</p></td>
</tr>
<tr class="even">
<td><p><a href="updatebatch-method-ado.md">UpdateBatch</a></p></td>
<td><p>用于将所有挂起的批更新写入磁盘。</p></td>
</tr>
<tr class="odd">
<td><p><a href="write-method-ado.md">Write</a></p></td>
<td><p>用于将二进制数据写入 <strong>Stream</strong> 对象。</p></td>
</tr>
<tr class="even">
<td><p><a href="writetext-method-ado.md">WriteText</a></p></td>
<td><p>用于将指定的文本字符串写入 <strong>Stream</strong> 对象。</p></td>
</tr>
</tbody>
</table>

<br/>
