---
title: Microsoft OLE DB Provider for Microsoft Indexing Service
TOCTitle: Microsoft OLE DB Provider for Microsoft Indexing Service
ms:assetid: 01c2e75c-950a-dd8a-2b20-bbd916315ec5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248786(v=office.15)
ms:contentKeyID: 48542942
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e41633ddb2730af66ddeee400ad035d5a17ed90d
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25607051"
---
# <a name="microsoft-ole-db-provider-for-microsoft-indexing-service"></a>Microsoft OLE DB Provider for Microsoft Indexing Service


**适用于**： Access 2013 |Office 2013

<<<<<<< 标头 Microsoft OLE DB Provider for Microsoft Indexing Service 提供对文件系统和 Web 数据由 Microsoft Indexing Service 编制索引的编程只读访问权限。 ADO 应用程序可以发出 SQL 查询，以检索内容和文件属性信息。
=== Microsoft OLE DB Provider for Microsoft Indexing Service 提供对由 Microsoft Indexing Service 编制索引的文件系统和 web 数据的编程只读访问权限。 ADO 应用程序可以发出 SQL 查询，以检索内容和文件属性信息。
>>>>>>> master

该提供程序为自由线程且支持 Unicode。

## <a name="connection-string-parameters"></a>连接字符串参数

若要连接到此提供程序，请将 **ConnectionString** 属性的 [Provider=](connectionstring-property-ado.md) 参数设置为：

```vb 
 
MSIDXS 
```

读取 [Provider](provider-property-ado.md) 属性时，也会返回此字符串。

## <a name="typical-connection-string"></a>典型的连接字符串

此提供程序典型的连接字符串为：

```vb 
 
"Provider=MSIDXS;Data Source=myCatalog;Locale Identifier=nnnn;" 
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
<td><p>指定 Microsoft OLE DB Provider for Microsoft Indexing Service。通常，这是在连接字符串中指定的唯一一个关键字。</p></td>
</tr>
<tr class="even">
<td><p><strong>Data Source</strong></p></td>
<td><p>指定 Indexing Service 目录名称。如果没有指定此关键字。则将使用默认的系统目录。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Locale Identifier</strong></p></td>
<td><p>指定唯一的 32 位编号（例如 1033），用于指定与用户的语言相关的首选项。这些首选项指示设置日期和时间格式的方式、按字母顺序对项排序的方式、比较字符串的方式等。如果没有指定此关键字，则将使用默认的系统区域设置标识符。</p></td>
</tr>
</tbody>
</table>


## <a name="command-text"></a>命令文本

Indexing Service SQL 查询语法包含对 SQL-92 **SELECT** 语句及其 **FROM** 和 **WHERE 子句** 的扩展。查询结果通过 OLE DB 行集返回，查询结果可供 ADO 使用并可将其作为 [Recordset](recordset-object-ado.md) 对象进行操作。

可以搜索实际的单词或短语，也可以使用通配符搜索单词的模式或词干。搜索逻辑可能基于 Boolean 决策、加权的术语或与其他单词的近似程度。您还可以按"自由文本"进行搜索，从而根据意义（而不是实际的单词）来查找匹配项。

该提供程序不会接受存储过程调用或简单的表名称（例如，[CommandType](commandtype-property-ado.md) 属性将始终为 **adCmdText**）。

## <a name="recordset-behavior"></a>Recordset 行为

下表列出了使用此提供程序打开的 **Recordset** 对象中可用的功能。 仅静态游标类型 (**为 adOpenStatic**) 才可用。

有关提供程序配置的 **Recordset** 行为的详细信息，请运行 [Supports](supports-method-ado.md) 方法并枚举 [Recordset](properties-collection-ado.md) 的 **Properties** 集合，以确定提供程序特定的动态属性是否存在。

标准 ADO **Recordset** 属性的可用性：

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>属性</p></th>
<th><p>可用性</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="absolutepage-property-ado.md">AbsolutePage</a></p></td>
<td><p>读/写</p></td>
</tr>
<tr class="even">
<td><p><a href="absoluteposition-property-ado.md">AbsolutePosition</a></p></td>
<td><p>读/写</p></td>
</tr>
<tr class="odd">
<td><p><a href="activeconnection-property-ado.md">ActiveConnection</a></p></td>
<td><p>只读</p></td>
</tr>
<tr class="even">
<td><p><a href="bof-eof-properties-ado.md">BOF</a></p></td>
<td><p>只读</p></td>
</tr>
<tr class="odd">
<td><p><a href="bookmark-property-ado.md">书签</a>*</p></td>
<td><p>读/写</p></td>
</tr>
<tr class="even">
<td><p><a href="cachesize-property-ado.md">CacheSize</a></p></td>
<td><p>读/写</p></td>
</tr>
<tr class="odd">
<td><p><a href="cursorlocation-property-ado.md">CursorLocation</a></p></td>
<td><p>始终为 <strong>adUseServer</strong></p></td>
</tr>
<tr class="even">
<td><p><a href="cursortype-property-ado.md">CursorType</a></p></td>
<td><p>始终为 <strong>adOpenStatic</strong></p></td>
</tr>
<tr class="odd">
<td><p><a href="editmode-property-ado.md">EditMode</a></p></td>
<td><p>始终为 <strong>adEditNone</strong></p></td>
</tr>
<tr class="even">
<td><p><a href="bof-eof-properties-ado.md">EOF</a></p></td>
<td><p>只读</p></td>
</tr>
<tr class="odd">
<td><p><a href="filter-property-ado.md">Filter</a></p></td>
<td><p>读/写</p></td>
</tr>
<tr class="even">
<td><p><a href="locktype-property-ado.md">LockType</a></p></td>
<td><p>读/写</p></td>
</tr>
<tr class="odd">
<td><p><a href="marshaloptions-property-ado.md">MarshalOptions</a></p></td>
<td><p>暂无</p></td>
</tr>
<tr class="even">
<td><p><a href="maxrecords-property-ado.md">MaxRecords</a></p></td>
<td><p>读/写</p></td>
</tr>
<tr class="odd">
<td><p><a href="pagecount-property-ado.md">PageCount</a></p></td>
<td><p>只读</p></td>
</tr>
<tr class="even">
<td><p><a href="pagesize-property-ado.md">PageSize</a></p></td>
<td><p>读/写</p></td>
</tr>
<tr class="odd">
<td><p><a href="recordcount-property-ado.md">RecordCount</a></p></td>
<td><p>只读</p></td>
</tr>
<tr class="even">
<td><p><a href="source-property-ado-recordset.md">Source</a></p></td>
<td><p>读/写</p></td>
</tr>
<tr class="odd">
<td><p><a href="state-property-ado.md">State</a></p></td>
<td><p>只读</p></td>
</tr>
<tr class="even">
<td><p><a href="status-property-ado-recordset.md">Status</a></p></td>
<td><p>只读</p></td>
</tr>
</tbody>
</table>


\*必须在此功能的顺序提供程序，以在**Recordset**上启用书签。

标准 ADO **Recordset** 方法的可用性：

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>方法</p></th>
<th><p>是否可用</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="addnew-method-ado.md">AddNew</a></p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p><a href="cancel-method-ado.md">Cancel</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="cancelbatch-method-ado.md">CancelBatch</a></p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p><a href="cancelupdate-method-ado.md">CancelUpdate</a></p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p><a href="clone-method-ado.md">Clone</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="close-method-ado.md">Close</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="delete-method-ado-recordset.md">Delete</a></p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p><a href="getrows-method-ado.md">GetRows</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="move-method-ado.md">移动</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="nextrecordset-method-ado.md">NextRecordset</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="open-method-ado-recordset.md">Open</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="requery-method-ado.md">Requery</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="resync-method-ado.md">Resync</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="supports-method-ado.md">支持</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="update-method-ado.md">更新</a></p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p><a href="updatebatch-method-ado.md">UpdateBatch</a></p></td>
<td><p>否</p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>另请参阅

有关具体的实现详细信息和有关 Microsoft OLE DB Provider for Microsoft Indexing Service 的功能信息，请参阅 Microsoft OLE DB 程序员参考。

