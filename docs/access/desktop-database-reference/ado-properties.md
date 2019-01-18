---
title: ActiveX 数据对象 (ADO) 属性
TOCTitle: ADO properties
ms:assetid: 04f08f22-6327-c603-229e-d06a9f1c0d83
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248809(v=office.15)
ms:contentKeyID: 48543020
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a0efb40d1b5e4c5d675d8add7cdb7a05760578a9
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28704257"
---
# <a name="ado-properties"></a>ADO 属性

**适用于**： Access 2013、 Office 2013

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="even">
<th>属性</th>
<th>说明</th>
</tr>
<tr class="odd">
<td><p><a href="absolutepage-property-ado.md">AbsolutePage</a></p></td>
<td><p>指示当前记录驻留在哪一页。</p></td>
</tr>
<tr class="even">
<td><p><a href="absoluteposition-property-ado.md">AbsolutePosition</a></p></td>
<td><p>指示 <strong>Recordset</strong> 对象的当前记录的序号位置。</p></td>
</tr>
<tr class="odd">
<td><p><a href="activecommand-property-ado.md">ActiveCommand</a></p></td>
<td><p>指示创建关联的 <strong>Recordset</strong> 对象的 <strong>Command</strong> 对象。</p></td>
</tr>
<tr class="even">
<td><p><a href="activeconnection-property-ado.md">ActiveConnection</a></p></td>
<td><p>指示指定的 <strong>Command</strong>、<strong>Recordset</strong> 或 <strong>Record</strong> 对象当前属于哪个 <strong>Connection</strong> 对象。</p></td>
</tr>
<tr class="odd">
<td><p><a href="actualsize-property-ado.md">ActualSize</a></p></td>
<td><p>指示字段值的实际长度。</p></td>
</tr>
<tr class="even">
<td><p><a href="attributes-property-ado.md">Attributes</a></p></td>
<td><p>指示对象的一个或多个特征。</p></td>
</tr>
<tr class="odd">
<td><p><a href="bof-eof-properties-ado.md">BOF 和 EOF</a></p></td>
<td><p><strong>BOF</strong> — 指示当前记录位置在<strong>Recordset</strong>对象中的第一个记录之前。 <strong>EOF</strong> — 指示当前记录位置在<strong>Recordset</strong>对象中的最后一个记录之后。</p></td>
</tr>
<tr class="even">
<td><p><a href="bookmark-property-ado.md">Bookmark</a></p></td>
<td><p>指示在 <strong>Recordset</strong> 对象中唯一标识当前记录的书签，或者将 <strong>Recordset</strong> 对象中的当前记录设置为有效书签标识的记录。</p></td>
</tr>
<tr class="odd">
<td><p><a href="cachesize-property-ado.md">CacheSize</a></p></td>
<td><p>指示本地缓存在内存中的 <strong>Recordset</strong> 对象的记录数。</p></td>
</tr>
<tr class="even">
<td><p><a href="chapter-property-ado.md">章</a></p></td>
<td><p>从 <strong>ADORecordsetConstruction</strong> 对象获取（或对它设置）OLE DB <strong>Chapter</strong> 对象。</p></td>
</tr>
<tr class="odd">
<td><p><a href="charset-property-ado.md">CharSet</a></p></td>
<td><p>指示文本 <strong>Stream</strong> 的内容应当转换成哪个字符集。</p></td>
</tr>
<tr class="even">
<td><p><a href="commandtext-property-ado.md">CommandText</a></p></td>
<td><p>指示要对提供程序发出的命令的文本。</p></td>
</tr>
<tr class="odd">
<td><p><a href="commandtimeout-property-ado.md">CommandTimeout</a></p></td>
<td><p>指示在执行命令时要等待多长时间才终止操作尝试并生成错误。</p></td>
</tr>
<tr class="even">
<td><p><a href="commandtype-property-ado.md">CommandType</a></p></td>
<td><p>指示 <strong>Command</strong> 对象的类型。</p></td>
</tr>
<tr class="odd">
<td><p><a href="connectionstring-property-ado.md">ConnectionString 属性</a></p></td>
<td><p>指示用于建立数据源连接的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="connectiontimeout-property-ado.md">ConnectionTimeout</a></p></td>
<td><p>指示在建立连接时要等待多长时间才终止连接尝试并生成错误。</p></td>
</tr>
<tr class="odd">
<td><p><a href="count-property-ado.md">Count</a></p></td>
<td><p>指示集合中的对象数。</p></td>
</tr>
<tr class="even">
<td><p><a href="cursorlocation-property-ado.md">CursorLocation</a></p></td>
<td><p>指示游标服务的位置。</p></td>
</tr>
<tr class="odd">
<td><p><a href="cursortype-property-ado.md">CursorType</a></p></td>
<td><p>指示在 <strong>Recordset</strong> 对象中使用的游标类型。</p></td>
</tr>
<tr class="even">
<td><p><a href="datamember-property-ado.md">DataMember</a></p></td>
<td><p>指示将从 <strong>DataSource</strong> 属性所引用的对象中检索的数据成员的名称。</p></td>
</tr>
<tr class="odd">
<td><p><a href="datasource-property-ado.md">DataSource</a></p></td>
<td><p>指示一个对象，其中包含要表示为 <strong>Recordset</strong> 对象的数据。</p></td>
</tr>
<tr class="even">
<td><p><a href="defaultdatabase-property-ado.md">DefaultDatabase</a></p></td>
<td><p>指示 <strong>Connection</strong> 对象的默认数据库。</p></td>
</tr>
<tr class="odd">
<td><p><a href="definedsize-property-ado.md">DefinedSize</a></p></td>
<td><p>指示 <strong>Field</strong> 对象的数据容量。</p></td>
</tr>
<tr class="even">
<td><p><a href="description-property-ado.md">说明</a></p></td>
<td><p>描述 <strong>Error</strong> 对象。</p></td>
</tr>
<tr class="odd">
<td><p><a href="direction-property-ado.md">Direction</a></p></td>
<td><p>指示 <strong>Parameter</strong> 是否表示输入参数和/或输出参数，或者参数是否是存储过程的返回值。</p></td>
</tr>
<tr class="even">
<td><p><a href="editmode-property-ado.md">EditMode</a></p></td>
<td><p>指示当前记录的编辑状态。</p></td>
</tr>
<tr class="odd">
<td><p><a href="eos-property-ado.md">EOS</a></p></td>
<td><p>指示当前位置是否位于流的末尾。</p></td>
</tr>
<tr class="even">
<td><p><a href="filter-property-ado.md">Filter</a></p></td>
<td><p>指示 <strong>Recordset</strong> 中数据的筛选条件。</p></td>
</tr>
<tr class="odd">
<td><p><a href="helpcontext-helpfile-properties-ado.md">HelpContext 和 HelpFile</a></p></td>
<td><p>指示与 <strong>Error</strong> 对象关联的帮助文件和主题。 <strong>HelpContextID</strong>  返回帮助文件中主题的上下文 ID，返回值的类型为 <strong>Long</strong> 。 <strong>HelpFile</strong>  返回一个 <strong>String</strong> 类型的值，作为帮助文件完全解析路径的计算结果。</p></td>
</tr>
<tr class="even">
<td><p><a href="index-property-ado.md">索引</a></p></td>
<td><p>指示当前对 <strong>Recordset</strong> 对象有效的索引的名称。</p></td>
</tr>
<tr class="odd">
<td><p><a href="isolationlevel-property-ado.md">IsolationLevel</a></p></td>
<td><p>指示 <strong>Connection</strong> 对象的隔离级别。</p></td>
</tr>
<tr class="even">
<td><p><a href="item-property-ado.md">项</a></p></td>
<td><p>按名称或序号指示集合的特定成员。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lineseparator-property-ado.md">LineSeparator</a></p></td>
<td><p>指示要在文本 <strong>Stream</strong> 对象中用作行分隔符的二进制字符。</p></td>
</tr>
<tr class="even">
<td><p><a href="locktype-property-ado.md">LockType</a></p></td>
<td><p>指示编辑过程中为记录设置的锁定类型。</p></td>
</tr>
<tr class="odd">
<td><p><a href="marshaloptions-property-ado.md">MarshalOptions</a></p></td>
<td><p>指示哪些记录要封送回服务器。</p></td>
</tr>
<tr class="even">
<td><p><a href="maxrecords-property-ado.md">MaxRecords</a></p></td>
<td><p>指示通过查询返回到 <strong>Recordset</strong> 的最大记录数。</p></td>
</tr>
<tr class="odd">
<td><p><a href="mode-property-ado.md">Mode</a></p></td>
<td><p>指示在 <strong>Connection</strong>、<strong>Record</strong> 或 <strong>Stream</strong> 对象中修改数据的可用权限。</p></td>
</tr>
<tr class="even">
<td><p><a href="name-property-ado.md">Name</a></p></td>
<td><p>指示对象的名称。</p></td>
</tr>
<tr class="odd">
<td><p><a href="nativeerror-property-ado.md">NativeError</a></p></td>
<td><p>指示给定 <strong>Error</strong> 对象特定于提供程序的错误代码。</p></td>
</tr>
<tr class="even">
<td><p><a href="number-property-ado.md">Number</a></p></td>
<td><p>指示用于唯一标识 <strong>Error</strong> 对象的编号。</p></td>
</tr>
<tr class="odd">
<td><p><a href="numericscale-property-ado.md">NumericScale</a></p></td>
<td><p>指示 <strong>Parameter</strong> 或 <strong>Field</strong> 对象中数值的小数位数。</p></td>
</tr>
<tr class="even">
<td><p><a href="originalvalue-property-ado.md">OriginalValue</a></p></td>
<td><p>指示记录发生任何更改之前的 <strong>Field</strong> 值。</p></td>
</tr>
<tr class="odd">
<td><p><a href="pagecount-property-ado.md">PageCount</a></p></td>
<td><p>指示 <strong>Recordset</strong> 对象包含的数据页数。</p></td>
</tr>
<tr class="even">
<td><p><a href="pagesize-property-ado.md">PageSize</a></p></td>
<td><p>指示由多少记录构成 <strong>Recordset</strong> 中的一页。</p></td>
</tr>
<tr class="odd">
<td><p><a href="parentrow-property-ado.md">ParentRow</a></p></td>
<td><p>在 <strong>ADORecordConstruction</strong> 对象上设置 OLE DB <strong>Row</strong> 对象的容器，以便将行的父项转换为 ADO <strong>Record</strong> 对象。</p></td>
</tr>
<tr class="even">
<td><p><a href="parenturl-property-ado.md">ParentURL</a></p></td>
<td><p>指示指向当前 <strong>Record</strong> 对象的父 <strong>Record</strong> 的绝对 URL 字符串。</p></td>
</tr>
<tr class="odd">
<td><p><a href="position-property-ado.md">Position</a></p></td>
<td><p>指示 <strong>Stream</strong> 对象中的当前位置。</p></td>
</tr>
<tr class="even">
<td><p><a href="precision-property-ado.md">精度</a></p></td>
<td><p>指示 <strong>Parameter</strong> 对象或数字 <strong>Field</strong> 对象中数值的精度。</p></td>
</tr>
<tr class="odd">
<td><p><a href="prepared-property-ado.md">只有在准备好</a></p></td>
<td><p>指示是否在执行之前保存命令的已编译版本。</p></td>
</tr>
<tr class="even">
<td><p><a href="provider-property-ado.md">Provider</a></p></td>
<td><p>指示 <strong>Connection</strong> 对象的提供程序的名称。</p></td>
</tr>
<tr class="odd">
<td><p><a href="recordcount-property-ado.md">RecordCount</a></p></td>
<td><p>指示 <strong>Recordset</strong> 对象中的记录数。</p></td>
</tr>
<tr class="even">
<td><p><a href="recordtype-property-ado.md">RecordType</a></p></td>
<td><p>指示 <strong>Record</strong> 对象的类型。</p></td>
</tr>
<tr class="odd">
<td><p><a href="row-property-ado.md">行</a></p></td>
<td><p>获取或设置 <strong>ADORecordConstruction</strong> 对象的 OLE DB <strong>Row</strong> 对象。</p></td>
</tr>
<tr class="even">
<td><p><a href="rowposition-property-ado.md">RowPosition</a></p></td>
<td><p>通过 <strong>ADORecordsetConstruction</strong> 对象获取或设置一个 OLE DB <strong>RowPosition</strong> 对象。</p></td>
</tr>
<tr class="odd">
<td><p><a href="rowset-property-ado.md">行集</a></p></td>
<td><p>通过 <strong>ADORecordsetConstruction</strong> 对象获取或设置一个 OLE DB <strong>Rowset</strong> 对象。</p></td>
</tr>
<tr class="even">
<td><p><a href="size-property-ado.md">Size</a></p></td>
<td><p>指示 <strong>Parameter</strong> 对象的最大大小，以字节或字符为单位。</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/size-property-ado-stream">大小 (ADO Stream)</a></p></td>
<td><p>指示流的总计大小（字节数）。</p></td>
</tr>
<tr class="even">
<td><p><a href="sort-property-ado.md">Sort</a></p></td>
<td><p>指示一个或多个作为 <strong>Recordset</strong> 的排序依据的字段名称，并指定是按升序还是降序对字段进行排序。</p></td>
</tr>
<tr class="odd">
<td><p><a href="source-property-ado-error.md">源 (ADO Error)</a></p></td>
<td><p>指示最初生成错误的对象或应用程序的名称。</p></td>
</tr>
<tr class="even">
<td><p><a href="source-property-ado-record.md">源 (ADO Record)</a></p></td>
<td><p>指示 <strong>Record</strong> 对象所表示的实体。</p></td>
</tr>
<tr class="odd">
<td><p><a href="source-property-ado-recordset.md">源 (ADO Recordset)</a></p></td>
<td><p>指示 <strong>Recordset</strong> 对象中数据的来源</p></td>
</tr>
<tr class="even">
<td><p><a href="sqlstate-property-ado.md">SQLState</a></p></td>
<td><p>指示给定 <strong>Error</strong> 对象的 SQL 状态。</p></td>
</tr>
<tr class="odd">
<td><p><a href="state-property-ado.md">State</a></p></td>
<td><p>对所有适用的对象，指示其状态是打开还是关闭。 指示对象的当前状态是连接、执行还是检索，针对执行异步方法的所有适用对象</p></td>
</tr>
<tr class="even">
<td><p><a href="status-property-ado-field.md">状态 (ADO Field)</a></p></td>
<td><p>指示 <strong>Field</strong> 对象的状态。</p></td>
</tr>
<tr class="odd">
<td><p><a href="status-property-ado-recordset.md">状态 (ADO Recordset)</a></p></td>
<td><p>指示与批更新或其他批量操作相关的当前记录的状态。</p></td>
</tr>
<tr class="even">
<td><p><a href="stayinsync-property-ado.md">StayInSync</a></p></td>
<td><p>指示在分层 <strong>Recordset</strong> 对象中，当父行位置更改时，对基础子记录（即<em>章节</em>）的引用是否发生了更改。</p></td>
</tr>
<tr class="odd">
<td><p><a href="type-property-ado.md">Type</a></p></td>
<td><p>指示 <strong>Parameter</strong>、<strong>Field</strong> 或 <strong>Property</strong> 对象的操作类型或数据类型。</p></td>
</tr>
<tr class="even">
<td><p><a href="type-property-ado-stream.md">类型 (ADO Stream)</a></p></td>
<td><p>指示 <strong>Stream</strong> 中包含的数据类型（二进制或文本）。</p></td>
</tr>
<tr class="odd">
<td><p><a href="underlyingvalue-property-ado.md">UnderlyingValue</a></p></td>
<td><p>指示数据库中 <strong>Field</strong> 对象的当前值。</p></td>
</tr>
<tr class="even">
<td><p><a href="value-property-ado.md">Value</a></p></td>
<td><p>指示赋给 <strong>Field</strong>、<strong>Parameter</strong> 或 <strong>Property</strong> 对象的值。</p></td>
</tr>
<tr class="odd">
<td><p><a href="version-property-ado.md">Version</a></p></td>
<td><p>指示 ADO 版本号。</p></td>
</tr>
</tbody>
</table>

<br/>
