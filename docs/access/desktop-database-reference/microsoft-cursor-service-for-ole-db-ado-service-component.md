---
title: Microsoft Cursor Service for OLE DB（ADO 服务组件）
TOCTitle: Microsoft Cursor Service for OLE DB (ADO Service Component)
ms:assetid: 6818fc05-9c9f-9b67-07d2-e622c93133c2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249405(v=office.15)
ms:contentKeyID: 48545376
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d79d060922c6e7f28209242ebe82821c2ba97bfd
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28713728"
---
# <a name="microsoft-cursor-service-for-ole-db-ado-service-component"></a>Microsoft Cursor Service for OLE DB（ADO 服务组件）


**适用于**： Access 2013、 Office 2013

Microsoft Cursor Service for OLE DB 增加了数据提供程序的游标支持功能。因此，用户可以从所有数据提供程序体验相对统一的功能。

Cursor Service 使动态属性可用，并增强了某些方法的行为。例如，[Optimize](optimize-property-dynamic-ado.md) 动态属性允许创建临时索引，以便于某些操作的执行，如 [Find](find-method-ado.md) 方法。

在所有情况下，Cursor Service 都支持批更新。此外，如果数据提供程序只能提供功能不太强的游标（如静态游标），Cursor Service 还可以模拟功能较强的游标类型（如动态游标）。

## <a name="keyword"></a>关键字

要调用此服务组件，请将 [Recordset](recordset-object-ado.md) 或 [Connection](connection-object-ado.md) 对象的 [CursorLocation](cursorlocation-property-ado.md) 属性设置为 **adUseClient** 。

`connection.CursorLocation=adUseClientrecordset.CursorLocation=adUseClient`

## <a name="dynamic-properties"></a>动态属性

调用 Cursor Service for OLE DB 时，会将以下动态属性添加到 **Recordset** 对象的 [Properties](properties-collection-ado.md) 集合中。 **Connection** 和 **Recordset** 对象的动态属性的完整列表在 [ADO 动态属性索引](ado-dynamic-property-index.md)中列出。关联的 OLE DB 属性名称（如果适合）包括在 ADO 属性名后的括号中。

调用 Cursor Service 后，对某些动态属性所做的更改对基础数据源不可见。 例如，在**Recordset**上设置*命令超时*属性将无法看到基础数据提供程序。

```vb 
... 
Recordset1.CursorLocation = adUseClient 'invokes cursor service 
Recordset1.Open "authors", _ 
 "Provider=SQLOLEDB;Data Source=DBServer;User Id=usr;" & _ 
 "Password=pwd;Initial Catalog=pubs;",,adCmdTable 
Recordset1.Properties.Item("Command Time out") = 50 
' 'Command Time out' property on DBServer is still default (30). 
... 

```

如果应用程序需要 Cursor Service，但您需要在基础提供程序上设置动态属性，则请先设置动态属性，随后调用 Cursor Service。Command 对象属性设置始终会被传递给基础数据提供程序，无论游标所处的位置如何。因此，您还可以随时使用 Command 对象来设置属性。

> [!NOTE]
> 动态属性 DBPROP_SERVERDATAONINSERT 不受 Cursor Service 支持，即使受基础数据提供程序支持也是如此。



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
<td><p>Auto Recalc<br />
(DBPROP_ADC_AUTORECALC)</p></td>
<td><p>对于使用 Data Shaping Service 创建的记录集，此值指示计算列和聚合列的计算频率。默认值 (1) 表示 Data Shaping Service 每次确定值已更改时都重新进行计算。如果该值为 0，则仅在最初建立层次结构时对计算列或聚合列进行计算。</p></td>
</tr>
<tr class="even">
<td><p>Batch Size<br />
(DBPROP_ADC_BATCHSIZE)</p></td>
<td><p>指示在发送到数据存储区之前可以进行批处理的更新语句的数量。批中的语句越多，往返数据存储区的次数就越少。</p></td>
</tr>
<tr class="odd">
<td><p>Cache Child Rows<br />
(DBPROP_ADC_CACHECHILDROWS)</p></td>
<td><p>对于使用 Data Shaping Service 创建的记录集，此值指示是否将子记录集存储在缓存中以供以后使用。</p></td>
</tr>
<tr class="even">
<td><p>Cursor Engine Version<br />
(DBPROP_ADC_CEVER)</p></td>
<td><p>指示正在使用的 Cursor Service 的版本。</p></td>
</tr>
<tr class="odd">
<td><p>Maintain Change Status<br />
(DBPROP_ADC_MAINTAINCHANGESTATUS)</p></td>
<td><p>指示用于重新同步多重表连接中的一行或多行的命令文本。</p></td>
</tr>
<tr class="even">
<td><p><a href="optimize-property-dynamic-ado.md">优化</a></p></td>
<td><p>指示是否应该创建索引。当设置为 <strong>True</strong> 时，表示允许创建临时索引，以提高特定操作的执行性能。</p></td>
</tr>
<tr class="odd">
<td><p><a href="reshape-name-property-dynamic-ado.md">Reshape Name</a></p></td>
<td><p>指示 <strong>Recordset</strong> 的名称。可以在当前 Data Shaping 命令或后续的 Data Shaping 命令中引用该属性。</p></td>
</tr>
<tr class="even">
<td><p><a href="resync-command-property-dynamic-ado.md">Resync Command</a></p></td>
<td><p>指示 <a href="unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md">Unique Table</a> 属性生效时 <a href="resync-method-ado.md">Resync</a> 方法所使用的自定义命令字符串。</p></td>
</tr>
<tr class="odd">
<td><p><a href="unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md">Unique Catalog</a></p></td>
<td><p>指示包含 <strong>Unique Table</strong> 属性中引用的表的数据库的名称。</p></td>
</tr>
<tr class="even">
<td><p><a href="unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md">Unique Schema</a></p></td>
<td><p>指示 <strong>Unique Table</strong> 属性中引用的表的所有者的名称。</p></td>
</tr>
<tr class="odd">
<td><p><a href="unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md">Unique Table</a></p></td>
<td><p>指示通过多个表创建的 <strong>Recordset</strong> 中的一个表的名称，该表可以通过插入、更新或删除操作来修改。</p></td>
</tr>
<tr class="even">
<td><p>Update Criteria<br />
(DBPROP_ADC_UPDATECRITERIA)</p></td>
<td><p>指示使用 <strong>WHERE</strong> 子句中的哪些字段来处理更新期间发生的冲突。</p></td>
</tr>
<tr class="odd">
<td><p><a href="update-resync-property-dynamic-ado.md">Update Resync</a>(DBPROP_ADC_UPDATERESYNC)</p></td>
<td><p>指示 <strong>Unique Table</strong> 属性生效时，在调用 <a href="updatebatch-method-ado.md">UpdateBatch</a> 方法（及其行为）后是否要隐式调用 <strong>Resync</strong> 方法。</p></td>
</tr>
</tbody>
</table>


此外，通过将动态属性的名称指定为 **Properties** 集合的索引，您还可以对动态属性进行设置或检索。例如，可以像下面这样，获取并输出 [Optimize](optimize-property-dynamic-ado.md) 动态属性的当前值，然后设置一个新值：

```vb 
 
Debug.Print rs.Properties("Optimize") 
rs.Properties("Optimize") = True 
```

## <a name="built-in-property-behavior"></a>内置属性行为

Cursor Service for OLE DB 还会影响某些内置属性的行为。

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
<td><p><a href="cursortype-property-ado.md">CursorType</a></p></td>
<td><p>补充可用于 <strong>Recordset</strong> 的游标类型。</p></td>
</tr>
<tr class="even">
<td><p><a href="locktype-property-ado.md">LockType</a></p></td>
<td><p>补充可用于 <strong>Recordset</strong> 的锁定类型。可启用批更新。</p></td>
</tr>
<tr class="odd">
<td><p><a href="sort-property-ado.md">Sort</a></p></td>
<td><p>指定 <strong>Recordset</strong> 排序所依据的一个或多个字段名称，以及按升序还是降序排列每个字段。</p></td>
</tr>
</tbody>
</table>


## <a name="method-behavior"></a>方法行为

Cursor Service for OLE DB 可启用或影响 [Field](field-object-ado.md) 对象的 [Append](append-method-ado.md) 方法，以及 **Recordset** 对象的 [Open](open-method-ado-recordset.md)、[Resync](resync-method-ado.md)、[UpdateBatch](updatebatch-method-ado.md) 和 [Save](save-method-ado.md) 方法。

