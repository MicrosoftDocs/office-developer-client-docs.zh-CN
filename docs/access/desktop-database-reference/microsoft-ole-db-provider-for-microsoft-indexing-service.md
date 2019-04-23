---
title: Microsoft OLE DB Provider for Microsoft Indexing Service
TOCTitle: Microsoft OLE DB Provider for Microsoft Indexing Service
ms:assetid: 01c2e75c-950a-dd8a-2b20-bbd916315ec5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248786(v=office.15)
ms:contentKeyID: 48542942
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ba27bfdf6cc1317b441e626c61784e2c50b589f1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288916"
---
# <a name="microsoft-ole-db-provider-for-microsoft-indexing-service"></a><span data-ttu-id="0a815-102">用于 Microsoft 索引服务的 Microsoft OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="0a815-102">Microsoft OLE DB Provider for Microsoft Indexing Service</span></span>


<span data-ttu-id="0a815-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="0a815-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0a815-104">microsoft OLE DB Provider for microsoft 索引服务提供以编程方式对由 Microsoft 索引服务编制索引的文件系统和 web 数据的只读访问。</span><span class="sxs-lookup"><span data-stu-id="0a815-104">The Microsoft OLE DB Provider for Microsoft Indexing Service provides programmatic read-only access to file system and web data indexed by Microsoft Indexing Service.</span></span> <span data-ttu-id="0a815-105">ADO 应用程序可以发出 SQL 查询，以检索内容和文件属性信息。</span><span class="sxs-lookup"><span data-stu-id="0a815-105">ADO applications can issue SQL queries to retrieve content and file property information.</span></span>

<span data-ttu-id="0a815-106">该提供程序为自由线程且支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="0a815-106">The provider is free-threaded and unicode enabled.</span></span>

## <a name="connection-string-parameters"></a><span data-ttu-id="0a815-107">连接字符串参数</span><span class="sxs-lookup"><span data-stu-id="0a815-107">Connection String Parameters</span></span>

<span data-ttu-id="0a815-108">若要连接到此提供程序，请将 [ConnectionString](connectionstring-property-ado.md) 属性的 **Provider=** 参数设置为：</span><span class="sxs-lookup"><span data-stu-id="0a815-108">To connect to this provider, set the **Provider=** argument to the [ConnectionString](connectionstring-property-ado.md) property to:</span></span>

```vb 
 
MSIDXS 
```

<span data-ttu-id="0a815-109">读取 [Provider](provider-property-ado.md) 属性时，也会返回此字符串。</span><span class="sxs-lookup"><span data-stu-id="0a815-109">Reading the [Provider](provider-property-ado.md) property will return this string as well.</span></span>

## <a name="typical-connection-string"></a><span data-ttu-id="0a815-110">典型的连接字符串</span><span class="sxs-lookup"><span data-stu-id="0a815-110">Typical Connection String</span></span>

<span data-ttu-id="0a815-111">此提供程序典型的连接字符串为：</span><span class="sxs-lookup"><span data-stu-id="0a815-111">A typical connection string for this provider is:</span></span>

```vb 
 
"Provider=MSIDXS;Data Source=myCatalog;Locale Identifier=nnnn;" 
```

<span data-ttu-id="0a815-112">该字符串由以下关键字组成：</span><span class="sxs-lookup"><span data-stu-id="0a815-112">The string consists of these keywords:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0a815-113">关键字</span><span class="sxs-lookup"><span data-stu-id="0a815-113">Keyword</span></span></p></th>
<th><p><span data-ttu-id="0a815-114">说明</span><span class="sxs-lookup"><span data-stu-id="0a815-114">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a815-115"><strong>Provider</strong></span><span class="sxs-lookup"><span data-stu-id="0a815-115"><strong>Provider</strong></span></span></p></td>
<td><p><span data-ttu-id="0a815-116">指定 Microsoft OLE DB Provider for Microsoft Indexing Service。</span><span class="sxs-lookup"><span data-stu-id="0a815-116">Specifies the OLE DB Provider for Microsoft Indexing Service.</span></span> <span data-ttu-id="0a815-117">通常，这是在连接字符串中指定的唯一一个关键字。</span><span class="sxs-lookup"><span data-stu-id="0a815-117">Typically this is the only keyword specified in the connection string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a815-118"><strong>Data Source</strong></span><span class="sxs-lookup"><span data-stu-id="0a815-118"><strong>Data Source</strong></span></span></p></td>
<td><p><span data-ttu-id="0a815-p103">指定 Indexing Service 目录名称。如果没有指定此关键字。则将使用默认的系统目录。</span><span class="sxs-lookup"><span data-stu-id="0a815-p103">Specifies the Indexing Service catalog name. If this keyword is not specified, the default system catalog is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a815-121"><strong>Locale Identifier</strong></span><span class="sxs-lookup"><span data-stu-id="0a815-121"><strong>Locale Identifier</strong></span></span></p></td>
<td><p><span data-ttu-id="0a815-p104">指定唯一的 32 位编号（例如 1033），用于指定与用户的语言相关的首选项。这些首选项指示设置日期和时间格式的方式、按字母顺序对项排序的方式、比较字符串的方式等。如果没有指定此关键字，则将使用默认的系统区域设置标识符。</span><span class="sxs-lookup"><span data-stu-id="0a815-p104">Specifies a unique 32-bit number (for example, 1033) that specifies preferences related to the user's language. These preferences indicate how dates and times are formatted, items are sorted alphabetically, strings are compared, and so on. If this keyword is not specified, the default system locale identifier is used.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="command-text"></a><span data-ttu-id="0a815-125">命令文本</span><span class="sxs-lookup"><span data-stu-id="0a815-125">Command Text</span></span>

<span data-ttu-id="0a815-p105">Indexing Service SQL 查询语法包含对 SQL-92 **SELECT** 语句及其 **FROM** 和 **WHERE 子句** 的扩展。查询结果通过 OLE DB 行集返回，查询结果可供 ADO 使用并可将其作为 [Recordset](recordset-object-ado.md) 对象进行操作。</span><span class="sxs-lookup"><span data-stu-id="0a815-p105">The Indexing Service SQL query syntax consists of extensions to the SQL-92 **SELECT** statement and its **FROM** and **WHERE** clauses. The results of the query are returned via OLE DB rowsets, which can be consumed by ADO and manipulated as [Recordset](recordset-object-ado.md) objects.</span></span>

<span data-ttu-id="0a815-p106">可以搜索实际的单词或短语，也可以使用通配符搜索单词的模式或词干。搜索逻辑可能基于 Boolean 决策、加权的术语或与其他单词的近似程度。您还可以按"自由文本"进行搜索，从而根据意义（而不是实际的单词）来查找匹配项。</span><span class="sxs-lookup"><span data-stu-id="0a815-p106">You can search for exact words or phrases, or use wildcards to search for patterns or stems of words. The search logic can be based on Boolean decisions, weighted terms, or proximity to other words. You can also search by "free text," which finds matches based on meaning, rather than exact words.</span></span>

<span data-ttu-id="0a815-131">该提供程序不会接受存储过程调用或简单的表名称（例如，[CommandType](commandtype-property-ado.md) 属性将始终为 **adCmdText**）。</span><span class="sxs-lookup"><span data-stu-id="0a815-131">The provider does not accept stored procedure calls or simple table names (for example, the [CommandType](commandtype-property-ado.md) property will always be **adCmdText**).</span></span>

## <a name="recordset-behavior"></a><span data-ttu-id="0a815-132">Recordset 行为</span><span class="sxs-lookup"><span data-stu-id="0a815-132">Recordset Behavior</span></span>

<span data-ttu-id="0a815-133">下表列出了使用此提供程序打开的 **Recordset** 对象中可用的功能。</span><span class="sxs-lookup"><span data-stu-id="0a815-133">The following tables list the features available with a **Recordset** object opened with this provider.</span></span> <span data-ttu-id="0a815-134">仅静态游标类型 (**adOpenStatic**) 可用。</span><span class="sxs-lookup"><span data-stu-id="0a815-134">Only the Static cursor type (**adOpenStatic**) is available.</span></span>

<span data-ttu-id="0a815-135">有关提供程序配置的 **Recordset** 行为的详细信息，请运行 [Supports](supports-method-ado.md) 方法并枚举 [Recordset](properties-collection-ado.md) 的 **Properties** 集合，以确定提供程序特定的动态属性是否存在。</span><span class="sxs-lookup"><span data-stu-id="0a815-135">For more detailed information about **Recordset** behavior for your provider configuration, run the [Supports](supports-method-ado.md) method and enumerate the [Properties](properties-collection-ado.md) collection of the **Recordset** to determine whether provider-specific dynamic properties are present.</span></span>

<span data-ttu-id="0a815-136">标准 ADO **Recordset** 属性的可用性：</span><span class="sxs-lookup"><span data-stu-id="0a815-136">Availability of standard ADO **Recordset** properties:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0a815-137">属性</span><span class="sxs-lookup"><span data-stu-id="0a815-137">Property</span></span></p></th>
<th><p><span data-ttu-id="0a815-138">供应情况</span><span class="sxs-lookup"><span data-stu-id="0a815-138">Availability</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a815-139"><a href="absolutepage-property-ado.md">AbsolutePage</a></span><span class="sxs-lookup"><span data-stu-id="0a815-139"><a href="absolutepage-property-ado.md">AbsolutePage</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-140">读/写</span><span class="sxs-lookup"><span data-stu-id="0a815-140">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a815-141"><a href="absoluteposition-property-ado.md">AbsolutePosition</a></span><span class="sxs-lookup"><span data-stu-id="0a815-141"><a href="absoluteposition-property-ado.md">AbsolutePosition</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-142">读/写</span><span class="sxs-lookup"><span data-stu-id="0a815-142">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a815-143"><a href="activeconnection-property-ado.md">ActiveConnection</a></span><span class="sxs-lookup"><span data-stu-id="0a815-143"><a href="activeconnection-property-ado.md">ActiveConnection</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-144">只读</span><span class="sxs-lookup"><span data-stu-id="0a815-144">read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a815-145"><a href="bof-eof-properties-ado.md">BOF</a></span><span class="sxs-lookup"><span data-stu-id="0a815-145"><a href="bof-eof-properties-ado.md">BOF</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-146">只读</span><span class="sxs-lookup"><span data-stu-id="0a815-146">read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a815-147"><a href="bookmark-property-ado.md">书签</a>\*</span><span class="sxs-lookup"><span data-stu-id="0a815-147"><a href="bookmark-property-ado.md">Bookmark</a>\*</span></span></p></td>
<td><p><span data-ttu-id="0a815-148">读/写</span><span class="sxs-lookup"><span data-stu-id="0a815-148">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a815-149"><a href="cachesize-property-ado.md">CacheSize</a></span><span class="sxs-lookup"><span data-stu-id="0a815-149"><a href="cachesize-property-ado.md">CacheSize</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-150">读/写</span><span class="sxs-lookup"><span data-stu-id="0a815-150">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a815-151"><a href="cursorlocation-property-ado.md">CursorLocation</a></span><span class="sxs-lookup"><span data-stu-id="0a815-151"><a href="cursorlocation-property-ado.md">CursorLocation</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-152">始终为 <strong>adUseServer</strong></span><span class="sxs-lookup"><span data-stu-id="0a815-152">always <strong>adUseServer</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a815-153"><a href="cursortype-property-ado.md">CursorType</a></span><span class="sxs-lookup"><span data-stu-id="0a815-153"><a href="cursortype-property-ado.md">CursorType</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-154">始终为 <strong>adOpenStatic</strong></span><span class="sxs-lookup"><span data-stu-id="0a815-154">always <strong>adOpenStatic</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a815-155"><a href="editmode-property-ado.md">EditMode</a></span><span class="sxs-lookup"><span data-stu-id="0a815-155"><a href="editmode-property-ado.md">EditMode</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-156">始终为 <strong>adEditNone</strong></span><span class="sxs-lookup"><span data-stu-id="0a815-156">always <strong>adEditNone</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a815-157"><a href="bof-eof-properties-ado.md">EOF</a></span><span class="sxs-lookup"><span data-stu-id="0a815-157"><a href="bof-eof-properties-ado.md">EOF</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-158">只读</span><span class="sxs-lookup"><span data-stu-id="0a815-158">read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a815-159"><a href="filter-property-ado.md">Filter</a></span><span class="sxs-lookup"><span data-stu-id="0a815-159"><a href="filter-property-ado.md">Filter</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-160">读/写</span><span class="sxs-lookup"><span data-stu-id="0a815-160">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a815-161"><a href="locktype-property-ado.md">LockType</a></span><span class="sxs-lookup"><span data-stu-id="0a815-161"><a href="locktype-property-ado.md">LockType</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-162">读/写</span><span class="sxs-lookup"><span data-stu-id="0a815-162">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a815-163"><a href="marshaloptions-property-ado.md">MarshalOptions</a></span><span class="sxs-lookup"><span data-stu-id="0a815-163"><a href="marshaloptions-property-ado.md">MarshalOptions</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-164">不可用</span><span class="sxs-lookup"><span data-stu-id="0a815-164">not available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a815-165"><a href="maxrecords-property-ado.md">MaxRecords</a></span><span class="sxs-lookup"><span data-stu-id="0a815-165"><a href="maxrecords-property-ado.md">MaxRecords</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-166">读/写</span><span class="sxs-lookup"><span data-stu-id="0a815-166">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a815-167"><a href="pagecount-property-ado.md">PageCount</a></span><span class="sxs-lookup"><span data-stu-id="0a815-167"><a href="pagecount-property-ado.md">PageCount</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-168">只读</span><span class="sxs-lookup"><span data-stu-id="0a815-168">read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a815-169"><a href="pagesize-property-ado.md">PageSize</a></span><span class="sxs-lookup"><span data-stu-id="0a815-169"><a href="pagesize-property-ado.md">PageSize</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-170">读/写</span><span class="sxs-lookup"><span data-stu-id="0a815-170">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a815-171"><a href="recordcount-property-ado.md">RecordCount</a></span><span class="sxs-lookup"><span data-stu-id="0a815-171"><a href="recordcount-property-ado.md">RecordCount</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-172">只读</span><span class="sxs-lookup"><span data-stu-id="0a815-172">read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a815-173"><a href="source-property-ado-recordset.md">Source</a></span><span class="sxs-lookup"><span data-stu-id="0a815-173"><a href="source-property-ado-recordset.md">Source</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-174">读/写</span><span class="sxs-lookup"><span data-stu-id="0a815-174">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a815-175"><a href="state-property-ado.md">State</a></span><span class="sxs-lookup"><span data-stu-id="0a815-175"><a href="state-property-ado.md">State</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-176">只读</span><span class="sxs-lookup"><span data-stu-id="0a815-176">read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a815-177"><a href="status-property-ado-recordset.md">Status</a></span><span class="sxs-lookup"><span data-stu-id="0a815-177"><a href="status-property-ado-recordset.md">Status</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-178">只读</span><span class="sxs-lookup"><span data-stu-id="0a815-178">read-only</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0a815-179">\*必须在提供程序上启用书签, 此功能才存在于**Recordset**中。</span><span class="sxs-lookup"><span data-stu-id="0a815-179">\*Bookmarks must be enabled on the provider in order for this feature to exist on the **Recordset**.</span></span>

<span data-ttu-id="0a815-180">标准 ADO **Recordset** 方法的可用性：</span><span class="sxs-lookup"><span data-stu-id="0a815-180">Availability of standard ADO **Recordset** methods:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0a815-181">方法</span><span class="sxs-lookup"><span data-stu-id="0a815-181">Method</span></span></p></th>
<th><p><span data-ttu-id="0a815-182">可用?</span><span class="sxs-lookup"><span data-stu-id="0a815-182">Available?</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a815-183"><a href="addnew-method-ado.md">AddNew</a></span><span class="sxs-lookup"><span data-stu-id="0a815-183"><a href="addnew-method-ado.md">AddNew</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-184">否</span><span class="sxs-lookup"><span data-stu-id="0a815-184">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a815-185"><a href="cancel-method-ado.md">Cancel</a></span><span class="sxs-lookup"><span data-stu-id="0a815-185"><a href="cancel-method-ado.md">Cancel</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-186">是</span><span class="sxs-lookup"><span data-stu-id="0a815-186">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a815-187"><a href="cancelbatch-method-ado.md">CancelBatch</a></span><span class="sxs-lookup"><span data-stu-id="0a815-187"><a href="cancelbatch-method-ado.md">CancelBatch</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-188">否</span><span class="sxs-lookup"><span data-stu-id="0a815-188">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a815-189"><a href="cancelupdate-method-ado.md">CancelUpdate</a></span><span class="sxs-lookup"><span data-stu-id="0a815-189"><a href="cancelupdate-method-ado.md">CancelUpdate</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-190">否</span><span class="sxs-lookup"><span data-stu-id="0a815-190">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a815-191"><a href="clone-method-ado.md">Clone</a></span><span class="sxs-lookup"><span data-stu-id="0a815-191"><a href="clone-method-ado.md">Clone</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-192">是</span><span class="sxs-lookup"><span data-stu-id="0a815-192">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a815-193"><a href="close-method-ado.md">Close</a></span><span class="sxs-lookup"><span data-stu-id="0a815-193"><a href="close-method-ado.md">Close</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-194">是</span><span class="sxs-lookup"><span data-stu-id="0a815-194">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a815-195"><a href="delete-method-ado-recordset.md">删除</a></span><span class="sxs-lookup"><span data-stu-id="0a815-195"><a href="delete-method-ado-recordset.md">Delete</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-196">否</span><span class="sxs-lookup"><span data-stu-id="0a815-196">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a815-197"><a href="getrows-method-ado.md">GetRows</a></span><span class="sxs-lookup"><span data-stu-id="0a815-197"><a href="getrows-method-ado.md">GetRows</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-198">是</span><span class="sxs-lookup"><span data-stu-id="0a815-198">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a815-199"><a href="move-method-ado.md">Move</a></span><span class="sxs-lookup"><span data-stu-id="0a815-199"><a href="move-method-ado.md">Move</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-200">是</span><span class="sxs-lookup"><span data-stu-id="0a815-200">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a815-201"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst</a></span><span class="sxs-lookup"><span data-stu-id="0a815-201"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-202">是</span><span class="sxs-lookup"><span data-stu-id="0a815-202">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a815-203"><a href="nextrecordset-method-ado.md">NextRecordset</a></span><span class="sxs-lookup"><span data-stu-id="0a815-203"><a href="nextrecordset-method-ado.md">NextRecordset</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-204">是</span><span class="sxs-lookup"><span data-stu-id="0a815-204">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a815-205"><a href="open-method-ado-recordset.md">Open</a></span><span class="sxs-lookup"><span data-stu-id="0a815-205"><a href="open-method-ado-recordset.md">Open</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-206">是</span><span class="sxs-lookup"><span data-stu-id="0a815-206">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a815-207"><a href="requery-method-ado.md">Requery</a></span><span class="sxs-lookup"><span data-stu-id="0a815-207"><a href="requery-method-ado.md">Requery</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-208">是</span><span class="sxs-lookup"><span data-stu-id="0a815-208">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a815-209"><a href="resync-method-ado.md">同步</a></span><span class="sxs-lookup"><span data-stu-id="0a815-209"><a href="resync-method-ado.md">Resync</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-210">是</span><span class="sxs-lookup"><span data-stu-id="0a815-210">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a815-211"><a href="supports-method-ado.md">支持</a></span><span class="sxs-lookup"><span data-stu-id="0a815-211"><a href="supports-method-ado.md">Supports</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-212">是</span><span class="sxs-lookup"><span data-stu-id="0a815-212">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a815-213"><a href="update-method-ado.md">Update</a></span><span class="sxs-lookup"><span data-stu-id="0a815-213"><a href="update-method-ado.md">Update</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-214">否</span><span class="sxs-lookup"><span data-stu-id="0a815-214">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a815-215"><a href="updatebatch-method-ado.md">UpdateBatch</a></span><span class="sxs-lookup"><span data-stu-id="0a815-215"><a href="updatebatch-method-ado.md">UpdateBatch</a></span></span></p></td>
<td><p><span data-ttu-id="0a815-216">否</span><span class="sxs-lookup"><span data-stu-id="0a815-216">No</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="0a815-217">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a815-217">See also</span></span>

<span data-ttu-id="0a815-218">有关 microsoft ole db Provider for microsoft 索引服务的特定实现详细信息和功能信息, 请参阅 Microsoft ole db 程序员参考。</span><span class="sxs-lookup"><span data-stu-id="0a815-218">For specific implementation details and functional information about the Microsoft OLE DB Provider for Microsoft Indexing Service, consult the Microsoft OLE DB Programmer's Reference.</span></span>

