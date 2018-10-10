---
title: Microsoft OLE DB Provider for ODBC
TOCTitle: Microsoft OLE DB Provider for ODBC
ms:assetid: c507567e-5ad1-b32a-f6ad-5ba2c39aa4c2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249964(v=office.15)
ms:contentKeyID: 48547602
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 168799b517598211ca9de680730490a0a41d1dde
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468899"
---
# <a name="microsoft-ole-db-provider-for-odbc"></a>Microsoft OLE DB Provider for ODBC

**适用于**： Access 2013 |Office 2013

对 ADO 或 RDS 程序员来说，理想环境应该是：每个数据源都公开一个 OLE DB 接口，这样 ADO 就可以直接调入数据源。尽管越来越多的数据库供应商要实现 OLE DB 接口，但某些数据源却仍未以此方式公开。实际上，通过 ODBC 可以访问目前在用的所有 DBMS 系统。

ODBC 驱动程序可用于目前在用的所有主要的 DBMS，包括 Microsoft SQL Server、Microsoft Access（Microsoft Jet 数据库引擎）、Microsoft FoxPro 以及非 Microsoft 数据库产品（如 Oracle）。

Microsoft ODBC Provider 允许 ADO 连接到任何 ODBC 数据源。此提供程序为自由线程并使用 Unicode。

此提供程序支持事务处理，但不同的 DBMS 引擎所支持的事务类型不同。例如，Microsoft Access 支持的嵌套事务可达五层。

此提供程序是 ADO 的默认提供程序，它支持所有与提供程序有关的 ADO 属性和方法。

## <a name="connection-string-parameters"></a>连接字符串参数

要连接到此提供程序，请将 **ConnectionString** 属性的 [Provider=](connectionstring-property-ado.md) 参数设置为：

```sql 
 
MSDASQL 
```

读取 [Provider](provider-property-ado.md) 属性时，也会返回此字符串。

## <a name="typical-connection-string"></a>典型的连接字符串

此提供程序典型的连接字符串为：

```sql 
 
"Provider=MSDASQL;DSN=dsnName;UID=userName;PWD=userPassword;" 
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
<td><p>指定 OLE DB Provider for ODBC。</p></td>
</tr>
<tr class="even">
<td><p><strong>DSN</strong></p></td>
<td><p>指定数据源名称。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UID</strong></p></td>
<td><p>指定用户名。</p></td>
</tr>
<tr class="even">
<td><p><strong>PWD</strong></p></td>
<td><p>指定用户密码。</p></td>
</tr>
<tr class="odd">
<td><p><strong>URL</strong></p></td>
<td><p>指定 Web 文件夹中已发布文件或目录的 URL。</p></td>
</tr>
</tbody>
</table>


如果在连接字符串中省略 **Provider=** 参数，则 ADO 将尝试建立与此提供程序（因为它是 ADO 的默认提供程序）的连接。

除了 ADO 定义的连接参数以外，此提供程序不支持任何特定的连接参数，但它会将任何非 ADO 连接参数传递给 ODBC 驱动程序管理器。

由于可以省略 **Provider** 参数，因此，可以构造与同一个数据源的 ODBC 连接字符串完全一样的 ADO 连接字符串。参数名称（**DRIVER=**、**DATABASE=**、**DSN=** 等）、值和语法也和构造 ODBC 连接字符串时所用的一样。连接时，可以使用也可以不使用预定义的数据源名称 (DSN) 或 FileDSN。

**带有 DSN 或 FileDSN 的语法：**

`"[Provider=MSDASQL;] { DSN=name | FileDSN=filename } ; [DATABASE=database;] UID=user; PWD=password"`

**不带 DSN（无 DSN 连接）的语法：**

`"[Provider=MSDASQL;] DRIVER=driver; SERVER=server;DATABASE=database; UID=user; PWD=password"`

如果要使用 **DSN** 或 **FileDSN** ，必须通过 Windows "控制面板"中的"ODBC 数据源管理器"进行定义。在 Microsoft Windows 2000 中，ODBC 管理器位于"管理工具"中。在以前的 Windows 版本中，"ODBC 管理器"图标的名称是 **32 位 ODBC** 或者就是 **ODBC** 。

除了设置 **DSN** 以外，还可以指定 ODBC 驱动程序，如“SQL Server” (**DRIVER=**)；可以指定服务器名称 (**SERVER=**) 和数据库名称 (**DATABASE=**)。

也可以在 ODBC 特定的参数中或在标准的 ADO 定义的 *user* 和 *password* 参数中指定用户帐户名 (**UID=**) 以及用户帐户的密码 (**PWD=**)。

虽然**DSN**定义已指定了数据库，您可以指定除了**DSN**连接到其他数据库*的**数据库*参数。 最好若要使用**DSN**时始终包含**database*参数*。 这将确保在上次检查了 **DSN** 定义后其他用户更改了默认的数据库参数的情况下，依然可以连接到正确的数据库。

## <a name="provider-specific-connection-properties"></a>提供程序特定的连接属性

OLE DB Provider for ODBC 会将多个属性添加到 [Connection](properties-collection-ado.md) 对象的 **Properties** 集合中。下表列出了这些属性以及对应的 OLE DB 属性名（括在括号中）。

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
<td><p>可访问的过程<br />
(KAGPROP_ACCESSIBLEPROCEDURES)</p></td>
<td><p>指示用户是否有权访问存储过程。</p></td>
</tr>
<tr class="even">
<td><p>可访问的表<br />
(KAGPROP_ACCESSIBLETABLES)</p></td>
<td><p>指示用户是否有权针对数据库表执行 SELECT 语句。</p></td>
</tr>
<tr class="odd">
<td><p>活动语句<br />
(KAGPROP_ACTIVESTATEMENTS)</p></td>
<td><p>指示 ODBC 驱动程序在连接上可支持的句柄数量。</p></td>
</tr>
<tr class="even">
<td><p>驱动程序名称<br />
(KAGPROP_DRIVERNAME)</p></td>
<td><p>指示 ODBC 驱动程序的文件名。</p></td>
</tr>
<tr class="odd">
<td><p>ODBC 驱动程序版本<br />
(KAGPROP_DRIVERODBCVER)</p></td>
<td><p>指示此驱动程序支持的 ODBC 版本。</p></td>
</tr>
<tr class="even">
<td><p>文件的使用情况<br />
(KAGPROP_FILEUSAGE)</p></td>
<td><p>指示驱动程序在数据源中处理文件的方式，作为表还是作为目录。</p></td>
</tr>
<tr class="odd">
<td><p>Like 转义子句<br />
(KAGPROP_LIKEESCAPECLAUSE)</p></td>
<td><p>指示驱动程序是否支持为 WHERE 子句的 LIKE 谓词中的百分号字符 (%) 和下划线字符 (_) 定义和使用转义字符。</p></td>
</tr>
<tr class="even">
<td><p>在组中的最大列数<br />
(KAGPROP_MAXCOLUMNSINGROUPBY)</p></td>
<td><p>指示 SELECT 语句的 GROUP BY 子句中可以列出的列的最大数目。</p></td>
</tr>
<tr class="odd">
<td><p>在索引中的最大列<br />
(KAGPROP_MAXCOLUMNSININDEX)</p></td>
<td><p>指示索引中可以包括的列的最大数目。</p></td>
</tr>
<tr class="even">
<td><p>按顺序的最大列<br />
(KAGPROP_MAXCOLUMNSINORDERBY)</p></td>
<td><p>指示 SELECT 语句的 ORDER BY 子句中可以列出的列的最大数目。</p></td>
</tr>
<tr class="odd">
<td><p>在选择最大列数<br />
(KAGPROP_MAXCOLUMNSINSELECT)</p></td>
<td><p>指示 SELECT 语句的 SELECT 部分中可以列出的列的最大数目。</p></td>
</tr>
<tr class="even">
<td><p>表中的最大列<br />
(KAGPROP_MAXCOLUMNSINTABLE)</p></td>
<td><p>指示表中允许的列的最大数目。</p></td>
</tr>
<tr class="odd">
<td><p>数值函数<br />
(KAGPROP_NUMERICFUNCTIONS)</p></td>
<td><p>指示 ODBC 驱动程序支持的数值函数。有关此位掩码中使用的函数名称和关联值的列表，请参阅 ODBC 文档中的“附录 E：标量函数”。</p></td>
</tr>
<tr class="even">
<td><p>外部联接功能<br />
(KAGPROP_OJCAPABILITY)</p></td>
<td><p>指示此提供程序支持的 OUTER JOIN 类型。</p></td>
</tr>
<tr class="odd">
<td><p>Outer Join<br />
(KAGPROP_OUTERJOINS)</p></td>
<td><p>指示支持 OUTER JOIN 的提供程序。</p></td>
</tr>
<tr class="even">
<td><p>特殊字符<br />
(KAGPROP_SPECIALCHARACTERS)</p></td>
<td><p>指示哪些字符对于 ODBC 驱动程序具有特殊意义。</p></td>
</tr>
<tr class="odd">
<td><p>存储过程<br />
(KAGPROP_PROCEDURES)</p></td>
<td><p>指示是否可以在此 ODBC 驱动程序中使用存储过程。</p></td>
</tr>
<tr class="even">
<td><p>字符串函数<br />
(KAGPROP_STRINGFUNCTIONS)</p></td>
<td><p>指示 ODBC 驱动程序支持的字符串函数。有关此位掩码中使用的函数名称和关联值的列表，请参阅 ODBC 文档中的“附录 E：标量函数”。</p></td>
</tr>
<tr class="odd">
<td><p>系统函数<br />
(KAGPROP_SYSTEMFUNCTIONS)</p></td>
<td><p>指示 ODBC 驱动程序支持的系统函数。有关此位掩码中使用的函数名称和关联值的列表，请参阅 ODBC 文档中的“附录 E：标量函数”。</p></td>
</tr>
<tr class="even">
<td><p>时间/日期函数<br />
(KAGPROP_TIMEDATEFUNCTIONS)</p></td>
<td><p>指示 ODBC 驱动程序支持的时间和日期函数。有关此位掩码中使用的函数名称和关联值的列表，请参阅 ODBC 文档中的“附录 E：标量函数”。</p></td>
</tr>
<tr class="odd">
<td><p>SQL 语法支持<br />
(KAGPROP_ODBCSQLCONFORMANCE)</p></td>
<td><p>指示 ODBC 驱动程序支持的 SQL 语法。</p></td>
</tr>
</tbody>
</table>


## <a name="provider-specific-recordset-and-command-properties"></a>提供程序特定的 Recordset 和 Command 属性

OLE DB Provider for ODBC 会将多个属性添加到 **Recordset** 和 **Command** 对象的 **Properties** 集合中。下表列出了这些属性以及对应的 OLE DB 属性名（括在括号中）。

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
<td><p>基于查询的插入/删除/更新<br />
(KAGPROP_QUERYBASEDUPDATES)</p></td>
<td><p>指示是否可以使用 SQL 查询执行更新、删除和插入。</p></td>
</tr>
<tr class="even">
<td><p>ODBC 并发类型<br />
(KAGPROP_CONCURRENCY)</p></td>
<td><p>指示用于减少由两个用户试图同时访问数据源中的相同数据而导致的潜在问题的方法。</p></td>
</tr>
<tr class="odd">
<td><p>仅向前型游标的 BLOB 辅助功能<br />
(KAGPROP_BLOBSONFOCURSOR)</p></td>
<td><p>指示在使用只进游标时是否可以访问 BLOB <strong>字段</strong>。</p></td>
</tr>
<tr class="even">
<td><p>在 QBU WHERE 子句中包括 SQL_FLOAT、 SQL_DOUBLE 和 SQL_REAL<br />
(KAGPROP_INCLUDENONEXACT)</p></td>
<td><p>指示 QBU WHERE 子句中是否可以包括 SQL_FLOAT、SQL_DOUBLE 和 SQL_REAL 值。</p></td>
</tr>
<tr class="odd">
<td><p>在最后一行之后插入的位置<br />
(KAGPROP_POSITIONONNEWROW)</p></td>
<td><p>指示在表中插入新记录后，表中的最后一行是否将为当前行。</p></td>
</tr>
<tr class="even">
<td><p>IRowsetChangeExtInfo<br />
(KAGPROP_IROWSETCHANGEEXTINFO)</p></td>
<td><p>指示 <strong>IRowsetChange</strong> 接口是否提供扩展的信息支持。</p></td>
</tr>
<tr class="odd">
<td><p>ODBC 游标类型<br />
(KAGPROP_CURSOR)</p></td>
<td><p>指示 <strong>Recordset</strong> 使用的游标类型。</p></td>
</tr>
<tr class="even">
<td><p>生成可封送的行集<br />
(KAGPROP_MARSHALLABLE)</p></td>
<td><p>指示 ODBC 驱动程序将生成可封送的记录集</p></td>
</tr>
</tbody>
</table>


## <a name="command-text"></a>命令文本

如何使用 [Command](command-object-ado.md) 对象在很大程度上取决于数据源及其将接受的查询语句或命令语句的类型。

ODBC 提供了用于调用存储过程的特定语法。 **Command**对象、 的[Connection](connection-object-ado.md)对象的**Execute**方法的*CommandText*参数或[Recordset](recordset-object-ado.md)的**Open**方法的*源*参数[将 CommandText](commandtext-property-ado.md)属性对象，此语法与字符串中传递：

`"{ [ ? = ] call procedure [ ( ? [, ? [ ,  ]] ) ] }"`

每个 **?** 都引用 [Parameters](parameters-collection-ado.md) 集合中的一个对象。第一个 **?** 引用 **Parameters**(0)，接下来的 **?** 引用 **Parameters**(1)，依此类推。

参数引用是可选的，且取决于存储过程的结构。如果要调用未定义参数的存储过程，则字符串的形式将与以下所示类似：

`"{ call procedure }"`

如果具有两个查询参数，则字符串的形式将与以下所示类似：

`"{ call procedure ( ?, ? ) }"`

如果存储过程返回一个值，则返回值被作为其他参数进行处理。如果您没有查询参数，但是有返回值，则字符串的形式将与以下所示类似：

`"{ ? = call procedure }"`

最后，如果您具有一个返回值和两个查询参数，则字符串的形式将与以下所示类似：

`"{ ? = call procedure ( ?, ? ) }"`

## <a name="recordset-behavior"></a>Recordset 行为

下面的表列出了使用此提供程序打开的 **Recordset** 对象中可用的标准 ADO 方法和属性。

有关提供程序配置的 **Recordset** 行为的详细信息，请运行 [Supports](supports-method-ado.md) 方法并枚举 **Recordset** 的 **Properties** 集合，以确定提供程序特定的动态属性是否存在。

标准 ADO **Recordset** 属性的可用性：

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><p>属性</p></th>
<th><p>ForwardOnly</p></th>
<th><p>动态</p></th>
<th><p>键集</p></th>
<th><p>静态</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="absolutepage-property-ado.md">AbsolutePage</a></p></td>
<td><p>不可用</p></td>
<td><p>不可用</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
</tr>
<tr class="even">
<td><p><a href="absoluteposition-property-ado.md">AbsolutePosition</a></p></td>
<td><p>不可用</p></td>
<td><p>不可用</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
</tr>
<tr class="odd">
<td><p><a href="activeconnection-property-ado.md">ActiveConnection</a></p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
</tr>
<tr class="even">
<td><p><a href="bof-eof-properties-ado.md">BOF</a></p></td>
<td><p>只读</p></td>
<td><p>只读</p></td>
<td><p>只读</p></td>
<td><p>只读</p></td>
</tr>
<tr class="odd">
<td><p><a href="bookmark-property-ado.md">Bookmark</a></p></td>
<td><p>不可用</p></td>
<td><p>不可用</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
</tr>
<tr class="even">
<td><p><a href="cachesize-property-ado.md">CacheSize</a></p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
</tr>
<tr class="odd">
<td><p><a href="cursorlocation-property-ado.md">CursorLocation</a></p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
</tr>
<tr class="even">
<td><p><a href="cursortype-property-ado.md">CursorType</a></p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
</tr>
<tr class="odd">
<td><p><a href="editmode-property-ado.md">EditMode</a></p></td>
<td><p>只读</p></td>
<td><p>只读</p></td>
<td><p>只读</p></td>
<td><p>只读</p></td>
</tr>
<tr class="even">
<td><p><a href="filter-property-ado.md">Filter</a></p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
</tr>
<tr class="odd">
<td><p><a href="locktype-property-ado.md">LockType</a></p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
</tr>
<tr class="even">
<td><p><a href="marshaloptions-property-ado.md">MarshalOptions</a></p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
</tr>
<tr class="odd">
<td><p><a href="maxrecords-property-ado.md">MaxRecords</a></p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
</tr>
<tr class="even">
<td><p><a href="pagecount-property-ado.md">PageCount</a></p></td>
<td><p>读/写</p></td>
<td><p>不可用</p></td>
<td><p>只读</p></td>
<td><p>只读</p></td>
</tr>
<tr class="odd">
<td><p><a href="pagesize-property-ado.md">PageSize</a></p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
</tr>
<tr class="even">
<td><p><a href="recordcount-property-ado.md">RecordCount</a></p></td>
<td><p>读/写</p></td>
<td><p>不可用</p></td>
<td><p>只读</p></td>
<td><p>只读</p></td>
</tr>
<tr class="odd">
<td><p><a href="source-property-ado-recordset.md">Source</a></p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
<td><p>读/写</p></td>
</tr>
<tr class="even">
<td><p><a href="state-property-ado.md">State</a></p></td>
<td><p>只读</p></td>
<td><p>只读</p></td>
<td><p>只读</p></td>
<td><p>只读</p></td>
</tr>
<tr class="odd">
<td><p><a href="status-property-ado-recordset.md">Status</a></p></td>
<td><p>只读</p></td>
<td><p>只读</p></td>
<td><p>只读</p></td>
<td><p>只读</p></td>
</tr>
</tbody>
</table>


在 1.0 版的 Microsoft OLE DB Provider for ODBC 中使用 ADO 时，[AbsolutePosition](absoluteposition-property-ado.md) 和 [AbsolutePage](absolutepage-property-ado.md) 属性是只写属性。

标准 ADO **Recordset** 方法的可用性：

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><p>方法</p></th>
<th><p>ForwardOnly</p></th>
<th><p>动态</p></th>
<th><p>键集</p></th>
<th><p>静态</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="addnew-method-ado.md">AddNew</a></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="cancel-method-ado.md">Cancel</a></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="cancelbatch-method-ado.md">CancelBatch</a></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="cancelupdate-method-ado.md">CancelUpdate</a></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="clone-method-ado.md">Clone</a></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="close-method-ado.md">Close</a></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="delete-method-ado-recordset.md">Delete</a></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="getrows-method-ado.md">GetRows</a></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="move-method-ado.md">移动</a></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst</a></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveLast</a></p></td>
<td><p>否</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveNext</a></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MovePrevious</a></p></td>
<td><p>否</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="nextrecordset-method-ado.md">NextRecordset</a>*</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="open-method-ado-recordset.md">Open</a></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="requery-method-ado.md">Requery</a></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="resync-method-ado.md">Resync</a></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="supports-method-ado.md">支持</a></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="update-method-ado.md">更新</a></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="updatebatch-method-ado.md">UpdateBatch</a></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
</tbody>
</table>


\*不受 Microsoft Access 数据库支持。

## <a name="dynamic-properties"></a>动态属性

Microsoft OLE DB Provider for ODBC 会将多个动态属性插入到未打开的 **Connection**、[Recordset](connection-object-ado.md) 和 [Command](recordset-object-ado.md) 对象的 [Properties](command-object-ado.md) 集合中。

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
<td><p>Password</p></td>
<td><p>DBPROP_AUTH_PASSWORD</p></td>
</tr>
<tr class="even">
<td><p>Pass By Ref Accessors</p></td>
<td><p>DBPROP_BYREFACCESSORS</p></td>
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
<td><p>Blocking Storage Objects</p></td>
<td><p>DBPROP_BLOCKINGSTORAGEOBJECTS</p></td>
</tr>
<tr class="odd">
<td><p>Bookmark Type</p></td>
<td><p>DBPROP_BOOKMARKTYPE</p></td>
</tr>
<tr class="even">
<td><p>Bookmarkable</p></td>
<td><p>DBPROP_IROWSETLOCATE</p></td>
</tr>
<tr class="odd">
<td><p>Change Inserted Rows</p></td>
<td><p>DBPROP_CHANGEINSERTEDROWS</p></td>
</tr>
<tr class="even">
<td><p>Column Privileges</p></td>
<td><p>DBPROP_COLUMNRESTRICT</p></td>
</tr>
<tr class="odd">
<td><p>Column Set Notification</p></td>
<td><p>DBPROP_NOTIFYCOLUMNSET</p></td>
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
<td><p>IRowsetUpdate</p></td>
<td><p>DBPROP_IRowsetUpdate</p></td>
</tr>
<tr class="even">
<td><p>ISequentialStream</p></td>
<td><p>DBPROP_ISequentialStream</p></td>
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
<td><p>DBPROP_NOTIFYROWSETFETCHPOSISIONCHANGE</p></td>
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
<td><p>Skip Deleted Bookmarks</p></td>
<td><p>DBPROP_BOOKMARKSKIPPED</p></td>
</tr>
<tr class="odd">
<td><p>Strong Row Identity</p></td>
<td><p>DBPROP_STRONGITDENTITY</p></td>
</tr>
<tr class="even">
<td><p>Unique Rows</p></td>
<td><p>DBPROP_UNIQUEROWS</p></td>
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
<td><p>Blocking Storage Objects</p></td>
<td><p>DBPROP_BLOCKINGSTORAGEOBJECTS</p></td>
</tr>
<tr class="odd">
<td><p>Bookmark Type</p></td>
<td><p>DBPROP_BOOKMARKTYPE</p></td>
</tr>
<tr class="even">
<td><p>Bookmarkable</p></td>
<td><p>DBPROP_IROWSETLOCATE</p></td>
</tr>
<tr class="odd">
<td><p>Change Inserted Rows</p></td>
<td><p>DBPROP_CHANGEINSERTEDROWS</p></td>
</tr>
<tr class="even">
<td><p>Column Privileges</p></td>
<td><p>DBPROP_COLUMNRESTRICT</p></td>
</tr>
<tr class="odd">
<td><p>Column Set Notification</p></td>
<td><p>DBPROP_NOTIFYCOLUMNSET</p></td>
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
<td><p>IRowsetUpdate</p></td>
<td><p>DBPROP_IRowsetUpdate</p></td>
</tr>
<tr class="even">
<td><p>ISequentialStream</p></td>
<td><p>DBPROP_ISequentialStream</p></td>
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
<td><p>Skip Deleted Bookmarks</p></td>
<td><p>DBPROP_BOOKMARKSKIP</p></td>
</tr>
<tr class="odd">
<td><p>Strong Row Identity</p></td>
<td><p>DBPROP_STRONGIDENTITY</p></td>
</tr>
<tr class="even">
<td><p>Updatability</p></td>
<td><p>DBPROP_UPDATABILITY</p></td>
</tr>
<tr class="odd">
<td><p>Use Bookmarks</p></td>
<td><p>DBPROP_BOOKMARKS</p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>另请参阅

有关具体的实现以及有关 Microsoft OLE DB Provider for ODBC 的功能信息的详细信息，请参阅[OLE DB 程序员指南 》](https://docs.microsoft.com/previous-versions/windows/desktop/ms713643(v=vs.85))或访问[数据平台开发人员中心](https://docs.microsoft.com/sql/connect/sql-data-developer?view=sql-server-2017)。

