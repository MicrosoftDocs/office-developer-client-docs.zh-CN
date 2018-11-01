---
title: Microsoft OLE DB Provider for Microsoft Active Directory Service
TOCTitle: Microsoft OLE DB Provider for Microsoft Active Directory Service
ms:assetid: 92d1c967-aa61-f3b5-1c0a-301ef236894c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249647(v=office.15)
ms:contentKeyID: 48546385
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c1555883ef8305225d6ddd1969d98de082288a6b
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25887535"
---
# <a name="microsoft-ole-db-provider-for-microsoft-active-directory-service"></a><span data-ttu-id="ecf63-102">Microsoft OLE DB Provider for Microsoft Active Directory Service</span><span class="sxs-lookup"><span data-stu-id="ecf63-102">Microsoft OLE DB Provider for Microsoft Active Directory Service</span></span>

<span data-ttu-id="ecf63-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ecf63-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ecf63-p101">Microsoft Active Directory Service Interfaces (ADSI) 提供程序允许 ADO 通过 ADSI 连接到各种异构目录服务。这样，除可以访问任何 LDAP 兼容目录服务和 Novell 目录服务外，还为 ADO 应用程序提供了对 Microsoft Windows NT 4.0 和 Microsoft Windows 2000 目录服务的只读访问权限。ADSI 本身就基于一个提供程序模型，因此，如果有一个新的提供程序提供了对其他目录的访问权限，ADO 应用程序就可以对该目录进行无缝访问。ADSI 提供程序为自由线程且支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="ecf63-p101">The Microsoft Active Directory Service Interfaces (ADSI) Provider allows ADO to connect to heterogeneous directory services through ADSI. This gives ADO applications read-only access to the Microsoft Windows NT 4.0 and Microsoft Windows 2000 directory services, in addition to any LDAP-compliant directory service and Novell Directory Services. ADSI itself is based on a provider model, so if there is a new provider giving access to another directory, the ADO application will be able to access it seamlessly. The ADSI provider is free-threaded and unicode enabled.</span></span>

## <a name="connection-string-parameters"></a><span data-ttu-id="ecf63-108">连接字符串参数</span><span class="sxs-lookup"><span data-stu-id="ecf63-108">Connection String Parameters</span></span>

<span data-ttu-id="ecf63-109">若要连接到此提供程序，请将 **ConnectionString** 属性的 [Provider](connectionstring-property-ado.md) 参数设置为：</span><span class="sxs-lookup"><span data-stu-id="ecf63-109">To connect to this provider, set the **Provider** argument of the [ConnectionString](connectionstring-property-ado.md) property to:</span></span>

```vb 
 
ADSDSOObject 
```

<span data-ttu-id="ecf63-110">读取 [Provider](provider-property-ado.md) 属性时，也会返回此字符串。</span><span class="sxs-lookup"><span data-stu-id="ecf63-110">Reading the [Provider](provider-property-ado.md) property will return this string as well.</span></span>

## <a name="typical-connection-string"></a><span data-ttu-id="ecf63-111">典型的连接字符串</span><span class="sxs-lookup"><span data-stu-id="ecf63-111">Typical Connection String</span></span>

<span data-ttu-id="ecf63-112">此提供程序典型的连接字符串为：</span><span class="sxs-lookup"><span data-stu-id="ecf63-112">A typical connection string for this provider is:</span></span>

```vb 
 
"Provider=ADSDSOObject;User ID=userName;Password=userPassword;" 
```

<span data-ttu-id="ecf63-113">该字符串由以下关键字组成：</span><span class="sxs-lookup"><span data-stu-id="ecf63-113">The string consists of these keywords:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ecf63-114">关键字</span><span class="sxs-lookup"><span data-stu-id="ecf63-114">Keyword</span></span></p></th>
<th><p><span data-ttu-id="ecf63-115">说明</span><span class="sxs-lookup"><span data-stu-id="ecf63-115">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-116"><strong>Provider</strong></span><span class="sxs-lookup"><span data-stu-id="ecf63-116"><strong>Provider</strong></span></span></p></td>
<td><p><span data-ttu-id="ecf63-117">指定 Microsoft OLE DB Provider for Microsoft Active Directory Service。</span><span class="sxs-lookup"><span data-stu-id="ecf63-117">Specifies the OLE DB Provider for Microsoft Active Directory Service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-118"><strong>User ID</strong></span><span class="sxs-lookup"><span data-stu-id="ecf63-118"><strong>User ID</strong></span></span></p></td>
<td><p><span data-ttu-id="ecf63-p102">指定用户名。如果忽略此关键字，则使用当前的登录用户名。</span><span class="sxs-lookup"><span data-stu-id="ecf63-p102">Specifies the user name. If this keyword is omitted, then the current logon is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-121"><strong>Password</strong></span><span class="sxs-lookup"><span data-stu-id="ecf63-121"><strong>Password</strong></span></span></p></td>
<td><p><span data-ttu-id="ecf63-p103">指定用户密码。如果忽略此关键字，则使用当前的登录密码。</span><span class="sxs-lookup"><span data-stu-id="ecf63-p103">Specifies the user password. If this keyword is omitted, then the current logon is used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ecf63-124">**命令文本**</span><span class="sxs-lookup"><span data-stu-id="ecf63-124">**Command Text**</span></span>

<span data-ttu-id="ecf63-125">该提供程序采用以下语法识别包含四个部分的命令文本字符串：</span><span class="sxs-lookup"><span data-stu-id="ecf63-125">A four-part command text string is recognized by the provider in the following syntax:</span></span>

`"Root; Filter; Attributes[; Scope]"`

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ecf63-126">值</span><span class="sxs-lookup"><span data-stu-id="ecf63-126">Value</span></span></p></th>
<th><p><span data-ttu-id="ecf63-127">说明</span><span class="sxs-lookup"><span data-stu-id="ecf63-127">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-128"><em>根</em></span><span class="sxs-lookup"><span data-stu-id="ecf63-128"><em>Root</em></span></span></p></td>
<td><p><span data-ttu-id="ecf63-129">指示搜索开始的 <strong>ADsPath</strong> 对象（即搜索的根目录）。</span><span class="sxs-lookup"><span data-stu-id="ecf63-129">Indicates the <strong>ADsPath</strong> object from which to start the search (that is, the root of the search).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-130"><em>Filter</em></span><span class="sxs-lookup"><span data-stu-id="ecf63-130"><em>Filter</em></span></span></p></td>
<td><p><span data-ttu-id="ecf63-131">指示采用 RFC 1960 格式的搜索筛选器。</span><span class="sxs-lookup"><span data-stu-id="ecf63-131">Indicates the search filter in the RFC 1960 format.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-132"><em>Attributes</em></span><span class="sxs-lookup"><span data-stu-id="ecf63-132"><em>Attributes</em></span></span></p></td>
<td><p><span data-ttu-id="ecf63-133">指示要返回的以逗号分隔的属性列表。</span><span class="sxs-lookup"><span data-stu-id="ecf63-133">Indicates a comma-delimited list of attributes to be returned.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-134"><em>Scope</em></span><span class="sxs-lookup"><span data-stu-id="ecf63-134"><em>Scope</em></span></span></p></td>
<td><p><span data-ttu-id="ecf63-135">可选。</span><span class="sxs-lookup"><span data-stu-id="ecf63-135">Optional.</span></span> <span data-ttu-id="ecf63-136">指定搜索的作用域的<strong>字符串</strong>。</span><span class="sxs-lookup"><span data-stu-id="ecf63-136">A <strong>String</strong> that specifies the scope of the search.</span></span> <span data-ttu-id="ecf63-137">可以是下列选项之一： 基本 — 搜索基对象 （搜索的根）。</span><span class="sxs-lookup"><span data-stu-id="ecf63-137">Can be one of the following: Base — Search only the base object (root of the search).</span></span><br />
<span data-ttu-id="ecf63-138">OneLevel — Search 只有一个级别。</span><span class="sxs-lookup"><span data-stu-id="ecf63-138">OneLevel — Search only one level.</span></span><br />
<span data-ttu-id="ecf63-139">子树 — 搜索整个子树。</span><span class="sxs-lookup"><span data-stu-id="ecf63-139">Subtree — Search the entire subtree.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ecf63-140">例如：</span><span class="sxs-lookup"><span data-stu-id="ecf63-140">For example:</span></span>

```vb 
 
"<LDAP://DC=ArcadiaBay,DC=COM>;(objectClass=*);sn, givenName; subtree" 
```

<span data-ttu-id="ecf63-p105">该提供程序还支持命令文本使用 SQL SELECT。例如：</span><span class="sxs-lookup"><span data-stu-id="ecf63-p105">The provider also supports SQL SELECT for command text. For example:</span></span>

```vb 
 
"SELECT title, telephoneNumber From 'LDAP://DC=Microsoft, DC=COM' WHERE 
objectClass='user' AND objectCategory='Person'" 
```

<span data-ttu-id="ecf63-p106">该提供程序不会接受存储过程调用或简单的表名称（例如，[CommandType](commandtype-property-ado.md) 属性将始终为 **adCmdText**）。有关命令文本元素的更完整的说明，请参阅 Active Directory Service Interfaces 文档。</span><span class="sxs-lookup"><span data-stu-id="ecf63-p106">The provider does not accept stored procedure calls or simple table names (for example, the [CommandType](commandtype-property-ado.md) property will always be **adCmdText**). See the Active Directory Service Interfaces documentation for a more complete description of the command text elements.</span></span>

## <a name="recordset-behavior"></a><span data-ttu-id="ecf63-145">Recordset 行为</span><span class="sxs-lookup"><span data-stu-id="ecf63-145">Recordset Behavior</span></span>

<span data-ttu-id="ecf63-146">下面的表列出了使用此提供程序打开的 [Recordset](recordset-object-ado.md) 对象上可用的功能。</span><span class="sxs-lookup"><span data-stu-id="ecf63-146">The following tables list the features available on a [Recordset](recordset-object-ado.md) object opened with this provider.</span></span> <span data-ttu-id="ecf63-147">仅静态游标类型 (**为 adOpenStatic**) 才可用。</span><span class="sxs-lookup"><span data-stu-id="ecf63-147">Only the Static cursor type (**adOpenStatic**) is available.</span></span>

<span data-ttu-id="ecf63-148">有关提供程序配置的 **Recordset** 行为的详细信息，请运行 [Supports](supports-method-ado.md) 方法并枚举 [Recordset](properties-collection-ado.md) 的 **Properties** 集合，以确定提供程序特定的动态属性是否存在。</span><span class="sxs-lookup"><span data-stu-id="ecf63-148">For more detailed information about **Recordset** behavior for your provider configuration, run the [Supports](supports-method-ado.md) method and enumerate the [Properties](properties-collection-ado.md) collection of the **Recordset** to determine whether provider-specific dynamic properties are present.</span></span>

<span data-ttu-id="ecf63-149">标准 ADO **Recordset** 属性的可用性：</span><span class="sxs-lookup"><span data-stu-id="ecf63-149">Availability of standard ADO **Recordset** properties:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ecf63-150">属性</span><span class="sxs-lookup"><span data-stu-id="ecf63-150">Property</span></span></p></th>
<th><p><span data-ttu-id="ecf63-151">可用性</span><span class="sxs-lookup"><span data-stu-id="ecf63-151">Availability</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-152"><a href="absolutepage-property-ado.md">AbsolutePage</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-152"><a href="absolutepage-property-ado.md">AbsolutePage</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-153">读/写</span><span class="sxs-lookup"><span data-stu-id="ecf63-153">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-154"><a href="absoluteposition-property-ado.md">AbsolutePosition</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-154"><a href="absoluteposition-property-ado.md">AbsolutePosition</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-155">读/写</span><span class="sxs-lookup"><span data-stu-id="ecf63-155">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-156"><a href="activeconnection-property-ado.md">ActiveConnection</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-156"><a href="activeconnection-property-ado.md">ActiveConnection</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-157">只读</span><span class="sxs-lookup"><span data-stu-id="ecf63-157">read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-158"><a href="bof-eof-properties-ado.md">BOF</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-158"><a href="bof-eof-properties-ado.md">BOF</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-159">只读</span><span class="sxs-lookup"><span data-stu-id="ecf63-159">read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-160"><a href="bookmark-property-ado.md">Bookmark</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-160"><a href="bookmark-property-ado.md">Bookmark</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-161">读/写</span><span class="sxs-lookup"><span data-stu-id="ecf63-161">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-162"><a href="cachesize-property-ado.md">CacheSize</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-162"><a href="cachesize-property-ado.md">CacheSize</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-163">读/写</span><span class="sxs-lookup"><span data-stu-id="ecf63-163">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-164"><a href="cursorlocation-property-ado.md">CursorLocation</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-164"><a href="cursorlocation-property-ado.md">CursorLocation</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-165">始终为 <strong>adUseServer</strong></span><span class="sxs-lookup"><span data-stu-id="ecf63-165">always <strong>adUseServer</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-166"><a href="cursortype-property-ado.md">CursorType</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-166"><a href="cursortype-property-ado.md">CursorType</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-167">始终为 <strong>adOpenStatic</strong></span><span class="sxs-lookup"><span data-stu-id="ecf63-167">always <strong>adOpenStatic</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-168"><a href="editmode-property-ado.md">EditMode</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-168"><a href="editmode-property-ado.md">EditMode</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-169">始终为 <strong>adEditNone</strong></span><span class="sxs-lookup"><span data-stu-id="ecf63-169">always <strong>adEditNone</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-170"><a href="bof-eof-properties-ado.md">EOF</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-170"><a href="bof-eof-properties-ado.md">EOF</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-171">只读</span><span class="sxs-lookup"><span data-stu-id="ecf63-171">read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-172"><a href="filter-property-ado.md">Filter</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-172"><a href="filter-property-ado.md">Filter</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-173">读/写</span><span class="sxs-lookup"><span data-stu-id="ecf63-173">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-174"><a href="locktype-property-ado.md">LockType</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-174"><a href="locktype-property-ado.md">LockType</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-175">读/写</span><span class="sxs-lookup"><span data-stu-id="ecf63-175">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-176"><a href="marshaloptions-property-ado.md">MarshalOptions</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-176"><a href="marshaloptions-property-ado.md">MarshalOptions</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-177">暂无</span><span class="sxs-lookup"><span data-stu-id="ecf63-177">not available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-178"><a href="maxrecords-property-ado.md">MaxRecords</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-178"><a href="maxrecords-property-ado.md">MaxRecords</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-179">读/写</span><span class="sxs-lookup"><span data-stu-id="ecf63-179">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-180"><a href="pagecount-property-ado.md">PageCount</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-180"><a href="pagecount-property-ado.md">PageCount</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-181">只读</span><span class="sxs-lookup"><span data-stu-id="ecf63-181">read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-182"><a href="pagesize-property-ado.md">PageSize</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-182"><a href="pagesize-property-ado.md">PageSize</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-183">读/写</span><span class="sxs-lookup"><span data-stu-id="ecf63-183">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-184"><a href="recordcount-property-ado.md">RecordCount</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-184"><a href="recordcount-property-ado.md">RecordCount</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-185">只读</span><span class="sxs-lookup"><span data-stu-id="ecf63-185">read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-186"><a href="source-property-ado-recordset.md">Source</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-186"><a href="source-property-ado-recordset.md">Source</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-187">读/写</span><span class="sxs-lookup"><span data-stu-id="ecf63-187">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-188"><a href="state-property-ado.md">State</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-188"><a href="state-property-ado.md">State</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-189">只读</span><span class="sxs-lookup"><span data-stu-id="ecf63-189">read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-190"><a href="status-property-ado-recordset.md">Status</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-190"><a href="status-property-ado-recordset.md">Status</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-191">只读</span><span class="sxs-lookup"><span data-stu-id="ecf63-191">read-only</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ecf63-192">标准 ADO **Recordset** 方法的可用性：</span><span class="sxs-lookup"><span data-stu-id="ecf63-192">Availability of standard ADO **Recordset** methods:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ecf63-193">方法</span><span class="sxs-lookup"><span data-stu-id="ecf63-193">Method</span></span></p></th>
<th><p><span data-ttu-id="ecf63-194">是否可用</span><span class="sxs-lookup"><span data-stu-id="ecf63-194">Available?</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-195"><a href="addnew-method-ado.md">AddNew</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-195"><a href="addnew-method-ado.md">AddNew</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-196">否</span><span class="sxs-lookup"><span data-stu-id="ecf63-196">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-197"><a href="cancel-method-ado.md">Cancel</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-197"><a href="cancel-method-ado.md">Cancel</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-198">否</span><span class="sxs-lookup"><span data-stu-id="ecf63-198">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-199"><a href="cancelbatch-method-ado.md">CancelBatch</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-199"><a href="cancelbatch-method-ado.md">CancelBatch</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-200">否</span><span class="sxs-lookup"><span data-stu-id="ecf63-200">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-201"><a href="cancelupdate-method-ado.md">CancelUpdate</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-201"><a href="cancelupdate-method-ado.md">CancelUpdate</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-202">否</span><span class="sxs-lookup"><span data-stu-id="ecf63-202">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-203"><a href="clone-method-ado.md">Clone</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-203"><a href="clone-method-ado.md">Clone</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-204">是</span><span class="sxs-lookup"><span data-stu-id="ecf63-204">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-205"><a href="close-method-ado.md">Close</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-205"><a href="close-method-ado.md">Close</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-206">是</span><span class="sxs-lookup"><span data-stu-id="ecf63-206">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-207"><a href="delete-method-ado-recordset.md">Delete</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-207"><a href="delete-method-ado-recordset.md">Delete</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-208">否</span><span class="sxs-lookup"><span data-stu-id="ecf63-208">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-209"><a href="getrows-method-ado.md">GetRows</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-209"><a href="getrows-method-ado.md">GetRows</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-210">是</span><span class="sxs-lookup"><span data-stu-id="ecf63-210">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-211"><a href="move-method-ado.md">移动</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-211"><a href="move-method-ado.md">Move</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-212">是</span><span class="sxs-lookup"><span data-stu-id="ecf63-212">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-213"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-213"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-214">是</span><span class="sxs-lookup"><span data-stu-id="ecf63-214">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-215"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveLast</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-215"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveLast</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-216">是</span><span class="sxs-lookup"><span data-stu-id="ecf63-216">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-217"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveNext</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-217"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveNext</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-218">是</span><span class="sxs-lookup"><span data-stu-id="ecf63-218">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-219"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MovePrevious</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-219"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MovePrevious</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-220">是</span><span class="sxs-lookup"><span data-stu-id="ecf63-220">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-221"><a href="nextrecordset-method-ado.md">NextRecordset</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-221"><a href="nextrecordset-method-ado.md">NextRecordset</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-222">是</span><span class="sxs-lookup"><span data-stu-id="ecf63-222">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-223"><a href="open-method-ado-recordset.md">Open</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-223"><a href="open-method-ado-recordset.md">Open</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-224">是</span><span class="sxs-lookup"><span data-stu-id="ecf63-224">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-225"><a href="requery-method-ado.md">Requery</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-225"><a href="requery-method-ado.md">Requery</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-226">是</span><span class="sxs-lookup"><span data-stu-id="ecf63-226">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-227"><a href="resync-method-ado.md">Resync</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-227"><a href="resync-method-ado.md">Resync</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-228">是</span><span class="sxs-lookup"><span data-stu-id="ecf63-228">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-229"><a href="supports-method-ado.md">支持</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-229"><a href="supports-method-ado.md">Supports</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-230">是</span><span class="sxs-lookup"><span data-stu-id="ecf63-230">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf63-231"><a href="update-method-ado.md">更新</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-231"><a href="update-method-ado.md">Update</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-232">否</span><span class="sxs-lookup"><span data-stu-id="ecf63-232">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf63-233"><a href="updatebatch-method-ado.md">UpdateBatch</a></span><span class="sxs-lookup"><span data-stu-id="ecf63-233"><a href="updatebatch-method-ado.md">UpdateBatch</a></span></span></p></td>
<td><p><span data-ttu-id="ecf63-234">否</span><span class="sxs-lookup"><span data-stu-id="ecf63-234">No</span></span></p></td>
</tr>
</tbody>
</table>

