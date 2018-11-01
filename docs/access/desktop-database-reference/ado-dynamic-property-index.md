---
title: ADO 动态属性索引
TOCTitle: ADO Dynamic Property Index
ms:assetid: 437beced-b97a-894d-b08f-4a322629a5a6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249202(v=office.15)
ms:contentKeyID: 48544502
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6f385f3637f9a64ff94d571345d88fbaa088d126
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25876062"
---
# <a name="ado-dynamic-property-index"></a>ADO 动态属性索引


**适用于**： Access 2013、 Office 2013

数据提供程序、服务提供程序及服务组件可以将动态属性添加到未打开的 **Connection** 和 [Recordset](connection-object-ado.md) 对象的 [Properties](recordset-object-ado.md) 集合中。打开这些对象时，给定的提供程序还可以插入其他属性。其中的一些属性在 [ADO 动态属性](ado-dynamic-properties.md) 一节中列出。更多其他属性在 [附录 A：提供程序](appendix-a-providers.md)一节的特定提供程序下列出。

下表是每个标准 OLE DB 提供程序动态属性的 ADO 和 OLE DB 名称的交叉索引。除了此处列出的属性外，提供程序还可能添加更多的属性。有关提供程序特定动态属性的具体信息，请参阅提供程序文档。

《OLE DB 程序员参考》使用术语"说明"来引用 ADO 属性名。您可以在该书中找到有关这些标准属性的详细信息。请在"索引"中搜索 OLE DB 属性名或参阅以下主题：

  - 附录 C：OLE DB 属性

  - Cursor Service 支持的属性

  - 持久性提供程序支持的属性

  - 远程提供程序支持的 OLE DB 属性

## <a name="remarks"></a>备注

请注意交叉索引中使用的数字：

(1) 此属性是一个 Boolean 标志，指示是否应使用指定接口。将列出等效的 OLE DB 属性名（如果存在）。

（2） 的"Bookmarkable"ADO 属性是内部生成的向后兼容性和映射到的 OLE DB 属性，需要的 DBPROP\_IROWSETLOCATE。 此属性是与 ADO 属性 IRowsetLocate 对应的同一属性。

(3) ADO 属性名"Hidden Columns"的命名不同于 OLE DB 属性名说明"Hidden Columns Count"。

(4) 对于分级记录集，"Maximum Rows"ADO 属性应用于所有的子记录集。根据行的返回顺序，结果集中的每个父记录集和孤立子记录集可能都具有子记录集，有一些具有子记录集，或者都没有子记录集。因此，重构分级记录集时，每个子记录集的标识符都应该是唯一的。一般情况下，[Microsoft Data Shaping Service for OLE DB (MSDATASHAPE)](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) 提供程序不考虑可从父记录集继承的属性与不能继承的属性间的区别。

(5) 不适用。

**Connection 动态属性**

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>ADO 属性名</p></th>
<th><p>OLE DB 属性名</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Active Sessions</p></td>
<td><p>DBPROP_ACTIVESESSIONS</p></td>
</tr>
<tr class="even">
<td><p>Asynchable Abort</p></td>
<td><p>DBPROP_ASYNCTXNABORT</p></td>
</tr>
<tr class="odd">
<td><p>Asynchable Commit</p></td>
<td><p>DBPROP_ASYNCTNXCOMMIT</p></td>
</tr>
<tr class="even">
<td><p>Autocommit Isolation Levels</p></td>
<td><p>DBPROP_SESS_AUTOCOMMITISOLEVELS</p></td>
</tr>
<tr class="odd">
<td><p>Catalog Location</p></td>
<td><p>DBPROP_CATALOGLOCATION</p></td>
</tr>
<tr class="even">
<td><p>Catalog Term</p></td>
<td><p>DBPROP_CATALOGTERM</p></td>
</tr>
<tr class="odd">
<td><p>Column Definition</p></td>
<td><p>DBPROP_COLUMNDEFINITION</p></td>
</tr>
<tr class="even">
<td><p>Connect Timeout</p></td>
<td><p>DBPROP_INIT_TIMEOUT</p></td>
</tr>
<tr class="odd">
<td><p>Current Catalog</p></td>
<td><p>DBPROP_CURRENTCATALOG</p></td>
</tr>
<tr class="even">
<td><p>Data Source</p></td>
<td><p>DBPROP_INIT_DATASOURCE</p></td>
</tr>
<tr class="odd">
<td><p>Data Source Name</p></td>
<td><p>DBPROP_DATASOURCENAME</p></td>
</tr>
<tr class="even">
<td><p>Data Source Object Threading Model</p></td>
<td><p>DBPROP_DSOTHREADMODEL</p></td>
</tr>
<tr class="odd">
<td><p>DBMS Name</p></td>
<td><p>DBPROP_DBMSNAME</p></td>
</tr>
<tr class="even">
<td><p>DBMS Version</p></td>
<td><p>DBPROP_DBMSVER</p></td>
</tr>
<tr class="odd">
<td><p>Extended Properties</p></td>
<td><p>DBPROP_INIT_PROVIDERSTRING</p></td>
</tr>
<tr class="even">
<td><p>GROUP BY Support</p></td>
<td><p>DBPROP_GROUPBY</p></td>
</tr>
<tr class="odd">
<td><p>Heterogeneous Table Support</p></td>
<td><p>DBPROP_HETEROGENEOUSTABLES</p></td>
</tr>
<tr class="even">
<td><p>Identifier Case Sensitivity</p></td>
<td><p>DBPROP_IDENTIFIERCASE</p></td>
</tr>
<tr class="odd">
<td><p>Initial Catalog</p></td>
<td><p>DBPROP_INIT_CATALOG</p></td>
</tr>
<tr class="even">
<td><p>Isolation Levels</p></td>
<td><p>DBPROP_SUPPORTEDTXNISOLEVELS</p></td>
</tr>
<tr class="odd">
<td><p>Isolation Retention</p></td>
<td><p>DBPROP_SUPPORTEDTXNISORETAIN</p></td>
</tr>
<tr class="even">
<td><p>Locale Identifier</p></td>
<td><p>DBPROP_INIT_LCID</p></td>
</tr>
<tr class="odd">
<td><p>Location</p></td>
<td><p>DBPROP_INIT_LOCATION</p></td>
</tr>
<tr class="even">
<td><p>Maximum Index Size</p></td>
<td><p>DBPROP_MAXINDEXSIZE</p></td>
</tr>
<tr class="odd">
<td><p>Maximum Row Size</p></td>
<td><p>DBPROP_MAXROWSIZE</p></td>
</tr>
<tr class="even">
<td><p>Maximum Row Size Includes BLOB</p></td>
<td><p>DBPROP_MAXROWSIZEINCLUDESBLOB</p></td>
</tr>
<tr class="odd">
<td><p>Maximum Tables in SELECT</p></td>
<td><p>DBPROP_MAXTABLESINSELECT</p></td>
</tr>
<tr class="even">
<td><p>Mode</p></td>
<td><p>DBPROP_INIT_MODE</p></td>
</tr>
<tr class="odd">
<td><p>Multiple Parameter Sets</p></td>
<td><p>DBPROP_MULTIPLEPARAMSETS</p></td>
</tr>
<tr class="even">
<td><p>Multiple Results</p></td>
<td><p>DBPROP_MULTIPLERESULTS</p></td>
</tr>
<tr class="odd">
<td><p>Multiple Storage Objects</p></td>
<td><p>DBPROP_MULTIPLESTORAGEOBJECTS</p></td>
</tr>
<tr class="even">
<td><p>Multi-Table Update</p></td>
<td><p>DBPROP_MULTITABLEUPDATE</p></td>
</tr>
<tr class="odd">
<td><p>NULL Collation Order</p></td>
<td><p>DBPROP_NULLCOLLATION</p></td>
</tr>
<tr class="even">
<td><p>NULL Concatenation Behavior</p></td>
<td><p>DBPROP_CONCATNULLBEHAVIOR</p></td>
</tr>
<tr class="odd">
<td><p>OLE DB Services</p></td>
<td><p>DBPROP_INIT_OLEDBSERVICES</p></td>
</tr>
<tr class="even">
<td><p>OLE DB Version</p></td>
<td><p>DBPROP_PROVIDEROLEDBVER</p></td>
</tr>
<tr class="odd">
<td><p>OLE Object Support</p></td>
<td><p>DBPROP_OLEOBJECTS</p></td>
</tr>
<tr class="even">
<td><p>Open Rowset Support</p></td>
<td><p>DBPROP_OPENROWSETSUPPORT</p></td>
</tr>
<tr class="odd">
<td><p>ORDER BY Columns in Select List</p></td>
<td><p>DBPROP_ORDERBYCOLUMNSINSELECT</p></td>
</tr>
<tr class="even">
<td><p>Output Parameter Availability</p></td>
<td><p>DBPROP_OUTPUTPARAMETERAVAILABILITY</p></td>
</tr>
<tr class="odd">
<td><p>Pass By Ref Accessors</p></td>
<td><p>DBPROP_BYREFACCESSORS</p></td>
</tr>
<tr class="even">
<td><p>Password</p></td>
<td><p>DBPROP_AUTH_PASSWORD</p></td>
</tr>
<tr class="odd">
<td><p>Persist Security Info</p></td>
<td><p>DBPROP_AUTH_PERSIST_SENSITIVE_AUTHINFO</p></td>
</tr>
<tr class="even">
<td><p>Persistent ID Type</p></td>
<td><p>DBPROP_PERSISTENTIDTYPE</p></td>
</tr>
<tr class="odd">
<td><p>Prepare Abort Behavior</p></td>
<td><p>DBPROP_PREPAREABORTBEHAVIOR</p></td>
</tr>
<tr class="even">
<td><p>Prepare Commit Behavior</p></td>
<td><p>DBPROP_PREPARECOMMITBEHAVIOR</p></td>
</tr>
<tr class="odd">
<td><p>Procedure Term</p></td>
<td><p>DBPROP_PROCEDURETERM</p></td>
</tr>
<tr class="even">
<td><p>Prompt</p></td>
<td><p>DBPROP_INIT_PROMPT</p></td>
</tr>
<tr class="odd">
<td><p>Provider Friendly Name</p></td>
<td><p>DBPROP_PROVIDERFRIENDLYNAME</p></td>
</tr>
<tr class="even">
<td><p>Provider Name</p></td>
<td><p>DBPROP_PROVIDERFILENAME</p></td>
</tr>
<tr class="odd">
<td><p>Provider Version</p></td>
<td><p>DBPROP_PROVIDERVER</p></td>
</tr>
<tr class="even">
<td><p>Read-Only Data Source</p></td>
<td><p>DBPROP_DATASOURCEREADONLY</p></td>
</tr>
<tr class="odd">
<td><p>Rowset Conversions on Command</p></td>
<td><p>DBPROP_ROWSETCONVERSIONSONCOMMAND</p></td>
</tr>
<tr class="even">
<td><p>Schema Term</p></td>
<td><p>DBPROP_SCHEMATERM</p></td>
</tr>
<tr class="odd">
<td><p>Schema Usage</p></td>
<td><p>DBPROP_SCHEMAUSAGE</p></td>
</tr>
<tr class="even">
<td><p>SQL Support</p></td>
<td><p>DBPROP_SQLSUPPORT</p></td>
</tr>
<tr class="odd">
<td><p>Structured Storage</p></td>
<td><p>DBPROP_STRUCTUREDSTORAGE</p></td>
</tr>
<tr class="even">
<td><p>Subquery Support</p></td>
<td><p>DBPROP_SUBQUERIES</p></td>
</tr>
<tr class="odd">
<td><p>Table Term</p></td>
<td><p>DBPROP_TABLETERM</p></td>
</tr>
<tr class="even">
<td><p>Transaction DDL</p></td>
<td><p>DBPROP_SUPPORTEDTXNDDL</p></td>
</tr>
<tr class="odd">
<td><p>User ID</p></td>
<td><p>DBPROP_AUTH_USERID</p></td>
</tr>
<tr class="even">
<td><p>User Name</p></td>
<td><p>DBPROP_USERNAME</p></td>
</tr>
<tr class="odd">
<td><p>Window Handle</p></td>
<td><p>DBPROP_INIT_HWND</p></td>
</tr>
</tbody>
</table>


**Recordset 动态属性**

请注意，关闭 **Recordset** 时， **Recordset** 对象的 **动态属性** 将超出范围（不可用）。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>ADO 属性名</p></th>
<th><p>OLE DB 属性名</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IAccessor</p></td>
<td><p>DBPROP_IACCESSOR (1)</p></td>
</tr>
<tr class="even">
<td><p>IChapteredRowset</p></td>
<td><p>(1)</p></td>
</tr>
<tr class="odd">
<td><p>IColumnsInfo</p></td>
<td><p>DBPROP_ICOLUMNSINFO (1)</p></td>
</tr>
<tr class="even">
<td><p>IColumnsRowset</p></td>
<td><p>DBPROP_ICOLUMNSROWSET (1)</p></td>
</tr>
<tr class="odd">
<td><p>IConnectionPointContainer</p></td>
<td><p>DBPROP_ICONNECTIONPOINTCONTAINER (1)</p></td>
</tr>
<tr class="even">
<td><p>IConvertType</p></td>
<td><p>(1)</p></td>
</tr>
<tr class="odd">
<td><p>ILockBytes</p></td>
<td><p>DBPROP_ILOCKBYTES (1)</p></td>
</tr>
<tr class="even">
<td><p>IRowset</p></td>
<td><p>DBPROP_IROWSET (1)</p></td>
</tr>
<tr class="odd">
<td><p>IDBAsynchStatus</p></td>
<td><p>DBPROP_IDBASYNCHSTATUS (1)</p></td>
</tr>
<tr class="even">
<td><p>IParentRowset</p></td>
<td><p>(1)</p></td>
</tr>
<tr class="odd">
<td><p>IRowsetChange</p></td>
<td><p>DBPROP_IROWSETCHANGE (1)</p></td>
</tr>
<tr class="even">
<td><p>IRowsetExactScroll</p></td>
<td><p>(1)</p></td>
</tr>
<tr class="odd">
<td><p>IRowsetFind</p></td>
<td><p>DBPROP_IROWSETFIND (1)</p></td>
</tr>
<tr class="even">
<td><p>IRowsetIdentity</p></td>
<td><p>DBPROP_IROWSETIDENTITY (1)</p></td>
</tr>
<tr class="odd">
<td><p>IRowsetInfo</p></td>
<td><p>DBPROP_IROWSETINFO (1)</p></td>
</tr>
<tr class="even">
<td><p>IRowsetLocate</p></td>
<td><p>DBPROP_IROWSETLOCATE (1)</p></td>
</tr>
<tr class="odd">
<td><p>IRowsetRefresh</p></td>
<td><p>DBPROP_IROWSETREFRESH (1)</p></td>
</tr>
<tr class="even">
<td><p>IRowsetResynch</p></td>
<td><p>(1)</p></td>
</tr>
<tr class="odd">
<td><p>IRowsetScroll</p></td>
<td><p>DBPROP_IROWSETSCROLL (1)</p></td>
</tr>
<tr class="even">
<td><p>IRowsetUpdate</p></td>
<td><p>DBPROP_IROWSETUPDATE (1)</p></td>
</tr>
<tr class="odd">
<td><p>IRowsetView</p></td>
<td><p>DBPROP_IROWSETVIEW (1)</p></td>
</tr>
<tr class="even">
<td><p>IRowsetIndex</p></td>
<td><p>DBPROP_IROWSETINDEX (1)</p></td>
</tr>
<tr class="odd">
<td><p>ISequentialStream</p></td>
<td><p>DBPROP_ISEQUENTIALSTREAM (1)</p></td>
</tr>
<tr class="even">
<td><p>IStorage</p></td>
<td><p>DBPROP_ISTORAGE (1)</p></td>
</tr>
<tr class="odd">
<td><p>IStream</p></td>
<td><p>DBPROP_ISTREAM (1)</p></td>
</tr>
<tr class="even">
<td><p>ISupportErrorInfo</p></td>
<td><p>DBPROP_ISUPPORTERRORINFO (1)</p></td>
</tr>
<tr class="odd">
<td><p>Access Order</p></td>
<td><p>DBPROP_ACCESSORDER</p></td>
</tr>
<tr class="even">
<td><p>Append-Only Rowset</p></td>
<td><p>DBPROP_APPENDONLY</p></td>
</tr>
<tr class="odd">
<td><p>Asynchronous Rowset Processing</p></td>
<td><p>DBPROP_ROWSET_ASYNCH</p></td>
</tr>
<tr class="even">
<td><p>Auto Recalc</p></td>
<td><p>DBPROP_ADC_AUTORECALC</p></td>
</tr>
<tr class="odd">
<td><p>Background Fetch Size</p></td>
<td><p>DBPROP_ASYNCHFETCHSIZE</p></td>
</tr>
<tr class="even">
<td><p>Background Thread Priority</p></td>
<td><p>DBPROP_ASYNCHTHREADPRIORITY</p></td>
</tr>
<tr class="odd">
<td><p>Batch Size</p></td>
<td><p>DBPROP_ADC_BATCHSIZE</p></td>
</tr>
<tr class="even">
<td><p>Blocking Storage Objects</p></td>
<td><p>DBPROP_BLOCKINGSTORAGEOBJECTS</p></td>
</tr>
<tr class="odd">
<td><p>Bookmark Type</p></td>
<td><p>DBPROP_BOOKMARKTYPE</p></td>
</tr>
<tr class="even">
<td><p>Bookmarkable</p></td>
<td><p>DBPROP_IROWSETLOCATE (2)</p></td>
</tr>
<tr class="odd">
<td><p>Bookmarks Ordered</p></td>
<td><p>DBPROP_ORDEREDBOOKMARKS</p></td>
</tr>
<tr class="even">
<td><p>Cache Child Rows</p></td>
<td><p>DBPROP_ADC_CACHECHILDROWS</p></td>
</tr>
<tr class="odd">
<td><p>Cache Deferred Columns</p></td>
<td><p>DBPROP_CACHEDEFERRED</p></td>
</tr>
<tr class="even">
<td><p>Change Inserted Rows</p></td>
<td><p>DBPROP_CHANGEINSERTEDROWS</p></td>
</tr>
<tr class="odd">
<td><p>Column Privileges</p></td>
<td><p>DBPROP_COLUMNRESTRICT</p></td>
</tr>
<tr class="even">
<td><p>Column Set Notification</p></td>
<td><p>DBPROP_NOTIFYCOLUMNSET</p></td>
</tr>
<tr class="odd">
<td><p>Column Writable</p></td>
<td><p>DBPROP_MAYWRITECOLUMN</p></td>
</tr>
<tr class="even">
<td><p>Command Time Out</p></td>
<td><p>DBPROP_COMMANDTIMEOUT</p></td>
</tr>
<tr class="odd">
<td><p>Cursor Engine Version</p></td>
<td><p>DBPROP_ADC_CEVER</p></td>
</tr>
<tr class="even">
<td><p>Defer Column</p></td>
<td><p>DBPROP_DEFERRED</p></td>
</tr>
<tr class="odd">
<td><p>Delay Storage Object Updates</p></td>
<td><p>DBPROP_DELAYSTORAGEOBJECTS</p></td>
</tr>
<tr class="even">
<td><p>Fetch Backwards</p></td>
<td><p>DBPROP_CANFETCHBACKWARDS</p></td>
</tr>
<tr class="odd">
<td><p>Filter Operations</p></td>
<td><p>DBPROP_FILTERCOMPAREOPS</p></td>
</tr>
<tr class="even">
<td><p>Find Operations</p></td>
<td><p>DBPROP_FINDCOMPAREOPS</p></td>
</tr>
<tr class="odd">
<td><p>Hidden Columns (Count)</p></td>
<td><p>DBPROP_HIDDENCOLUMNS (3)</p></td>
</tr>
<tr class="even">
<td><p>Hold Rows</p></td>
<td><p>DBPROP_CANHOLDROWS</p></td>
</tr>
<tr class="odd">
<td><p>Immobile Rows</p></td>
<td><p>DBPROP_IMMOBILEROWS</p></td>
</tr>
<tr class="even">
<td><p>Initial Fetch Size</p></td>
<td><p>DBPROP_ASYNCHPREFETCHSIZE</p></td>
</tr>
<tr class="odd">
<td><p>Literal Bookmarks</p></td>
<td><p>DBPROP_LITERALBOOKMARKS</p></td>
</tr>
<tr class="even">
<td><p>Literal Row Identity</p></td>
<td><p>DBPROP_LITERALIDENTITY</p></td>
</tr>
<tr class="odd">
<td><p>Maintain Change Status</p></td>
<td><p>DBPROP_ADC_MAINTAINCHANGESTATUS</p></td>
</tr>
<tr class="even">
<td><p>Maximum Open Rows</p></td>
<td><p>DBPROP_MAXOPENROWS</p></td>
</tr>
<tr class="odd">
<td><p>Maximum Pending Rows</p></td>
<td><p>DBPROP_MAXPENDINGROWS</p></td>
</tr>
<tr class="even">
<td><p>Maximum Rows</p></td>
<td><p>DBPROP_MAXROWS (4)</p></td>
</tr>
<tr class="odd">
<td><p>Memory Usage</p></td>
<td><p>DBPROP_MEMORYUSAGE</p></td>
</tr>
<tr class="even">
<td><p>Notification Granularity</p></td>
<td><p>DBPROP_NOTIFICATIONGRANULARITY</p></td>
</tr>
<tr class="odd">
<td><p>Notification Phases</p></td>
<td><p>DBPROP_NOTIFICATIONPHASES</p></td>
</tr>
<tr class="even">
<td><p>Objects Transacted</p></td>
<td><p>DBPROP_TRANSACTEDOBJECT</p></td>
</tr>
<tr class="odd">
<td><p>Others' Changes Visible</p></td>
<td><p>DBPROP_OTHERUPDATEDELETE</p></td>
</tr>
<tr class="even">
<td><p>Others' Inserts Visible</p></td>
<td><p>DBPROP_OTHERINSERT</p></td>
</tr>
<tr class="odd">
<td><p>Own Changes Visible</p></td>
<td><p>DBPROP_OWNUPDATEDELETE</p></td>
</tr>
<tr class="even">
<td><p>Own Inserts Visible</p></td>
<td><p>DBPROP_OWNINSERT</p></td>
</tr>
<tr class="odd">
<td><p>Preserve on Abort</p></td>
<td><p>DBPROP_ABORTPRESERVE</p></td>
</tr>
<tr class="even">
<td><p>Preserve on Commit</p></td>
<td><p>DBPROP_COMMITPRESERVE</p></td>
</tr>
<tr class="odd">
<td><p>Private1</p></td>
<td><p>(5)</p></td>
</tr>
<tr class="even">
<td><p>Quick Restart</p></td>
<td><p>DBPROP_QUICKRESTART</p></td>
</tr>
<tr class="odd">
<td><p>Reentrant Events</p></td>
<td><p>DBPROP_REENTRANTEVENTS</p></td>
</tr>
<tr class="even">
<td><p>Remove Deleted Rows</p></td>
<td><p>DBPROP_REMOVEDELETED</p></td>
</tr>
<tr class="odd">
<td><p>Report Multiple Changes</p></td>
<td><p>DBPROP_REPORTMULTIPLECHANGES</p></td>
</tr>
<tr class="even">
<td><p>Reshape Name</p></td>
<td><p>DBPROP_ADC_RESHAPENAME</p></td>
</tr>
<tr class="odd">
<td><p>Resync Command</p></td>
<td><p>DBPROP_ADC_CUSTOMRESYNCH</p></td>
</tr>
<tr class="even">
<td><p>Return Pending Inserts</p></td>
<td><p>DBPROP_RETURNPENDINGINSERTS</p></td>
</tr>
<tr class="odd">
<td><p>Row Delete Notification</p></td>
<td><p>DBPROP_NOTIFYROWDELETE</p></td>
</tr>
<tr class="even">
<td><p>Row First Change Notification</p></td>
<td><p>DBPROP_NOTIFYROWFIRSTCHANGE</p></td>
</tr>
<tr class="odd">
<td><p>Row Insert Notification</p></td>
<td><p>DBPROP_NOTIFYROWINSERT</p></td>
</tr>
<tr class="even">
<td><p>Row Privileges</p></td>
<td><p>DBPROP_ROWRESTRICT</p></td>
</tr>
<tr class="odd">
<td><p>Row Resynchronization Notification</p></td>
<td><p>DBPROP_NOTIFYROWRESYNCH</p></td>
</tr>
<tr class="even">
<td><p>Row Threading Model</p></td>
<td><p>DBPROP_ROWTHREADMODEL</p></td>
</tr>
<tr class="odd">
<td><p>Row Undo Change Notification</p></td>
<td><p>DBPROP_NOTIFYROWUNDOCHANGE</p></td>
</tr>
<tr class="even">
<td><p>Row Undo Delete Notification</p></td>
<td><p>DBPROP_NOTIFYROWUNDODELETE</p></td>
</tr>
<tr class="odd">
<td><p>Row Undo Insert Notification</p></td>
<td><p>DBPROP_NOTIFYROWUNDOINSERT</p></td>
</tr>
<tr class="even">
<td><p>Row Update Notification</p></td>
<td><p>DBPROP_NOTIFYROWUPDATE</p></td>
</tr>
<tr class="odd">
<td><p>Rowset Fetch Position Change Notification</p></td>
<td><p>DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE</p></td>
</tr>
<tr class="even">
<td><p>Rowset Release Notification</p></td>
<td><p>DBPROP_NOTIFYROWSETRELEASE</p></td>
</tr>
<tr class="odd">
<td><p>Scroll Backwards</p></td>
<td><p>DBPROP_CANSCROLLBACKWARDS</p></td>
</tr>
<tr class="even">
<td><p>Server Cursor</p></td>
<td><p>DBPROP_SERVERCURSOR</p></td>
</tr>
<tr class="odd">
<td><p>Skip Deleted Bookmarks</p></td>
<td><p>DBPROP_BOOKMARKSKIPPED</p></td>
</tr>
<tr class="even">
<td><p>Strong Row Identity</p></td>
<td><p>DBPROP_STRONGIDENTITY</p></td>
</tr>
<tr class="odd">
<td><p>Unique Catalog</p></td>
<td><p>DBPROP_ADC_UNIQUECATALOG</p></td>
</tr>
<tr class="even">
<td><p>Unique Rows</p></td>
<td><p>DBPROP_UNIQUEROWS</p></td>
</tr>
<tr class="odd">
<td><p>Unique Schema</p></td>
<td><p>DBPROP_ADC_UNIQUESCHEMA</p></td>
</tr>
<tr class="even">
<td><p>Unique Table</p></td>
<td><p>DBPROP_ADC_UNIQUETABLE</p></td>
</tr>
<tr class="odd">
<td><p>Updatability</p></td>
<td><p>DBPROP_UPDATABILITY</p></td>
</tr>
<tr class="even">
<td><p>Update Criteria</p></td>
<td><p>DBPROP_ADC_UPDATECRITERIA</p></td>
</tr>
<tr class="odd">
<td><p>Update Resync</p></td>
<td><p>DBPROP_ADC_UPDATERESYNC</p></td>
</tr>
<tr class="even">
<td><p>Use Bookmarks</p></td>
<td><p>DBPROP_BOOKMARKS</p></td>
</tr>
</tbody>
</table>

