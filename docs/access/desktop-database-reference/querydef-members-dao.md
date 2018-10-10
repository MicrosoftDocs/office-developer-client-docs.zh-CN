---
title: QueryDef Members (DAO)
TOCTitle: QueryDef Members
ms:assetid: 3f914d23-aa63-3ebd-1d86-4f53da71131b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192855(v=office.15)
ms:contentKeyID: 48544403
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 357e419f27efdcc7b6b46004cd340c100114a72a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466724"
---
# <a name="querydef-members-dao"></a>QueryDef Members (DAO)


**适用于**： Access 2013 |Office 2013

QueryDef 对象是 Microsoft Access 数据库引擎数据库中某个查询的存储定义。

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
<td><p><strong><a href="querydef-cancel-method-dao.md">Cancel</a></strong></p></td>
<td><p></p>

> [!NOTE]
> <P>Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</P>


<p>取消执行待定的异步方法调用（仅适用于 ODBCDirect 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="querydef-close-method-dao.md">关闭</a></strong></p></td>
<td><p>关闭已打开的 <strong>QueryDef</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="querydef-createproperty-method-dao.md">CreateProperty</a></strong></p></td>
<td><p>创建一个新的用户定义的 <strong><a href="property-object-dao.md">Property</a></strong> 对象（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="querydef-execute-method-dao.md">Execute</a></strong></p></td>
<td><p>对指定的对象执行 SQL 语句。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="querydef-openrecordset-method-dao.md">OpenRecordset</a></strong></p></td>
<td><p>创建一个新的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象，并将其追加到 <strong>Recordsets</strong> 集合。</p></td>
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
<td><p><strong><a href="querydef-cachesize-property-dao.md">CacheSize</a></strong></p></td>
<td><p>设置或返回从 ODBC 数据源中检索的、需要本地缓存的记录数。可读/写 <strong>Long</strong> 类型。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="querydef-connect-property-dao.md">Connect</a></strong></p></td>
<td><p>设置或返回一个值，该值提供有关在传递查询中使用的数据库源的信息。只读 <strong>String</strong> 类型。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="querydef-datecreated-property-dao.md">DateCreated</a></strong></p></td>
<td><p>返回对象的创建日期和时间（仅适用于 Microsoft Access 工作区）。只读 <strong>Variant</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="querydef-fields-property-dao.md">字段</a></strong></p></td>
<td><p>返回一个 <strong><a href="fields-collection-dao.md">Fields</a></strong> 集合，该集合表示指定对象的所有存储 <strong><a href="field-object-dao.md">Field</a></strong> 对象。只读。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="querydef-lastupdated-property-dao.md">LastUpdated</a></strong></p></td>
<td><p>返回对象的最近更改日期和时间。只读 <strong>Variant</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="querydef-maxrecords-property-dao.md">MaxRecords</a></strong></p></td>
<td><p>设置或返回针对 ODBC 数据源的查询所返回的最大记录数。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="querydef-name-property-dao.md">Name</a></strong></p></td>
<td><p>返回或设置指定对象的名称。可读/写 <strong>String</strong> 类型。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="querydef-odbctimeout-property-dao.md">ODBCTimeout</a></strong></p></td>
<td><p>指示在开放式数据库连接 (ODBC) 数据库上执行 <strong><a href="querydef-object-dao.md">QueryDef</a></strong> 时，发生超时错误之前等待的秒数。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="querydef-parameters-property-dao.md">参数</a></strong></p></td>
<td><p>返回一个 <strong><a href="parameters-collection-dao.md">Parameters</a></strong> 集合，该集合包含指定 <a href="parameter-object-dao.md">QueryDef</a> 的所有 <strong><strong>Parameter</strong></strong> 对象。只读。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="querydef-prepare-property-dao.md">Prepare</a></strong></p></td>
<td><p></p>

> [!NOTE]
> <P>Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</P>


<p>设置或返回一个值，用于指示是应当在执行之前使用 ODBC <strong>SQLPrepare</strong> API 函数在服务器上将查询作为临时存储过程来准备，还是应当使用 ODBC <strong>SQLExecDirect</strong> API 函数（只适用于 ODBCDirect 工作区）来执行查询。可读写。 <strong><a href="querydefstateenum-enumeration-dao.md">QueryDefStateEnum</a></strong> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="querydef-properties-property-dao.md">属性</a></strong></p></td>
<td><p>返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。只读。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="querydef-recordsaffected-property-dao.md">RecordsAffected</a></strong></p></td>
<td><p>返回最近调用的 <strong><a href="querydef-execute-method-dao.md">Execute</a></strong> 方法所影响的记录数。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="querydef-returnsrecords-property-dao.md">ReturnsRecords</a></strong></p></td>
<td><p>设置或返回一个值，该值指示针对外部数据库的 SQL 传递查询是否返回记录（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="querydef-sql-property-dao.md">SQL</a></strong></p></td>
<td><p>设置或返回定义 <strong><a href="querydef-object-dao.md">QueryDef</a></strong> 对象所执行的查询的 SQL 语句。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="querydef-stillexecuting-property-dao.md">StillExecuting</a></strong></p></td>
<td><p></p>

> [!NOTE]
> <P>Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</P>


<p>指示异步操作（即用 <a href="recordsetoptionenum-enumeration-dao.md">dbRunAsync</a> 选项调用的方法）是否已执行完毕（仅适用于 ODBCDirect 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="querydef-type-property-dao.md">类型</a></strong></p></td>
<td><p>设置或返回一个值，该值指示对象的操作类型或数据类型。 只读的<strong>整数</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="querydef-updatable-property-dao.md">Updatable</a></strong></p></td>
<td><p>返回一个值，该值指示是否可以更改 DAO 对象。只读 <strong>Boolean</strong>。</p></td>
</tr>
</tbody>
</table>

