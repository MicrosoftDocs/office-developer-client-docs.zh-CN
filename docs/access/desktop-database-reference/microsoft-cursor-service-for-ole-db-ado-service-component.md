---
title: Microsoft Cursor Service for OLE DB（ADO 服务组件）
TOCTitle: Microsoft Cursor Service for OLE DB (ADO Service Component)
ms:assetid: 6818fc05-9c9f-9b67-07d2-e622c93133c2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249405(v=office.15)
ms:contentKeyID: 48545376
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 175023f12d1efa23422afb15e693d44976421cc0
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466358"
---
# <a name="microsoft-cursor-service-for-ole-db-ado-service-component"></a><span data-ttu-id="63452-102">Microsoft Cursor Service for OLE DB（ADO 服务组件）</span><span class="sxs-lookup"><span data-stu-id="63452-102">Microsoft Cursor Service for OLE DB (ADO Service Component)</span></span>


<span data-ttu-id="63452-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="63452-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="63452-p101">Microsoft Cursor Service for OLE DB 增加了数据提供程序的游标支持功能。因此，用户可以从所有数据提供程序体验相对统一的功能。</span><span class="sxs-lookup"><span data-stu-id="63452-p101">The Microsoft Cursor Service for OLE DB supplements the cursor support functions of data providers. As a result, the user perceives relatively uniform functionality from all data providers.</span></span>

<span data-ttu-id="63452-p102">Cursor Service 使动态属性可用，并增强了某些方法的行为。例如，[Optimize](optimize-property-dynamic-ado.md) 动态属性允许创建临时索引，以便于某些操作的执行，如 [Find](find-method-ado.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="63452-p102">The Cursor Service makes dynamic properties available and enhances the behavior of certain methods. For example, the [Optimize](optimize-property-dynamic-ado.md) dynamic property enables the creation of temporary indexes to facilitate certain operations, such as the [Find](find-method-ado.md) method.</span></span>

<span data-ttu-id="63452-p103">在所有情况下，Cursor Service 都支持批更新。此外，如果数据提供程序只能提供功能不太强的游标（如静态游标），Cursor Service 还可以模拟功能较强的游标类型（如动态游标）。</span><span class="sxs-lookup"><span data-stu-id="63452-p103">The Cursor Service enables support for batch updating in all cases. It also simulates more capable cursor types, such as dynamic cursors, when a data provider can only supply less capable cursors, such as static cursors.</span></span>

## <a name="keyword"></a><span data-ttu-id="63452-110">关键字</span><span class="sxs-lookup"><span data-stu-id="63452-110">Keyword</span></span>

<span data-ttu-id="63452-111">要调用此服务组件，请将 [Recordset](recordset-object-ado.md) 或 [Connection](connection-object-ado.md) 对象的 [CursorLocation](cursorlocation-property-ado.md) 属性设置为 **adUseClient** 。</span><span class="sxs-lookup"><span data-stu-id="63452-111">To invoke this service component, set the [Recordset](recordset-object-ado.md) or [Connection](connection-object-ado.md) object's [CursorLocation](cursorlocation-property-ado.md) property to **adUseClient**.</span></span>

`connection.CursorLocation=adUseClientrecordset.CursorLocation=adUseClient`

## <a name="dynamic-properties"></a><span data-ttu-id="63452-112">动态属性</span><span class="sxs-lookup"><span data-stu-id="63452-112">Dynamic Properties</span></span>

<span data-ttu-id="63452-p104">调用 Cursor Service for OLE DB 时，会将以下动态属性添加到 **Recordset** 对象的 [Properties](properties-collection-ado.md) 集合中。 **Connection** 和 **Recordset** 对象的动态属性的完整列表在 [ADO 动态属性索引](ado-dynamic-property-index.md)中列出。关联的 OLE DB 属性名称（如果适合）包括在 ADO 属性名后的括号中。</span><span class="sxs-lookup"><span data-stu-id="63452-p104">When the Cursor Service for OLE DB is invoked, the following dynamic properties are added to the **Recordset** object's [Properties](properties-collection-ado.md) collection. The full list of **Connection** and **Recordset** object dynamic properties is listed in the [ADO Dynamic Property Index](ado-dynamic-property-index.md). The associated OLE DB property names, where appropriate, are included in parenthesis after the ADO property name.</span></span>

<span data-ttu-id="63452-116">调用 Cursor Service 后，对某些动态属性所做的更改对基础数据源不可见。</span><span class="sxs-lookup"><span data-stu-id="63452-116">Changes to some dynamic properties are not visible to the underlying data source after the Cursor Service has been invoked.</span></span> <span data-ttu-id="63452-117">例如，在**Recordset**上设置*命令超时*属性将无法看到基础数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="63452-117">For example, setting the *Command Time out* property on a **Recordset** will not be visible to the underlying data provider.</span></span>

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

<span data-ttu-id="63452-p106">如果应用程序需要 Cursor Service，但您需要在基础提供程序上设置动态属性，则请先设置动态属性，随后调用 Cursor Service。Command 对象属性设置始终会被传递给基础数据提供程序，无论游标所处的位置如何。因此，您还可以随时使用 Command 对象来设置属性。</span><span class="sxs-lookup"><span data-stu-id="63452-p106">If your application requires the Cursor Service, but you need to set dynamic properties on the underlying provider, set the properties before invoking the Cursor Service. Command object property settings are always passed to the underlying data provider regardless of cursor location. Therefore, you can also use a command object to set the properties at any time.</span></span>

> [!NOTE]
> <span data-ttu-id="63452-121">动态属性 DBPROP_SERVERDATAONINSERT 不受 Cursor Service 支持，即使受基础数据提供程序支持也是如此。</span><span class="sxs-lookup"><span data-stu-id="63452-121">The dynamic property DBPROP_SERVERDATAONINSERT is not supported by the cursor service, even if it is supported by the underlying data provider.</span></span>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="63452-122">属性名称</span><span class="sxs-lookup"><span data-stu-id="63452-122">Property Name</span></span></p></th>
<th><p><span data-ttu-id="63452-123">说明</span><span class="sxs-lookup"><span data-stu-id="63452-123">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63452-124">Auto Recalc</span><span class="sxs-lookup"><span data-stu-id="63452-124">Auto Recalc</span></span><br />
<span data-ttu-id="63452-125">(DBPROP_ADC_AUTORECALC)</span><span class="sxs-lookup"><span data-stu-id="63452-125">(DBPROP_ADC_AUTORECALC)</span></span></p></td>
<td><p><span data-ttu-id="63452-p107">对于使用 Data Shaping Service 创建的记录集，此值指示计算列和聚合列的计算频率。默认值 (1) 表示 Data Shaping Service 每次确定值已更改时都重新进行计算。如果该值为 0，则仅在最初建立层次结构时对计算列或聚合列进行计算。</span><span class="sxs-lookup"><span data-stu-id="63452-p107">For recordsets created with the Data Shaping Service, this value indicates how often calculated and aggregate columns are calculated. The default (value=1) is to recalculate whenever the Data Shaping Service determines that the values have changed. If the value is 0, the calculated or aggregate columns are only calculated when the hierarchy is initially built.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63452-129">Batch Size</span><span class="sxs-lookup"><span data-stu-id="63452-129">Batch Size</span></span><br />
<span data-ttu-id="63452-130">(DBPROP_ADC_BATCHSIZE)</span><span class="sxs-lookup"><span data-stu-id="63452-130">(DBPROP_ADC_BATCHSIZE)</span></span></p></td>
<td><p><span data-ttu-id="63452-p108">指示在发送到数据存储区之前可以进行批处理的更新语句的数量。批中的语句越多，往返数据存储区的次数就越少。</span><span class="sxs-lookup"><span data-stu-id="63452-p108">Indicates the number of update statements that can be batched before being sent to the data store. The more statements in a batch, the fewer round trips to the data store.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63452-133">Cache Child Rows</span><span class="sxs-lookup"><span data-stu-id="63452-133">Cache Child Rows</span></span><br />
<span data-ttu-id="63452-134">(DBPROP_ADC_CACHECHILDROWS)</span><span class="sxs-lookup"><span data-stu-id="63452-134">(DBPROP_ADC_CACHECHILDROWS)</span></span></p></td>
<td><p><span data-ttu-id="63452-135">对于使用 Data Shaping Service 创建的记录集，此值指示是否将子记录集存储在缓存中以供以后使用。</span><span class="sxs-lookup"><span data-stu-id="63452-135">For recordsets created with the Data Shaping Service, this value indicates whether child recordsets are stored in a cache for later use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63452-136">Cursor Engine Version</span><span class="sxs-lookup"><span data-stu-id="63452-136">Cursor Engine Version</span></span><br />
<span data-ttu-id="63452-137">(DBPROP_ADC_CEVER)</span><span class="sxs-lookup"><span data-stu-id="63452-137">(DBPROP_ADC_CEVER)</span></span></p></td>
<td><p><span data-ttu-id="63452-138">指示正在使用的 Cursor Service 的版本。</span><span class="sxs-lookup"><span data-stu-id="63452-138">Indicates the version of the Cursor Service being used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63452-139">Maintain Change Status</span><span class="sxs-lookup"><span data-stu-id="63452-139">Maintain Change Status</span></span><br />
<span data-ttu-id="63452-140">(DBPROP_ADC_MAINTAINCHANGESTATUS)</span><span class="sxs-lookup"><span data-stu-id="63452-140">(DBPROP_ADC_MAINTAINCHANGESTATUS)</span></span></p></td>
<td><p><span data-ttu-id="63452-141">指示用于重新同步多重表连接中的一行或多行的命令文本。</span><span class="sxs-lookup"><span data-stu-id="63452-141">Indicates the text of the command used for resynchronizing a one or more rows in a multiple table join.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63452-142"><a href="optimize-property-dynamic-ado.md">优化</a></span><span class="sxs-lookup"><span data-stu-id="63452-142"><a href="optimize-property-dynamic-ado.md">Optimize</a></span></span></p></td>
<td><p><span data-ttu-id="63452-p109">指示是否应该创建索引。当设置为 <strong>True</strong> 时，表示允许创建临时索引，以提高特定操作的执行性能。</span><span class="sxs-lookup"><span data-stu-id="63452-p109">Indicates whether an index should be created. When set to <strong>True</strong>, authorizes the temporary creation of indexes to improve the execution of certain operations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63452-145"><a href="reshape-name-property-dynamic-ado.md">Reshape Name</a></span><span class="sxs-lookup"><span data-stu-id="63452-145"><a href="reshape-name-property-dynamic-ado.md">Reshape Name</a></span></span></p></td>
<td><p><span data-ttu-id="63452-p110">指示 <strong>Recordset</strong> 的名称。可以在当前 Data Shaping 命令或后续的 Data Shaping 命令中引用该属性。</span><span class="sxs-lookup"><span data-stu-id="63452-p110">Indicates the name of the <strong>Recordset</strong>. May be referenced within the current, or subsequent, data shaping commands.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63452-148"><a href="resync-command-property-dynamic-ado.md">Resync Command</a></span><span class="sxs-lookup"><span data-stu-id="63452-148"><a href="resync-command-property-dynamic-ado.md">Resync Command</a></span></span></p></td>
<td><p><span data-ttu-id="63452-149">指示 <a href="unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md">Unique Table</a> 属性生效时 <a href="resync-method-ado.md">Resync</a> 方法所使用的自定义命令字符串。</span><span class="sxs-lookup"><span data-stu-id="63452-149">Indicates a custom command string that is used by the <a href="resync-method-ado.md">Resync</a> method when the <a href="unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md">Unique Table</a> property is in effect.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63452-150"><a href="unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md">Unique Catalog</a></span><span class="sxs-lookup"><span data-stu-id="63452-150"><a href="unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md">Unique Catalog</a></span></span></p></td>
<td><p><span data-ttu-id="63452-151">指示包含 <strong>Unique Table</strong> 属性中引用的表的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="63452-151">Indicates the name of the database containing the table referenced in the <strong>Unique Table</strong> property.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63452-152"><a href="unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md">Unique Schema</a></span><span class="sxs-lookup"><span data-stu-id="63452-152"><a href="unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md">Unique Schema</a></span></span></p></td>
<td><p><span data-ttu-id="63452-153">指示 <strong>Unique Table</strong> 属性中引用的表的所有者的名称。</span><span class="sxs-lookup"><span data-stu-id="63452-153">Indicates the name of the owner of the table referenced in the <strong>Unique Table</strong> property.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63452-154"><a href="unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md">Unique Table</a></span><span class="sxs-lookup"><span data-stu-id="63452-154"><a href="unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md">Unique Table</a></span></span></p></td>
<td><p><span data-ttu-id="63452-155">指示通过多个表创建的 <strong>Recordset</strong> 中的一个表的名称，该表可以通过插入、更新或删除操作来修改。</span><span class="sxs-lookup"><span data-stu-id="63452-155">Indicates the name of the one table in a <strong>Recordset</strong> created from multiple tables that may be modified by insertions, updates, or deletions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63452-156">Update Criteria</span><span class="sxs-lookup"><span data-stu-id="63452-156">Update Criteria</span></span><br />
<span data-ttu-id="63452-157">(DBPROP_ADC_UPDATECRITERIA)</span><span class="sxs-lookup"><span data-stu-id="63452-157">(DBPROP_ADC_UPDATECRITERIA)</span></span></p></td>
<td><p><span data-ttu-id="63452-158">指示使用 <strong>WHERE</strong> 子句中的哪些字段来处理更新期间发生的冲突。</span><span class="sxs-lookup"><span data-stu-id="63452-158">Indicates which fields in the <strong>WHERE</strong> clause are used to handle collisions occurring during an update.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63452-159"><a href="update-resync-property-dynamic-ado.md">Update Resync</a>(DBPROP_ADC_UPDATERESYNC)</span><span class="sxs-lookup"><span data-stu-id="63452-159"><a href="update-resync-property-dynamic-ado.md">Update Resync</a>(DBPROP_ADC_UPDATERESYNC)</span></span></p></td>
<td><p><span data-ttu-id="63452-160">指示 <strong>Unique Table</strong> 属性生效时，在调用 <a href="updatebatch-method-ado.md">UpdateBatch</a> 方法（及其行为）后是否要隐式调用 <strong>Resync</strong> 方法。</span><span class="sxs-lookup"><span data-stu-id="63452-160">Indicates whether the <strong>Resync</strong> method is implicitly invoked after the <a href="updatebatch-method-ado.md">UpdateBatch</a> method (and its behavior), when the <strong>Unique Table</strong> property is in effect.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="63452-p111">此外，通过将动态属性的名称指定为 **Properties** 集合的索引，您还可以对动态属性进行设置或检索。例如，可以像下面这样，获取并输出 [Optimize](optimize-property-dynamic-ado.md) 动态属性的当前值，然后设置一个新值：</span><span class="sxs-lookup"><span data-stu-id="63452-p111">You may also set or retrieve a dynamic property by specifying its name as the index to the **Properties** collection. For example, get and print the current value of the [Optimize](optimize-property-dynamic-ado.md) dynamic property, then set a new value, like this:</span></span>

```vb 
 
Debug.Print rs.Properties("Optimize") 
rs.Properties("Optimize") = True 
```

## <a name="built-in-property-behavior"></a><span data-ttu-id="63452-163">内置属性行为</span><span class="sxs-lookup"><span data-stu-id="63452-163">Built-in Property Behavior</span></span>

<span data-ttu-id="63452-164">Cursor Service for OLE DB 还会影响某些内置属性的行为。</span><span class="sxs-lookup"><span data-stu-id="63452-164">The Cursor Service for OLE DB also affects the behavior of certain built-in properties.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="63452-165">属性名称</span><span class="sxs-lookup"><span data-stu-id="63452-165">Property Name</span></span></p></th>
<th><p><span data-ttu-id="63452-166">说明</span><span class="sxs-lookup"><span data-stu-id="63452-166">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63452-167"><a href="cursortype-property-ado.md">CursorType</a></span><span class="sxs-lookup"><span data-stu-id="63452-167"><a href="cursortype-property-ado.md">CursorType</a></span></span></p></td>
<td><p><span data-ttu-id="63452-168">补充可用于 <strong>Recordset</strong> 的游标类型。</span><span class="sxs-lookup"><span data-stu-id="63452-168">Supplements the types of cursors that are available for a <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63452-169"><a href="locktype-property-ado.md">LockType</a></span><span class="sxs-lookup"><span data-stu-id="63452-169"><a href="locktype-property-ado.md">LockType</a></span></span></p></td>
<td><p><span data-ttu-id="63452-p112">补充可用于 <strong>Recordset</strong> 的锁定类型。可启用批更新。</span><span class="sxs-lookup"><span data-stu-id="63452-p112">Supplements the types of locks available for a <strong>Recordset</strong>. Enables batch updates.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63452-172"><a href="sort-property-ado.md">Sort</a></span><span class="sxs-lookup"><span data-stu-id="63452-172"><a href="sort-property-ado.md">Sort</a></span></span></p></td>
<td><p><span data-ttu-id="63452-173">指定 <strong>Recordset</strong> 排序所依据的一个或多个字段名称，以及按升序还是降序排列每个字段。</span><span class="sxs-lookup"><span data-stu-id="63452-173">Specifies one or more field names that the <strong>Recordset</strong> is sorted on, and whether each field is sorted in ascending or descending order.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="method-behavior"></a><span data-ttu-id="63452-174">方法行为</span><span class="sxs-lookup"><span data-stu-id="63452-174">Method Behavior</span></span>

<span data-ttu-id="63452-175">Cursor Service for OLE DB 可启用或影响 [Field](field-object-ado.md) 对象的 [Append](append-method-ado.md) 方法，以及 **Recordset** 对象的 [Open](open-method-ado-recordset.md)、[Resync](resync-method-ado.md)、[UpdateBatch](updatebatch-method-ado.md) 和 [Save](save-method-ado.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="63452-175">The Cursor Service for OLE DB enables or affects the behavior of the [Field](field-object-ado.md) object's [Append](append-method-ado.md) method; and the **Recordset** object's [Open](open-method-ado-recordset.md), [Resync](resync-method-ado.md), [UpdateBatch](updatebatch-method-ado.md), and [Save](save-method-ado.md) methods.</span></span>

