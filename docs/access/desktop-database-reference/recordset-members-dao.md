---
title: 记录集成员 (DAO)
TOCTitle: Recordset Members
ms:assetid: cfaae9ec-1b88-4285-1ebe-637564e99dc8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834683(v=office.15)
ms:contentKeyID: 48547815
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 70593fdcab32602ba6b0e4597368f64371d8f116
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25937363"
---
# <a name="recordset-members-dao"></a>记录集成员 (DAO)


**适用于**： Access 2013、 Office 2013

Recordset 对象代表基表中的记录或通过运行查询得到的记录。

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
<td><p><strong><a href="recordset-addnew-method-dao.md">AddNew</a></strong></p></td>
<td><p>为可更新的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象创建新记录。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-cancel-method-dao.md">取消</a></strong></p></td>
<td><p></p>

> [!NOTE]
> Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。


<p>取消执行待定的异步方法调用（仅适用于 ODBCDirect 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-cancelupdate-method-dao.md">CancelUpdate</a></strong></p></td>
<td><p>取消 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象的任何待定更新。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-clone-method-dao.md">Clone</a></strong></p></td>
<td><p>创建一个引用原始 <a href="recordset-object-dao.md">Recordset</a> 对象的复制 <strong><strong>Recordset</strong></strong> 对象。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-close-method-dao.md">关闭</a></strong></p></td>
<td><p>关闭已打开的 <strong>Recordset</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-copyquerydef-method-dao.md">CopyQueryDef</a></strong></p></td>
<td><p>返回一个<strong>QueryDef</strong>的副本的<strong><a href="querydef-object-dao.md">QueryDef</a></strong>对象用于创建<strong><a href="recordset-object-dao.md">Recordset</a></strong>对象表示由 recordset 占位符 （仅限 Microsoft Access 工作区）。 .</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-delete-method-dao.md">删除</a></strong></p></td>
<td><p>不支持此对象。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-edit-method-dao.md">Edit</a></strong></p></td>
<td><p>将当前记录从可更新的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象复制到复制缓冲区，以进行后续编辑。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-fillcache-method-dao.md">FillCache</a></strong></p></td>
<td><p>为某个 <strong>Recordset</strong> 对象填充所有或一部分本地缓存，该对象包含来自 Microsoft Access 数据库引擎连接的 ODBC 数据源中的数据（仅适用于 Microsoft Access 数据库引擎连接的 ODBC 数据库）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-findfirst-method-dao.md">FindFirst</a></strong></p></td>
<td><p>在动态集类型或快照类型的 <strong>Recordset</strong> 对象中查找符合指定条件的第一条记录，并使该记录成为当前记录（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-findlast-method-dao.md">FindLast</a></strong></p></td>
<td><p>在动态集类型或快照类型的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象中查找符合指定条件的最后一条记录，并且使该记录成为当前记录（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-findnext-method-dao.md">FindNext</a></strong></p></td>
<td><p>在动态集类型或快照类型的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象中查找符合指定条件的下一条记录，并且使该记录成为当前记录（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-findprevious-method-dao.md">FindPrevious</a></strong></p></td>
<td><p>在动态集类型或快照类型的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象中查找符合指定条件的上一条记录，并且使该记录成为当前记录（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-getrows-method-dao.md">GetRows</a></strong></p></td>
<td><p>检索 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象中的多行。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-move-method-dao.md">Move</a></strong></p></td>
<td><p>移动 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象中的当前记录的位置。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-movefirst-method-dao.md">MoveFirst</a></strong></p></td>
<td><p>移到指定的 <strong>Recordset</strong> 对象中的第一条记录，并使该记录成为当前记录。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-movelast-method-dao.md">MoveLast</a></strong></p></td>
<td><p>移到指定的 <strong>Recordset</strong> 对象中的最后一条记录，并使该记录成为当前记录。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-movenext-method-dao.md">MoveNext</a></strong></p></td>
<td><p>移到指定的 <strong>Recordset</strong> 对象中的下一条记录，并使该记录成为当前记录。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-moveprevious-method-dao.md">MovePrevious</a></strong></p></td>
<td><p>移到指定的 <strong>Recordset</strong> 对象中的上一条记录，并使该记录成为当前记录。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-nextrecordset-method-dao.md">NextRecordset</a></strong></p></td>
<td><p></p>

> [!NOTE]
> Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。


<p>获取 <strong><a href="connection-openrecordset-method-dao.md">OpenRecordset</a></strong> 调用中多部分选择查询返回的下一个记录集（如果有的话），并且返回一个 <strong>Boolean</strong> 值，用于指示是有一个还是有多个附加记录处于待定状态（仅适用于 ODBCDirect 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-openrecordset-method-dao.md">OpenRecordset</a></strong></p></td>
<td><p>创建一个新的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象，并将其追加到 <strong>Recordsets</strong> 集合。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-requery-method-dao.md">Requery</a></strong></p></td>
<td><p>通过重新执行对象所基于的查询，更新 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象中的数据。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-seek-method-dao.md">Seek</a></strong></p></td>
<td><p>在已建立索引的表类型 <strong>Recordset</strong> 对象中查找符合当前索引的指定条件的记录，并使该记录成为当前记录（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-update-method-dao.md">Update</a></strong></p></td>
<td><p></p>

> [!NOTE]
> Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。


<p>将复制缓冲区的内容保存到可更新的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象。</p></td>
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
<td><p><strong><a href="recordset-absoluteposition-property-dao.md">AbsolutePosition</a></strong></p></td>
<td><p>设置或返回 <strong>Recordset</strong> 对象的当前记录的相对记录编号。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-batchcollisioncount-property-dao.md">BatchCollisionCount</a></strong></p></td>
<td><p></p>

> [!NOTE]
> Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。


<p>返回未完成上一批更新的记录数（仅适用于 ODBCDirect 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-batchcollisions-property-dao.md">BatchCollisions</a></strong></p></td>
<td><p></p>

> [!NOTE]
> Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。


<p>返回一个书签数组，用于指示在上次批更新操作中产生冲突的行（仅适用于 ODBCDirect 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-batchsize-property-dao.md">BatchSize</a></strong></p></td>
<td><p></p>

> [!NOTE]
> Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。


<p>设置或返回每次批处理中发送回服务器的语句数（仅适用于 ODBCDirect 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-bof-property-dao.md">BOF</a></strong></p></td>
<td><p>返回一个值，该值指示当前记录的位置是否在 <strong>Recordset</strong> 对象中的第一条记录之前。只读 <strong>Boolean</strong> 类型。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-bookmark-property-dao.md">书签</a></strong></p></td>
<td><p>设置或返回一个书签，该书签唯一地标识 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象中的当前记录。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-bookmarkable-property-dao.md">Bookmarkable</a></strong></p></td>
<td><p>返回一个值，该值表示 <strong>Recordset</strong> 对象是否支持书签（可以使用 <strong><a href="recordset-bookmark-property-dao.md">Bookmark</a></strong> 属性来设置书签）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-cachesize-property-dao.md">CacheSize</a></strong></p></td>
<td><p>设置或返回从 ODBC 数据源中检索的、需要本地缓存的记录数。可读/写 <strong>Long</strong> 类型。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-cachestart-property-dao.md">CacheStart</a></strong></p></td>
<td><p>设置或返回一个值，该值指定动态集类型 Recordset 对象（包含从 ODBC 数据源本地缓存的数据）中的第一条记录的书签（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-connection-property-dao.md">Connection</a></strong></p></td>
<td><p>返回对应于数据库的 <strong><a href="connection-object-dao.md">Connection</a></strong> 对象。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-datecreated-property-dao.md">DateCreated</a></strong></p></td>
<td><p>返回基表的创建日期和时间（仅适用于 Microsoft Access 工作区）。只读 <strong>Variant</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-editmode-property-dao.md">EditMode</a></strong></p></td>
<td><p>返回一个值，该值指示当前记录的编辑状态。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-eof-property-dao.md">EOF</a></strong></p></td>
<td><p>返回一个值，该值指示当前记录位置是否位于 <strong>Recordset</strong> 对象的最后一条记录之后。只读 <strong>Boolean</strong> 类型。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-fields-property-dao.md">字段</a></strong></p></td>
<td><p>返回一个 <strong>Fields</strong> 集合，该集合表示指定对象的所有存储 <strong>Field</strong> 对象。只读。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-filter-property-dao.md">筛选器</a></strong></p></td>
<td><p>设置或返回一个值，该值确定在以后打开的 <strong>Recordset</strong> 对象中包含的记录（仅适用于 Microsoft Access 工作区）。可读写 <strong>String</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-index-property-dao.md">索引</a></strong></p></td>
<td><p>设置或返回一个值，该值指示表类型 <strong><a href="index-object-dao.md">Recordset</a></strong> 对象中的当前 <strong><a href="recordset-object-dao.md">Index</a></strong> 对象的名称（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-lastmodified-property-dao.md">LastModified</a></strong></p></td>
<td><p>返回一个书签，该书签指示最近添加或更改的记录。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-lastupdated-property-dao.md">LastUpdated</a></strong></p></td>
<td><p>返回基表的最近更改日期和时间。只读 <strong>Variant</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-lockedits-property-dao.md">LockEdits</a></strong></p></td>
<td><p>设置或返回一个值，该值指示编辑时生效的锁定的类型。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-name-property-dao.md">Name</a></strong></p></td>
<td><p>返回指定对象的名称。只读 <strong>String</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-nomatch-property-dao.md">NoMatch</a></strong></p></td>
<td><p>指示在使用 <strong><a href="recordset-seek-method-dao.md">Seek</a></strong> 方法或 <strong><a href="recordset-findfirst-method-dao.md">Find</a></strong> 方法之一后，是否找到了特定的记录（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-percentposition-property-dao.md">PercentPosition</a></strong></p></td>
<td><p>设置或返回一个值，用于根据 <a href="recordset-object-dao.md">Recordset</a> 中的记录百分比指示 <strong><strong>Recordset</strong></strong> 对象中当前记录的大概位置。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-properties-property-dao.md">属性</a></strong></p></td>
<td><p>返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。只读。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-recordcount-property-dao.md">RecordCount</a></strong></p></td>
<td><p>返回在 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象中访问的记录数，或者返回表类型 <strong>Recordset</strong> 对象或 <strong><a href="tabledef-object-dao.md">TableDef</a></strong> 对象中的记录总数。只读 <strong>Long</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-recordstatus-property-dao.md">RecordStatus</a></strong></p></td>
<td><p></p>

> [!NOTE]
> Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。


<p>返回一个值，如果当前记录是批更新的一部分，该值将指示当前记录的更新状态（仅适用于 ODBCDirect 工作区）。只读 <strong><a href="recordstatusenum-enumeration-dao.md">RecordStatusEnum</a></strong> 。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-restartable-property-dao.md">Restartable</a></strong></p></td>
<td><p>返回一个值，该值表示 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象是否支持 <strong><a href="recordset-requery-method-dao.md">Requery</a></strong> 方法，该方法重新执行 <strong>Recordset</strong> 对象所基于的查询。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-sort-property-dao.md">Sort</a></strong></p></td>
<td><p>设置或返回 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象中的记录的排序次序（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-stillexecuting-property-dao.md">StillExecuting</a></strong></p></td>
<td><p></p>

> [!NOTE]
> Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。


<p>指示异步操作（即用 <strong>dbRunAsync</strong> 选项调用的方法）是否已执行完毕（仅适用于 ODBCDirect 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-transactions-property-dao.md">事务</a></strong></p></td>
<td><p>返回一个值，该值指示对象是否支持事务。只读 <strong>Boolean</strong> 类型。</p></td>
</tr>
<tr class="even">
<td><p><strong>类型</strong></p></td>
<td><p>Office 14 的最终版本中将会提供此成员的说明。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-updatable-property-dao.md">Updatable</a></strong></p></td>
<td><p>返回一个值，该值指示是否可以更改 DAO 对象。只读 <strong>Boolean</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-updateoptions-property-dao.md">UpdateOptions</a></strong></p></td>
<td><p></p>

> [!NOTE]
> Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。


<p>设置或返回一个值，该值指示在批更新过程中如何为每条记录构建 WHERE 子句，以及批更新是应当使用 UPDATE 语句，还是应当使用后跟 INSERT 的 DELETE（仅适用于 ODBCDirect 工作区）。可读写。 <strong><a href="updatecriteriaenum-enumeration-dao.md">UpdateCriteriaEnum</a></strong> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="recordset-validationrule-property-dao.md">ValidationRule</a></strong></p></td>
<td><p>设置或返回一个值，当字段中的数据更改或添加到表中时，该值对这些数据进行验证（仅适用于 Microsoft Access 工作区）。可读写 <strong>String</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="recordset-validationtext-property-dao.md">ValidationText</a></strong></p></td>
<td><p>设置或返回一个值，该值指定在 <strong>Field</strong> 对象的值不满足 <strong>ValidationRule</strong> 属性设置所指定的验证规则时应用程序显示的消息文本（仅适用于 Microsoft Access 工作区）。只读 <strong>String</strong>。</p></td>
</tr>
</tbody>
</table>

