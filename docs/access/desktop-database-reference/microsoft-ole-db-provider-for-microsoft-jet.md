---
title: Microsoft OLE DB Provider for Microsoft Jet
TOCTitle: Microsoft OLE DB Provider for Microsoft Jet
ms:assetid: 4a210d72-8c90-aa7c-4621-1a555a30a2d2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249228(v=office.15)
ms:contentKeyID: 48544660
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 39cb1288ef5e6be4f50d4ef976725122635db1dc
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25884084"
---
# <a name="microsoft-ole-db-provider-for-microsoft-jet"></a>Microsoft OLE DB Provider for Microsoft Jet

**适用于**： Access 2013、 Office 2013

OLE DB Provider for Microsoft Jet 允许 ADO 访问 Microsoft Jet 数据库。

## <a name="connection-string-parameters"></a>连接字符串参数

若要连接到此提供程序，请将 *ConnectionString* 属性的 [Provider](connectionstring-property-ado.md) 参数设置为：

```vb 
 
Microsoft.Jet.OLEDB.4.0 
```

读取 [Provider](provider-property-ado.md) 属性时，也会返回此字符串。

## <a name="typical-connection-string"></a>典型的连接字符串

此提供程序典型的连接字符串为：

```vb 
 
"Provider=Microsoft.Jet.OLEDB.4.0;Data Source=databaseName;User ID=userName;Password=userPassword;" 
```

该字符串由以下关键字组成：

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>关键字</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Provider</strong></p></td>
<td><p>指定 OLE DB Provider for Microsoft Jet。</p></td>
</tr>
<tr class="even">
<td><p><strong>Data Source</strong></p></td>
<td><p>指定数据库路径和文件名称 (例如，c:\Northwind.mdb)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>User ID</strong></p></td>
<td><p>指定用户名。 如果未指定此关键字，字符串&quot;管理&quot;，默认情况下使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>Password</strong></p></td>
<td><p>指定用户密码。 如果未指定此关键字，则空字符串 (&quot;&quot;)，默认情况下使用。</p></td>
</tr>
</tbody>
</table>


## <a name="provider-specific-connection-parameters"></a>提供程序特定的连接参数

OLE DB Provider for Microsoft Jet 除了支持 ADO 定义的那些属性以外，还支持几个提供程序特定的动态属性。与所有其他的 **Connection** 参数一样，可以通过 **Connection** 对象的 **Properties** 集合或将其作为连接字符串的一部分来设置这些动态属性。

下表列出了这些属性以及对应的 OLE DB 属性名（括在括号中）。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Jet OLEDB:Compact 回收的空间量<br />
(DBPROP_JETOLEDB_COMPACTFREESPACESIZE)</p></td>
<td><p>指示空间量的估计值（以字节为单位），可通过压缩数据库来回收空间。仅在建立了数据库连接后，此值才有效。</p></td>
</tr>
<tr class="even">
<td><p>Jet OLEDB:Connection 控件<br />
(DBPROP_JETOLEDB_CONNECTIONCONTROL)</p></td>
<td><p>指示用户是否可以连接到数据库。</p></td>
</tr>
<tr class="odd">
<td><p>Jet OLEDB： 创建系统数据库<br />
(DBPROP_JETOLEDB_CREATESYSTEMDATABASE)</p></td>
<td><p>指示在创建新的数据源时是否应该创建系统数据库。</p></td>
</tr>
<tr class="even">
<td><p>Jet OLEDB:Database 锁定模式<br />
(DBPROP_JETOLEDB_DATABASELOCKMODE)</p></td>
<td><p>指示此数据库的锁定模式。打开该数据库的第一个用户可以确定数据库打开时使用的模式。</p></td>
</tr>
<tr class="odd">
<td><p>Jet OLEDB:Database Password<br />
(DBPROP_JETOLEDB_DATABASEPASSWORD)</p></td>
<td><p>指示数据库密码。</p></td>
</tr>
<tr class="even">
<td><p>Jet OLEDB:Don't Copy Locale on Compact<br />
(DBPROP_JETOLEDB_COMPACT_DONTCOPYLOCALE)</p></td>
<td><p>指示压缩数据库时 Jet 是否应该复制区域设置信息。</p></td>
</tr>
<tr class="odd">
<td><p>Jet OLEDB:Encrypt Database<br />
(DBPROP_JETOLEDB_ENCRYPTDATABASE)</p></td>
<td><p>指示是否应对压缩的数据库进行加密。如果没有设置此属性，则在对原始数据库进行加密时也会对压缩的数据库加密。</p></td>
</tr>
<tr class="even">
<td><p>Jet OLEDB:Engine Type<br />
(DBPROP_JETOLEDB_ENGINE)</p></td>
<td><p>指示用于访问当前数据存储区的存储引擎。</p></td>
</tr>
<tr class="odd">
<td><p>Jet OLEDB:Exclusive Async Delay<br />
(DBPROP_JETOLEDB_EXCLUSIVEASYNCDELAY)</p></td>
<td><p>指示以独占方式打开数据库时，Jet 可延迟磁盘异步写入的最长时间（以毫秒为单位）。
 除非将 <strong>Jet OLEDB:Flush Transaction Timeout</strong> 设置为 0，否则将忽略此属性。</p></td>
</tr>
<tr class="even">
<td><p>Jet OLEDB:Flush Transaction Timeout<br />
(DBPROP_JETOLEDB_FLUSHTRANSACTIONTIMEOUT)</p></td>
<td><p>指示将存储在缓存中要异步写入的数据实际写入磁盘之前等待的时间。此设置将覆盖 <strong>Jet OLEDB:Shared Async Delay</strong> 和 <strong>Jet OLEDB:Exclusive Async Delay</strong> 的值。</p></td>
</tr>
<tr class="odd">
<td><p>Jet OLEDB： 全局批量事务<br />
(DBPROP_JETOLEDB_GLOBALBULKNOTRANSACTIONS)</p></td>
<td><p>指示是否要处理 SQL 批量事务处理。</p></td>
</tr>
<tr class="even">
<td><p>Jet OLEDB： 全局部分批量操作<br />
(DBPROP_JETOLEDB_GLOBALBULKPARTIAL)</p></td>
<td><p>指示用于打开数据库的密码。</p></td>
</tr>
<tr class="odd">
<td><p>Jet OLEDB:Implicit Commit Sync<br />
(DBPROP_JETOLEDB_IMPLICITCOMMITSYNC)</p></td>
<td><p>指示采用同步模式还是异步模式写入在内部隐式事务处理中所做的更改。</p></td>
</tr>
<tr class="even">
<td><p>Jet OLEDB:Lock Delay<br />
(DBPROP_JETOLEDB_LOCKDELAY)</p></td>
<td><p>指示在上一次尝试失败后与再次尝试获取锁定之前等待的毫秒数。</p></td>
</tr>
<tr class="odd">
<td><p>Jet OLEDB:Lock Retry<br />
(DBPROP_JETOLEDB_LOCKRETRY)</p></td>
<td><p>指示重复尝试访问已锁定页面的次数。</p></td>
</tr>
<tr class="even">
<td><p>Jet OLEDB:Max Buffer Size<br />
(DBPROP_JETOLEDB_MAXBUFFERSIZE)</p></td>
<td><p>指示 Jet 在开始刷新对磁盘所做的更改之前可以使用的最大内存量 (KB)。</p></td>
</tr>
<tr class="odd">
<td><p>Jet OLEDB:Max Locks Per File<br />
(DBPROP_JETOLEDB_MAXLOCKSPERFILE)</p></td>
<td><p>指示 Jet 可在数据库上放置的最大锁定数目。默认值为 9500。</p></td>
</tr>
<tr class="even">
<td><p>Jet OLEDB： 新数据库密码<br />
(DBPROP_JETOLEDB_NEWDATABASEPASSWORD)</p></td>
<td><p>指示要为此数据库设置的新密码。旧密码存储在 <strong>Jet OLEDB:Database Password</strong> 中。</p></td>
</tr>
<tr class="odd">
<td><p>Jet OLEDB:ODBC Command Time Out<br />
(DBPROP_JETOLEDB_ODBCCOMMANDTIMEOUT)</p></td>
<td><p>指示 Jet 中的远程 ODBC 查询超时之前的毫秒数。</p></td>
</tr>
<tr class="even">
<td><p>为表锁定 jet OLEDB:Page 锁定<br />
(DBPROP_JETOLEDB_PAGELOCKSTOTABLELOCK)</p></td>
<td><p>指示 Jet 尝试将锁定提升到表锁定之前，在事务处理中需要锁定的页数。如果此值为 0，则永远不会提升锁定。</p></td>
</tr>
<tr class="odd">
<td><p>Jet OLEDB:Page Timeout<br />
(DBPROP_JETOLEDB_PAGETIMEOUT)</p></td>
<td><p>指示 Jet 在查看其数据文件的缓存是否过期之前等待的毫秒数。</p></td>
</tr>
<tr class="even">
<td><p>Jet OLEDB:Recycle Long-Valued Pages<br />
(DBPROP_JETOLEDB_RECYCLELONGVALUEPAGES)</p></td>
<td><p>指示释放 BLOB 页后 Jet 是否应该主动尝试回收这些 BLOB 页。</p></td>
</tr>
<tr class="odd">
<td><p>Jet OLEDB:Registry Path<br />
(DBPROP_JETOLEDB_REGPATH)</p></td>
<td><p>指示包含 Jet 数据库引擎的值的 Windows 注册表项。</p></td>
</tr>
<tr class="even">
<td><p>Jet OLEDB:Reset ISAM Stats<br />
(DBPROP_JETOLEDB_RESETISAMSTATS)</p></td>
<td><p>指示返回性能信息后，架构 <strong>Recordset</strong> DBSCHEMA_JETOLEDB_ISAMSTATS 是否应该重新设置其性能计数器。</p></td>
</tr>
<tr class="odd">
<td><p>Jet OLEDB:Shared Async Delay<br />
(DBPROP_JETOLEDB_SHAREDASYNCDELAY)</p></td>
<td><p>指示以多用户模式打开数据库时，Jet 可以延迟异步磁盘写入的最长时间（以毫秒为单位）。</p></td>
</tr>
<tr class="even">
<td><p>Jet OLEDB:System Database<br />
(DBPROP_JETOLEDB_SYSDBPATH)</p></td>
<td><p>指示工作组信息文件（系统数据库）的路径和文件名。</p></td>
</tr>
<tr class="odd">
<td><p>Jet OLEDB:Transaction 提交模式<br />
(DBPROP_JETOLEDB_TXNCOMMITMODE)</p></td>
<td><p>指示提交事务处理时 Jet 采用同步方式还是异步方式将数据写入磁盘。</p></td>
</tr>
<tr class="even">
<td><p>Jet OLEDB:User Commit Sync<br />
(DBPROP_JETOLEDB_USERCOMMITSYNC)</p></td>
<td><p>指示采用同步模式还是异步模式写入在事务处理中所做的更改。</p></td>
</tr>
</tbody>
</table>


## <a name="provider-specific-recordset-and-command-properties"></a>提供程序特定的 Recordset 和 Command 属性

Jet 提供程序还支持多个提供程序特定的 **Recordset** 和 **Command** 属性。这些属性可通过 **Recordset** 或 **Command** 对象的 **Properties** 集合进行访问和设置。该表列出了 ADO 属性名及其对应的 OLE DB 属性名（括在括号中）。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>属性名称</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Jet OLEDB:Bulk 事务<br />
(DBPROP_JETOLEDB_BULKNOTRANSACTIONS)</p></td>
<td><p>指示是否处理 SQL 批量操作。处理时，由于资源延迟，大量的批量操作可能会失败。</p></td>
</tr>
<tr class="even">
<td><p>Jet OLEDB:Enable Fat 游标<br />
(DBPROP_JETOLEDB_ENABLEFATCURSOR)</p></td>
<td><p>指示为远程行源填充记录集时，Jet 是否应该缓存多个行。</p></td>
</tr>
<tr class="odd">
<td><p>Jet OLEDB:Fat 光标缓存大小<br />
(DBPROP_JETOLEDB_FATCURSORMAXROWS)</p></td>
<td><p>指示使用远程数据存储区行缓存时要缓存的行数。除非 <strong>Jet OLEDB:Enable Fat Cursors</strong> 为 True，否则将忽略此值。</p></td>
</tr>
<tr class="even">
<td><p>Jet OLEDB： 不一致<br />
(DBPROP_JETOLEDB_INCONSISTENT)</p></td>
<td><p>指示查询结果是否允许不一致的更新。</p></td>
</tr>
<tr class="odd">
<td><p>Jet OLEDB： 锁定粒度<br />
(DBPROP_JETOLEDB_LOCKGRANULARITY)</p></td>
<td><p>指示是否使用行级锁定打开表。</p></td>
</tr>
<tr class="even">
<td><p>Jet OLEDB:ODBC 传递语句<br />
(DBPROP_JETOLEDB_ODBCPASSTHROUGH)</p></td>
<td><p>指示 Jet 是否应该将 <strong>Command</strong> 对象中的 SQL 文本原封不动地传递到后端。</p></td>
</tr>
<tr class="odd">
<td><p>Jet OLEDB:Partial 批量操作<br />
(DBPROP_JETOLEDB_BULKPARTIAL)</p></td>
<td><p>指示 SQL DML 操作失败时 Jet 的行为。</p></td>
</tr>
<tr class="even">
<td><p>通过查询批量桌面 jet OLEDB:Pass<br />
(DBPROP_JETOLEDB_PASSTHROUGHBULKOP)</p></td>
<td><p>指示是否将不返回 <strong>Recordset</strong> 的查询原封不动地传递到数据源。</p></td>
</tr>
<tr class="odd">
<td><p>通过查询 jet OLEDB:Pass 连接字符串<br />
(DBPROP_JETOLEDB_ODBCPASSTHROUGHCONNECTSTRING)</p></td>
<td><p>指示用于连接到远程数据存储区的 Jet 连接字符串。除非 <strong>Jet OLEDB:ODBC Pass-Through Statement</strong> 为 True，否则将忽略此值。</p></td>
</tr>
<tr class="even">
<td><p>Jet OLEDB： 存储查询<br />
(DBPROP_JETOLEDB_STOREDQUERY)</p></td>
<td><p>指示是否应将命令文本解释为存储查询，而不是解释为 SQL 命令。</p></td>
</tr>
<tr class="odd">
<td><p>Jet OLEDB： 验证规则集<br />
(DBPROP_JETOLEDB_VALIDATEONSET)</p></td>
<td><p>指示在设置列数据或将更改提交到数据库时，是否应该评估 Jet 验证规则。</p></td>
</tr>
</tbody>
</table>


默认情况下，OLE DB Provider for Microsoft Jet 在可读/写模式下打开 Microsoft Jet 数据库。若要在只读模式下打开数据库，请将 ADO [Connection](mode-property-ado.md) 对象上的 **Mode** 属性设置为 **adModeRead** 。

## <a name="command-object-usage"></a>Command 对象用法

[Command](command-object-ado.md) 对象中的命令文本使用 Microsoft Jet SQL 语句。您可以在命令文本中指定行返回查询、操作查询和表名称；但是，存储过程不受支持，因而不应指定。

## <a name="recordset-behavior"></a>Recordset 行为

Microsoft Jet 数据库引擎不支持动态游标。因此，OLE DB Provider for Microsoft Jet 也不支持 **adLockDynamic** 游标类型。请求动态游标时，该提供程序将返回键集游标并重新设置 [CursorType](cursortype-property-ado.md) 属性，以指示返回的 [Recordset](recordset-object-ado.md) 的类型。而且，如果请求可更新的 **Recordset**（**LockType** 是 **adLockOptimistic**、**adLockBatchOptimistic** 或 **adLockPessimistic**），则该提供程序也会返回一个键集游标并重新设置 **CursorType** 属性。

## <a name="dynamic-properties"></a>动态属性

OLE DB Provider for Microsoft Jet 可以将多个动态属性插入到未打开的 **Connection**、[Recordset](connection-object-ado.md) 和 [Command](recordset-object-ado.md) 对象的 [Properties](command-object-ado.md) 集合中。

下面的表是每个动态属性的 ADO 和 OLE DB 名称的交叉索引。《OLE DB 程序员参考》使用术语"说明"来引用 ADO 属性名。您可以在《OLE DB 程序员参考》中找到有关这些属性的详细信息。请在"索引"中搜索 OLE DB 属性名，或者请参阅"附录 C：OLE DB 属性"。

## <a name="connection-dynamic-properties"></a>Connection 动态属性

以下属性将被添加到 **Connection** 对象的 **Properties** 集合中。

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
<td><p>Current Catalog</p></td>
<td><p>DBPROP_CURRENTCATALOG</p></td>
</tr>
<tr class="odd">
<td><p>Data Source</p></td>
<td><p>DBPROP_INIT_DATASOURCE</p></td>
</tr>
<tr class="even">
<td><p>Data Source Name</p></td>
<td><p>DBPROP_DATASOURCENAME</p></td>
</tr>
<tr class="odd">
<td><p>Data Source Object Threading Model</p></td>
<td><p>DBPROP_DSOTHREADMODEL</p></td>
</tr>
<tr class="even">
<td><p>DBMS Name</p></td>
<td><p>DBPROP_DBMSNAME</p></td>
</tr>
<tr class="odd">
<td><p>DBMS Version</p></td>
<td><p>DBPROP_DBMSVER</p></td>
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
<td><p>Isolation Levels</p></td>
<td><p>DBPROP_SUPPORTEDTXNISOLEVELS</p></td>
</tr>
<tr class="even">
<td><p>Isolation Retention</p></td>
<td><p>DBPROP_SUPPORTEDTXNISORETAIN</p></td>
</tr>
<tr class="odd">
<td><p>Locale Identifier</p></td>
<td><p>DBPROP_INIT_LCID</p></td>
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
<td><p>OLE DB Version</p></td>
<td><p>DBPROP_PROVIDEROLEDBVER</p></td>
</tr>
<tr class="even">
<td><p>OLE Object Support</p></td>
<td><p>DBPROP_OLEOBJECTS</p></td>
</tr>
<tr class="odd">
<td><p>Open Rowset Support</p></td>
<td><p>DBPROP_OPENROWSETSUPPORT</p></td>
</tr>
<tr class="even">
<td><p>ORDER BY Columns in Select List</p></td>
<td><p>DBPROP_ORDERBYCOLUMNSINSELECT</p></td>
</tr>
<tr class="odd">
<td><p>Output Parameter Availability</p></td>
<td><p>DBPROP_OUTPUTPARAMETERAVAILABILITY</p></td>
</tr>
<tr class="even">
<td><p>Pass By Ref Accessors</p></td>
<td><p>DBPROP_BYREFACCESSORS</p></td>
</tr>
<tr class="odd">
<td><p>Password</p></td>
<td><p>DBPROP_AUTH_PASSWORD</p></td>
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


## <a name="recordset-dynamic-properties"></a>Recordset 动态属性

以下属性将被添加到 **Recordset** 对象的 **Properties** 集合中。

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
<td><p>Access Order</p></td>
<td><p>DBPROP_ACCESSORDER</p></td>
</tr>
<tr class="even">
<td><p>Append-Only Rowset</p></td>
<td><p>DBPROP_APPENDONLY</p></td>
</tr>
<tr class="odd">
<td><p>Blocking Storage Objects</p></td>
<td><p>DBPROP_BLOCKINGSTORAGEOBJECTS</p></td>
</tr>
<tr class="even">
<td><p>Bookmark Type</p></td>
<td><p>DBPROP_BOOKMARKTYPE</p></td>
</tr>
<tr class="odd">
<td><p>Bookmarkable</p></td>
<td><p>DBPROP_IROWSETLOCATE</p></td>
</tr>
<tr class="even">
<td><p>Bookmarks Ordered</p></td>
<td><p>DBPROP_ORDEREDBOOKMARKS</p></td>
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
<td><p>Hold Rows</p></td>
<td><p>DBPROP_CANHOLDROWS</p></td>
</tr>
<tr class="even">
<td><p>IAccessor</p></td>
<td><p>DBPROP_IAccessor</p></td>
</tr>
<tr class="odd">
<td><p>IColumnsInfo</p></td>
<td><p>DBPROP_IColumnsInfo</p></td>
</tr>
<tr class="even">
<td><p>IColumnsRowset</p></td>
<td><p>DBPROP_IColumnsRowset</p></td>
</tr>
<tr class="odd">
<td><p>IConnectionPointContainer</p></td>
<td><p>DBPROP_IConnectionPointContainer</p></td>
</tr>
<tr class="even">
<td><p>IConvertType</p></td>
<td><p>DBPROP_IConvertType</p></td>
</tr>
<tr class="odd">
<td><p>ILockBytes</p></td>
<td><p>DBPROP_ILockBytes</p></td>
</tr>
<tr class="even">
<td><p>Immobile Rows</p></td>
<td><p>DBPROP_IMMOBILEROWS</p></td>
</tr>
<tr class="odd">
<td><p>IRowset</p></td>
<td><p>DBPROP_IRowset</p></td>
</tr>
<tr class="even">
<td><p>IRowsetChange</p></td>
<td><p>DBPROP_IRowsetChange</p></td>
</tr>
<tr class="odd">
<td><p>IRowsetIdentity</p></td>
<td><p>DBPROP_IRowsetIdentity</p></td>
</tr>
<tr class="even">
<td><p>IRowsetIndex</p></td>
<td><p>DBPROP_IRowsetIndex</p></td>
</tr>
<tr class="odd">
<td><p>IRowsetInfo</p></td>
<td><p>DBPROP_IRowsetInfo</p></td>
</tr>
<tr class="even">
<td><p>IRowsetLocate</p></td>
<td><p>DBPROP_IRowsestLocate</p></td>
</tr>
<tr class="odd">
<td><p>IRowsetResynch</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>IRowsetScroll</p></td>
<td><p>DBPROP_IRowsetScroll</p></td>
</tr>
<tr class="odd">
<td><p>IRowsetUpdate</p></td>
<td><p>DBPROP_IRowsetUpdate</p></td>
</tr>
<tr class="even">
<td><p>ISequentialStream</p></td>
<td><p>DBPROP_ISequentialStream</p></td>
</tr>
<tr class="odd">
<td><p>IStorage</p></td>
<td><p>DBPROP_IStorage</p></td>
</tr>
<tr class="even">
<td><p>IStream</p></td>
<td><p>DBPROP_IStream</p></td>
</tr>
<tr class="odd">
<td><p>ISupportErrorInfo</p></td>
<td><p>DBPROP_ISupportErrorInfo</p></td>
</tr>
<tr class="even">
<td><p>Literal Bookmarks</p></td>
<td><p>DBPROP_LITERALBOOKMARKS</p></td>
</tr>
<tr class="odd">
<td><p>Literal Row Identity</p></td>
<td><p>DBPROP_LITERALIDENTITY</p></td>
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
<td><p>DBPROP_MAXROWS</p></td>
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
<td><p>Quick Restart</p></td>
<td><p>DBPROP_QUICKRESTART</p></td>
</tr>
<tr class="even">
<td><p>Reentrant Events</p></td>
<td><p>DBPROP_REENTRANTEVENTS</p></td>
</tr>
<tr class="odd">
<td><p>Remove Deleted Rows</p></td>
<td><p>DBPROP_REMOVEDELETED</p></td>
</tr>
<tr class="even">
<td><p>Report Multiple Changes</p></td>
<td><p>DBPROP_REPORTMULTIPLECHANGES</p></td>
</tr>
<tr class="odd">
<td><p>Return Pending Inserts</p></td>
<td><p>DBPROP_RETURNPENDINGINSERTS</p></td>
</tr>
<tr class="even">
<td><p>Row Delete Notification</p></td>
<td><p>DBPROP_NOTIFYROWDELETE</p></td>
</tr>
<tr class="odd">
<td><p>Row First Change Notification</p></td>
<td><p>DBPROP_NOTIFYROWFIRSTCHANGE</p></td>
</tr>
<tr class="even">
<td><p>Row Insert Notification</p></td>
<td><p>DBPROP_NOTIFYROWINSERT</p></td>
</tr>
<tr class="odd">
<td><p>Row Privileges</p></td>
<td><p>DBPROP_ROWRESTRICT</p></td>
</tr>
<tr class="even">
<td><p>Row Resynchronization Notification</p></td>
<td><p>DBPROP_NOTIFYROWRESYNCH</p></td>
</tr>
<tr class="odd">
<td><p>Row Threading Model</p></td>
<td><p>DBPROP_ROWTHREADMODEL</p></td>
</tr>
<tr class="even">
<td><p>Row Undo Change Notification</p></td>
<td><p>DBPROP_NOTIFYROWUNDOCHANGE</p></td>
</tr>
<tr class="odd">
<td><p>Row Undo Delete Notification</p></td>
<td><p>DBPROP_NOTIFYROWUNDODELETE</p></td>
</tr>
<tr class="even">
<td><p>Row Undo Insert Notification</p></td>
<td><p>DBPROP_NOTIFYROWUNDOINSERT</p></td>
</tr>
<tr class="odd">
<td><p>Row Update Notification</p></td>
<td><p>DBPROP_NOTIFYROWUPDATE</p></td>
</tr>
<tr class="even">
<td><p>Rowset Fetch Position Change Notification</p></td>
<td><p>DBPROP_NOTIFYROWSETFETCHPOSISIONCHANGE</p></td>
</tr>
<tr class="odd">
<td><p>Rowset Release Notification</p></td>
<td><p>DBPROP_NOTIFYROWSETRELEASE</p></td>
</tr>
<tr class="even">
<td><p>Scroll Backwards</p></td>
<td><p>DBPROP_CANSCROLLBACKWARDS</p></td>
</tr>
<tr class="odd">
<td><p>Skip Deleted Bookmarks</p></td>
<td><p>DBPROP_BOOKMARKSKIPPED</p></td>
</tr>
<tr class="even">
<td><p>Strong Row Identity</p></td>
<td><p>DBPROP_STRONGITDENTITY</p></td>
</tr>
<tr class="odd">
<td><p>Updatability</p></td>
<td><p>DBPROP_UPDATABILITY</p></td>
</tr>
<tr class="even">
<td><p>Use Bookmarks</p></td>
<td><p>DBPROP_BOOKMARKS</p></td>
</tr>
</tbody>
</table>


## <a name="command-dynamic-properties"></a>Command 动态属性

以下属性将被添加到 **Command** 对象的 **Properties** 集合中。

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
<td><p>Access Order</p></td>
<td><p>DBPROP_ACCESSORDER</p></td>
</tr>
<tr class="even">
<td><p>Append-Only Rowset</p></td>
<td><p>DBPROP_APPENDONLY</p></td>
</tr>
<tr class="odd">
<td><p>Blocking Storage Objects</p></td>
<td><p>DBPROP_BLOCKINGSTORAGEOBJECTS</p></td>
</tr>
<tr class="even">
<td><p>Bookmark Type</p></td>
<td><p>DBPROP_BOOKMARKTYPE</p></td>
</tr>
<tr class="odd">
<td><p>Bookmarkable</p></td>
<td><p>DBPROP_IROWSETLOCATE</p></td>
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
<td><p>Defer Column</p></td>
<td><p>DBPROP_DEFERRED</p></td>
</tr>
<tr class="even">
<td><p>Delay Storage Object Updates</p></td>
<td><p>DBPROP_DELAYSTORAGEOBJECTS</p></td>
</tr>
<tr class="odd">
<td><p>Fetch Backwards</p></td>
<td><p>DBPROP_CANFETCHBACKWARDS</p></td>
</tr>
<tr class="even">
<td><p>Hold Rows</p></td>
<td><p>DBPROP_CANHOLDROWS</p></td>
</tr>
<tr class="odd">
<td><p>IAccessor</p></td>
<td><p>DBPROP_IAccessor</p></td>
</tr>
<tr class="even">
<td><p>IColumnsInfo</p></td>
<td><p>DBPROP_IColumnsInfo</p></td>
</tr>
<tr class="odd">
<td><p>IColumnsRowset</p></td>
<td><p>DBPROP_IColumnsRowset</p></td>
</tr>
<tr class="even">
<td><p>IConnectionPointContainer</p></td>
<td><p>DBPROP_IConnectionPointContainer</p></td>
</tr>
<tr class="odd">
<td><p>IConvertType</p></td>
<td><p>DBPROP_IConvertType</p></td>
</tr>
<tr class="even">
<td><p>ILockBytes</p></td>
<td><p>DBPROP_ILockBytes</p></td>
</tr>
<tr class="odd">
<td><p>Immobile Rows</p></td>
<td><p>DBPROP_IMMOBILEROWS</p></td>
</tr>
<tr class="even">
<td><p>IRowset</p></td>
<td><p>DBPROP_IRowset</p></td>
</tr>
<tr class="odd">
<td><p>IRowsetChange</p></td>
<td><p>DBPROP_IRowsetChange</p></td>
</tr>
<tr class="even">
<td><p>IRowsetIdentity</p></td>
<td><p>DBPROP_IRowsetIdentity</p></td>
</tr>
<tr class="odd">
<td><p>IRowsetIndex</p></td>
<td><p>DBPROP_IRowsetIndex</p></td>
</tr>
<tr class="even">
<td><p>IRowsetInfo</p></td>
<td><p>DBPROP_IRowsetInfo</p></td>
</tr>
<tr class="odd">
<td><p>IRowsetLocate</p></td>
<td><p>DBPROP_IRowsetLocate</p></td>
</tr>
<tr class="even">
<td><p>IRowsetResynch</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>IRowsetScroll</p></td>
<td><p>DBPROP_IRowsetScroll</p></td>
</tr>
<tr class="even">
<td><p>IRowsetUpdate</p></td>
<td><p>DBPROP_IRowsetUpdate</p></td>
</tr>
<tr class="odd">
<td><p>ISequentialStream</p></td>
<td><p>DBPROP_ISequentialStream</p></td>
</tr>
<tr class="even">
<td><p>IStorage</p></td>
<td><p>DBPROP_IStorage</p></td>
</tr>
<tr class="odd">
<td><p>IStream</p></td>
<td><p>DBPROP_IStream</p></td>
</tr>
<tr class="even">
<td><p>ISupportErrorInfo</p></td>
<td><p>DBPROP_ISupportErrorInfo</p></td>
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
<td><p>Lock Mode</p></td>
<td><p>DBPROP_LOCKMODE</p></td>
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
<td><p>DBPROP_MAXROWS</p></td>
</tr>
<tr class="odd">
<td><p>Notification Granularity</p></td>
<td><p>DBPROP_NOTIFICATIONGRANULARITY</p></td>
</tr>
<tr class="even">
<td><p>Notification Phases</p></td>
<td><p>DBPROP_NOTIFICATIONPHASES</p></td>
</tr>
<tr class="odd">
<td><p>Objects Transacted</p></td>
<td><p>DBPROP_TRANSACTEDOBJECT</p></td>
</tr>
<tr class="even">
<td><p>Others' Changes Visible</p></td>
<td><p>DBPROP_OTHERUPDATEDELETE</p></td>
</tr>
<tr class="odd">
<td><p>Others' Inserts Visible</p></td>
<td><p>DBPROP_OTHERINSERT</p></td>
</tr>
<tr class="even">
<td><p>Own Changes Visible</p></td>
<td><p>DBPROP_OWNUPDATEDELETE</p></td>
</tr>
<tr class="odd">
<td><p>Own Inserts Visible</p></td>
<td><p>DBPROP_OWNINSERT</p></td>
</tr>
<tr class="even">
<td><p>Preserve on Abort</p></td>
<td><p>DBPROP_ABORTPRESERVE</p></td>
</tr>
<tr class="odd">
<td><p>Preserve on Commit</p></td>
<td><p>DBPROP_COMMITPRESERVE</p></td>
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
<td><p>Server Data on Insert</p></td>
<td><p>DBPROP_SERVERDATAONINSERT</p></td>
</tr>
<tr class="odd">
<td><p>Skip Deleted Bookmarks</p></td>
<td><p>DBPROP_BOOKMARKSKIP</p></td>
</tr>
<tr class="even">
<td><p>Strong Row Identity</p></td>
<td><p>DBPROP_STRONGIDENTITY</p></td>
</tr>
<tr class="odd">
<td><p>Updatability</p></td>
<td><p>DBPROP_UPDATABILITY</p></td>
</tr>
<tr class="even">
<td><p>Use Bookmarks</p></td>
<td><p>DBPROP_BOOKMARKS</p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>另请参阅

有关具体的实现详细信息以及有关 OLE DB Provider for Microsoft Jet 的功能信息，请参阅 OLE DB Provider for Microsoft Jet MDAC SDK 中的文档。

