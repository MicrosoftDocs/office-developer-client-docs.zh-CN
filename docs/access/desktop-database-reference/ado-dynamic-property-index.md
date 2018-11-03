---
title: ADO 动态属性索引
TOCTitle: ADO dynamic property index
ms:assetid: 437beced-b97a-894d-b08f-4a322629a5a6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249202(v=office.15)
ms:contentKeyID: 48544502
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 19b7ddca0395869b5a1dba4182a123d33e54e66d
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25947600"
---
# <a name="ado-dynamic-property-index"></a><span data-ttu-id="3e8dd-102">ADO 动态属性索引</span><span class="sxs-lookup"><span data-stu-id="3e8dd-102">ADO dynamic property index</span></span>

<span data-ttu-id="3e8dd-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="3e8dd-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3e8dd-p101">数据提供程序、服务提供程序及服务组件可以将动态属性添加到未打开的 **Connection** 和 [Recordset](connection-object-ado.md) 对象的 [Properties](recordset-object-ado.md) 集合中。打开这些对象时，给定的提供程序还可以插入其他属性。其中的一些属性在 [ADO 动态属性](ado-dynamic-properties.md) 一节中列出。更多其他属性在 [附录 A：提供程序](appendix-a-providers.md)一节的特定提供程序下列出。</span><span class="sxs-lookup"><span data-stu-id="3e8dd-p101">Data providers, service providers, and service components can add dynamic properties to the **Properties** collections of the unopened [Connection](connection-object-ado.md) and [Recordset](recordset-object-ado.md) objects. A given provider may also insert additional properties when these objects are opened. Some of these properties are listed in the [ADO Dynamic Properties](ado-dynamic-properties.md) section. More are listed under the specific providers in the [Appendix A: Providers](appendix-a-providers.md) section.</span></span>

<span data-ttu-id="3e8dd-p102">下表是每个标准 OLE DB 提供程序动态属性的 ADO 和 OLE DB 名称的交叉索引。除了此处列出的属性外，提供程序还可能添加更多的属性。有关提供程序特定动态属性的具体信息，请参阅提供程序文档。</span><span class="sxs-lookup"><span data-stu-id="3e8dd-p102">The table below is a cross-index of the ADO and OLE DB names for each standard OLE DB provider dynamic property. Your providers may add more properties than listed here. For the specific information about provider-specific dynamic properties, see your provider documentation.</span></span>

<span data-ttu-id="3e8dd-p103">《OLE DB 程序员参考》使用术语"说明"来引用 ADO 属性名。您可以在该书中找到有关这些标准属性的详细信息。请在"索引"中搜索 OLE DB 属性名或参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="3e8dd-p103">The OLE DB Programmer's Reference refers to an ADO property name by the term, "Description." You can find more information about these standard properties in the OLE DB Programmer's Reference. Search for the OLE DB property name in the Index or see the following topics:</span></span>

- <span data-ttu-id="3e8dd-114">附录 C：OLE DB 属性</span><span class="sxs-lookup"><span data-stu-id="3e8dd-114">Appendix C: OLE DB Properties</span></span>

- <span data-ttu-id="3e8dd-115">Cursor Service 支持的属性</span><span class="sxs-lookup"><span data-stu-id="3e8dd-115">Supported Properties of the Cursor Service</span></span>

- <span data-ttu-id="3e8dd-116">持久性提供程序支持的属性</span><span class="sxs-lookup"><span data-stu-id="3e8dd-116">Supported Properties of the Persistence Provider</span></span>

- <span data-ttu-id="3e8dd-117">远程提供程序支持的 OLE DB 属性</span><span class="sxs-lookup"><span data-stu-id="3e8dd-117">Supported OLE DB Properties of the Remoting Provider</span></span>

## <a name="remarks"></a><span data-ttu-id="3e8dd-118">备注</span><span class="sxs-lookup"><span data-stu-id="3e8dd-118">Remarks</span></span>

<span data-ttu-id="3e8dd-119">请注意交叉索引中使用的数字：</span><span class="sxs-lookup"><span data-stu-id="3e8dd-119">Note numbers used in the cross-index:</span></span>

<span data-ttu-id="3e8dd-p104">(1) 此属性是一个 Boolean 标志，指示是否应使用指定接口。将列出等效的 OLE DB 属性名（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="3e8dd-p104">(1) This property is a Boolean flag indicating whether the named interface should be used. The equivalent OLE DB property name is listed if it exists.</span></span>

<span data-ttu-id="3e8dd-122">（2） 的"Bookmarkable"ADO 属性是内部生成的向后兼容性和映射到的 OLE DB 属性，需要的 DBPROP\_IROWSETLOCATE。</span><span class="sxs-lookup"><span data-stu-id="3e8dd-122">(2) The "Bookmarkable" ADO property is generated internally for backwards compatibility, and is mapped to the OLE DB property, DBPROP\_IROWSETLOCATE.</span></span> <span data-ttu-id="3e8dd-123">此属性是与 ADO 属性 IRowsetLocate 对应的同一属性。</span><span class="sxs-lookup"><span data-stu-id="3e8dd-123">This is the same property that corresponds to the ADO property, IRowsetLocate.</span></span>

<span data-ttu-id="3e8dd-124">(3) ADO 属性名"Hidden Columns"的命名不同于 OLE DB 属性名说明"Hidden Columns Count"。</span><span class="sxs-lookup"><span data-stu-id="3e8dd-124">(3) The ADO property name, "Hidden Columns", is named differently than the OLE DB property name Description, "Hidden Columns Count."</span></span>

<span data-ttu-id="3e8dd-p106">(4) 对于分级记录集，"Maximum Rows"ADO 属性应用于所有的子记录集。根据行的返回顺序，结果集中的每个父记录集和孤立子记录集可能都具有子记录集，有一些具有子记录集，或者都没有子记录集。因此，重构分级记录集时，每个子记录集的标识符都应该是唯一的。一般情况下，[Microsoft Data Shaping Service for OLE DB (MSDATASHAPE)](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) 提供程序不考虑可从父记录集继承的属性与不能继承的属性间的区别。</span><span class="sxs-lookup"><span data-stu-id="3e8dd-p106">(4) For hierarchical recordsets, the "Maximum Rows" ADO property gets applied across all children. Depending on the order in which the rows are returned, you might have all, some or no children for each parent or orphaned children in the result set. Therefore, when reshaping hierarchical recordsets, the identifier for every child should be unique. In general, the [Microsoft Data Shaping Service for OLE DB (MSDATASHAPE)](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) provider does not allow for distinction between properties that can be inherited from the parent and those that cannot be inherited.</span></span>

<span data-ttu-id="3e8dd-129">(5) 不适用。</span><span class="sxs-lookup"><span data-stu-id="3e8dd-129">(5) Does not apply.</span></span>

<span data-ttu-id="3e8dd-130">**Connection 动态属性**</span><span class="sxs-lookup"><span data-stu-id="3e8dd-130">**Connection Dynamic Properties**</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="3e8dd-131">ADO 属性名</span><span class="sxs-lookup"><span data-stu-id="3e8dd-131">ADO Property Name</span></span></p></th>
<th><p><span data-ttu-id="3e8dd-132">OLE DB 属性名</span><span class="sxs-lookup"><span data-stu-id="3e8dd-132">OLE DB Property Name</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-133">Active Sessions</span><span class="sxs-lookup"><span data-stu-id="3e8dd-133">Active Sessions</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-134">DBPROP_ACTIVESESSIONS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-134">DBPROP_ACTIVESESSIONS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-135">Asynchable Abort</span><span class="sxs-lookup"><span data-stu-id="3e8dd-135">Asynchable Abort</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-136">DBPROP_ASYNCTXNABORT</span><span class="sxs-lookup"><span data-stu-id="3e8dd-136">DBPROP_ASYNCTXNABORT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-137">Asynchable Commit</span><span class="sxs-lookup"><span data-stu-id="3e8dd-137">Asynchable Commit</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-138">DBPROP_ASYNCTNXCOMMIT</span><span class="sxs-lookup"><span data-stu-id="3e8dd-138">DBPROP_ASYNCTNXCOMMIT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-139">Autocommit Isolation Levels</span><span class="sxs-lookup"><span data-stu-id="3e8dd-139">Autocommit Isolation Levels</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-140">DBPROP_SESS_AUTOCOMMITISOLEVELS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-140">DBPROP_SESS_AUTOCOMMITISOLEVELS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-141">Catalog Location</span><span class="sxs-lookup"><span data-stu-id="3e8dd-141">Catalog Location</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-142">DBPROP_CATALOGLOCATION</span><span class="sxs-lookup"><span data-stu-id="3e8dd-142">DBPROP_CATALOGLOCATION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-143">Catalog Term</span><span class="sxs-lookup"><span data-stu-id="3e8dd-143">Catalog Term</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-144">DBPROP_CATALOGTERM</span><span class="sxs-lookup"><span data-stu-id="3e8dd-144">DBPROP_CATALOGTERM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-145">Column Definition</span><span class="sxs-lookup"><span data-stu-id="3e8dd-145">Column Definition</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-146">DBPROP_COLUMNDEFINITION</span><span class="sxs-lookup"><span data-stu-id="3e8dd-146">DBPROP_COLUMNDEFINITION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-147">Connect Timeout</span><span class="sxs-lookup"><span data-stu-id="3e8dd-147">Connect Timeout</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-148">DBPROP_INIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3e8dd-148">DBPROP_INIT_TIMEOUT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-149">Current Catalog</span><span class="sxs-lookup"><span data-stu-id="3e8dd-149">Current Catalog</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-150">DBPROP_CURRENTCATALOG</span><span class="sxs-lookup"><span data-stu-id="3e8dd-150">DBPROP_CURRENTCATALOG</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-151">Data Source</span><span class="sxs-lookup"><span data-stu-id="3e8dd-151">Data Source</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-152">DBPROP_INIT_DATASOURCE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-152">DBPROP_INIT_DATASOURCE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-153">Data Source Name</span><span class="sxs-lookup"><span data-stu-id="3e8dd-153">Data Source Name</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-154">DBPROP_DATASOURCENAME</span><span class="sxs-lookup"><span data-stu-id="3e8dd-154">DBPROP_DATASOURCENAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-155">Data Source Object Threading Model</span><span class="sxs-lookup"><span data-stu-id="3e8dd-155">Data Source Object Threading Model</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-156">DBPROP_DSOTHREADMODEL</span><span class="sxs-lookup"><span data-stu-id="3e8dd-156">DBPROP_DSOTHREADMODEL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-157">DBMS Name</span><span class="sxs-lookup"><span data-stu-id="3e8dd-157">DBMS Name</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-158">DBPROP_DBMSNAME</span><span class="sxs-lookup"><span data-stu-id="3e8dd-158">DBPROP_DBMSNAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-159">DBMS Version</span><span class="sxs-lookup"><span data-stu-id="3e8dd-159">DBMS Version</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-160">DBPROP_DBMSVER</span><span class="sxs-lookup"><span data-stu-id="3e8dd-160">DBPROP_DBMSVER</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-161">Extended Properties</span><span class="sxs-lookup"><span data-stu-id="3e8dd-161">Extended Properties</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-162">DBPROP_INIT_PROVIDERSTRING</span><span class="sxs-lookup"><span data-stu-id="3e8dd-162">DBPROP_INIT_PROVIDERSTRING</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-163">GROUP BY Support</span><span class="sxs-lookup"><span data-stu-id="3e8dd-163">GROUP BY Support</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-164">DBPROP_GROUPBY</span><span class="sxs-lookup"><span data-stu-id="3e8dd-164">DBPROP_GROUPBY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-165">Heterogeneous Table Support</span><span class="sxs-lookup"><span data-stu-id="3e8dd-165">Heterogeneous Table Support</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-166">DBPROP_HETEROGENEOUSTABLES</span><span class="sxs-lookup"><span data-stu-id="3e8dd-166">DBPROP_HETEROGENEOUSTABLES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-167">Identifier Case Sensitivity</span><span class="sxs-lookup"><span data-stu-id="3e8dd-167">Identifier Case Sensitivity</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-168">DBPROP_IDENTIFIERCASE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-168">DBPROP_IDENTIFIERCASE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-169">Initial Catalog</span><span class="sxs-lookup"><span data-stu-id="3e8dd-169">Initial Catalog</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-170">DBPROP_INIT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e8dd-170">DBPROP_INIT_CATALOG</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-171">Isolation Levels</span><span class="sxs-lookup"><span data-stu-id="3e8dd-171">Isolation Levels</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-172">DBPROP_SUPPORTEDTXNISOLEVELS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-172">DBPROP_SUPPORTEDTXNISOLEVELS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-173">Isolation Retention</span><span class="sxs-lookup"><span data-stu-id="3e8dd-173">Isolation Retention</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-174">DBPROP_SUPPORTEDTXNISORETAIN</span><span class="sxs-lookup"><span data-stu-id="3e8dd-174">DBPROP_SUPPORTEDTXNISORETAIN</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-175">Locale Identifier</span><span class="sxs-lookup"><span data-stu-id="3e8dd-175">Locale Identifier</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-176">DBPROP_INIT_LCID</span><span class="sxs-lookup"><span data-stu-id="3e8dd-176">DBPROP_INIT_LCID</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-177">Location</span><span class="sxs-lookup"><span data-stu-id="3e8dd-177">Location</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-178">DBPROP_INIT_LOCATION</span><span class="sxs-lookup"><span data-stu-id="3e8dd-178">DBPROP_INIT_LOCATION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-179">Maximum Index Size</span><span class="sxs-lookup"><span data-stu-id="3e8dd-179">Maximum Index Size</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-180">DBPROP_MAXINDEXSIZE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-180">DBPROP_MAXINDEXSIZE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-181">Maximum Row Size</span><span class="sxs-lookup"><span data-stu-id="3e8dd-181">Maximum Row Size</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-182">DBPROP_MAXROWSIZE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-182">DBPROP_MAXROWSIZE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-183">Maximum Row Size Includes BLOB</span><span class="sxs-lookup"><span data-stu-id="3e8dd-183">Maximum Row Size Includes BLOB</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-184">DBPROP_MAXROWSIZEINCLUDESBLOB</span><span class="sxs-lookup"><span data-stu-id="3e8dd-184">DBPROP_MAXROWSIZEINCLUDESBLOB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-185">Maximum Tables in SELECT</span><span class="sxs-lookup"><span data-stu-id="3e8dd-185">Maximum Tables in SELECT</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-186">DBPROP_MAXTABLESINSELECT</span><span class="sxs-lookup"><span data-stu-id="3e8dd-186">DBPROP_MAXTABLESINSELECT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-187">Mode</span><span class="sxs-lookup"><span data-stu-id="3e8dd-187">Mode</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-188">DBPROP_INIT_MODE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-188">DBPROP_INIT_MODE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-189">Multiple Parameter Sets</span><span class="sxs-lookup"><span data-stu-id="3e8dd-189">Multiple Parameter Sets</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-190">DBPROP_MULTIPLEPARAMSETS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-190">DBPROP_MULTIPLEPARAMSETS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-191">Multiple Results</span><span class="sxs-lookup"><span data-stu-id="3e8dd-191">Multiple Results</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-192">DBPROP_MULTIPLERESULTS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-192">DBPROP_MULTIPLERESULTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-193">Multiple Storage Objects</span><span class="sxs-lookup"><span data-stu-id="3e8dd-193">Multiple Storage Objects</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-194">DBPROP_MULTIPLESTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-194">DBPROP_MULTIPLESTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-195">Multi-Table Update</span><span class="sxs-lookup"><span data-stu-id="3e8dd-195">Multi-Table Update</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-196">DBPROP_MULTITABLEUPDATE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-196">DBPROP_MULTITABLEUPDATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-197">NULL Collation Order</span><span class="sxs-lookup"><span data-stu-id="3e8dd-197">NULL Collation Order</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-198">DBPROP_NULLCOLLATION</span><span class="sxs-lookup"><span data-stu-id="3e8dd-198">DBPROP_NULLCOLLATION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-199">NULL Concatenation Behavior</span><span class="sxs-lookup"><span data-stu-id="3e8dd-199">NULL Concatenation Behavior</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-200">DBPROP_CONCATNULLBEHAVIOR</span><span class="sxs-lookup"><span data-stu-id="3e8dd-200">DBPROP_CONCATNULLBEHAVIOR</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-201">OLE DB Services</span><span class="sxs-lookup"><span data-stu-id="3e8dd-201">OLE DB Services</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-202">DBPROP_INIT_OLEDBSERVICES</span><span class="sxs-lookup"><span data-stu-id="3e8dd-202">DBPROP_INIT_OLEDBSERVICES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-203">OLE DB Version</span><span class="sxs-lookup"><span data-stu-id="3e8dd-203">OLE DB Version</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-204">DBPROP_PROVIDEROLEDBVER</span><span class="sxs-lookup"><span data-stu-id="3e8dd-204">DBPROP_PROVIDEROLEDBVER</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-205">OLE Object Support</span><span class="sxs-lookup"><span data-stu-id="3e8dd-205">OLE Object Support</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-206">DBPROP_OLEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-206">DBPROP_OLEOBJECTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-207">Open Rowset Support</span><span class="sxs-lookup"><span data-stu-id="3e8dd-207">Open Rowset Support</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-208">DBPROP_OPENROWSETSUPPORT</span><span class="sxs-lookup"><span data-stu-id="3e8dd-208">DBPROP_OPENROWSETSUPPORT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-209">ORDER BY Columns in Select List</span><span class="sxs-lookup"><span data-stu-id="3e8dd-209">ORDER BY Columns in Select List</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-210">DBPROP_ORDERBYCOLUMNSINSELECT</span><span class="sxs-lookup"><span data-stu-id="3e8dd-210">DBPROP_ORDERBYCOLUMNSINSELECT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-211">Output Parameter Availability</span><span class="sxs-lookup"><span data-stu-id="3e8dd-211">Output Parameter Availability</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-212">DBPROP_OUTPUTPARAMETERAVAILABILITY</span><span class="sxs-lookup"><span data-stu-id="3e8dd-212">DBPROP_OUTPUTPARAMETERAVAILABILITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-213">Pass By Ref Accessors</span><span class="sxs-lookup"><span data-stu-id="3e8dd-213">Pass By Ref Accessors</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-214">DBPROP_BYREFACCESSORS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-214">DBPROP_BYREFACCESSORS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-215">Password</span><span class="sxs-lookup"><span data-stu-id="3e8dd-215">Password</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-216">DBPROP_AUTH_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="3e8dd-216">DBPROP_AUTH_PASSWORD</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-217">Persist Security Info</span><span class="sxs-lookup"><span data-stu-id="3e8dd-217">Persist Security Info</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-218">DBPROP_AUTH_PERSIST_SENSITIVE_AUTHINFO</span><span class="sxs-lookup"><span data-stu-id="3e8dd-218">DBPROP_AUTH_PERSIST_SENSITIVE_AUTHINFO</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-219">Persistent ID Type</span><span class="sxs-lookup"><span data-stu-id="3e8dd-219">Persistent ID Type</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-220">DBPROP_PERSISTENTIDTYPE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-220">DBPROP_PERSISTENTIDTYPE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-221">Prepare Abort Behavior</span><span class="sxs-lookup"><span data-stu-id="3e8dd-221">Prepare Abort Behavior</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-222">DBPROP_PREPAREABORTBEHAVIOR</span><span class="sxs-lookup"><span data-stu-id="3e8dd-222">DBPROP_PREPAREABORTBEHAVIOR</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-223">Prepare Commit Behavior</span><span class="sxs-lookup"><span data-stu-id="3e8dd-223">Prepare Commit Behavior</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-224">DBPROP_PREPARECOMMITBEHAVIOR</span><span class="sxs-lookup"><span data-stu-id="3e8dd-224">DBPROP_PREPARECOMMITBEHAVIOR</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-225">Procedure Term</span><span class="sxs-lookup"><span data-stu-id="3e8dd-225">Procedure Term</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-226">DBPROP_PROCEDURETERM</span><span class="sxs-lookup"><span data-stu-id="3e8dd-226">DBPROP_PROCEDURETERM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-227">Prompt</span><span class="sxs-lookup"><span data-stu-id="3e8dd-227">Prompt</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-228">DBPROP_INIT_PROMPT</span><span class="sxs-lookup"><span data-stu-id="3e8dd-228">DBPROP_INIT_PROMPT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-229">Provider Friendly Name</span><span class="sxs-lookup"><span data-stu-id="3e8dd-229">Provider Friendly Name</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-230">DBPROP_PROVIDERFRIENDLYNAME</span><span class="sxs-lookup"><span data-stu-id="3e8dd-230">DBPROP_PROVIDERFRIENDLYNAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-231">Provider Name</span><span class="sxs-lookup"><span data-stu-id="3e8dd-231">Provider Name</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-232">DBPROP_PROVIDERFILENAME</span><span class="sxs-lookup"><span data-stu-id="3e8dd-232">DBPROP_PROVIDERFILENAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-233">Provider Version</span><span class="sxs-lookup"><span data-stu-id="3e8dd-233">Provider Version</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-234">DBPROP_PROVIDERVER</span><span class="sxs-lookup"><span data-stu-id="3e8dd-234">DBPROP_PROVIDERVER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-235">Read-Only Data Source</span><span class="sxs-lookup"><span data-stu-id="3e8dd-235">Read-Only Data Source</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-236">DBPROP_DATASOURCEREADONLY</span><span class="sxs-lookup"><span data-stu-id="3e8dd-236">DBPROP_DATASOURCEREADONLY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-237">Rowset Conversions on Command</span><span class="sxs-lookup"><span data-stu-id="3e8dd-237">Rowset Conversions on Command</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-238">DBPROP_ROWSETCONVERSIONSONCOMMAND</span><span class="sxs-lookup"><span data-stu-id="3e8dd-238">DBPROP_ROWSETCONVERSIONSONCOMMAND</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-239">Schema Term</span><span class="sxs-lookup"><span data-stu-id="3e8dd-239">Schema Term</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-240">DBPROP_SCHEMATERM</span><span class="sxs-lookup"><span data-stu-id="3e8dd-240">DBPROP_SCHEMATERM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-241">Schema Usage</span><span class="sxs-lookup"><span data-stu-id="3e8dd-241">Schema Usage</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-242">DBPROP_SCHEMAUSAGE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-242">DBPROP_SCHEMAUSAGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-243">SQL Support</span><span class="sxs-lookup"><span data-stu-id="3e8dd-243">SQL Support</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-244">DBPROP_SQLSUPPORT</span><span class="sxs-lookup"><span data-stu-id="3e8dd-244">DBPROP_SQLSUPPORT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-245">Structured Storage</span><span class="sxs-lookup"><span data-stu-id="3e8dd-245">Structured Storage</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-246">DBPROP_STRUCTUREDSTORAGE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-246">DBPROP_STRUCTUREDSTORAGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-247">Subquery Support</span><span class="sxs-lookup"><span data-stu-id="3e8dd-247">Subquery Support</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-248">DBPROP_SUBQUERIES</span><span class="sxs-lookup"><span data-stu-id="3e8dd-248">DBPROP_SUBQUERIES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-249">Table Term</span><span class="sxs-lookup"><span data-stu-id="3e8dd-249">Table Term</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-250">DBPROP_TABLETERM</span><span class="sxs-lookup"><span data-stu-id="3e8dd-250">DBPROP_TABLETERM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-251">Transaction DDL</span><span class="sxs-lookup"><span data-stu-id="3e8dd-251">Transaction DDL</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-252">DBPROP_SUPPORTEDTXNDDL</span><span class="sxs-lookup"><span data-stu-id="3e8dd-252">DBPROP_SUPPORTEDTXNDDL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-253">User ID</span><span class="sxs-lookup"><span data-stu-id="3e8dd-253">User ID</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-254">DBPROP_AUTH_USERID</span><span class="sxs-lookup"><span data-stu-id="3e8dd-254">DBPROP_AUTH_USERID</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-255">User Name</span><span class="sxs-lookup"><span data-stu-id="3e8dd-255">User Name</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-256">DBPROP_USERNAME</span><span class="sxs-lookup"><span data-stu-id="3e8dd-256">DBPROP_USERNAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-257">Window Handle</span><span class="sxs-lookup"><span data-stu-id="3e8dd-257">Window Handle</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-258">DBPROP_INIT_HWND</span><span class="sxs-lookup"><span data-stu-id="3e8dd-258">DBPROP_INIT_HWND</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3e8dd-259">**Recordset 动态属性**</span><span class="sxs-lookup"><span data-stu-id="3e8dd-259">**Recordset Dynamic Properties**</span></span>

<span data-ttu-id="3e8dd-260">请注意，关闭 **Recordset** 时， **Recordset** 对象的 **动态属性** 将超出范围（不可用）。</span><span class="sxs-lookup"><span data-stu-id="3e8dd-260">Note that the **Dynamic Properties** of the **Recordset** object go out of scope (become unavailable) when the **Recordset** is closed.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="3e8dd-261">ADO 属性名</span><span class="sxs-lookup"><span data-stu-id="3e8dd-261">ADO Property Name</span></span></p></th>
<th><p><span data-ttu-id="3e8dd-262">OLE DB 属性名</span><span class="sxs-lookup"><span data-stu-id="3e8dd-262">OLE DB Property Name</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-263">IAccessor</span><span class="sxs-lookup"><span data-stu-id="3e8dd-263">IAccessor</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-264">DBPROP_IACCESSOR (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-264">DBPROP_IACCESSOR (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-265">IChapteredRowset</span><span class="sxs-lookup"><span data-stu-id="3e8dd-265">IChapteredRowset</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-266">(1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-266">(1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-267">IColumnsInfo</span><span class="sxs-lookup"><span data-stu-id="3e8dd-267">IColumnsInfo</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-268">DBPROP_ICOLUMNSINFO (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-268">DBPROP_ICOLUMNSINFO (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-269">IColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="3e8dd-269">IColumnsRowset</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-270">DBPROP_ICOLUMNSROWSET (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-270">DBPROP_ICOLUMNSROWSET (1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-271">IConnectionPointContainer</span><span class="sxs-lookup"><span data-stu-id="3e8dd-271">IConnectionPointContainer</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-272">DBPROP_ICONNECTIONPOINTCONTAINER (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-272">DBPROP_ICONNECTIONPOINTCONTAINER (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-273">IConvertType</span><span class="sxs-lookup"><span data-stu-id="3e8dd-273">IConvertType</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-274">(1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-274">(1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-275">ILockBytes</span><span class="sxs-lookup"><span data-stu-id="3e8dd-275">ILockBytes</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-276">DBPROP_ILOCKBYTES (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-276">DBPROP_ILOCKBYTES (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-277">IRowset</span><span class="sxs-lookup"><span data-stu-id="3e8dd-277">IRowset</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-278">DBPROP_IROWSET (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-278">DBPROP_IROWSET (1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-279">IDBAsynchStatus</span><span class="sxs-lookup"><span data-stu-id="3e8dd-279">IDBAsynchStatus</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-280">DBPROP_IDBASYNCHSTATUS (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-280">DBPROP_IDBASYNCHSTATUS (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-281">IParentRowset</span><span class="sxs-lookup"><span data-stu-id="3e8dd-281">IParentRowset</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-282">(1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-282">(1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-283">IRowsetChange</span><span class="sxs-lookup"><span data-stu-id="3e8dd-283">IRowsetChange</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-284">DBPROP_IROWSETCHANGE (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-284">DBPROP_IROWSETCHANGE (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-285">IRowsetExactScroll</span><span class="sxs-lookup"><span data-stu-id="3e8dd-285">IRowsetExactScroll</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-286">(1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-286">(1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-287">IRowsetFind</span><span class="sxs-lookup"><span data-stu-id="3e8dd-287">IRowsetFind</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-288">DBPROP_IROWSETFIND (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-288">DBPROP_IROWSETFIND (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-289">IRowsetIdentity</span><span class="sxs-lookup"><span data-stu-id="3e8dd-289">IRowsetIdentity</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-290">DBPROP_IROWSETIDENTITY (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-290">DBPROP_IROWSETIDENTITY (1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-291">IRowsetInfo</span><span class="sxs-lookup"><span data-stu-id="3e8dd-291">IRowsetInfo</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-292">DBPROP_IROWSETINFO (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-292">DBPROP_IROWSETINFO (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-293">IRowsetLocate</span><span class="sxs-lookup"><span data-stu-id="3e8dd-293">IRowsetLocate</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-294">DBPROP_IROWSETLOCATE (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-294">DBPROP_IROWSETLOCATE (1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-295">IRowsetRefresh</span><span class="sxs-lookup"><span data-stu-id="3e8dd-295">IRowsetRefresh</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-296">DBPROP_IROWSETREFRESH (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-296">DBPROP_IROWSETREFRESH (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-297">IRowsetResynch</span><span class="sxs-lookup"><span data-stu-id="3e8dd-297">IRowsetResynch</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-298">(1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-298">(1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-299">IRowsetScroll</span><span class="sxs-lookup"><span data-stu-id="3e8dd-299">IRowsetScroll</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-300">DBPROP_IROWSETSCROLL (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-300">DBPROP_IROWSETSCROLL (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-301">IRowsetUpdate</span><span class="sxs-lookup"><span data-stu-id="3e8dd-301">IRowsetUpdate</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-302">DBPROP_IROWSETUPDATE (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-302">DBPROP_IROWSETUPDATE (1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-303">IRowsetView</span><span class="sxs-lookup"><span data-stu-id="3e8dd-303">IRowsetView</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-304">DBPROP_IROWSETVIEW (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-304">DBPROP_IROWSETVIEW (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-305">IRowsetIndex</span><span class="sxs-lookup"><span data-stu-id="3e8dd-305">IRowsetIndex</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-306">DBPROP_IROWSETINDEX (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-306">DBPROP_IROWSETINDEX (1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-307">ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="3e8dd-307">ISequentialStream</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-308">DBPROP_ISEQUENTIALSTREAM (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-308">DBPROP_ISEQUENTIALSTREAM (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-309">IStorage</span><span class="sxs-lookup"><span data-stu-id="3e8dd-309">IStorage</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-310">DBPROP_ISTORAGE (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-310">DBPROP_ISTORAGE (1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-311">IStream</span><span class="sxs-lookup"><span data-stu-id="3e8dd-311">IStream</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-312">DBPROP_ISTREAM (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-312">DBPROP_ISTREAM (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-313">ISupportErrorInfo</span><span class="sxs-lookup"><span data-stu-id="3e8dd-313">ISupportErrorInfo</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-314">DBPROP_ISUPPORTERRORINFO (1)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-314">DBPROP_ISUPPORTERRORINFO (1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-315">Access Order</span><span class="sxs-lookup"><span data-stu-id="3e8dd-315">Access Order</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-316">DBPROP_ACCESSORDER</span><span class="sxs-lookup"><span data-stu-id="3e8dd-316">DBPROP_ACCESSORDER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-317">Append-Only Rowset</span><span class="sxs-lookup"><span data-stu-id="3e8dd-317">Append-Only Rowset</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-318">DBPROP_APPENDONLY</span><span class="sxs-lookup"><span data-stu-id="3e8dd-318">DBPROP_APPENDONLY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-319">Asynchronous Rowset Processing</span><span class="sxs-lookup"><span data-stu-id="3e8dd-319">Asynchronous Rowset Processing</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-320">DBPROP_ROWSET_ASYNCH</span><span class="sxs-lookup"><span data-stu-id="3e8dd-320">DBPROP_ROWSET_ASYNCH</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-321">Auto Recalc</span><span class="sxs-lookup"><span data-stu-id="3e8dd-321">Auto Recalc</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-322">DBPROP_ADC_AUTORECALC</span><span class="sxs-lookup"><span data-stu-id="3e8dd-322">DBPROP_ADC_AUTORECALC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-323">Background Fetch Size</span><span class="sxs-lookup"><span data-stu-id="3e8dd-323">Background Fetch Size</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-324">DBPROP_ASYNCHFETCHSIZE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-324">DBPROP_ASYNCHFETCHSIZE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-325">Background Thread Priority</span><span class="sxs-lookup"><span data-stu-id="3e8dd-325">Background Thread Priority</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-326">DBPROP_ASYNCHTHREADPRIORITY</span><span class="sxs-lookup"><span data-stu-id="3e8dd-326">DBPROP_ASYNCHTHREADPRIORITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-327">Batch Size</span><span class="sxs-lookup"><span data-stu-id="3e8dd-327">Batch Size</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-328">DBPROP_ADC_BATCHSIZE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-328">DBPROP_ADC_BATCHSIZE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-329">Blocking Storage Objects</span><span class="sxs-lookup"><span data-stu-id="3e8dd-329">Blocking Storage Objects</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-330">DBPROP_BLOCKINGSTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-330">DBPROP_BLOCKINGSTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-331">Bookmark Type</span><span class="sxs-lookup"><span data-stu-id="3e8dd-331">Bookmark Type</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-332">DBPROP_BOOKMARKTYPE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-332">DBPROP_BOOKMARKTYPE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-333">Bookmarkable</span><span class="sxs-lookup"><span data-stu-id="3e8dd-333">Bookmarkable</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-334">DBPROP_IROWSETLOCATE (2)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-334">DBPROP_IROWSETLOCATE (2)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-335">Bookmarks Ordered</span><span class="sxs-lookup"><span data-stu-id="3e8dd-335">Bookmarks Ordered</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-336">DBPROP_ORDEREDBOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-336">DBPROP_ORDEREDBOOKMARKS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-337">Cache Child Rows</span><span class="sxs-lookup"><span data-stu-id="3e8dd-337">Cache Child Rows</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-338">DBPROP_ADC_CACHECHILDROWS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-338">DBPROP_ADC_CACHECHILDROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-339">Cache Deferred Columns</span><span class="sxs-lookup"><span data-stu-id="3e8dd-339">Cache Deferred Columns</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-340">DBPROP_CACHEDEFERRED</span><span class="sxs-lookup"><span data-stu-id="3e8dd-340">DBPROP_CACHEDEFERRED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-341">Change Inserted Rows</span><span class="sxs-lookup"><span data-stu-id="3e8dd-341">Change Inserted Rows</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-342">DBPROP_CHANGEINSERTEDROWS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-342">DBPROP_CHANGEINSERTEDROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-343">Column Privileges</span><span class="sxs-lookup"><span data-stu-id="3e8dd-343">Column Privileges</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-344">DBPROP_COLUMNRESTRICT</span><span class="sxs-lookup"><span data-stu-id="3e8dd-344">DBPROP_COLUMNRESTRICT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-345">Column Set Notification</span><span class="sxs-lookup"><span data-stu-id="3e8dd-345">Column Set Notification</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-346">DBPROP_NOTIFYCOLUMNSET</span><span class="sxs-lookup"><span data-stu-id="3e8dd-346">DBPROP_NOTIFYCOLUMNSET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-347">Column Writable</span><span class="sxs-lookup"><span data-stu-id="3e8dd-347">Column Writable</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-348">DBPROP_MAYWRITECOLUMN</span><span class="sxs-lookup"><span data-stu-id="3e8dd-348">DBPROP_MAYWRITECOLUMN</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-349">Command Time Out</span><span class="sxs-lookup"><span data-stu-id="3e8dd-349">Command Time Out</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-350">DBPROP_COMMANDTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3e8dd-350">DBPROP_COMMANDTIMEOUT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-351">Cursor Engine Version</span><span class="sxs-lookup"><span data-stu-id="3e8dd-351">Cursor Engine Version</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-352">DBPROP_ADC_CEVER</span><span class="sxs-lookup"><span data-stu-id="3e8dd-352">DBPROP_ADC_CEVER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-353">Defer Column</span><span class="sxs-lookup"><span data-stu-id="3e8dd-353">Defer Column</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-354">DBPROP_DEFERRED</span><span class="sxs-lookup"><span data-stu-id="3e8dd-354">DBPROP_DEFERRED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-355">Delay Storage Object Updates</span><span class="sxs-lookup"><span data-stu-id="3e8dd-355">Delay Storage Object Updates</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-356">DBPROP_DELAYSTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-356">DBPROP_DELAYSTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-357">Fetch Backwards</span><span class="sxs-lookup"><span data-stu-id="3e8dd-357">Fetch Backwards</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-358">DBPROP_CANFETCHBACKWARDS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-358">DBPROP_CANFETCHBACKWARDS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-359">Filter Operations</span><span class="sxs-lookup"><span data-stu-id="3e8dd-359">Filter Operations</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-360">DBPROP_FILTERCOMPAREOPS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-360">DBPROP_FILTERCOMPAREOPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-361">Find Operations</span><span class="sxs-lookup"><span data-stu-id="3e8dd-361">Find Operations</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-362">DBPROP_FINDCOMPAREOPS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-362">DBPROP_FINDCOMPAREOPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-363">Hidden Columns (Count)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-363">Hidden Columns (Count)</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-364">DBPROP_HIDDENCOLUMNS (3)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-364">DBPROP_HIDDENCOLUMNS (3)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-365">Hold Rows</span><span class="sxs-lookup"><span data-stu-id="3e8dd-365">Hold Rows</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-366">DBPROP_CANHOLDROWS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-366">DBPROP_CANHOLDROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-367">Immobile Rows</span><span class="sxs-lookup"><span data-stu-id="3e8dd-367">Immobile Rows</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-368">DBPROP_IMMOBILEROWS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-368">DBPROP_IMMOBILEROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-369">Initial Fetch Size</span><span class="sxs-lookup"><span data-stu-id="3e8dd-369">Initial Fetch Size</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-370">DBPROP_ASYNCHPREFETCHSIZE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-370">DBPROP_ASYNCHPREFETCHSIZE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-371">Literal Bookmarks</span><span class="sxs-lookup"><span data-stu-id="3e8dd-371">Literal Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-372">DBPROP_LITERALBOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-372">DBPROP_LITERALBOOKMARKS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-373">Literal Row Identity</span><span class="sxs-lookup"><span data-stu-id="3e8dd-373">Literal Row Identity</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-374">DBPROP_LITERALIDENTITY</span><span class="sxs-lookup"><span data-stu-id="3e8dd-374">DBPROP_LITERALIDENTITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-375">Maintain Change Status</span><span class="sxs-lookup"><span data-stu-id="3e8dd-375">Maintain Change Status</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-376">DBPROP_ADC_MAINTAINCHANGESTATUS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-376">DBPROP_ADC_MAINTAINCHANGESTATUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-377">Maximum Open Rows</span><span class="sxs-lookup"><span data-stu-id="3e8dd-377">Maximum Open Rows</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-378">DBPROP_MAXOPENROWS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-378">DBPROP_MAXOPENROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-379">Maximum Pending Rows</span><span class="sxs-lookup"><span data-stu-id="3e8dd-379">Maximum Pending Rows</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-380">DBPROP_MAXPENDINGROWS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-380">DBPROP_MAXPENDINGROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-381">Maximum Rows</span><span class="sxs-lookup"><span data-stu-id="3e8dd-381">Maximum Rows</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-382">DBPROP_MAXROWS (4)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-382">DBPROP_MAXROWS (4)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-383">Memory Usage</span><span class="sxs-lookup"><span data-stu-id="3e8dd-383">Memory Usage</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-384">DBPROP_MEMORYUSAGE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-384">DBPROP_MEMORYUSAGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-385">Notification Granularity</span><span class="sxs-lookup"><span data-stu-id="3e8dd-385">Notification Granularity</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-386">DBPROP_NOTIFICATIONGRANULARITY</span><span class="sxs-lookup"><span data-stu-id="3e8dd-386">DBPROP_NOTIFICATIONGRANULARITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-387">Notification Phases</span><span class="sxs-lookup"><span data-stu-id="3e8dd-387">Notification Phases</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-388">DBPROP_NOTIFICATIONPHASES</span><span class="sxs-lookup"><span data-stu-id="3e8dd-388">DBPROP_NOTIFICATIONPHASES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-389">Objects Transacted</span><span class="sxs-lookup"><span data-stu-id="3e8dd-389">Objects Transacted</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-390">DBPROP_TRANSACTEDOBJECT</span><span class="sxs-lookup"><span data-stu-id="3e8dd-390">DBPROP_TRANSACTEDOBJECT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-391">Others' Changes Visible</span><span class="sxs-lookup"><span data-stu-id="3e8dd-391">Others' Changes Visible</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-392">DBPROP_OTHERUPDATEDELETE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-392">DBPROP_OTHERUPDATEDELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-393">Others' Inserts Visible</span><span class="sxs-lookup"><span data-stu-id="3e8dd-393">Others' Inserts Visible</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-394">DBPROP_OTHERINSERT</span><span class="sxs-lookup"><span data-stu-id="3e8dd-394">DBPROP_OTHERINSERT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-395">Own Changes Visible</span><span class="sxs-lookup"><span data-stu-id="3e8dd-395">Own Changes Visible</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-396">DBPROP_OWNUPDATEDELETE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-396">DBPROP_OWNUPDATEDELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-397">Own Inserts Visible</span><span class="sxs-lookup"><span data-stu-id="3e8dd-397">Own Inserts Visible</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-398">DBPROP_OWNINSERT</span><span class="sxs-lookup"><span data-stu-id="3e8dd-398">DBPROP_OWNINSERT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-399">Preserve on Abort</span><span class="sxs-lookup"><span data-stu-id="3e8dd-399">Preserve on Abort</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-400">DBPROP_ABORTPRESERVE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-400">DBPROP_ABORTPRESERVE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-401">Preserve on Commit</span><span class="sxs-lookup"><span data-stu-id="3e8dd-401">Preserve on Commit</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-402">DBPROP_COMMITPRESERVE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-402">DBPROP_COMMITPRESERVE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-403">Private1</span><span class="sxs-lookup"><span data-stu-id="3e8dd-403">Private1</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-404">(5)</span><span class="sxs-lookup"><span data-stu-id="3e8dd-404">(5)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-405">Quick Restart</span><span class="sxs-lookup"><span data-stu-id="3e8dd-405">Quick Restart</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-406">DBPROP_QUICKRESTART</span><span class="sxs-lookup"><span data-stu-id="3e8dd-406">DBPROP_QUICKRESTART</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-407">Reentrant Events</span><span class="sxs-lookup"><span data-stu-id="3e8dd-407">Reentrant Events</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-408">DBPROP_REENTRANTEVENTS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-408">DBPROP_REENTRANTEVENTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-409">Remove Deleted Rows</span><span class="sxs-lookup"><span data-stu-id="3e8dd-409">Remove Deleted Rows</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-410">DBPROP_REMOVEDELETED</span><span class="sxs-lookup"><span data-stu-id="3e8dd-410">DBPROP_REMOVEDELETED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-411">Report Multiple Changes</span><span class="sxs-lookup"><span data-stu-id="3e8dd-411">Report Multiple Changes</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-412">DBPROP_REPORTMULTIPLECHANGES</span><span class="sxs-lookup"><span data-stu-id="3e8dd-412">DBPROP_REPORTMULTIPLECHANGES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-413">Reshape Name</span><span class="sxs-lookup"><span data-stu-id="3e8dd-413">Reshape Name</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-414">DBPROP_ADC_RESHAPENAME</span><span class="sxs-lookup"><span data-stu-id="3e8dd-414">DBPROP_ADC_RESHAPENAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-415">Resync Command</span><span class="sxs-lookup"><span data-stu-id="3e8dd-415">Resync Command</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-416">DBPROP_ADC_CUSTOMRESYNCH</span><span class="sxs-lookup"><span data-stu-id="3e8dd-416">DBPROP_ADC_CUSTOMRESYNCH</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-417">Return Pending Inserts</span><span class="sxs-lookup"><span data-stu-id="3e8dd-417">Return Pending Inserts</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-418">DBPROP_RETURNPENDINGINSERTS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-418">DBPROP_RETURNPENDINGINSERTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-419">Row Delete Notification</span><span class="sxs-lookup"><span data-stu-id="3e8dd-419">Row Delete Notification</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-420">DBPROP_NOTIFYROWDELETE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-420">DBPROP_NOTIFYROWDELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-421">Row First Change Notification</span><span class="sxs-lookup"><span data-stu-id="3e8dd-421">Row First Change Notification</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-422">DBPROP_NOTIFYROWFIRSTCHANGE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-422">DBPROP_NOTIFYROWFIRSTCHANGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-423">Row Insert Notification</span><span class="sxs-lookup"><span data-stu-id="3e8dd-423">Row Insert Notification</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-424">DBPROP_NOTIFYROWINSERT</span><span class="sxs-lookup"><span data-stu-id="3e8dd-424">DBPROP_NOTIFYROWINSERT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-425">Row Privileges</span><span class="sxs-lookup"><span data-stu-id="3e8dd-425">Row Privileges</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-426">DBPROP_ROWRESTRICT</span><span class="sxs-lookup"><span data-stu-id="3e8dd-426">DBPROP_ROWRESTRICT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-427">Row Resynchronization Notification</span><span class="sxs-lookup"><span data-stu-id="3e8dd-427">Row Resynchronization Notification</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-428">DBPROP_NOTIFYROWRESYNCH</span><span class="sxs-lookup"><span data-stu-id="3e8dd-428">DBPROP_NOTIFYROWRESYNCH</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-429">Row Threading Model</span><span class="sxs-lookup"><span data-stu-id="3e8dd-429">Row Threading Model</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-430">DBPROP_ROWTHREADMODEL</span><span class="sxs-lookup"><span data-stu-id="3e8dd-430">DBPROP_ROWTHREADMODEL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-431">Row Undo Change Notification</span><span class="sxs-lookup"><span data-stu-id="3e8dd-431">Row Undo Change Notification</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-432">DBPROP_NOTIFYROWUNDOCHANGE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-432">DBPROP_NOTIFYROWUNDOCHANGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-433">Row Undo Delete Notification</span><span class="sxs-lookup"><span data-stu-id="3e8dd-433">Row Undo Delete Notification</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-434">DBPROP_NOTIFYROWUNDODELETE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-434">DBPROP_NOTIFYROWUNDODELETE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-435">Row Undo Insert Notification</span><span class="sxs-lookup"><span data-stu-id="3e8dd-435">Row Undo Insert Notification</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-436">DBPROP_NOTIFYROWUNDOINSERT</span><span class="sxs-lookup"><span data-stu-id="3e8dd-436">DBPROP_NOTIFYROWUNDOINSERT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-437">Row Update Notification</span><span class="sxs-lookup"><span data-stu-id="3e8dd-437">Row Update Notification</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-438">DBPROP_NOTIFYROWUPDATE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-438">DBPROP_NOTIFYROWUPDATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-439">Rowset Fetch Position Change Notification</span><span class="sxs-lookup"><span data-stu-id="3e8dd-439">Rowset Fetch Position Change Notification</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-440">DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-440">DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-441">Rowset Release Notification</span><span class="sxs-lookup"><span data-stu-id="3e8dd-441">Rowset Release Notification</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-442">DBPROP_NOTIFYROWSETRELEASE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-442">DBPROP_NOTIFYROWSETRELEASE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-443">Scroll Backwards</span><span class="sxs-lookup"><span data-stu-id="3e8dd-443">Scroll Backwards</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-444">DBPROP_CANSCROLLBACKWARDS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-444">DBPROP_CANSCROLLBACKWARDS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-445">Server Cursor</span><span class="sxs-lookup"><span data-stu-id="3e8dd-445">Server Cursor</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-446">DBPROP_SERVERCURSOR</span><span class="sxs-lookup"><span data-stu-id="3e8dd-446">DBPROP_SERVERCURSOR</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-447">Skip Deleted Bookmarks</span><span class="sxs-lookup"><span data-stu-id="3e8dd-447">Skip Deleted Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-448">DBPROP_BOOKMARKSKIPPED</span><span class="sxs-lookup"><span data-stu-id="3e8dd-448">DBPROP_BOOKMARKSKIPPED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-449">Strong Row Identity</span><span class="sxs-lookup"><span data-stu-id="3e8dd-449">Strong Row Identity</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-450">DBPROP_STRONGIDENTITY</span><span class="sxs-lookup"><span data-stu-id="3e8dd-450">DBPROP_STRONGIDENTITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-451">Unique Catalog</span><span class="sxs-lookup"><span data-stu-id="3e8dd-451">Unique Catalog</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-452">DBPROP_ADC_UNIQUECATALOG</span><span class="sxs-lookup"><span data-stu-id="3e8dd-452">DBPROP_ADC_UNIQUECATALOG</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-453">Unique Rows</span><span class="sxs-lookup"><span data-stu-id="3e8dd-453">Unique Rows</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-454">DBPROP_UNIQUEROWS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-454">DBPROP_UNIQUEROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-455">Unique Schema</span><span class="sxs-lookup"><span data-stu-id="3e8dd-455">Unique Schema</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-456">DBPROP_ADC_UNIQUESCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e8dd-456">DBPROP_ADC_UNIQUESCHEMA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-457">Unique Table</span><span class="sxs-lookup"><span data-stu-id="3e8dd-457">Unique Table</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-458">DBPROP_ADC_UNIQUETABLE</span><span class="sxs-lookup"><span data-stu-id="3e8dd-458">DBPROP_ADC_UNIQUETABLE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-459">Updatability</span><span class="sxs-lookup"><span data-stu-id="3e8dd-459">Updatability</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-460">DBPROP_UPDATABILITY</span><span class="sxs-lookup"><span data-stu-id="3e8dd-460">DBPROP_UPDATABILITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-461">Update Criteria</span><span class="sxs-lookup"><span data-stu-id="3e8dd-461">Update Criteria</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-462">DBPROP_ADC_UPDATECRITERIA</span><span class="sxs-lookup"><span data-stu-id="3e8dd-462">DBPROP_ADC_UPDATECRITERIA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e8dd-463">Update Resync</span><span class="sxs-lookup"><span data-stu-id="3e8dd-463">Update Resync</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-464">DBPROP_ADC_UPDATERESYNC</span><span class="sxs-lookup"><span data-stu-id="3e8dd-464">DBPROP_ADC_UPDATERESYNC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e8dd-465">Use Bookmarks</span><span class="sxs-lookup"><span data-stu-id="3e8dd-465">Use Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="3e8dd-466">DBPROP_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="3e8dd-466">DBPROP_BOOKMARKS</span></span></p></td>
</tr>
</tbody>
</table>

