---
title: Microsoft OLE DB Provider for Microsoft Indexing Service
TOCTitle: Microsoft OLE DB Provider for Microsoft Indexing Service
ms:assetid: 01c2e75c-950a-dd8a-2b20-bbd916315ec5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248786(v=office.15)
ms:contentKeyID: 48542942
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 10af40231fc10e222f818896b3d65f44ac3d6d71
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466779"
---
# <a name="microsoft-ole-db-provider-for-microsoft-indexing-service"></a><span data-ttu-id="f6d21-102">Microsoft OLE DB Provider for Microsoft Indexing Service</span><span class="sxs-lookup"><span data-stu-id="f6d21-102">Microsoft OLE DB Provider for Microsoft Indexing Service</span></span>


<span data-ttu-id="f6d21-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="f6d21-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="f6d21-p101">Microsoft OLE DB Provider for Microsoft Indexing Service 提供了对通过 Microsoft Indexing Service 建立索引的文件系统和 Web 数据的只读编程访问权。ADO 应用程序可以发出 SQL 查询，以检索内容和文件属性信息。</span><span class="sxs-lookup"><span data-stu-id="f6d21-p101">The Microsoft OLE DB Provider for Microsoft Indexing Service provides programmatic read-only access to file system and Web data indexed by Microsoft Indexing Service. ADO applications can issue SQL queries to retrieve content and file property information.</span></span>

<span data-ttu-id="f6d21-106">该提供程序为自由线程且支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="f6d21-106">The provider is free-threaded and unicode enabled.</span></span>

## <a name="connection-string-parameters"></a><span data-ttu-id="f6d21-107">连接字符串参数</span><span class="sxs-lookup"><span data-stu-id="f6d21-107">Connection String Parameters</span></span>

<span data-ttu-id="f6d21-108">若要连接到此提供程序，请将 **ConnectionString** 属性的 [Provider=](connectionstring-property-ado.md) 参数设置为：</span><span class="sxs-lookup"><span data-stu-id="f6d21-108">To connect to this provider, set the **Provider=** argument to the [ConnectionString](connectionstring-property-ado.md) property to:</span></span>

```vb 
 
MSIDXS 
```

<span data-ttu-id="f6d21-109">读取 [Provider](provider-property-ado.md) 属性时，也会返回此字符串。</span><span class="sxs-lookup"><span data-stu-id="f6d21-109">Reading the [Provider](provider-property-ado.md) property will return this string as well.</span></span>

## <a name="typical-connection-string"></a><span data-ttu-id="f6d21-110">典型的连接字符串</span><span class="sxs-lookup"><span data-stu-id="f6d21-110">Typical Connection String</span></span>

<span data-ttu-id="f6d21-111">此提供程序典型的连接字符串为：</span><span class="sxs-lookup"><span data-stu-id="f6d21-111">A typical connection string for this provider is:</span></span>

```vb 
 
"Provider=MSIDXS;Data Source=myCatalog;Locale Identifier=nnnn;" 
```

<span data-ttu-id="f6d21-112">该字符串由以下关键字组成：</span><span class="sxs-lookup"><span data-stu-id="f6d21-112">The string consists of these keywords:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f6d21-113">关键字</span><span class="sxs-lookup"><span data-stu-id="f6d21-113">Keyword</span></span></p></th>
<th><p><span data-ttu-id="f6d21-114">说明</span><span class="sxs-lookup"><span data-stu-id="f6d21-114">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-115"><strong>Provider</strong></span><span class="sxs-lookup"><span data-stu-id="f6d21-115"><strong>Provider</strong></span></span></p></td>
<td><p><span data-ttu-id="f6d21-p102">指定 Microsoft OLE DB Provider for Microsoft Indexing Service。通常，这是在连接字符串中指定的唯一一个关键字。</span><span class="sxs-lookup"><span data-stu-id="f6d21-p102">Specifies the OLE DB Provider for Microsoft Indexing Service. Typically this is the only keyword specified in the connection string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d21-118"><strong>Data Source</strong></span><span class="sxs-lookup"><span data-stu-id="f6d21-118"><strong>Data Source</strong></span></span></p></td>
<td><p><span data-ttu-id="f6d21-p103">指定 Indexing Service 目录名称。如果没有指定此关键字。则将使用默认的系统目录。</span><span class="sxs-lookup"><span data-stu-id="f6d21-p103">Specifies the Indexing Service catalog name. If this keyword is not specified, the default system catalog is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-121"><strong>Locale Identifier</strong></span><span class="sxs-lookup"><span data-stu-id="f6d21-121"><strong>Locale Identifier</strong></span></span></p></td>
<td><p><span data-ttu-id="f6d21-p104">指定唯一的 32 位编号（例如 1033），用于指定与用户的语言相关的首选项。这些首选项指示设置日期和时间格式的方式、按字母顺序对项排序的方式、比较字符串的方式等。如果没有指定此关键字，则将使用默认的系统区域设置标识符。</span><span class="sxs-lookup"><span data-stu-id="f6d21-p104">Specifies a unique 32-bit number (for example, 1033) that specifies preferences related to the user's language. These preferences indicate how dates and times are formatted, items are sorted alphabetically, strings are compared, and so on. If this keyword is not specified, the default system locale identifier is used.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="command-text"></a><span data-ttu-id="f6d21-125">命令文本</span><span class="sxs-lookup"><span data-stu-id="f6d21-125">Command Text</span></span>

<span data-ttu-id="f6d21-p105">Indexing Service SQL 查询语法包含对 SQL-92 **SELECT** 语句及其 **FROM** 和 **WHERE 子句** 的扩展。查询结果通过 OLE DB 行集返回，查询结果可供 ADO 使用并可将其作为 [Recordset](recordset-object-ado.md) 对象进行操作。</span><span class="sxs-lookup"><span data-stu-id="f6d21-p105">The Indexing Service SQL query syntax consists of extensions to the SQL-92 **SELECT** statement and its **FROM** and **WHERE** clauses. The results of the query are returned via OLE DB rowsets, which can be consumed by ADO and manipulated as [Recordset](recordset-object-ado.md) objects.</span></span>

<span data-ttu-id="f6d21-p106">可以搜索实际的单词或短语，也可以使用通配符搜索单词的模式或词干。搜索逻辑可能基于 Boolean 决策、加权的术语或与其他单词的近似程度。您还可以按"自由文本"进行搜索，从而根据意义（而不是实际的单词）来查找匹配项。</span><span class="sxs-lookup"><span data-stu-id="f6d21-p106">You can search for exact words or phrases, or use wildcards to search for patterns or stems of words. The search logic can be based on Boolean decisions, weighted terms, or proximity to other words. You can also search by "free text," which finds matches based on meaning, rather than exact words.</span></span>

<span data-ttu-id="f6d21-131">该提供程序不会接受存储过程调用或简单的表名称（例如，[CommandType](commandtype-property-ado.md) 属性将始终为 **adCmdText**）。</span><span class="sxs-lookup"><span data-stu-id="f6d21-131">The provider does not accept stored procedure calls or simple table names (for example, the [CommandType](commandtype-property-ado.md) property will always be **adCmdText**).</span></span>

## <a name="recordset-behavior"></a><span data-ttu-id="f6d21-132">Recordset 行为</span><span class="sxs-lookup"><span data-stu-id="f6d21-132">Recordset Behavior</span></span>

<span data-ttu-id="f6d21-133">下表列出了使用此提供程序打开的 **Recordset** 对象中可用的功能。</span><span class="sxs-lookup"><span data-stu-id="f6d21-133">The following tables list the features available with a **Recordset** object opened with this provider.</span></span> <span data-ttu-id="f6d21-134">仅静态游标类型 (**为 adOpenStatic**) 才可用。</span><span class="sxs-lookup"><span data-stu-id="f6d21-134">Only the Static cursor type (**adOpenStatic**) is available.</span></span>

<span data-ttu-id="f6d21-135">有关提供程序配置的 **Recordset** 行为的详细信息，请运行 [Supports](supports-method-ado.md) 方法并枚举 [Recordset](properties-collection-ado.md) 的 **Properties** 集合，以确定提供程序特定的动态属性是否存在。</span><span class="sxs-lookup"><span data-stu-id="f6d21-135">For more detailed information about **Recordset** behavior for your provider configuration, run the [Supports](supports-method-ado.md) method and enumerate the [Properties](properties-collection-ado.md) collection of the **Recordset** to determine whether provider-specific dynamic properties are present.</span></span>

<span data-ttu-id="f6d21-136">标准 ADO **Recordset** 属性的可用性：</span><span class="sxs-lookup"><span data-stu-id="f6d21-136">Availability of standard ADO **Recordset** properties:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f6d21-137">属性</span><span class="sxs-lookup"><span data-stu-id="f6d21-137">Property</span></span></p></th>
<th><p><span data-ttu-id="f6d21-138">可用性</span><span class="sxs-lookup"><span data-stu-id="f6d21-138">Availability</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-139"><a href="absolutepage-property-ado.md">AbsolutePage</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-139"><a href="absolutepage-property-ado.md">AbsolutePage</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-140">读/写</span><span class="sxs-lookup"><span data-stu-id="f6d21-140">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d21-141"><a href="absoluteposition-property-ado.md">AbsolutePosition</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-141"><a href="absoluteposition-property-ado.md">AbsolutePosition</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-142">读/写</span><span class="sxs-lookup"><span data-stu-id="f6d21-142">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-143"><a href="activeconnection-property-ado.md">ActiveConnection</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-143"><a href="activeconnection-property-ado.md">ActiveConnection</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-144">只读</span><span class="sxs-lookup"><span data-stu-id="f6d21-144">read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d21-145"><a href="bof-eof-properties-ado.md">BOF</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-145"><a href="bof-eof-properties-ado.md">BOF</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-146">只读</span><span class="sxs-lookup"><span data-stu-id="f6d21-146">read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-147"><a href="bookmark-property-ado.md">书签</a>\*</span><span class="sxs-lookup"><span data-stu-id="f6d21-147"><a href="bookmark-property-ado.md">Bookmark</a>\*</span></span></p></td>
<td><p><span data-ttu-id="f6d21-148">读/写</span><span class="sxs-lookup"><span data-stu-id="f6d21-148">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d21-149"><a href="cachesize-property-ado.md">CacheSize</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-149"><a href="cachesize-property-ado.md">CacheSize</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-150">读/写</span><span class="sxs-lookup"><span data-stu-id="f6d21-150">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-151"><a href="cursorlocation-property-ado.md">CursorLocation</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-151"><a href="cursorlocation-property-ado.md">CursorLocation</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-152">始终为 <strong>adUseServer</strong></span><span class="sxs-lookup"><span data-stu-id="f6d21-152">always <strong>adUseServer</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d21-153"><a href="cursortype-property-ado.md">CursorType</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-153"><a href="cursortype-property-ado.md">CursorType</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-154">始终为 <strong>adOpenStatic</strong></span><span class="sxs-lookup"><span data-stu-id="f6d21-154">always <strong>adOpenStatic</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-155"><a href="editmode-property-ado.md">EditMode</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-155"><a href="editmode-property-ado.md">EditMode</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-156">始终为 <strong>adEditNone</strong></span><span class="sxs-lookup"><span data-stu-id="f6d21-156">always <strong>adEditNone</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d21-157"><a href="bof-eof-properties-ado.md">EOF</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-157"><a href="bof-eof-properties-ado.md">EOF</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-158">只读</span><span class="sxs-lookup"><span data-stu-id="f6d21-158">read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-159"><a href="filter-property-ado.md">Filter</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-159"><a href="filter-property-ado.md">Filter</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-160">读/写</span><span class="sxs-lookup"><span data-stu-id="f6d21-160">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d21-161"><a href="locktype-property-ado.md">LockType</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-161"><a href="locktype-property-ado.md">LockType</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-162">读/写</span><span class="sxs-lookup"><span data-stu-id="f6d21-162">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-163"><a href="marshaloptions-property-ado.md">MarshalOptions</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-163"><a href="marshaloptions-property-ado.md">MarshalOptions</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-164">暂无</span><span class="sxs-lookup"><span data-stu-id="f6d21-164">not available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d21-165"><a href="maxrecords-property-ado.md">MaxRecords</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-165"><a href="maxrecords-property-ado.md">MaxRecords</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-166">读/写</span><span class="sxs-lookup"><span data-stu-id="f6d21-166">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-167"><a href="pagecount-property-ado.md">PageCount</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-167"><a href="pagecount-property-ado.md">PageCount</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-168">只读</span><span class="sxs-lookup"><span data-stu-id="f6d21-168">read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d21-169"><a href="pagesize-property-ado.md">PageSize</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-169"><a href="pagesize-property-ado.md">PageSize</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-170">读/写</span><span class="sxs-lookup"><span data-stu-id="f6d21-170">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-171"><a href="recordcount-property-ado.md">RecordCount</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-171"><a href="recordcount-property-ado.md">RecordCount</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-172">只读</span><span class="sxs-lookup"><span data-stu-id="f6d21-172">read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d21-173"><a href="source-property-ado-recordset.md">Source</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-173"><a href="source-property-ado-recordset.md">Source</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-174">读/写</span><span class="sxs-lookup"><span data-stu-id="f6d21-174">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-175"><a href="state-property-ado.md">State</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-175"><a href="state-property-ado.md">State</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-176">只读</span><span class="sxs-lookup"><span data-stu-id="f6d21-176">read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d21-177"><a href="status-property-ado-recordset.md">Status</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-177"><a href="status-property-ado-recordset.md">Status</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-178">只读</span><span class="sxs-lookup"><span data-stu-id="f6d21-178">read-only</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f6d21-179">\*必须在此功能的顺序提供程序，以在**Recordset**上启用书签。</span><span class="sxs-lookup"><span data-stu-id="f6d21-179">\*Bookmarks must be enabled on the provider in order for this feature to exist on the **Recordset**.</span></span>

<span data-ttu-id="f6d21-180">标准 ADO **Recordset** 方法的可用性：</span><span class="sxs-lookup"><span data-stu-id="f6d21-180">Availability of standard ADO **Recordset** methods:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f6d21-181">方法</span><span class="sxs-lookup"><span data-stu-id="f6d21-181">Method</span></span></p></th>
<th><p><span data-ttu-id="f6d21-182">是否可用</span><span class="sxs-lookup"><span data-stu-id="f6d21-182">Available?</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-183"><a href="addnew-method-ado.md">AddNew</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-183"><a href="addnew-method-ado.md">AddNew</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-184">否</span><span class="sxs-lookup"><span data-stu-id="f6d21-184">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d21-185"><a href="cancel-method-ado.md">Cancel</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-185"><a href="cancel-method-ado.md">Cancel</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-186">是</span><span class="sxs-lookup"><span data-stu-id="f6d21-186">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-187"><a href="cancelbatch-method-ado.md">CancelBatch</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-187"><a href="cancelbatch-method-ado.md">CancelBatch</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-188">否</span><span class="sxs-lookup"><span data-stu-id="f6d21-188">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d21-189"><a href="cancelupdate-method-ado.md">CancelUpdate</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-189"><a href="cancelupdate-method-ado.md">CancelUpdate</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-190">否</span><span class="sxs-lookup"><span data-stu-id="f6d21-190">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-191"><a href="clone-method-ado.md">Clone</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-191"><a href="clone-method-ado.md">Clone</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-192">是</span><span class="sxs-lookup"><span data-stu-id="f6d21-192">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d21-193"><a href="close-method-ado.md">Close</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-193"><a href="close-method-ado.md">Close</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-194">是</span><span class="sxs-lookup"><span data-stu-id="f6d21-194">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-195"><a href="delete-method-ado-recordset.md">Delete</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-195"><a href="delete-method-ado-recordset.md">Delete</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-196">否</span><span class="sxs-lookup"><span data-stu-id="f6d21-196">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d21-197"><a href="getrows-method-ado.md">GetRows</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-197"><a href="getrows-method-ado.md">GetRows</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-198">是</span><span class="sxs-lookup"><span data-stu-id="f6d21-198">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-199"><a href="move-method-ado.md">移动</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-199"><a href="move-method-ado.md">Move</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-200">是</span><span class="sxs-lookup"><span data-stu-id="f6d21-200">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d21-201"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-201"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-202">是</span><span class="sxs-lookup"><span data-stu-id="f6d21-202">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-203"><a href="nextrecordset-method-ado.md">NextRecordset</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-203"><a href="nextrecordset-method-ado.md">NextRecordset</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-204">是</span><span class="sxs-lookup"><span data-stu-id="f6d21-204">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d21-205"><a href="open-method-ado-recordset.md">Open</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-205"><a href="open-method-ado-recordset.md">Open</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-206">是</span><span class="sxs-lookup"><span data-stu-id="f6d21-206">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-207"><a href="requery-method-ado.md">Requery</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-207"><a href="requery-method-ado.md">Requery</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-208">是</span><span class="sxs-lookup"><span data-stu-id="f6d21-208">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d21-209"><a href="resync-method-ado.md">Resync</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-209"><a href="resync-method-ado.md">Resync</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-210">是</span><span class="sxs-lookup"><span data-stu-id="f6d21-210">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-211"><a href="supports-method-ado.md">支持</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-211"><a href="supports-method-ado.md">Supports</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-212">是</span><span class="sxs-lookup"><span data-stu-id="f6d21-212">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d21-213"><a href="update-method-ado.md">更新</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-213"><a href="update-method-ado.md">Update</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-214">否</span><span class="sxs-lookup"><span data-stu-id="f6d21-214">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6d21-215"><a href="updatebatch-method-ado.md">UpdateBatch</a></span><span class="sxs-lookup"><span data-stu-id="f6d21-215"><a href="updatebatch-method-ado.md">UpdateBatch</a></span></span></p></td>
<td><p><span data-ttu-id="f6d21-216">否</span><span class="sxs-lookup"><span data-stu-id="f6d21-216">No</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="f6d21-217">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6d21-217">See also</span></span>

<span data-ttu-id="f6d21-218">有关具体的实现详细信息和有关 Microsoft OLE DB Provider for Microsoft Indexing Service 的功能信息，请参阅 Microsoft OLE DB 程序员参考。</span><span class="sxs-lookup"><span data-stu-id="f6d21-218">For specific implementation details and functional information about the Microsoft OLE DB Provider for Microsoft Indexing Service, consult the Microsoft OLE DB Programmer's Reference.</span></span>
