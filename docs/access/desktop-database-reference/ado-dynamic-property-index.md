---
title: ADO 动态属性索引
TOCTitle: ADO dynamic property index
ms:assetid: 437beced-b97a-894d-b08f-4a322629a5a6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249202(v=office.15)
ms:contentKeyID: 48544502
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2bfe788923d623300edac28f0f27534b3ffd8b32
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283399"
---
# <a name="ado-dynamic-property-index"></a><span data-ttu-id="070fd-102">ADO 动态属性索引</span><span class="sxs-lookup"><span data-stu-id="070fd-102">ADO dynamic property index</span></span>

<span data-ttu-id="070fd-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="070fd-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="070fd-p101">数据提供程序、服务提供程序及服务组件可以将动态属性添加到未打开的 **Connection** 和 [Recordset](connection-object-ado.md) 对象的 [Properties](recordset-object-ado.md) 集合中。打开这些对象时，给定的提供程序还可以插入其他属性。其中的一些属性在 [ADO 动态属性](ado-dynamic-properties.md) 一节中列出。更多其他属性在 [附录 A：提供程序](appendix-a-providers.md)一节的特定提供程序下列出。</span><span class="sxs-lookup"><span data-stu-id="070fd-p101">Data providers, service providers, and service components can add dynamic properties to the **Properties** collections of the unopened [Connection](connection-object-ado.md) and [Recordset](recordset-object-ado.md) objects. A given provider may also insert additional properties when these objects are opened. Some of these properties are listed in the [ADO Dynamic Properties](ado-dynamic-properties.md) section. More are listed under the specific providers in the [Appendix A: Providers](appendix-a-providers.md) section.</span></span>

<span data-ttu-id="070fd-p102">下表是每个标准 OLE DB 提供程序动态属性的 ADO 和 OLE DB 名称的交叉索引。除了此处列出的属性外，提供程序还可能添加更多的属性。有关提供程序特定动态属性的具体信息，请参阅提供程序文档。</span><span class="sxs-lookup"><span data-stu-id="070fd-p102">The table below is a cross-index of the ADO and OLE DB names for each standard OLE DB provider dynamic property. Your providers may add more properties than listed here. For the specific information about provider-specific dynamic properties, see your provider documentation.</span></span>

<span data-ttu-id="070fd-p103">《OLE DB 程序员参考》使用术语"说明"来引用 ADO 属性名。您可以在该书中找到有关这些标准属性的详细信息。请在"索引"中搜索 OLE DB 属性名或参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="070fd-p103">The OLE DB Programmer's Reference refers to an ADO property name by the term, "Description." You can find more information about these standard properties in the OLE DB Programmer's Reference. Search for the OLE DB property name in the Index or see the following topics:</span></span>

- <span data-ttu-id="070fd-114">附录 C：OLE DB 属性</span><span class="sxs-lookup"><span data-stu-id="070fd-114">Appendix C: OLE DB Properties</span></span>

- <span data-ttu-id="070fd-115">Cursor Service 支持的属性</span><span class="sxs-lookup"><span data-stu-id="070fd-115">Supported Properties of the Cursor Service</span></span>

- <span data-ttu-id="070fd-116">持久性提供程序支持的属性</span><span class="sxs-lookup"><span data-stu-id="070fd-116">Supported Properties of the Persistence Provider</span></span>

- <span data-ttu-id="070fd-117">远程提供程序支持的 OLE DB 属性</span><span class="sxs-lookup"><span data-stu-id="070fd-117">Supported OLE DB Properties of the Remoting Provider</span></span>

## <a name="remarks"></a><span data-ttu-id="070fd-118">注解</span><span class="sxs-lookup"><span data-stu-id="070fd-118">Remarks</span></span>

<span data-ttu-id="070fd-119">请注意交叉索引中使用的数字：</span><span class="sxs-lookup"><span data-stu-id="070fd-119">Note numbers used in the cross-index:</span></span>

<span data-ttu-id="070fd-p104">(1) 此属性是一个 Boolean 标志，指示是否应使用指定接口。将列出等效的 OLE DB 属性名（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="070fd-p104">(1) This property is a Boolean flag indicating whether the named interface should be used. The equivalent OLE DB property name is listed if it exists.</span></span>

<span data-ttu-id="070fd-122">(2) 在内部生成 "Bookmarkable" ADO 属性以实现向后兼容性, 并将其映射到 OLE DB 属性\_DBPROP IROWSETLOCATE。</span><span class="sxs-lookup"><span data-stu-id="070fd-122">(2) The "Bookmarkable" ADO property is generated internally for backwards compatibility, and is mapped to the OLE DB property, DBPROP\_IROWSETLOCATE.</span></span> <span data-ttu-id="070fd-123">此属性是与 ADO 属性 IRowsetLocate 对应的同一属性。</span><span class="sxs-lookup"><span data-stu-id="070fd-123">This is the same property that corresponds to the ADO property, IRowsetLocate.</span></span>

<span data-ttu-id="070fd-124">(3) ADO 属性名"Hidden Columns"的命名不同于 OLE DB 属性名说明"Hidden Columns Count"。</span><span class="sxs-lookup"><span data-stu-id="070fd-124">(3) The ADO property name, "Hidden Columns", is named differently than the OLE DB property name Description, "Hidden Columns Count."</span></span>

<span data-ttu-id="070fd-p106">(4) 对于分级记录集，"Maximum Rows"ADO 属性应用于所有的子记录集。根据行的返回顺序，结果集中的每个父记录集和孤立子记录集可能都具有子记录集，有一些具有子记录集，或者都没有子记录集。因此，重构分级记录集时，每个子记录集的标识符都应该是唯一的。一般情况下，[Microsoft Data Shaping Service for OLE DB (MSDATASHAPE)](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) 提供程序不考虑可从父记录集继承的属性与不能继承的属性间的区别。</span><span class="sxs-lookup"><span data-stu-id="070fd-p106">(4) For hierarchical recordsets, the "Maximum Rows" ADO property gets applied across all children. Depending on the order in which the rows are returned, you might have all, some or no children for each parent or orphaned children in the result set. Therefore, when reshaping hierarchical recordsets, the identifier for every child should be unique. In general, the [Microsoft Data Shaping Service for OLE DB (MSDATASHAPE)](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) provider does not allow for distinction between properties that can be inherited from the parent and those that cannot be inherited.</span></span>

<span data-ttu-id="070fd-129">(5) 不适用。</span><span class="sxs-lookup"><span data-stu-id="070fd-129">(5) Does not apply.</span></span>

<span data-ttu-id="070fd-130">**Connection 动态属性**</span><span class="sxs-lookup"><span data-stu-id="070fd-130">**Connection Dynamic Properties**</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="070fd-131">ADO 属性名</span><span class="sxs-lookup"><span data-stu-id="070fd-131">ADO Property Name</span></span></p></th>
<th><p><span data-ttu-id="070fd-132">OLE DB 属性名</span><span class="sxs-lookup"><span data-stu-id="070fd-132">OLE DB Property Name</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="070fd-133">Active Sessions</span><span class="sxs-lookup"><span data-stu-id="070fd-133">Active Sessions</span></span></p></td>
<td><p><span data-ttu-id="070fd-134">DBPROP_ACTIVESESSIONS</span><span class="sxs-lookup"><span data-stu-id="070fd-134">DBPROP_ACTIVESESSIONS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-135">Asynchable Abort</span><span class="sxs-lookup"><span data-stu-id="070fd-135">Asynchable Abort</span></span></p></td>
<td><p><span data-ttu-id="070fd-136">DBPROP_ASYNCTXNABORT</span><span class="sxs-lookup"><span data-stu-id="070fd-136">DBPROP_ASYNCTXNABORT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-137">Asynchable Commit</span><span class="sxs-lookup"><span data-stu-id="070fd-137">Asynchable Commit</span></span></p></td>
<td><p><span data-ttu-id="070fd-138">DBPROP_ASYNCTNXCOMMIT</span><span class="sxs-lookup"><span data-stu-id="070fd-138">DBPROP_ASYNCTNXCOMMIT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-139">Autocommit Isolation Levels</span><span class="sxs-lookup"><span data-stu-id="070fd-139">Autocommit Isolation Levels</span></span></p></td>
<td><p><span data-ttu-id="070fd-140">DBPROP_SESS_AUTOCOMMITISOLEVELS</span><span class="sxs-lookup"><span data-stu-id="070fd-140">DBPROP_SESS_AUTOCOMMITISOLEVELS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-141">Catalog Location</span><span class="sxs-lookup"><span data-stu-id="070fd-141">Catalog Location</span></span></p></td>
<td><p><span data-ttu-id="070fd-142">DBPROP_CATALOGLOCATION</span><span class="sxs-lookup"><span data-stu-id="070fd-142">DBPROP_CATALOGLOCATION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-143">Catalog Term</span><span class="sxs-lookup"><span data-stu-id="070fd-143">Catalog Term</span></span></p></td>
<td><p><span data-ttu-id="070fd-144">DBPROP_CATALOGTERM</span><span class="sxs-lookup"><span data-stu-id="070fd-144">DBPROP_CATALOGTERM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-145">Column Definition</span><span class="sxs-lookup"><span data-stu-id="070fd-145">Column Definition</span></span></p></td>
<td><p><span data-ttu-id="070fd-146">DBPROP_COLUMNDEFINITION</span><span class="sxs-lookup"><span data-stu-id="070fd-146">DBPROP_COLUMNDEFINITION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-147">Connect Timeout</span><span class="sxs-lookup"><span data-stu-id="070fd-147">Connect Timeout</span></span></p></td>
<td><p><span data-ttu-id="070fd-148">DBPROP_INIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="070fd-148">DBPROP_INIT_TIMEOUT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-149">Current Catalog</span><span class="sxs-lookup"><span data-stu-id="070fd-149">Current Catalog</span></span></p></td>
<td><p><span data-ttu-id="070fd-150">DBPROP_CURRENTCATALOG</span><span class="sxs-lookup"><span data-stu-id="070fd-150">DBPROP_CURRENTCATALOG</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-151">Data Source</span><span class="sxs-lookup"><span data-stu-id="070fd-151">Data Source</span></span></p></td>
<td><p><span data-ttu-id="070fd-152">DBPROP_INIT_DATASOURCE</span><span class="sxs-lookup"><span data-stu-id="070fd-152">DBPROP_INIT_DATASOURCE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-153">Data Source Name</span><span class="sxs-lookup"><span data-stu-id="070fd-153">Data Source Name</span></span></p></td>
<td><p><span data-ttu-id="070fd-154">DBPROP_DATASOURCENAME</span><span class="sxs-lookup"><span data-stu-id="070fd-154">DBPROP_DATASOURCENAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-155">Data Source Object Threading Model</span><span class="sxs-lookup"><span data-stu-id="070fd-155">Data Source Object Threading Model</span></span></p></td>
<td><p><span data-ttu-id="070fd-156">DBPROP_DSOTHREADMODEL</span><span class="sxs-lookup"><span data-stu-id="070fd-156">DBPROP_DSOTHREADMODEL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-157">DBMS Name</span><span class="sxs-lookup"><span data-stu-id="070fd-157">DBMS Name</span></span></p></td>
<td><p><span data-ttu-id="070fd-158">DBPROP_DBMSNAME</span><span class="sxs-lookup"><span data-stu-id="070fd-158">DBPROP_DBMSNAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-159">DBMS Version</span><span class="sxs-lookup"><span data-stu-id="070fd-159">DBMS Version</span></span></p></td>
<td><p><span data-ttu-id="070fd-160">DBPROP_DBMSVER</span><span class="sxs-lookup"><span data-stu-id="070fd-160">DBPROP_DBMSVER</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-161">Extended Properties</span><span class="sxs-lookup"><span data-stu-id="070fd-161">Extended Properties</span></span></p></td>
<td><p><span data-ttu-id="070fd-162">DBPROP_INIT_PROVIDERSTRING</span><span class="sxs-lookup"><span data-stu-id="070fd-162">DBPROP_INIT_PROVIDERSTRING</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-163">GROUP BY Support</span><span class="sxs-lookup"><span data-stu-id="070fd-163">GROUP BY Support</span></span></p></td>
<td><p><span data-ttu-id="070fd-164">DBPROP_GROUPBY</span><span class="sxs-lookup"><span data-stu-id="070fd-164">DBPROP_GROUPBY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-165">Heterogeneous Table Support</span><span class="sxs-lookup"><span data-stu-id="070fd-165">Heterogeneous Table Support</span></span></p></td>
<td><p><span data-ttu-id="070fd-166">DBPROP_HETEROGENEOUSTABLES</span><span class="sxs-lookup"><span data-stu-id="070fd-166">DBPROP_HETEROGENEOUSTABLES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-167">Identifier Case Sensitivity</span><span class="sxs-lookup"><span data-stu-id="070fd-167">Identifier Case Sensitivity</span></span></p></td>
<td><p><span data-ttu-id="070fd-168">DBPROP_IDENTIFIERCASE</span><span class="sxs-lookup"><span data-stu-id="070fd-168">DBPROP_IDENTIFIERCASE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-169">Initial Catalog</span><span class="sxs-lookup"><span data-stu-id="070fd-169">Initial Catalog</span></span></p></td>
<td><p><span data-ttu-id="070fd-170">DBPROP_INIT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="070fd-170">DBPROP_INIT_CATALOG</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-171">Isolation Levels</span><span class="sxs-lookup"><span data-stu-id="070fd-171">Isolation Levels</span></span></p></td>
<td><p><span data-ttu-id="070fd-172">DBPROP_SUPPORTEDTXNISOLEVELS</span><span class="sxs-lookup"><span data-stu-id="070fd-172">DBPROP_SUPPORTEDTXNISOLEVELS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-173">Isolation Retention</span><span class="sxs-lookup"><span data-stu-id="070fd-173">Isolation Retention</span></span></p></td>
<td><p><span data-ttu-id="070fd-174">DBPROP_SUPPORTEDTXNISORETAIN</span><span class="sxs-lookup"><span data-stu-id="070fd-174">DBPROP_SUPPORTEDTXNISORETAIN</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-175">Locale Identifier</span><span class="sxs-lookup"><span data-stu-id="070fd-175">Locale Identifier</span></span></p></td>
<td><p><span data-ttu-id="070fd-176">DBPROP_INIT_LCID</span><span class="sxs-lookup"><span data-stu-id="070fd-176">DBPROP_INIT_LCID</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-177">位置</span><span class="sxs-lookup"><span data-stu-id="070fd-177">Location</span></span></p></td>
<td><p><span data-ttu-id="070fd-178">DBPROP_INIT_LOCATION</span><span class="sxs-lookup"><span data-stu-id="070fd-178">DBPROP_INIT_LOCATION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-179">Maximum Index Size</span><span class="sxs-lookup"><span data-stu-id="070fd-179">Maximum Index Size</span></span></p></td>
<td><p><span data-ttu-id="070fd-180">DBPROP_MAXINDEXSIZE</span><span class="sxs-lookup"><span data-stu-id="070fd-180">DBPROP_MAXINDEXSIZE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-181">Maximum Row Size</span><span class="sxs-lookup"><span data-stu-id="070fd-181">Maximum Row Size</span></span></p></td>
<td><p><span data-ttu-id="070fd-182">DBPROP_MAXROWSIZE</span><span class="sxs-lookup"><span data-stu-id="070fd-182">DBPROP_MAXROWSIZE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-183">Maximum Row Size Includes BLOB</span><span class="sxs-lookup"><span data-stu-id="070fd-183">Maximum Row Size Includes BLOB</span></span></p></td>
<td><p><span data-ttu-id="070fd-184">DBPROP_MAXROWSIZEINCLUDESBLOB</span><span class="sxs-lookup"><span data-stu-id="070fd-184">DBPROP_MAXROWSIZEINCLUDESBLOB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-185">Maximum Tables in SELECT</span><span class="sxs-lookup"><span data-stu-id="070fd-185">Maximum Tables in SELECT</span></span></p></td>
<td><p><span data-ttu-id="070fd-186">DBPROP_MAXTABLESINSELECT</span><span class="sxs-lookup"><span data-stu-id="070fd-186">DBPROP_MAXTABLESINSELECT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-187">模式</span><span class="sxs-lookup"><span data-stu-id="070fd-187">Mode</span></span></p></td>
<td><p><span data-ttu-id="070fd-188">DBPROP_INIT_MODE</span><span class="sxs-lookup"><span data-stu-id="070fd-188">DBPROP_INIT_MODE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-189">Multiple Parameter Sets</span><span class="sxs-lookup"><span data-stu-id="070fd-189">Multiple Parameter Sets</span></span></p></td>
<td><p><span data-ttu-id="070fd-190">DBPROP_MULTIPLEPARAMSETS</span><span class="sxs-lookup"><span data-stu-id="070fd-190">DBPROP_MULTIPLEPARAMSETS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-191">Multiple Results</span><span class="sxs-lookup"><span data-stu-id="070fd-191">Multiple Results</span></span></p></td>
<td><p><span data-ttu-id="070fd-192">DBPROP_MULTIPLERESULTS</span><span class="sxs-lookup"><span data-stu-id="070fd-192">DBPROP_MULTIPLERESULTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-193">Multiple Storage Objects</span><span class="sxs-lookup"><span data-stu-id="070fd-193">Multiple Storage Objects</span></span></p></td>
<td><p><span data-ttu-id="070fd-194">DBPROP_MULTIPLESTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="070fd-194">DBPROP_MULTIPLESTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-195">Multi-Table Update</span><span class="sxs-lookup"><span data-stu-id="070fd-195">Multi-Table Update</span></span></p></td>
<td><p><span data-ttu-id="070fd-196">DBPROP_MULTITABLEUPDATE</span><span class="sxs-lookup"><span data-stu-id="070fd-196">DBPROP_MULTITABLEUPDATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-197">NULL Collation Order</span><span class="sxs-lookup"><span data-stu-id="070fd-197">NULL Collation Order</span></span></p></td>
<td><p><span data-ttu-id="070fd-198">DBPROP_NULLCOLLATION</span><span class="sxs-lookup"><span data-stu-id="070fd-198">DBPROP_NULLCOLLATION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-199">NULL Concatenation Behavior</span><span class="sxs-lookup"><span data-stu-id="070fd-199">NULL Concatenation Behavior</span></span></p></td>
<td><p><span data-ttu-id="070fd-200">DBPROP_CONCATNULLBEHAVIOR</span><span class="sxs-lookup"><span data-stu-id="070fd-200">DBPROP_CONCATNULLBEHAVIOR</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-201">OLE DB Services</span><span class="sxs-lookup"><span data-stu-id="070fd-201">OLE DB Services</span></span></p></td>
<td><p><span data-ttu-id="070fd-202">DBPROP_INIT_OLEDBSERVICES</span><span class="sxs-lookup"><span data-stu-id="070fd-202">DBPROP_INIT_OLEDBSERVICES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-203">OLE DB Version</span><span class="sxs-lookup"><span data-stu-id="070fd-203">OLE DB Version</span></span></p></td>
<td><p><span data-ttu-id="070fd-204">DBPROP_PROVIDEROLEDBVER</span><span class="sxs-lookup"><span data-stu-id="070fd-204">DBPROP_PROVIDEROLEDBVER</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-205">OLE Object Support</span><span class="sxs-lookup"><span data-stu-id="070fd-205">OLE Object Support</span></span></p></td>
<td><p><span data-ttu-id="070fd-206">DBPROP_OLEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="070fd-206">DBPROP_OLEOBJECTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-207">Open Rowset Support</span><span class="sxs-lookup"><span data-stu-id="070fd-207">Open Rowset Support</span></span></p></td>
<td><p><span data-ttu-id="070fd-208">DBPROP_OPENROWSETSUPPORT</span><span class="sxs-lookup"><span data-stu-id="070fd-208">DBPROP_OPENROWSETSUPPORT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-209">ORDER BY Columns in Select List</span><span class="sxs-lookup"><span data-stu-id="070fd-209">ORDER BY Columns in Select List</span></span></p></td>
<td><p><span data-ttu-id="070fd-210">DBPROP_ORDERBYCOLUMNSINSELECT</span><span class="sxs-lookup"><span data-stu-id="070fd-210">DBPROP_ORDERBYCOLUMNSINSELECT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-211">Output Parameter Availability</span><span class="sxs-lookup"><span data-stu-id="070fd-211">Output Parameter Availability</span></span></p></td>
<td><p><span data-ttu-id="070fd-212">DBPROP_OUTPUTPARAMETERAVAILABILITY</span><span class="sxs-lookup"><span data-stu-id="070fd-212">DBPROP_OUTPUTPARAMETERAVAILABILITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-213">Pass By Ref Accessors</span><span class="sxs-lookup"><span data-stu-id="070fd-213">Pass By Ref Accessors</span></span></p></td>
<td><p><span data-ttu-id="070fd-214">DBPROP_BYREFACCESSORS</span><span class="sxs-lookup"><span data-stu-id="070fd-214">DBPROP_BYREFACCESSORS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-215">Password</span><span class="sxs-lookup"><span data-stu-id="070fd-215">Password</span></span></p></td>
<td><p><span data-ttu-id="070fd-216">DBPROP_AUTH_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="070fd-216">DBPROP_AUTH_PASSWORD</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-217">Persist Security Info</span><span class="sxs-lookup"><span data-stu-id="070fd-217">Persist Security Info</span></span></p></td>
<td><p><span data-ttu-id="070fd-218">DBPROP_AUTH_PERSIST_SENSITIVE_AUTHINFO</span><span class="sxs-lookup"><span data-stu-id="070fd-218">DBPROP_AUTH_PERSIST_SENSITIVE_AUTHINFO</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-219">Persistent ID Type</span><span class="sxs-lookup"><span data-stu-id="070fd-219">Persistent ID Type</span></span></p></td>
<td><p><span data-ttu-id="070fd-220">DBPROP_PERSISTENTIDTYPE</span><span class="sxs-lookup"><span data-stu-id="070fd-220">DBPROP_PERSISTENTIDTYPE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-221">Prepare Abort Behavior</span><span class="sxs-lookup"><span data-stu-id="070fd-221">Prepare Abort Behavior</span></span></p></td>
<td><p><span data-ttu-id="070fd-222">DBPROP_PREPAREABORTBEHAVIOR</span><span class="sxs-lookup"><span data-stu-id="070fd-222">DBPROP_PREPAREABORTBEHAVIOR</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-223">Prepare Commit Behavior</span><span class="sxs-lookup"><span data-stu-id="070fd-223">Prepare Commit Behavior</span></span></p></td>
<td><p><span data-ttu-id="070fd-224">DBPROP_PREPARECOMMITBEHAVIOR</span><span class="sxs-lookup"><span data-stu-id="070fd-224">DBPROP_PREPARECOMMITBEHAVIOR</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-225">Procedure Term</span><span class="sxs-lookup"><span data-stu-id="070fd-225">Procedure Term</span></span></p></td>
<td><p><span data-ttu-id="070fd-226">DBPROP_PROCEDURETERM</span><span class="sxs-lookup"><span data-stu-id="070fd-226">DBPROP_PROCEDURETERM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-227">Prompt</span><span class="sxs-lookup"><span data-stu-id="070fd-227">Prompt</span></span></p></td>
<td><p><span data-ttu-id="070fd-228">DBPROP_INIT_PROMPT</span><span class="sxs-lookup"><span data-stu-id="070fd-228">DBPROP_INIT_PROMPT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-229">Provider Friendly Name</span><span class="sxs-lookup"><span data-stu-id="070fd-229">Provider Friendly Name</span></span></p></td>
<td><p><span data-ttu-id="070fd-230">DBPROP_PROVIDERFRIENDLYNAME</span><span class="sxs-lookup"><span data-stu-id="070fd-230">DBPROP_PROVIDERFRIENDLYNAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-231">Provider Name</span><span class="sxs-lookup"><span data-stu-id="070fd-231">Provider Name</span></span></p></td>
<td><p><span data-ttu-id="070fd-232">DBPROP_PROVIDERFILENAME</span><span class="sxs-lookup"><span data-stu-id="070fd-232">DBPROP_PROVIDERFILENAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-233">Provider Version</span><span class="sxs-lookup"><span data-stu-id="070fd-233">Provider Version</span></span></p></td>
<td><p><span data-ttu-id="070fd-234">DBPROP_PROVIDERVER</span><span class="sxs-lookup"><span data-stu-id="070fd-234">DBPROP_PROVIDERVER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-235">Read-Only Data Source</span><span class="sxs-lookup"><span data-stu-id="070fd-235">Read-Only Data Source</span></span></p></td>
<td><p><span data-ttu-id="070fd-236">DBPROP_DATASOURCEREADONLY</span><span class="sxs-lookup"><span data-stu-id="070fd-236">DBPROP_DATASOURCEREADONLY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-237">Rowset Conversions on Command</span><span class="sxs-lookup"><span data-stu-id="070fd-237">Rowset Conversions on Command</span></span></p></td>
<td><p><span data-ttu-id="070fd-238">DBPROP_ROWSETCONVERSIONSONCOMMAND</span><span class="sxs-lookup"><span data-stu-id="070fd-238">DBPROP_ROWSETCONVERSIONSONCOMMAND</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-239">Schema Term</span><span class="sxs-lookup"><span data-stu-id="070fd-239">Schema Term</span></span></p></td>
<td><p><span data-ttu-id="070fd-240">DBPROP_SCHEMATERM</span><span class="sxs-lookup"><span data-stu-id="070fd-240">DBPROP_SCHEMATERM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-241">Schema Usage</span><span class="sxs-lookup"><span data-stu-id="070fd-241">Schema Usage</span></span></p></td>
<td><p><span data-ttu-id="070fd-242">DBPROP_SCHEMAUSAGE</span><span class="sxs-lookup"><span data-stu-id="070fd-242">DBPROP_SCHEMAUSAGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-243">SQL Support</span><span class="sxs-lookup"><span data-stu-id="070fd-243">SQL Support</span></span></p></td>
<td><p><span data-ttu-id="070fd-244">DBPROP_SQLSUPPORT</span><span class="sxs-lookup"><span data-stu-id="070fd-244">DBPROP_SQLSUPPORT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-245">Structured Storage</span><span class="sxs-lookup"><span data-stu-id="070fd-245">Structured Storage</span></span></p></td>
<td><p><span data-ttu-id="070fd-246">DBPROP_STRUCTUREDSTORAGE</span><span class="sxs-lookup"><span data-stu-id="070fd-246">DBPROP_STRUCTUREDSTORAGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-247">Subquery Support</span><span class="sxs-lookup"><span data-stu-id="070fd-247">Subquery Support</span></span></p></td>
<td><p><span data-ttu-id="070fd-248">DBPROP_SUBQUERIES</span><span class="sxs-lookup"><span data-stu-id="070fd-248">DBPROP_SUBQUERIES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-249">Table Term</span><span class="sxs-lookup"><span data-stu-id="070fd-249">Table Term</span></span></p></td>
<td><p><span data-ttu-id="070fd-250">DBPROP_TABLETERM</span><span class="sxs-lookup"><span data-stu-id="070fd-250">DBPROP_TABLETERM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-251">Transaction DDL</span><span class="sxs-lookup"><span data-stu-id="070fd-251">Transaction DDL</span></span></p></td>
<td><p><span data-ttu-id="070fd-252">DBPROP_SUPPORTEDTXNDDL</span><span class="sxs-lookup"><span data-stu-id="070fd-252">DBPROP_SUPPORTEDTXNDDL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-253">User ID</span><span class="sxs-lookup"><span data-stu-id="070fd-253">User ID</span></span></p></td>
<td><p><span data-ttu-id="070fd-254">DBPROP_AUTH_USERID</span><span class="sxs-lookup"><span data-stu-id="070fd-254">DBPROP_AUTH_USERID</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-255">User Name</span><span class="sxs-lookup"><span data-stu-id="070fd-255">User Name</span></span></p></td>
<td><p><span data-ttu-id="070fd-256">DBPROP_USERNAME</span><span class="sxs-lookup"><span data-stu-id="070fd-256">DBPROP_USERNAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-257">Window Handle</span><span class="sxs-lookup"><span data-stu-id="070fd-257">Window Handle</span></span></p></td>
<td><p><span data-ttu-id="070fd-258">DBPROP_INIT_HWND</span><span class="sxs-lookup"><span data-stu-id="070fd-258">DBPROP_INIT_HWND</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="070fd-259">**Recordset 动态属性**</span><span class="sxs-lookup"><span data-stu-id="070fd-259">**Recordset Dynamic Properties**</span></span>

<span data-ttu-id="070fd-260">请注意，关闭 **Recordset** 时， **Recordset** 对象的 **动态属性** 将超出范围（不可用）。</span><span class="sxs-lookup"><span data-stu-id="070fd-260">Note that the **Dynamic Properties** of the **Recordset** object go out of scope (become unavailable) when the **Recordset** is closed.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="070fd-261">ADO 属性名</span><span class="sxs-lookup"><span data-stu-id="070fd-261">ADO Property Name</span></span></p></th>
<th><p><span data-ttu-id="070fd-262">OLE DB 属性名</span><span class="sxs-lookup"><span data-stu-id="070fd-262">OLE DB Property Name</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="070fd-263">IAccessor</span><span class="sxs-lookup"><span data-stu-id="070fd-263">IAccessor</span></span></p></td>
<td><p><span data-ttu-id="070fd-264">DBPROP_IACCESSOR (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-264">DBPROP_IACCESSOR (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-265">IChapteredRowset</span><span class="sxs-lookup"><span data-stu-id="070fd-265">IChapteredRowset</span></span></p></td>
<td><p><span data-ttu-id="070fd-266">1</span><span class="sxs-lookup"><span data-stu-id="070fd-266">(1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-267">IColumnsInfo</span><span class="sxs-lookup"><span data-stu-id="070fd-267">IColumnsInfo</span></span></p></td>
<td><p><span data-ttu-id="070fd-268">DBPROP_ICOLUMNSINFO (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-268">DBPROP_ICOLUMNSINFO (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-269">IColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="070fd-269">IColumnsRowset</span></span></p></td>
<td><p><span data-ttu-id="070fd-270">DBPROP_ICOLUMNSROWSET (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-270">DBPROP_ICOLUMNSROWSET (1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-271">IConnectionPointContainer</span><span class="sxs-lookup"><span data-stu-id="070fd-271">IConnectionPointContainer</span></span></p></td>
<td><p><span data-ttu-id="070fd-272">DBPROP_ICONNECTIONPOINTCONTAINER (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-272">DBPROP_ICONNECTIONPOINTCONTAINER (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-273">IConvertType</span><span class="sxs-lookup"><span data-stu-id="070fd-273">IConvertType</span></span></p></td>
<td><p><span data-ttu-id="070fd-274">1</span><span class="sxs-lookup"><span data-stu-id="070fd-274">(1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-275">ILockBytes</span><span class="sxs-lookup"><span data-stu-id="070fd-275">ILockBytes</span></span></p></td>
<td><p><span data-ttu-id="070fd-276">DBPROP_ILOCKBYTES (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-276">DBPROP_ILOCKBYTES (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-277">IRowset</span><span class="sxs-lookup"><span data-stu-id="070fd-277">IRowset</span></span></p></td>
<td><p><span data-ttu-id="070fd-278">DBPROP_IROWSET (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-278">DBPROP_IROWSET (1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-279">IDBAsynchStatus</span><span class="sxs-lookup"><span data-stu-id="070fd-279">IDBAsynchStatus</span></span></p></td>
<td><p><span data-ttu-id="070fd-280">DBPROP_IDBASYNCHSTATUS (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-280">DBPROP_IDBASYNCHSTATUS (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-281">IParentRowset</span><span class="sxs-lookup"><span data-stu-id="070fd-281">IParentRowset</span></span></p></td>
<td><p><span data-ttu-id="070fd-282">1</span><span class="sxs-lookup"><span data-stu-id="070fd-282">(1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-283">IRowsetChange</span><span class="sxs-lookup"><span data-stu-id="070fd-283">IRowsetChange</span></span></p></td>
<td><p><span data-ttu-id="070fd-284">DBPROP_IROWSETCHANGE (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-284">DBPROP_IROWSETCHANGE (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-285">IRowsetExactScroll</span><span class="sxs-lookup"><span data-stu-id="070fd-285">IRowsetExactScroll</span></span></p></td>
<td><p><span data-ttu-id="070fd-286">1</span><span class="sxs-lookup"><span data-stu-id="070fd-286">(1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-287">IRowsetFind</span><span class="sxs-lookup"><span data-stu-id="070fd-287">IRowsetFind</span></span></p></td>
<td><p><span data-ttu-id="070fd-288">DBPROP_IROWSETFIND (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-288">DBPROP_IROWSETFIND (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-289">IRowsetIdentity</span><span class="sxs-lookup"><span data-stu-id="070fd-289">IRowsetIdentity</span></span></p></td>
<td><p><span data-ttu-id="070fd-290">DBPROP_IROWSETIDENTITY (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-290">DBPROP_IROWSETIDENTITY (1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-291">IRowsetInfo</span><span class="sxs-lookup"><span data-stu-id="070fd-291">IRowsetInfo</span></span></p></td>
<td><p><span data-ttu-id="070fd-292">DBPROP_IROWSETINFO (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-292">DBPROP_IROWSETINFO (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-293">IRowsetLocate</span><span class="sxs-lookup"><span data-stu-id="070fd-293">IRowsetLocate</span></span></p></td>
<td><p><span data-ttu-id="070fd-294">DBPROP_IROWSETLOCATE (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-294">DBPROP_IROWSETLOCATE (1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-295">IRowsetRefresh</span><span class="sxs-lookup"><span data-stu-id="070fd-295">IRowsetRefresh</span></span></p></td>
<td><p><span data-ttu-id="070fd-296">DBPROP_IROWSETREFRESH (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-296">DBPROP_IROWSETREFRESH (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-297">IRowsetResynch</span><span class="sxs-lookup"><span data-stu-id="070fd-297">IRowsetResynch</span></span></p></td>
<td><p><span data-ttu-id="070fd-298">1</span><span class="sxs-lookup"><span data-stu-id="070fd-298">(1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-299">IRowsetScroll</span><span class="sxs-lookup"><span data-stu-id="070fd-299">IRowsetScroll</span></span></p></td>
<td><p><span data-ttu-id="070fd-300">DBPROP_IROWSETSCROLL (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-300">DBPROP_IROWSETSCROLL (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-301">IRowsetUpdate</span><span class="sxs-lookup"><span data-stu-id="070fd-301">IRowsetUpdate</span></span></p></td>
<td><p><span data-ttu-id="070fd-302">DBPROP_IROWSETUPDATE (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-302">DBPROP_IROWSETUPDATE (1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-303">IRowsetView</span><span class="sxs-lookup"><span data-stu-id="070fd-303">IRowsetView</span></span></p></td>
<td><p><span data-ttu-id="070fd-304">DBPROP_IROWSETVIEW (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-304">DBPROP_IROWSETVIEW (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-305">IRowsetIndex</span><span class="sxs-lookup"><span data-stu-id="070fd-305">IRowsetIndex</span></span></p></td>
<td><p><span data-ttu-id="070fd-306">DBPROP_IROWSETINDEX (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-306">DBPROP_IROWSETINDEX (1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-307">ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="070fd-307">ISequentialStream</span></span></p></td>
<td><p><span data-ttu-id="070fd-308">DBPROP_ISEQUENTIALSTREAM (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-308">DBPROP_ISEQUENTIALSTREAM (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-309">IStorage</span><span class="sxs-lookup"><span data-stu-id="070fd-309">IStorage</span></span></p></td>
<td><p><span data-ttu-id="070fd-310">DBPROP_ISTORAGE (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-310">DBPROP_ISTORAGE (1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-311">IStream</span><span class="sxs-lookup"><span data-stu-id="070fd-311">IStream</span></span></p></td>
<td><p><span data-ttu-id="070fd-312">DBPROP_ISTREAM (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-312">DBPROP_ISTREAM (1)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-313">ISupportErrorInfo</span><span class="sxs-lookup"><span data-stu-id="070fd-313">ISupportErrorInfo</span></span></p></td>
<td><p><span data-ttu-id="070fd-314">DBPROP_ISUPPORTERRORINFO (1)</span><span class="sxs-lookup"><span data-stu-id="070fd-314">DBPROP_ISUPPORTERRORINFO (1)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-315">Access Order</span><span class="sxs-lookup"><span data-stu-id="070fd-315">Access Order</span></span></p></td>
<td><p><span data-ttu-id="070fd-316">DBPROP_ACCESSORDER</span><span class="sxs-lookup"><span data-stu-id="070fd-316">DBPROP_ACCESSORDER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-317">Append-Only Rowset</span><span class="sxs-lookup"><span data-stu-id="070fd-317">Append-Only Rowset</span></span></p></td>
<td><p><span data-ttu-id="070fd-318">DBPROP_APPENDONLY</span><span class="sxs-lookup"><span data-stu-id="070fd-318">DBPROP_APPENDONLY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-319">Asynchronous Rowset Processing</span><span class="sxs-lookup"><span data-stu-id="070fd-319">Asynchronous Rowset Processing</span></span></p></td>
<td><p><span data-ttu-id="070fd-320">DBPROP_ROWSET_ASYNCH</span><span class="sxs-lookup"><span data-stu-id="070fd-320">DBPROP_ROWSET_ASYNCH</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-321">Auto Recalc</span><span class="sxs-lookup"><span data-stu-id="070fd-321">Auto Recalc</span></span></p></td>
<td><p><span data-ttu-id="070fd-322">DBPROP_ADC_AUTORECALC</span><span class="sxs-lookup"><span data-stu-id="070fd-322">DBPROP_ADC_AUTORECALC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-323">Background Fetch Size</span><span class="sxs-lookup"><span data-stu-id="070fd-323">Background Fetch Size</span></span></p></td>
<td><p><span data-ttu-id="070fd-324">DBPROP_ASYNCHFETCHSIZE</span><span class="sxs-lookup"><span data-stu-id="070fd-324">DBPROP_ASYNCHFETCHSIZE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-325">Background Thread Priority</span><span class="sxs-lookup"><span data-stu-id="070fd-325">Background Thread Priority</span></span></p></td>
<td><p><span data-ttu-id="070fd-326">DBPROP_ASYNCHTHREADPRIORITY</span><span class="sxs-lookup"><span data-stu-id="070fd-326">DBPROP_ASYNCHTHREADPRIORITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-327">Batch Size</span><span class="sxs-lookup"><span data-stu-id="070fd-327">Batch Size</span></span></p></td>
<td><p><span data-ttu-id="070fd-328">DBPROP_ADC_BATCHSIZE</span><span class="sxs-lookup"><span data-stu-id="070fd-328">DBPROP_ADC_BATCHSIZE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-329">Blocking Storage Objects</span><span class="sxs-lookup"><span data-stu-id="070fd-329">Blocking Storage Objects</span></span></p></td>
<td><p><span data-ttu-id="070fd-330">DBPROP_BLOCKINGSTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="070fd-330">DBPROP_BLOCKINGSTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-331">Bookmark Type</span><span class="sxs-lookup"><span data-stu-id="070fd-331">Bookmark Type</span></span></p></td>
<td><p><span data-ttu-id="070fd-332">DBPROP_BOOKMARKTYPE</span><span class="sxs-lookup"><span data-stu-id="070fd-332">DBPROP_BOOKMARKTYPE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-333">Bookmarkable</span><span class="sxs-lookup"><span data-stu-id="070fd-333">Bookmarkable</span></span></p></td>
<td><p><span data-ttu-id="070fd-334">DBPROP_IROWSETLOCATE (2)</span><span class="sxs-lookup"><span data-stu-id="070fd-334">DBPROP_IROWSETLOCATE (2)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-335">Bookmarks Ordered</span><span class="sxs-lookup"><span data-stu-id="070fd-335">Bookmarks Ordered</span></span></p></td>
<td><p><span data-ttu-id="070fd-336">DBPROP_ORDEREDBOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="070fd-336">DBPROP_ORDEREDBOOKMARKS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-337">Cache Child Rows</span><span class="sxs-lookup"><span data-stu-id="070fd-337">Cache Child Rows</span></span></p></td>
<td><p><span data-ttu-id="070fd-338">DBPROP_ADC_CACHECHILDROWS</span><span class="sxs-lookup"><span data-stu-id="070fd-338">DBPROP_ADC_CACHECHILDROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-339">Cache Deferred Columns</span><span class="sxs-lookup"><span data-stu-id="070fd-339">Cache Deferred Columns</span></span></p></td>
<td><p><span data-ttu-id="070fd-340">DBPROP_CACHEDEFERRED</span><span class="sxs-lookup"><span data-stu-id="070fd-340">DBPROP_CACHEDEFERRED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-341">Change Inserted Rows</span><span class="sxs-lookup"><span data-stu-id="070fd-341">Change Inserted Rows</span></span></p></td>
<td><p><span data-ttu-id="070fd-342">DBPROP_CHANGEINSERTEDROWS</span><span class="sxs-lookup"><span data-stu-id="070fd-342">DBPROP_CHANGEINSERTEDROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-343">Column Privileges</span><span class="sxs-lookup"><span data-stu-id="070fd-343">Column Privileges</span></span></p></td>
<td><p><span data-ttu-id="070fd-344">DBPROP_COLUMNRESTRICT</span><span class="sxs-lookup"><span data-stu-id="070fd-344">DBPROP_COLUMNRESTRICT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-345">Column Set Notification</span><span class="sxs-lookup"><span data-stu-id="070fd-345">Column Set Notification</span></span></p></td>
<td><p><span data-ttu-id="070fd-346">DBPROP_NOTIFYCOLUMNSET</span><span class="sxs-lookup"><span data-stu-id="070fd-346">DBPROP_NOTIFYCOLUMNSET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-347">Column Writable</span><span class="sxs-lookup"><span data-stu-id="070fd-347">Column Writable</span></span></p></td>
<td><p><span data-ttu-id="070fd-348">DBPROP_MAYWRITECOLUMN</span><span class="sxs-lookup"><span data-stu-id="070fd-348">DBPROP_MAYWRITECOLUMN</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-349">Command Time Out</span><span class="sxs-lookup"><span data-stu-id="070fd-349">Command Time Out</span></span></p></td>
<td><p><span data-ttu-id="070fd-350">DBPROP_COMMANDTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="070fd-350">DBPROP_COMMANDTIMEOUT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-351">Cursor Engine Version</span><span class="sxs-lookup"><span data-stu-id="070fd-351">Cursor Engine Version</span></span></p></td>
<td><p><span data-ttu-id="070fd-352">DBPROP_ADC_CEVER</span><span class="sxs-lookup"><span data-stu-id="070fd-352">DBPROP_ADC_CEVER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-353">Defer Column</span><span class="sxs-lookup"><span data-stu-id="070fd-353">Defer Column</span></span></p></td>
<td><p><span data-ttu-id="070fd-354">DBPROP_DEFERRED</span><span class="sxs-lookup"><span data-stu-id="070fd-354">DBPROP_DEFERRED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-355">Delay Storage Object Updates</span><span class="sxs-lookup"><span data-stu-id="070fd-355">Delay Storage Object Updates</span></span></p></td>
<td><p><span data-ttu-id="070fd-356">DBPROP_DELAYSTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="070fd-356">DBPROP_DELAYSTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-357">Fetch Backwards</span><span class="sxs-lookup"><span data-stu-id="070fd-357">Fetch Backwards</span></span></p></td>
<td><p><span data-ttu-id="070fd-358">DBPROP_CANFETCHBACKWARDS</span><span class="sxs-lookup"><span data-stu-id="070fd-358">DBPROP_CANFETCHBACKWARDS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-359">Filter Operations</span><span class="sxs-lookup"><span data-stu-id="070fd-359">Filter Operations</span></span></p></td>
<td><p><span data-ttu-id="070fd-360">DBPROP_FILTERCOMPAREOPS</span><span class="sxs-lookup"><span data-stu-id="070fd-360">DBPROP_FILTERCOMPAREOPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-361">Find Operations</span><span class="sxs-lookup"><span data-stu-id="070fd-361">Find Operations</span></span></p></td>
<td><p><span data-ttu-id="070fd-362">DBPROP_FINDCOMPAREOPS</span><span class="sxs-lookup"><span data-stu-id="070fd-362">DBPROP_FINDCOMPAREOPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-363">Hidden Columns (Count)</span><span class="sxs-lookup"><span data-stu-id="070fd-363">Hidden Columns (Count)</span></span></p></td>
<td><p><span data-ttu-id="070fd-364">DBPROP_HIDDENCOLUMNS (3)</span><span class="sxs-lookup"><span data-stu-id="070fd-364">DBPROP_HIDDENCOLUMNS (3)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-365">Hold Rows</span><span class="sxs-lookup"><span data-stu-id="070fd-365">Hold Rows</span></span></p></td>
<td><p><span data-ttu-id="070fd-366">DBPROP_CANHOLDROWS</span><span class="sxs-lookup"><span data-stu-id="070fd-366">DBPROP_CANHOLDROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-367">Immobile Rows</span><span class="sxs-lookup"><span data-stu-id="070fd-367">Immobile Rows</span></span></p></td>
<td><p><span data-ttu-id="070fd-368">DBPROP_IMMOBILEROWS</span><span class="sxs-lookup"><span data-stu-id="070fd-368">DBPROP_IMMOBILEROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-369">Initial Fetch Size</span><span class="sxs-lookup"><span data-stu-id="070fd-369">Initial Fetch Size</span></span></p></td>
<td><p><span data-ttu-id="070fd-370">DBPROP_ASYNCHPREFETCHSIZE</span><span class="sxs-lookup"><span data-stu-id="070fd-370">DBPROP_ASYNCHPREFETCHSIZE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-371">Literal Bookmarks</span><span class="sxs-lookup"><span data-stu-id="070fd-371">Literal Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="070fd-372">DBPROP_LITERALBOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="070fd-372">DBPROP_LITERALBOOKMARKS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-373">Literal Row Identity</span><span class="sxs-lookup"><span data-stu-id="070fd-373">Literal Row Identity</span></span></p></td>
<td><p><span data-ttu-id="070fd-374">DBPROP_LITERALIDENTITY</span><span class="sxs-lookup"><span data-stu-id="070fd-374">DBPROP_LITERALIDENTITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-375">Maintain Change Status</span><span class="sxs-lookup"><span data-stu-id="070fd-375">Maintain Change Status</span></span></p></td>
<td><p><span data-ttu-id="070fd-376">DBPROP_ADC_MAINTAINCHANGESTATUS</span><span class="sxs-lookup"><span data-stu-id="070fd-376">DBPROP_ADC_MAINTAINCHANGESTATUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-377">Maximum Open Rows</span><span class="sxs-lookup"><span data-stu-id="070fd-377">Maximum Open Rows</span></span></p></td>
<td><p><span data-ttu-id="070fd-378">DBPROP_MAXOPENROWS</span><span class="sxs-lookup"><span data-stu-id="070fd-378">DBPROP_MAXOPENROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-379">Maximum Pending Rows</span><span class="sxs-lookup"><span data-stu-id="070fd-379">Maximum Pending Rows</span></span></p></td>
<td><p><span data-ttu-id="070fd-380">DBPROP_MAXPENDINGROWS</span><span class="sxs-lookup"><span data-stu-id="070fd-380">DBPROP_MAXPENDINGROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-381">Maximum Rows</span><span class="sxs-lookup"><span data-stu-id="070fd-381">Maximum Rows</span></span></p></td>
<td><p><span data-ttu-id="070fd-382">DBPROP_MAXROWS (4)</span><span class="sxs-lookup"><span data-stu-id="070fd-382">DBPROP_MAXROWS (4)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-383">Memory Usage</span><span class="sxs-lookup"><span data-stu-id="070fd-383">Memory Usage</span></span></p></td>
<td><p><span data-ttu-id="070fd-384">DBPROP_MEMORYUSAGE</span><span class="sxs-lookup"><span data-stu-id="070fd-384">DBPROP_MEMORYUSAGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-385">Notification Granularity</span><span class="sxs-lookup"><span data-stu-id="070fd-385">Notification Granularity</span></span></p></td>
<td><p><span data-ttu-id="070fd-386">DBPROP_NOTIFICATIONGRANULARITY</span><span class="sxs-lookup"><span data-stu-id="070fd-386">DBPROP_NOTIFICATIONGRANULARITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-387">Notification Phases</span><span class="sxs-lookup"><span data-stu-id="070fd-387">Notification Phases</span></span></p></td>
<td><p><span data-ttu-id="070fd-388">DBPROP_NOTIFICATIONPHASES</span><span class="sxs-lookup"><span data-stu-id="070fd-388">DBPROP_NOTIFICATIONPHASES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-389">Objects Transacted</span><span class="sxs-lookup"><span data-stu-id="070fd-389">Objects Transacted</span></span></p></td>
<td><p><span data-ttu-id="070fd-390">DBPROP_TRANSACTEDOBJECT</span><span class="sxs-lookup"><span data-stu-id="070fd-390">DBPROP_TRANSACTEDOBJECT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-391">Others' Changes Visible</span><span class="sxs-lookup"><span data-stu-id="070fd-391">Others' Changes Visible</span></span></p></td>
<td><p><span data-ttu-id="070fd-392">DBPROP_OTHERUPDATEDELETE</span><span class="sxs-lookup"><span data-stu-id="070fd-392">DBPROP_OTHERUPDATEDELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-393">Others' Inserts Visible</span><span class="sxs-lookup"><span data-stu-id="070fd-393">Others' Inserts Visible</span></span></p></td>
<td><p><span data-ttu-id="070fd-394">DBPROP_OTHERINSERT</span><span class="sxs-lookup"><span data-stu-id="070fd-394">DBPROP_OTHERINSERT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-395">Own Changes Visible</span><span class="sxs-lookup"><span data-stu-id="070fd-395">Own Changes Visible</span></span></p></td>
<td><p><span data-ttu-id="070fd-396">DBPROP_OWNUPDATEDELETE</span><span class="sxs-lookup"><span data-stu-id="070fd-396">DBPROP_OWNUPDATEDELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-397">Own Inserts Visible</span><span class="sxs-lookup"><span data-stu-id="070fd-397">Own Inserts Visible</span></span></p></td>
<td><p><span data-ttu-id="070fd-398">DBPROP_OWNINSERT</span><span class="sxs-lookup"><span data-stu-id="070fd-398">DBPROP_OWNINSERT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-399">Preserve on Abort</span><span class="sxs-lookup"><span data-stu-id="070fd-399">Preserve on Abort</span></span></p></td>
<td><p><span data-ttu-id="070fd-400">DBPROP_ABORTPRESERVE</span><span class="sxs-lookup"><span data-stu-id="070fd-400">DBPROP_ABORTPRESERVE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-401">Preserve on Commit</span><span class="sxs-lookup"><span data-stu-id="070fd-401">Preserve on Commit</span></span></p></td>
<td><p><span data-ttu-id="070fd-402">DBPROP_COMMITPRESERVE</span><span class="sxs-lookup"><span data-stu-id="070fd-402">DBPROP_COMMITPRESERVE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-403">Private1</span><span class="sxs-lookup"><span data-stu-id="070fd-403">Private1</span></span></p></td>
<td><p><span data-ttu-id="070fd-404">5</span><span class="sxs-lookup"><span data-stu-id="070fd-404">(5)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-405">Quick Restart</span><span class="sxs-lookup"><span data-stu-id="070fd-405">Quick Restart</span></span></p></td>
<td><p><span data-ttu-id="070fd-406">DBPROP_QUICKRESTART</span><span class="sxs-lookup"><span data-stu-id="070fd-406">DBPROP_QUICKRESTART</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-407">Reentrant Events</span><span class="sxs-lookup"><span data-stu-id="070fd-407">Reentrant Events</span></span></p></td>
<td><p><span data-ttu-id="070fd-408">DBPROP_REENTRANTEVENTS</span><span class="sxs-lookup"><span data-stu-id="070fd-408">DBPROP_REENTRANTEVENTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-409">Remove Deleted Rows</span><span class="sxs-lookup"><span data-stu-id="070fd-409">Remove Deleted Rows</span></span></p></td>
<td><p><span data-ttu-id="070fd-410">DBPROP_REMOVEDELETED</span><span class="sxs-lookup"><span data-stu-id="070fd-410">DBPROP_REMOVEDELETED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-411">Report Multiple Changes</span><span class="sxs-lookup"><span data-stu-id="070fd-411">Report Multiple Changes</span></span></p></td>
<td><p><span data-ttu-id="070fd-412">DBPROP_REPORTMULTIPLECHANGES</span><span class="sxs-lookup"><span data-stu-id="070fd-412">DBPROP_REPORTMULTIPLECHANGES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-413">Reshape Name</span><span class="sxs-lookup"><span data-stu-id="070fd-413">Reshape Name</span></span></p></td>
<td><p><span data-ttu-id="070fd-414">DBPROP_ADC_RESHAPENAME</span><span class="sxs-lookup"><span data-stu-id="070fd-414">DBPROP_ADC_RESHAPENAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-415">Resync Command</span><span class="sxs-lookup"><span data-stu-id="070fd-415">Resync Command</span></span></p></td>
<td><p><span data-ttu-id="070fd-416">DBPROP_ADC_CUSTOMRESYNCH</span><span class="sxs-lookup"><span data-stu-id="070fd-416">DBPROP_ADC_CUSTOMRESYNCH</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-417">Return Pending Inserts</span><span class="sxs-lookup"><span data-stu-id="070fd-417">Return Pending Inserts</span></span></p></td>
<td><p><span data-ttu-id="070fd-418">DBPROP_RETURNPENDINGINSERTS</span><span class="sxs-lookup"><span data-stu-id="070fd-418">DBPROP_RETURNPENDINGINSERTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-419">Row Delete Notification</span><span class="sxs-lookup"><span data-stu-id="070fd-419">Row Delete Notification</span></span></p></td>
<td><p><span data-ttu-id="070fd-420">DBPROP_NOTIFYROWDELETE</span><span class="sxs-lookup"><span data-stu-id="070fd-420">DBPROP_NOTIFYROWDELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-421">Row First Change Notification</span><span class="sxs-lookup"><span data-stu-id="070fd-421">Row First Change Notification</span></span></p></td>
<td><p><span data-ttu-id="070fd-422">DBPROP_NOTIFYROWFIRSTCHANGE</span><span class="sxs-lookup"><span data-stu-id="070fd-422">DBPROP_NOTIFYROWFIRSTCHANGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-423">Row Insert Notification</span><span class="sxs-lookup"><span data-stu-id="070fd-423">Row Insert Notification</span></span></p></td>
<td><p><span data-ttu-id="070fd-424">DBPROP_NOTIFYROWINSERT</span><span class="sxs-lookup"><span data-stu-id="070fd-424">DBPROP_NOTIFYROWINSERT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-425">Row Privileges</span><span class="sxs-lookup"><span data-stu-id="070fd-425">Row Privileges</span></span></p></td>
<td><p><span data-ttu-id="070fd-426">DBPROP_ROWRESTRICT</span><span class="sxs-lookup"><span data-stu-id="070fd-426">DBPROP_ROWRESTRICT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-427">Row Resynchronization Notification</span><span class="sxs-lookup"><span data-stu-id="070fd-427">Row Resynchronization Notification</span></span></p></td>
<td><p><span data-ttu-id="070fd-428">DBPROP_NOTIFYROWRESYNCH</span><span class="sxs-lookup"><span data-stu-id="070fd-428">DBPROP_NOTIFYROWRESYNCH</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-429">Row Threading Model</span><span class="sxs-lookup"><span data-stu-id="070fd-429">Row Threading Model</span></span></p></td>
<td><p><span data-ttu-id="070fd-430">DBPROP_ROWTHREADMODEL</span><span class="sxs-lookup"><span data-stu-id="070fd-430">DBPROP_ROWTHREADMODEL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-431">Row Undo Change Notification</span><span class="sxs-lookup"><span data-stu-id="070fd-431">Row Undo Change Notification</span></span></p></td>
<td><p><span data-ttu-id="070fd-432">DBPROP_NOTIFYROWUNDOCHANGE</span><span class="sxs-lookup"><span data-stu-id="070fd-432">DBPROP_NOTIFYROWUNDOCHANGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-433">Row Undo Delete Notification</span><span class="sxs-lookup"><span data-stu-id="070fd-433">Row Undo Delete Notification</span></span></p></td>
<td><p><span data-ttu-id="070fd-434">DBPROP_NOTIFYROWUNDODELETE</span><span class="sxs-lookup"><span data-stu-id="070fd-434">DBPROP_NOTIFYROWUNDODELETE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-435">Row Undo Insert Notification</span><span class="sxs-lookup"><span data-stu-id="070fd-435">Row Undo Insert Notification</span></span></p></td>
<td><p><span data-ttu-id="070fd-436">DBPROP_NOTIFYROWUNDOINSERT</span><span class="sxs-lookup"><span data-stu-id="070fd-436">DBPROP_NOTIFYROWUNDOINSERT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-437">Row Update Notification</span><span class="sxs-lookup"><span data-stu-id="070fd-437">Row Update Notification</span></span></p></td>
<td><p><span data-ttu-id="070fd-438">DBPROP_NOTIFYROWUPDATE</span><span class="sxs-lookup"><span data-stu-id="070fd-438">DBPROP_NOTIFYROWUPDATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-439">Rowset Fetch Position Change Notification</span><span class="sxs-lookup"><span data-stu-id="070fd-439">Rowset Fetch Position Change Notification</span></span></p></td>
<td><p><span data-ttu-id="070fd-440">DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE</span><span class="sxs-lookup"><span data-stu-id="070fd-440">DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-441">Rowset Release Notification</span><span class="sxs-lookup"><span data-stu-id="070fd-441">Rowset Release Notification</span></span></p></td>
<td><p><span data-ttu-id="070fd-442">DBPROP_NOTIFYROWSETRELEASE</span><span class="sxs-lookup"><span data-stu-id="070fd-442">DBPROP_NOTIFYROWSETRELEASE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-443">Scroll Backwards</span><span class="sxs-lookup"><span data-stu-id="070fd-443">Scroll Backwards</span></span></p></td>
<td><p><span data-ttu-id="070fd-444">DBPROP_CANSCROLLBACKWARDS</span><span class="sxs-lookup"><span data-stu-id="070fd-444">DBPROP_CANSCROLLBACKWARDS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-445">Server Cursor</span><span class="sxs-lookup"><span data-stu-id="070fd-445">Server Cursor</span></span></p></td>
<td><p><span data-ttu-id="070fd-446">DBPROP_SERVERCURSOR</span><span class="sxs-lookup"><span data-stu-id="070fd-446">DBPROP_SERVERCURSOR</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-447">Skip Deleted Bookmarks</span><span class="sxs-lookup"><span data-stu-id="070fd-447">Skip Deleted Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="070fd-448">DBPROP_BOOKMARKSKIPPED</span><span class="sxs-lookup"><span data-stu-id="070fd-448">DBPROP_BOOKMARKSKIPPED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-449">Strong Row Identity</span><span class="sxs-lookup"><span data-stu-id="070fd-449">Strong Row Identity</span></span></p></td>
<td><p><span data-ttu-id="070fd-450">DBPROP_STRONGIDENTITY</span><span class="sxs-lookup"><span data-stu-id="070fd-450">DBPROP_STRONGIDENTITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-451">Unique Catalog</span><span class="sxs-lookup"><span data-stu-id="070fd-451">Unique Catalog</span></span></p></td>
<td><p><span data-ttu-id="070fd-452">DBPROP_ADC_UNIQUECATALOG</span><span class="sxs-lookup"><span data-stu-id="070fd-452">DBPROP_ADC_UNIQUECATALOG</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-453">Unique Rows</span><span class="sxs-lookup"><span data-stu-id="070fd-453">Unique Rows</span></span></p></td>
<td><p><span data-ttu-id="070fd-454">DBPROP_UNIQUEROWS</span><span class="sxs-lookup"><span data-stu-id="070fd-454">DBPROP_UNIQUEROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-455">Unique Schema</span><span class="sxs-lookup"><span data-stu-id="070fd-455">Unique Schema</span></span></p></td>
<td><p><span data-ttu-id="070fd-456">DBPROP_ADC_UNIQUESCHEMA</span><span class="sxs-lookup"><span data-stu-id="070fd-456">DBPROP_ADC_UNIQUESCHEMA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-457">Unique Table</span><span class="sxs-lookup"><span data-stu-id="070fd-457">Unique Table</span></span></p></td>
<td><p><span data-ttu-id="070fd-458">DBPROP_ADC_UNIQUETABLE</span><span class="sxs-lookup"><span data-stu-id="070fd-458">DBPROP_ADC_UNIQUETABLE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-459">Updatability</span><span class="sxs-lookup"><span data-stu-id="070fd-459">Updatability</span></span></p></td>
<td><p><span data-ttu-id="070fd-460">DBPROP_UPDATABILITY</span><span class="sxs-lookup"><span data-stu-id="070fd-460">DBPROP_UPDATABILITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-461">Update Criteria</span><span class="sxs-lookup"><span data-stu-id="070fd-461">Update Criteria</span></span></p></td>
<td><p><span data-ttu-id="070fd-462">DBPROP_ADC_UPDATECRITERIA</span><span class="sxs-lookup"><span data-stu-id="070fd-462">DBPROP_ADC_UPDATECRITERIA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="070fd-463">Update Resync</span><span class="sxs-lookup"><span data-stu-id="070fd-463">Update Resync</span></span></p></td>
<td><p><span data-ttu-id="070fd-464">DBPROP_ADC_UPDATERESYNC</span><span class="sxs-lookup"><span data-stu-id="070fd-464">DBPROP_ADC_UPDATERESYNC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="070fd-465">Use Bookmarks</span><span class="sxs-lookup"><span data-stu-id="070fd-465">Use Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="070fd-466">DBPROP_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="070fd-466">DBPROP_BOOKMARKS</span></span></p></td>
</tr>
</tbody>
</table>

