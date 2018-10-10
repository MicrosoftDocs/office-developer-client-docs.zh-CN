---
title: SchemaEnum （访问桌面数据库参考 （英文）
TOCTitle: SchemaEnum
ms:assetid: 6147b682-3c4f-ea91-fff6-ac73107d206d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249359(v=office.15)
ms:contentKeyID: 48545208
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e928271d61cf38232014db1c67482ca6d47fd863
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468569"
---
# <a name="schemaenum"></a><span data-ttu-id="16458-102">SchemaEnum</span><span class="sxs-lookup"><span data-stu-id="16458-102">SchemaEnum</span></span>


<span data-ttu-id="16458-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="16458-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="16458-104">用于指定 **OpenSchema** 方法检索的架构 [Recordset](openschema-method-ado.md) 的类型。</span><span class="sxs-lookup"><span data-stu-id="16458-104">Specifies the type of schema **Recordset** that the [OpenSchema](openschema-method-ado.md) method retrieves.</span></span>

<span data-ttu-id="16458-105">**备注**</span><span class="sxs-lookup"><span data-stu-id="16458-105">**Remarks**</span></span>

<span data-ttu-id="16458-p101">有关此函数以及为每个 ADO 常量返回的列的附加信息，请参阅 *《OLE DB 程序员参考》* 附录 B 中的主题。下表的“说明”部分的圆括号中列出了每个主题的名称。</span><span class="sxs-lookup"><span data-stu-id="16458-p101">Additional information about the function and columns returned for each ADO constant can be found in topics of Appendix B of the *OLE DB Programmers Reference*. The name of each topic is listed in parentheses in the Description section of the table below.</span></span>

<span data-ttu-id="16458-108">*OLE DB for OLAP*文档的第 23 章中的主题中，可以找到有关函数并为每个 ADO MD 常量返回的列的其他信息。</span><span class="sxs-lookup"><span data-stu-id="16458-108">Additional information about the function and columns returned for each ADO MD constant can be found in topics of Chapter 23 of the *OLE DB for OLAP* documentation.</span></span> <span data-ttu-id="16458-109">在括号中列出的每个主题名称并将其标有星号 (\*) 在说明列下表中。</span><span class="sxs-lookup"><span data-stu-id="16458-109">The name of each topic is listed in parentheses and marked with an asterisk (\*) in the Description column of the table below.</span></span>

<span data-ttu-id="16458-110">通过引用 ADO [DataTypeEnum](datatypeenum.md) 主题的"说明"列，将 OLE DB 文档中的列的数据类型转换为 ADO 数据类型。</span><span class="sxs-lookup"><span data-stu-id="16458-110">Translate the data types of columns in the OLE DB documentation to ADO data types by referring to the Description column of the ADO [DataTypeEnum](datatypeenum.md) topic.</span></span> <span data-ttu-id="16458-111">例如，OLE DB 数据类型的**DBTYPE\_WSTR**等效**adWChar**ADO 数据类型。</span><span class="sxs-lookup"><span data-stu-id="16458-111">For example, an OLE DB data type of **DBTYPE\_WSTR** is equivalent to an ADO data type of **adWChar**.</span></span>

<span data-ttu-id="16458-p104">对于常量 **adSchemaDBInfoKeywords** 和 **adSchemaDBInfoLiterals**，ADO 生成类似架构的结果。ADO 创建一个 **Recordset**，然后使用分别由 **IDBInfo::GetKeywords** 和 **IDBInfo::GetLiteralInfo** 方法返回的值填充每一行。有关这些方法的附加信息，请参阅 *《OLE DB 程序员参考》* 的“IDBInfo”部分。</span><span class="sxs-lookup"><span data-stu-id="16458-p104">ADO generates schema-like results for the constants, **adSchemaDBInfoKeywords** and **adSchemaDBInfoLiterals**. ADO creates a **Recordset**, then fills each row with the values returned respectively by the **IDBInfo::GetKeywords** and **IDBInfo::GetLiteralInfo** methods. Additional information about these methods can be found in the IDBInfo section of the *OLE DB Programmer's Reference.*</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="16458-115">常量</span><span class="sxs-lookup"><span data-stu-id="16458-115">Constant</span></span></p></th>
<th><p><span data-ttu-id="16458-116">值</span><span class="sxs-lookup"><span data-stu-id="16458-116">Value</span></span></p></th>
<th><p><span data-ttu-id="16458-117">说明</span><span class="sxs-lookup"><span data-stu-id="16458-117">Description</span></span></p></th>
<th><p><span data-ttu-id="16458-118">约束列</span><span class="sxs-lookup"><span data-stu-id="16458-118">Constraint Columns</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16458-119"><strong>adSchemaAsserts</strong></span><span class="sxs-lookup"><span data-stu-id="16458-119"><strong>adSchemaAsserts</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-120">0</span><span class="sxs-lookup"><span data-stu-id="16458-120">0</span></span></p></td>
<td><p><span data-ttu-id="16458-121">返回在目录中定义的、由指定用户拥有的声明。
</span><span class="sxs-lookup"><span data-stu-id="16458-121">Returns the assertions defined in the catalog that are owned by a given user.</span></span> <span data-ttu-id="16458-122">（ASSERTIONS 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-122">(ASSERTIONS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-123">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-123">CONSTRAINT_CATALOG</span></span><br />
<span data-ttu-id="16458-124">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-124">CONSTRAINT_SCHEMA</span></span><br />
<span data-ttu-id="16458-125">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-125">CONSTRAINT_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-126"><strong>adSchemaCatalogs</strong></span><span class="sxs-lookup"><span data-stu-id="16458-126"><strong>adSchemaCatalogs</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-127">1</span><span class="sxs-lookup"><span data-stu-id="16458-127">1</span></span></p></td>
<td><p><span data-ttu-id="16458-128">返回与目录关联的、可从 DBMS 访问的物理属性。
</span><span class="sxs-lookup"><span data-stu-id="16458-128">Returns the physical attributes associated with catalogs accessible from the DBMS.</span></span> <span data-ttu-id="16458-129">（CATALOGS 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-129">(CATALOGS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-130">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-130">CATALOG_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-131"><strong>adSchemaCharacterSets</strong></span><span class="sxs-lookup"><span data-stu-id="16458-131"><strong>adSchemaCharacterSets</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-132">2</span><span class="sxs-lookup"><span data-stu-id="16458-132">2</span></span></p></td>
<td><p><span data-ttu-id="16458-133">访问在目录中定义的、可供指定用户访问的字符集。
</span><span class="sxs-lookup"><span data-stu-id="16458-133">Returns the character sets defined in the catalog that are accessible to a given user.</span></span> <span data-ttu-id="16458-134">（CHARACTER_SETS 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-134">(CHARACTER_SETS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-135">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-135">CHARACTER_SET_CATALOG</span></span><br />
<span data-ttu-id="16458-136">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-136">CHARACTER_SET_SCHEMA</span></span><br />
<span data-ttu-id="16458-137">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-137">CHARACTER_SET_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-138"><strong>adSchemaCheckConstraints</strong></span><span class="sxs-lookup"><span data-stu-id="16458-138"><strong>adSchemaCheckConstraints</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-139">5</span><span class="sxs-lookup"><span data-stu-id="16458-139">5</span></span></p></td>
<td><p><span data-ttu-id="16458-140">返回在目录中定义的、由指定用户拥有的检查约束。
</span><span class="sxs-lookup"><span data-stu-id="16458-140">Returns the check constraints defined in the catalog that are owned by a given user.</span></span> <span data-ttu-id="16458-141">（CHECK_CONSTRAINTS 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-141">(CHECK_CONSTRAINTS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-142">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-142">CONSTRAINT_CATALOG</span></span><br />
<span data-ttu-id="16458-143">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-143">CONSTRAINT_SCHEMA</span></span><br />
<span data-ttu-id="16458-144">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-144">CONSTRAINT_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-145"><strong>adSchemaCollations</strong></span><span class="sxs-lookup"><span data-stu-id="16458-145"><strong>adSchemaCollations</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-146">3</span><span class="sxs-lookup"><span data-stu-id="16458-146">3</span></span></p></td>
<td><p><span data-ttu-id="16458-147">访问在目录中定义的、可供指定用户访问的字符排序规则。
</span><span class="sxs-lookup"><span data-stu-id="16458-147">Returns the character collations defined in the catalog that are accessible to a given user.</span></span> <span data-ttu-id="16458-148">（COLLATIONS 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-148">(COLLATIONS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-149">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-149">COLLATION_CATALOG</span></span><br />
<span data-ttu-id="16458-150">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-150">COLLATION_SCHEMA</span></span><br />
<span data-ttu-id="16458-151">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-151">COLLATION_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-152"><strong>adSchemaColumnPrivileges</strong></span><span class="sxs-lookup"><span data-stu-id="16458-152"><strong>adSchemaColumnPrivileges</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-153">13</span><span class="sxs-lookup"><span data-stu-id="16458-153">13</span></span></p></td>
<td><p><span data-ttu-id="16458-154">返回在目录中定义的、可用于指定用户或由指定用户授权的表列上的权限。
</span><span class="sxs-lookup"><span data-stu-id="16458-154">Returns the privileges on columns of tables defined in the catalog that are available to, or granted by, a given user.</span></span> <span data-ttu-id="16458-155">（COLUMN_PRIVILEGES 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-155">(COLUMN_PRIVILEGES Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-156">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-156">TABLE_CATALOG</span></span><br />
<span data-ttu-id="16458-157">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-157">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="16458-158">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-158">TABLE_NAME</span></span><br />
<span data-ttu-id="16458-159">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-159">COLUMN_NAME</span></span><br />
<span data-ttu-id="16458-160">授予或</span><span class="sxs-lookup"><span data-stu-id="16458-160">GRANTOR</span></span><br />
<span data-ttu-id="16458-161">被授予者</span><span class="sxs-lookup"><span data-stu-id="16458-161">GRANTEE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-162"><strong>adSchemaColumns</strong></span><span class="sxs-lookup"><span data-stu-id="16458-162"><strong>adSchemaColumns</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-163">4</span><span class="sxs-lookup"><span data-stu-id="16458-163">4</span></span></p></td>
<td><p><span data-ttu-id="16458-164">访问在目录中定义的、可供指定用户访问的表列（包括视图）。
</span><span class="sxs-lookup"><span data-stu-id="16458-164">Returns the columns of tables (including views) defined in the catalog that are accessible to a given user.</span></span> <span data-ttu-id="16458-165">（COLUMNS 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-165">(COLUMNS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-166">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-166">TABLE_CATALOG</span></span><br />
<span data-ttu-id="16458-167">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-167">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="16458-168">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-168">TABLE_NAME</span></span><br />
<span data-ttu-id="16458-169">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-169">COLUMN_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-170"><strong>adSchemaColumnsDomainUsage</strong></span><span class="sxs-lookup"><span data-stu-id="16458-170"><strong>adSchemaColumnsDomainUsage</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-171">11</span><span class="sxs-lookup"><span data-stu-id="16458-171">11</span></span></p></td>
<td><p><span data-ttu-id="16458-172">返回在目录中定义的、依赖在目录中定义的域且由指定用户拥有的列。
</span><span class="sxs-lookup"><span data-stu-id="16458-172">Returns the columns defined in the catalog that are dependent on a domain defined in the catalog and owned by a given user.</span></span> <span data-ttu-id="16458-173">（COLUMN_DOMAIN_USAGE 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-173">(COLUMN_DOMAIN_USAGE Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-174">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-174">DOMAIN_CATALOG</span></span><br />
<span data-ttu-id="16458-175">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-175">DOMAIN_SCHEMA</span></span><br />
<span data-ttu-id="16458-176">域名</span><span class="sxs-lookup"><span data-stu-id="16458-176">DOMAIN_NAME</span></span><br />
<span data-ttu-id="16458-177">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-177">COLUMN_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-178"><strong>adSchemaConstraintColumnUsage</strong></span><span class="sxs-lookup"><span data-stu-id="16458-178"><strong>adSchemaConstraintColumnUsage</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-179">6</span><span class="sxs-lookup"><span data-stu-id="16458-179">6</span></span></p></td>
<td><p><span data-ttu-id="16458-180">返回由在目录中定义的且由指定用户拥有的引用约束、唯一约束、检查约束和声明所使用的列。
</span><span class="sxs-lookup"><span data-stu-id="16458-180">Returns the columns used by referential constraints, unique constraints, check constraints, and assertions, defined in the catalog and owned by a given user.</span></span> <span data-ttu-id="16458-181">（CONSTRAINT_COLUMN_USAGE 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-181">(CONSTRAINT_COLUMN_USAGE Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-182">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-182">TABLE_CATALOG</span></span><br />
<span data-ttu-id="16458-183">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-183">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="16458-184">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-184">TABLE_NAME</span></span><br />
<span data-ttu-id="16458-185">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-185">COLUMN_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-186"><strong>adSchemaConstraintTableUsage</strong></span><span class="sxs-lookup"><span data-stu-id="16458-186"><strong>adSchemaConstraintTableUsage</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-187">7</span><span class="sxs-lookup"><span data-stu-id="16458-187">7</span></span></p></td>
<td><p><span data-ttu-id="16458-188">返回由在目录中定义的且由指定用户拥有的引用约束、唯一约束、检查约束和声明所使用的表。
</span><span class="sxs-lookup"><span data-stu-id="16458-188">Returns the tables that are used by referential constraints, unique constraints, check constraints, and assertions defined in the catalog and owned by a given user.</span></span> <span data-ttu-id="16458-189">（CONSTRAINT_TABLE_USAGE 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-189">(CONSTRAINT_TABLE_USAGE Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-190">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-190">TABLE_CATALOG</span></span><br />
<span data-ttu-id="16458-191">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-191">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="16458-192">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-192">TABLE_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-193"><strong>adSchemaCubes</strong></span><span class="sxs-lookup"><span data-stu-id="16458-193"><strong>adSchemaCubes</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-194">32</span><span class="sxs-lookup"><span data-stu-id="16458-194">32</span></span></p></td>
<td><p><span data-ttu-id="16458-195">返回有关架构（或目录，如果提供程序不支持架构）中的可用多维数据集的信息。
</span><span class="sxs-lookup"><span data-stu-id="16458-195">Returns information about the available cubes in a schema (or the catalog, if the provider does not support schemas).</span></span> <span data-ttu-id="16458-196">（CUBES 行集\*）</span><span class="sxs-lookup"><span data-stu-id="16458-196">(CUBES Rowset\*)</span></span></p></td>
<td><p><span data-ttu-id="16458-197">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-197">CATALOG_NAME</span></span><br />
<span data-ttu-id="16458-198">SCHEMA_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-198">SCHEMA_NAME</span></span><br />
<span data-ttu-id="16458-199">CUBE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-199">CUBE_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-200"><strong>adSchemaDBInfoKeywords</strong></span><span class="sxs-lookup"><span data-stu-id="16458-200"><strong>adSchemaDBInfoKeywords</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-201">30</span><span class="sxs-lookup"><span data-stu-id="16458-201">30</span></span></p></td>
<td><p><span data-ttu-id="16458-202">返回提供程序特定的关键字列表。
</span><span class="sxs-lookup"><span data-stu-id="16458-202">Returns a list of provider-specific keywords.</span></span> <span data-ttu-id="16458-203">(IDBInfo::GetKeywords \*)</span><span class="sxs-lookup"><span data-stu-id="16458-203">(IDBInfo::GetKeywords \*)</span></span></p></td>
<td><p><span data-ttu-id="16458-204">&lt;无&gt;</span><span class="sxs-lookup"><span data-stu-id="16458-204">&lt;None&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-205"><strong>adSchemaDBInfoLiterals</strong></span><span class="sxs-lookup"><span data-stu-id="16458-205"><strong>adSchemaDBInfoLiterals</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-206">31</span><span class="sxs-lookup"><span data-stu-id="16458-206">31</span></span></p></td>
<td><p><span data-ttu-id="16458-207">返回文本命令中使用的提供程序特定的文字列表。
</span><span class="sxs-lookup"><span data-stu-id="16458-207">Returns a list of provider-specific literals used in text commands.</span></span> <span data-ttu-id="16458-208">(IDBInfo::GetLiteralInfo \*)</span><span class="sxs-lookup"><span data-stu-id="16458-208">(IDBInfo::GetLiteralInfo \*)</span></span></p></td>
<td><p><span data-ttu-id="16458-209">&lt;无&gt;</span><span class="sxs-lookup"><span data-stu-id="16458-209">&lt;None&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-210"><strong>adSchemaDimensions</strong></span><span class="sxs-lookup"><span data-stu-id="16458-210"><strong>adSchemaDimensions</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-211">33</span><span class="sxs-lookup"><span data-stu-id="16458-211">33</span></span></p></td>
<td><p><span data-ttu-id="16458-212">在给定的多维数据集中返回信息尺寸。</span><span class="sxs-lookup"><span data-stu-id="16458-212">Returns information about the dimensions in a given cube.</span></span> <span data-ttu-id="16458-213">具有为每个维度的一行。</span><span class="sxs-lookup"><span data-stu-id="16458-213">It has one row for each dimension.</span></span> <span data-ttu-id="16458-214">（DIMENSIONS 行集\*）</span><span class="sxs-lookup"><span data-stu-id="16458-214">(DIMENSIONS Rowset \*)</span></span></p></td>
<td><p><span data-ttu-id="16458-215">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-215">CATALOG_NAME</span></span><br />
<span data-ttu-id="16458-216">SCHEMA_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-216">SCHEMA_NAME</span></span><br />
<span data-ttu-id="16458-217">CUBE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-217">CUBE_NAME</span></span><br />
<span data-ttu-id="16458-218">DIMENSION_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-218">DIMENSION_NAME</span></span><br />
<span data-ttu-id="16458-219">DIMENSION_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-219">DIMENSION_UNIQUE_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-220"><strong>adSchemaForeignKeys</strong></span><span class="sxs-lookup"><span data-stu-id="16458-220"><strong>adSchemaForeignKeys</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-221">27</span><span class="sxs-lookup"><span data-stu-id="16458-221">27</span></span></p></td>
<td><p><span data-ttu-id="16458-222">返回由指定用户在目录中定义的外键列。
</span><span class="sxs-lookup"><span data-stu-id="16458-222">Returns the foreign key columns defined in the catalog by a given user.</span></span> <span data-ttu-id="16458-223">（FOREIGN_KEYS 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-223">(FOREIGN_KEYS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-224">PK_TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-224">PK_TABLE_CATALOG</span></span><br />
<span data-ttu-id="16458-225">PK_TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-225">PK_TABLE_SCHEMA</span></span><br />
<span data-ttu-id="16458-226">PK_TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-226">PK_TABLE_NAME</span></span><br />
<span data-ttu-id="16458-227">FK_TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-227">FK_TABLE_CATALOG</span></span><br />
<span data-ttu-id="16458-228">FK_TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-228">FK_TABLE_SCHEMA</span></span><br />
<span data-ttu-id="16458-229">FK_TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-229">FK_TABLE_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-230"><strong>adSchemaHierarchies</strong></span><span class="sxs-lookup"><span data-stu-id="16458-230"><strong>adSchemaHierarchies</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-231">34</span><span class="sxs-lookup"><span data-stu-id="16458-231">34</span></span></p></td>
<td><p><span data-ttu-id="16458-232">返回有关维中可用的层次结构的信息。
</span><span class="sxs-lookup"><span data-stu-id="16458-232">Returns information about the hierarchies available in a dimension.</span></span> <span data-ttu-id="16458-233">（HIERARCHIES 行集\*）</span><span class="sxs-lookup"><span data-stu-id="16458-233">(HIERARCHIES Rowset \*)</span></span></p></td>
<td><p><span data-ttu-id="16458-234">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-234">CATALOG_NAME</span></span><br />
<span data-ttu-id="16458-235">SCHEMA_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-235">SCHEMA_NAME</span></span><br />
<span data-ttu-id="16458-236">CUBE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-236">CUBE_NAME</span></span><br />
<span data-ttu-id="16458-237">DIMENSION_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-237">DIMENSION_UNIQUE_NAME</span></span><br />
<span data-ttu-id="16458-238">HIERARCHY_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-238">HIERARCHY_NAME</span></span><br />
<span data-ttu-id="16458-239">HIERARCHY_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-239">HIERARCHY_UNIQUE_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-240"><strong>adSchemaIndexes</strong></span><span class="sxs-lookup"><span data-stu-id="16458-240"><strong>adSchemaIndexes</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-241">12</span><span class="sxs-lookup"><span data-stu-id="16458-241">12</span></span></p></td>
<td><p><span data-ttu-id="16458-242">返回在目录中定义的由指定用户拥有的索引。
</span><span class="sxs-lookup"><span data-stu-id="16458-242">Returns the indexes defined in the catalog that are owned by a given user.</span></span> <span data-ttu-id="16458-243">（INDEXES 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-243">(INDEXES Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-244">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-244">TABLE_CATALOG</span></span><br />
<span data-ttu-id="16458-245">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-245">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="16458-246">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-246">INDEX_NAME</span></span><br />
<span data-ttu-id="16458-247">类型</span><span class="sxs-lookup"><span data-stu-id="16458-247">TYPE</span></span><br />
<span data-ttu-id="16458-248">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-248">TABLE_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-249"><strong>adSchemaKeyColumnUsage</strong></span><span class="sxs-lookup"><span data-stu-id="16458-249"><strong>adSchemaKeyColumnUsage</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-250">8</span><span class="sxs-lookup"><span data-stu-id="16458-250">8</span></span></p></td>
<td><p><span data-ttu-id="16458-251">返回在目录中定义的、由指定用户约束为键的列。
</span><span class="sxs-lookup"><span data-stu-id="16458-251">Returns the columns defined in the catalog that are constrained as keys by a given user.</span></span> <span data-ttu-id="16458-252">（KEY_COLUMN_USAGE Rowset 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-252">(KEY_COLUMN_USAGE Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-253">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-253">CONSTRAINT_CATALOG</span></span><br />
<span data-ttu-id="16458-254">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-254">CONSTRAINT_SCHEMA</span></span><br />
<span data-ttu-id="16458-255">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-255">CONSTRAINT_NAME</span></span><br />
<span data-ttu-id="16458-256">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-256">TABLE_CATALOG</span></span><br />
<span data-ttu-id="16458-257">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-257">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="16458-258">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-258">TABLE_NAME</span></span><br />
<span data-ttu-id="16458-259">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-259">COLUMN_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-260"><strong>adSchemaLevels</strong></span><span class="sxs-lookup"><span data-stu-id="16458-260"><strong>adSchemaLevels</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-261">35</span><span class="sxs-lookup"><span data-stu-id="16458-261">35</span></span></p></td>
<td><p><span data-ttu-id="16458-262">返回有关维中可用的级别的信息。
</span><span class="sxs-lookup"><span data-stu-id="16458-262">Returns information about the levels available in a dimension.</span></span> <span data-ttu-id="16458-263">（LEVELS 行集\*）</span><span class="sxs-lookup"><span data-stu-id="16458-263">(LEVELS Rowset\*)</span></span></p></td>
<td><p><span data-ttu-id="16458-264">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-264">CATALOG_NAME</span></span><br />
<span data-ttu-id="16458-265">SCHEMA_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-265">SCHEMA_NAME</span></span><br />
<span data-ttu-id="16458-266">CUBE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-266">CUBE_NAME</span></span><br />
<span data-ttu-id="16458-267">DIMENSION_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-267">DIMENSION_UNIQUE_NAME</span></span><br />
<span data-ttu-id="16458-268">HIERARCHY_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-268">HIERARCHY_UNIQUE_NAME</span></span><br />
<span data-ttu-id="16458-269">LEVEL_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-269">LEVEL_NAME</span></span><br />
<span data-ttu-id="16458-270">LEVEL_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-270">LEVEL_UNIQUE_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-271"><strong>adSchemaMeasures</strong></span><span class="sxs-lookup"><span data-stu-id="16458-271"><strong>adSchemaMeasures</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-272">36</span><span class="sxs-lookup"><span data-stu-id="16458-272">36</span></span></p></td>
<td><p><span data-ttu-id="16458-273">返回有关可用度量的信息。
</span><span class="sxs-lookup"><span data-stu-id="16458-273">Returns information about the available measures.</span></span> <span data-ttu-id="16458-274">（MEASURES 行集\*）</span><span class="sxs-lookup"><span data-stu-id="16458-274">(MEASURES Rowset \*)</span></span></p></td>
<td><p><span data-ttu-id="16458-275">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-275">CATALOG_NAME</span></span><br />
<span data-ttu-id="16458-276">SCHEMA_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-276">SCHEMA_NAME</span></span><br />
<span data-ttu-id="16458-277">CUBE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-277">CUBE_NAME</span></span><br />
<span data-ttu-id="16458-278">MEASURE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-278">MEASURE_NAME</span></span><br />
<span data-ttu-id="16458-279">MEASURE_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-279">MEASURE_UNIQUE_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-280"><strong>adSchemaMembers</strong></span><span class="sxs-lookup"><span data-stu-id="16458-280"><strong>adSchemaMembers</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-281">38</span><span class="sxs-lookup"><span data-stu-id="16458-281">38</span></span></p></td>
<td><p><span data-ttu-id="16458-282">返回有关可用成员的信息。
</span><span class="sxs-lookup"><span data-stu-id="16458-282">Returns information about the available members.</span></span> <span data-ttu-id="16458-283">（MEMBERS 行集\*）</span><span class="sxs-lookup"><span data-stu-id="16458-283">(MEMBERS Rowset \*)</span></span></p></td>
<td><p><span data-ttu-id="16458-284">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-284">CATALOG_NAME</span></span><br />
<span data-ttu-id="16458-285">SCHEMA_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-285">SCHEMA_NAME</span></span><br />
<span data-ttu-id="16458-286">CUBE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-286">CUBE_NAME</span></span><br />
<span data-ttu-id="16458-287">DIMENSION_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-287">DIMENSION_UNIQUE_NAME</span></span><br />
<span data-ttu-id="16458-288">HIERARCHY_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-288">HIERARCHY_UNIQUE_NAME</span></span><br />
<span data-ttu-id="16458-289">LEVEL_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-289">LEVEL_UNIQUE_NAME</span></span><br />
<span data-ttu-id="16458-290">LEVEL_NUMBER</span><span class="sxs-lookup"><span data-stu-id="16458-290">LEVEL_NUMBER</span></span><br />
<span data-ttu-id="16458-291">MEMBER_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-291">MEMBER_NAME</span></span><br />
<span data-ttu-id="16458-292">MEMBER_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-292">MEMBER_UNIQUE_NAME</span></span><br />
<span data-ttu-id="16458-293">MEMBER_CAPTION</span><span class="sxs-lookup"><span data-stu-id="16458-293">MEMBER_CAPTION</span></span><br />
<span data-ttu-id="16458-294">MEMBER_TYPE</span><span class="sxs-lookup"><span data-stu-id="16458-294">MEMBER_TYPE</span></span><br />
<span data-ttu-id="16458-295">树运算符 （有关详细信息，请参阅 OLE DB for OLAP 文档）。</span><span class="sxs-lookup"><span data-stu-id="16458-295">Tree operator (For more information, see the OLE DB for OLAP documentation.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-296"><strong>adSchemaPrimaryKeys</strong></span><span class="sxs-lookup"><span data-stu-id="16458-296"><strong>adSchemaPrimaryKeys</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-297">28</span><span class="sxs-lookup"><span data-stu-id="16458-297">28</span></span></p></td>
<td><p><span data-ttu-id="16458-298">返回由指定用户在目录中定义的主键列。
</span><span class="sxs-lookup"><span data-stu-id="16458-298">Returns the primary key columns defined in the catalog by a given user.</span></span> <span data-ttu-id="16458-299">（PRIMARY_KEYS 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-299">(PRIMARY_KEYS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-300">PK_TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-300">PK_TABLE_CATALOG</span></span><br />
<span data-ttu-id="16458-301">PK_TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-301">PK_TABLE_SCHEMA</span></span><br />
<span data-ttu-id="16458-302">PK_TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-302">PK_TABLE_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-303"><strong>adSchemaProcedureColumns</strong></span><span class="sxs-lookup"><span data-stu-id="16458-303"><strong>adSchemaProcedureColumns</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-304">29</span><span class="sxs-lookup"><span data-stu-id="16458-304">29</span></span></p></td>
<td><p><span data-ttu-id="16458-305">返回由过程返回的行集的列的信息。
</span><span class="sxs-lookup"><span data-stu-id="16458-305">Returns information about the columns of rowsets returned by procedures.</span></span> <span data-ttu-id="16458-306">（PROCEDURE_COLUMNS 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-306">(PROCEDURE_COLUMNS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-307">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-307">PROCEDURE_CATALOG</span></span><br />
<span data-ttu-id="16458-308">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-308">PROCEDURE_SCHEMA</span></span><br />
<span data-ttu-id="16458-309">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-309">PROCEDURE_NAME</span></span><br />
<span data-ttu-id="16458-310">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-310">COLUMN_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-311"><strong>adSchemaProcedureParameters</strong></span><span class="sxs-lookup"><span data-stu-id="16458-311"><strong>adSchemaProcedureParameters</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-312">26</span><span class="sxs-lookup"><span data-stu-id="16458-312">26</span></span></p></td>
<td><p><span data-ttu-id="16458-313">返回有关过程的参数和返回代码的信息。
</span><span class="sxs-lookup"><span data-stu-id="16458-313">Returns information about the parameters and return codes of procedures.</span></span> <span data-ttu-id="16458-314">（PROCEDURE_PARAMETERS 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-314">(PROCEDURE_PARAMETERS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-315">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-315">PROCEDURE_CATALOG</span></span><br />
<span data-ttu-id="16458-316">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-316">PROCEDURE_SCHEMA</span></span><br />
<span data-ttu-id="16458-317">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-317">PROCEDURE_NAME</span></span><br />
<span data-ttu-id="16458-318">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-318">PARAMETER_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-319"><strong>adSchemaProcedures</strong></span><span class="sxs-lookup"><span data-stu-id="16458-319"><strong>adSchemaProcedures</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-320">16</span><span class="sxs-lookup"><span data-stu-id="16458-320">16</span></span></p></td>
<td><p><span data-ttu-id="16458-321">返回在目录中定义的、由指定用户拥有的过程。
</span><span class="sxs-lookup"><span data-stu-id="16458-321">Returns the procedures defined in the catalog that are owned by a given user.</span></span> <span data-ttu-id="16458-322">（PROCEDURES 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-322">(PROCEDURES Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-323">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-323">PROCEDURE_CATALOG</span></span><br />
<span data-ttu-id="16458-324">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-324">PROCEDURE_SCHEMA</span></span><br />
<span data-ttu-id="16458-325">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-325">PROCEDURE_NAME</span></span><br />
<span data-ttu-id="16458-326">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="16458-326">PROCEDURE_TYPE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-327"><strong>adSchemaProperties</strong></span><span class="sxs-lookup"><span data-stu-id="16458-327"><strong>adSchemaProperties</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-328">37</span><span class="sxs-lookup"><span data-stu-id="16458-328">37</span></span></p></td>
<td><p><span data-ttu-id="16458-329">返回有关维的每个级别的可用属性的信息。
</span><span class="sxs-lookup"><span data-stu-id="16458-329">Returns information about the available properties for each level of the dimension.</span></span> <span data-ttu-id="16458-330">（PROPERTIES 行集\*）</span><span class="sxs-lookup"><span data-stu-id="16458-330">(PROPERTIES Rowset \*)</span></span></p></td>
<td><p><span data-ttu-id="16458-331">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-331">CATALOG_NAME</span></span><br />
<span data-ttu-id="16458-332">SCHEMA_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-332">SCHEMA_NAME</span></span><br />
<span data-ttu-id="16458-333">CUBE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-333">CUBE_NAME</span></span><br />
<span data-ttu-id="16458-334">DIMENSION_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-334">DIMENSION_UNIQUE_NAME</span></span><br />
<span data-ttu-id="16458-335">HIERARCHY_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-335">HIERARCHY_UNIQUE_NAME</span></span><br />
<span data-ttu-id="16458-336">LEVEL_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-336">LEVEL_UNIQUE_NAME</span></span><br />
<span data-ttu-id="16458-337">MEMBER_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-337">MEMBER_UNIQUE_NAME</span></span><br />
<span data-ttu-id="16458-338">PROPERTY_TYPE</span><span class="sxs-lookup"><span data-stu-id="16458-338">PROPERTY_TYPE</span></span><br />
<span data-ttu-id="16458-339">PROPERTY_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-339">PROPERTY_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-340"><strong>adSchemaProviderSpecific</strong></span><span class="sxs-lookup"><span data-stu-id="16458-340"><strong>adSchemaProviderSpecific</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-341">-1</span><span class="sxs-lookup"><span data-stu-id="16458-341">-1</span></span></p></td>
<td><p><span data-ttu-id="16458-342">当提供程序定义其自己的非标准架构查询时使用。</span><span class="sxs-lookup"><span data-stu-id="16458-342">Used if the provider defines its own nonstandard schema queries.</span></span></p></td>
<td><p><span data-ttu-id="16458-343">&lt;特定提供程序&gt;</span><span class="sxs-lookup"><span data-stu-id="16458-343">&lt;Provider specific&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-344"><strong>adSchemaProviderTypes</strong></span><span class="sxs-lookup"><span data-stu-id="16458-344"><strong>adSchemaProviderTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-345">22</span><span class="sxs-lookup"><span data-stu-id="16458-345">22</span></span></p></td>
<td><p><span data-ttu-id="16458-346">返回数据提供程序支持的（基础）数据类型。
</span><span class="sxs-lookup"><span data-stu-id="16458-346">Returns the (base) data types supported by the data provider.</span></span> <span data-ttu-id="16458-347">（PROVIDER_TYPES 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-347">(PROVIDER_TYPES Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-348">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="16458-348">DATA_TYPE</span></span><br />
<span data-ttu-id="16458-349">BEST_MATCH</span><span class="sxs-lookup"><span data-stu-id="16458-349">BEST_MATCH</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-350"><strong>AdSchemaReferentialConstraints</strong></span><span class="sxs-lookup"><span data-stu-id="16458-350"><strong>AdSchemaReferentialConstraints</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-351">9</span><span class="sxs-lookup"><span data-stu-id="16458-351">9</span></span></p></td>
<td><p><span data-ttu-id="16458-352">返回在目录中定义的、由指定用户拥有的引用约束。
</span><span class="sxs-lookup"><span data-stu-id="16458-352">Returns the referential constraints defined in the catalog that are owned by a given user.</span></span> <span data-ttu-id="16458-353">（REFERENTIAL_CONSTRAINTS 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-353">(REFERENTIAL_CONSTRAINTS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-354">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-354">CONSTRAINT_CATALOG</span></span><br />
<span data-ttu-id="16458-355">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-355">CONSTRAINT_SCHEMA</span></span><br />
<span data-ttu-id="16458-356">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-356">CONSTRAINT_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-357"><strong>adSchemaSchemata</strong></span><span class="sxs-lookup"><span data-stu-id="16458-357"><strong>adSchemaSchemata</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-358">17</span><span class="sxs-lookup"><span data-stu-id="16458-358">17</span></span></p></td>
<td><p><span data-ttu-id="16458-359">返回由指定用户拥有的架构（数据库对象）。
</span><span class="sxs-lookup"><span data-stu-id="16458-359">Returns the schemas (database objects) that are owned by a given user.</span></span> <span data-ttu-id="16458-360">（SCHEMATA 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-360">(SCHEMATA Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-361">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-361">CATALOG_NAME</span></span><br />
<span data-ttu-id="16458-362">SCHEMA_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-362">SCHEMA_NAME</span></span><br />
<span data-ttu-id="16458-363">SCHEMA_OWNER</span><span class="sxs-lookup"><span data-stu-id="16458-363">SCHEMA_OWNER</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-364"><strong>adSchemaSQLLanguages</strong></span><span class="sxs-lookup"><span data-stu-id="16458-364"><strong>adSchemaSQLLanguages</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-365">18</span><span class="sxs-lookup"><span data-stu-id="16458-365">18</span></span></p></td>
<td><p><span data-ttu-id="16458-366">返回由目录中定义的 SQL 实现处理数据支持的一致性级别、选项和语句编写。
</span><span class="sxs-lookup"><span data-stu-id="16458-366">Returns the conformance levels, options, and dialects supported by the SQL-implementation processing data defined in the catalog.</span></span> <span data-ttu-id="16458-367">（SQL_LANGUAGES 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-367">(SQL_LANGUAGES Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-368">&lt;无&gt;</span><span class="sxs-lookup"><span data-stu-id="16458-368">&lt;None&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-369"><strong>adSchemaStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="16458-369"><strong>adSchemaStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-370">19</span><span class="sxs-lookup"><span data-stu-id="16458-370">19</span></span></p></td>
<td><p><span data-ttu-id="16458-371">返回在目录中定义的、由指定用户拥有的统计信息。
</span><span class="sxs-lookup"><span data-stu-id="16458-371">Returns the statistics defined in the catalog that are owned by a given user.</span></span> <span data-ttu-id="16458-372">（STATISTICS 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-372">(STATISTICS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-373">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-373">TABLE_CATALOG</span></span><br />
<span data-ttu-id="16458-374">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-374">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="16458-375">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-375">TABLE_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-376"><strong>adSchemaTableConstraints</strong></span><span class="sxs-lookup"><span data-stu-id="16458-376"><strong>adSchemaTableConstraints</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-377">10</span><span class="sxs-lookup"><span data-stu-id="16458-377">10</span></span></p></td>
<td><p><span data-ttu-id="16458-378">返回在目录中定义的、由指定用户拥有的表约束。
</span><span class="sxs-lookup"><span data-stu-id="16458-378">Returns the table constraints defined in the catalog that are owned by a given user.</span></span> <span data-ttu-id="16458-379">（TABLE_CONSTRAINTS 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-379">(TABLE_CONSTRAINTS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-380">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-380">CONSTRAINT_CATALOG</span></span><br />
<span data-ttu-id="16458-381">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-381">CONSTRAINT_SCHEMA</span></span><br />
<span data-ttu-id="16458-382">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-382">CONSTRAINT_NAME</span></span><br />
<span data-ttu-id="16458-383">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-383">TABLE_CATALOG</span></span><br />
<span data-ttu-id="16458-384">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-384">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="16458-385">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-385">TABLE_NAME</span></span><br />
<span data-ttu-id="16458-386">CONSTRAINT_TYPE</span><span class="sxs-lookup"><span data-stu-id="16458-386">CONSTRAINT_TYPE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-387"><strong>adSchemaTablePrivileges</strong></span><span class="sxs-lookup"><span data-stu-id="16458-387"><strong>adSchemaTablePrivileges</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-388">14</span><span class="sxs-lookup"><span data-stu-id="16458-388">14</span></span></p></td>
<td><p><span data-ttu-id="16458-389">返回在目录中定义的、可用于指定用户或由指定用户授权的表上的权限。
</span><span class="sxs-lookup"><span data-stu-id="16458-389">Returns the privileges on tables defined in the catalog that are available to, or granted by, a given user.</span></span> <span data-ttu-id="16458-390">（TABLE_PRIVILEGES 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-390">(TABLE_PRIVILEGES Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-391">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-391">TABLE_CATALOG</span></span><br />
<span data-ttu-id="16458-392">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-392">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="16458-393">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-393">TABLE_NAME</span></span><br />
<span data-ttu-id="16458-394">授予或</span><span class="sxs-lookup"><span data-stu-id="16458-394">GRANTOR</span></span><br />
<span data-ttu-id="16458-395">被授予者</span><span class="sxs-lookup"><span data-stu-id="16458-395">GRANTEE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-396"><strong>adSchemaTables</strong></span><span class="sxs-lookup"><span data-stu-id="16458-396"><strong>adSchemaTables</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-397">20</span><span class="sxs-lookup"><span data-stu-id="16458-397">20</span></span></p></td>
<td><p><span data-ttu-id="16458-398">返回在目录中定义的、可供指定用户访问的表（包括视图）。
</span><span class="sxs-lookup"><span data-stu-id="16458-398">Returns the tables (including views) defined in the catalog that are accessible to a given user.</span></span> <span data-ttu-id="16458-399">（TABLES 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-399">(TABLES Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-400">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-400">TABLE_CATALOG</span></span><br />
<span data-ttu-id="16458-401">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-401">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="16458-402">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-402">TABLE_NAME</span></span><br />
<span data-ttu-id="16458-403">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="16458-403">TABLE_TYPE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-404"><strong>adSchemaTranslations</strong></span><span class="sxs-lookup"><span data-stu-id="16458-404"><strong>adSchemaTranslations</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-405">21</span><span class="sxs-lookup"><span data-stu-id="16458-405">21</span></span></p></td>
<td><p><span data-ttu-id="16458-406">返回在目录中定义的、可供指定用户访问的字符转换。
</span><span class="sxs-lookup"><span data-stu-id="16458-406">Returns the character translations defined in the catalog that are accessible to a given user.</span></span> <span data-ttu-id="16458-407">（TRANSLATIONS 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-407">(TRANSLATIONS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-408">TRANSLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-408">TRANSLATION_CATALOG</span></span><br />
<span data-ttu-id="16458-409">TRANSLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-409">TRANSLATION_SCHEMA</span></span><br />
<span data-ttu-id="16458-410">TRANSLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-410">TRANSLATION_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-411"><strong>adSchemaTrustees</strong></span><span class="sxs-lookup"><span data-stu-id="16458-411"><strong>adSchemaTrustees</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-412">39</span><span class="sxs-lookup"><span data-stu-id="16458-412">39</span></span></p></td>
<td><p><span data-ttu-id="16458-413">保留以备将来使用。</span><span class="sxs-lookup"><span data-stu-id="16458-413">Reserved for future use.</span></span></p></td>
<td><p><br />
</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-414"><strong>adSchemaUsagePrivileges</strong></span><span class="sxs-lookup"><span data-stu-id="16458-414"><strong>adSchemaUsagePrivileges</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-415">15</span><span class="sxs-lookup"><span data-stu-id="16458-415">15</span></span></p></td>
<td><p><span data-ttu-id="16458-416">返回在目录中定义的、可用于指定用户或由指定用户授权的对象上的 USAGE 权限。
</span><span class="sxs-lookup"><span data-stu-id="16458-416">Returns the USAGE privileges on objects defined in the catalog that are available to, or granted by, a given user.</span></span> <span data-ttu-id="16458-417">（USAGE_PRIVILEGES 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-417">(USAGE_PRIVILEGES Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-418">OBJECT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-418">OBJECT_CATALOG</span></span><br />
<span data-ttu-id="16458-419">OBJECT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-419">OBJECT_SCHEMA</span></span><br />
<span data-ttu-id="16458-420">对象名称用于</span><span class="sxs-lookup"><span data-stu-id="16458-420">OBJECT_NAME</span></span><br />
<span data-ttu-id="16458-421">对象类型</span><span class="sxs-lookup"><span data-stu-id="16458-421">OBJECT_TYPE</span></span><br />
<span data-ttu-id="16458-422">授予或</span><span class="sxs-lookup"><span data-stu-id="16458-422">GRANTOR</span></span><br />
<span data-ttu-id="16458-423">被授予者</span><span class="sxs-lookup"><span data-stu-id="16458-423">GRANTEE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-424"><strong>adSchemaViewColumnUsage</strong></span><span class="sxs-lookup"><span data-stu-id="16458-424"><strong>adSchemaViewColumnUsage</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-425">24</span><span class="sxs-lookup"><span data-stu-id="16458-425">24</span></span></p></td>
<td><p><span data-ttu-id="16458-426">返回在目录中定义的、由指定用户拥有的被查看表所依赖的列。
</span><span class="sxs-lookup"><span data-stu-id="16458-426">Returns the columns on which viewed tables, defined in the catalog and owned by a given user, are dependent.</span></span> <span data-ttu-id="16458-427">（VIEW_COLUMN_USAGE 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-427">(VIEW_COLUMN_USAGE Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-428">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-428">VIEW_CATALOG</span></span><br />
<span data-ttu-id="16458-429">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-429">VIEW_SCHEMA</span></span><br />
<span data-ttu-id="16458-430">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-430">VIEW_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-431"><strong>adSchemaViews</strong></span><span class="sxs-lookup"><span data-stu-id="16458-431"><strong>adSchemaViews</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-432">23</span><span class="sxs-lookup"><span data-stu-id="16458-432">23</span></span></p></td>
<td><p><span data-ttu-id="16458-433">访问在目录中定义的、可供指定用户访问的视图。
</span><span class="sxs-lookup"><span data-stu-id="16458-433">Returns the views defined in the catalog that are accessible to a given user.</span></span> <span data-ttu-id="16458-434">（VIEWS 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-434">(VIEWS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-435">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-435">TABLE_CATALOG</span></span><br />
<span data-ttu-id="16458-436">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-436">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="16458-437">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-437">TABLE_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-438"><strong>adSchemaViewTableUsage</strong></span><span class="sxs-lookup"><span data-stu-id="16458-438"><strong>adSchemaViewTableUsage</strong></span></span></p></td>
<td><p><span data-ttu-id="16458-439">25</span><span class="sxs-lookup"><span data-stu-id="16458-439">25</span></span></p></td>
<td><p><span data-ttu-id="16458-440">返回在目录中定义的、由指定用户拥有的被查看表所依赖的表。
</span><span class="sxs-lookup"><span data-stu-id="16458-440">Returns the tables on which viewed tables, defined in the catalog and owned by a given user, are dependent.</span></span> <span data-ttu-id="16458-441">（VIEW_TABLE_USAGE 行集）</span><span class="sxs-lookup"><span data-stu-id="16458-441">(VIEW_TABLE_USAGE Rowset)</span></span></p></td>
<td><p><span data-ttu-id="16458-442">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="16458-442">VIEW_CATALOG</span></span><br />
<span data-ttu-id="16458-443">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="16458-443">VIEW_SCHEMA</span></span><br />
<span data-ttu-id="16458-444">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="16458-444">VIEW_NAME</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="16458-445">**ADO/WFC 等效值**</span><span class="sxs-lookup"><span data-stu-id="16458-445">**ADO/WFC Equivalent**</span></span>

<span data-ttu-id="16458-446">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="16458-446">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="16458-447">常量</span><span class="sxs-lookup"><span data-stu-id="16458-447">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16458-448">AdoEnums.Schema.ASSERTS</span><span class="sxs-lookup"><span data-stu-id="16458-448">AdoEnums.Schema.ASSERTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-449">AdoEnums.Schema.CATALOGS</span><span class="sxs-lookup"><span data-stu-id="16458-449">AdoEnums.Schema.CATALOGS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-450">AdoEnums.Schema.CHARACTERSETS</span><span class="sxs-lookup"><span data-stu-id="16458-450">AdoEnums.Schema.CHARACTERSETS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-451">AdoEnums.Schema.CHECKCONSTRAINTS</span><span class="sxs-lookup"><span data-stu-id="16458-451">AdoEnums.Schema.CHECKCONSTRAINTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-452">AdoEnums.Schema.COLLATIONS</span><span class="sxs-lookup"><span data-stu-id="16458-452">AdoEnums.Schema.COLLATIONS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-453">AdoEnums.Schema.COLUMNPRIVILEGES</span><span class="sxs-lookup"><span data-stu-id="16458-453">AdoEnums.Schema.COLUMNPRIVILEGES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-454">AdoEnums.Schema.COLUMNS</span><span class="sxs-lookup"><span data-stu-id="16458-454">AdoEnums.Schema.COLUMNS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-455">AdoEnums.Schema.COLUMNSDOMAINUSAGE</span><span class="sxs-lookup"><span data-stu-id="16458-455">AdoEnums.Schema.COLUMNSDOMAINUSAGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-456">AdoEnums.Schema.CONSTRAINTCOLUMNUSAGE</span><span class="sxs-lookup"><span data-stu-id="16458-456">AdoEnums.Schema.CONSTRAINTCOLUMNUSAGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-457">AdoEnums.Schema.CONSTRAINTTABLEUSAGE</span><span class="sxs-lookup"><span data-stu-id="16458-457">AdoEnums.Schema.CONSTRAINTTABLEUSAGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-458">AdoEnums.Schema.CUBES</span><span class="sxs-lookup"><span data-stu-id="16458-458">AdoEnums.Schema.CUBES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-459">AdoEnums.Schema.DBINFOKEYWORDS</span><span class="sxs-lookup"><span data-stu-id="16458-459">AdoEnums.Schema.DBINFOKEYWORDS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-460">AdoEnums.Schema.DBINFOLITERALS</span><span class="sxs-lookup"><span data-stu-id="16458-460">AdoEnums.Schema.DBINFOLITERALS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-461">AdoEnums.Schema.DIMENSIONS</span><span class="sxs-lookup"><span data-stu-id="16458-461">AdoEnums.Schema.DIMENSIONS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-462">AdoEnums.Schema.FOREIGNKEYS</span><span class="sxs-lookup"><span data-stu-id="16458-462">AdoEnums.Schema.FOREIGNKEYS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-463">AdoEnums.Schema.HIERARCHIES</span><span class="sxs-lookup"><span data-stu-id="16458-463">AdoEnums.Schema.HIERARCHIES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-464">AdoEnums.Schema.INDEXES</span><span class="sxs-lookup"><span data-stu-id="16458-464">AdoEnums.Schema.INDEXES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-465">AdoEnums.Schema.KEYCOLUMNUSAGE</span><span class="sxs-lookup"><span data-stu-id="16458-465">AdoEnums.Schema.KEYCOLUMNUSAGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-466">AdoEnums.Schema.LEVELS</span><span class="sxs-lookup"><span data-stu-id="16458-466">AdoEnums.Schema.LEVELS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-467">AdoEnums.Schema.MEASURES</span><span class="sxs-lookup"><span data-stu-id="16458-467">AdoEnums.Schema.MEASURES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-468">AdoEnums.Schema.MEMBERS</span><span class="sxs-lookup"><span data-stu-id="16458-468">AdoEnums.Schema.MEMBERS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-469">AdoEnums.Schema.PRIMARYKEYS</span><span class="sxs-lookup"><span data-stu-id="16458-469">AdoEnums.Schema.PRIMARYKEYS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-470">AdoEnums.Schema.PROCEDURECOLUMNS</span><span class="sxs-lookup"><span data-stu-id="16458-470">AdoEnums.Schema.PROCEDURECOLUMNS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-471">AdoEnums.Schema.PROCEDUREPARAMETERS</span><span class="sxs-lookup"><span data-stu-id="16458-471">AdoEnums.Schema.PROCEDUREPARAMETERS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-472">AdoEnums.Schema.PROCEDURES</span><span class="sxs-lookup"><span data-stu-id="16458-472">AdoEnums.Schema.PROCEDURES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-473">AdoEnums.Schema.PROPERTIES</span><span class="sxs-lookup"><span data-stu-id="16458-473">AdoEnums.Schema.PROPERTIES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-474">AdoEnums.Schema.PROVIDERSPECIFIC</span><span class="sxs-lookup"><span data-stu-id="16458-474">AdoEnums.Schema.PROVIDERSPECIFIC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-475">AdoEnums.Schema.PROVIDERTYPES</span><span class="sxs-lookup"><span data-stu-id="16458-475">AdoEnums.Schema.PROVIDERTYPES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-476">AdoEnums.Schema.REFERENTIALCONTRAINTS</span><span class="sxs-lookup"><span data-stu-id="16458-476">AdoEnums.Schema.REFERENTIALCONTRAINTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-477">AdoEnums.Schema.SCHEMATA</span><span class="sxs-lookup"><span data-stu-id="16458-477">AdoEnums.Schema.SCHEMATA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-478">AdoEnums.Schema.SQLLANGUAGES</span><span class="sxs-lookup"><span data-stu-id="16458-478">AdoEnums.Schema.SQLLANGUAGES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-479">AdoEnums.Schema.STATISTICS</span><span class="sxs-lookup"><span data-stu-id="16458-479">AdoEnums.Schema.STATISTICS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-480">AdoEnums.Schema.TABLECONSTRAINTS</span><span class="sxs-lookup"><span data-stu-id="16458-480">AdoEnums.Schema.TABLECONSTRAINTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-481">AdoEnums.Schema.TABLEPRIVILEGES</span><span class="sxs-lookup"><span data-stu-id="16458-481">AdoEnums.Schema.TABLEPRIVILEGES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-482">AdoEnums.Schema.TABLES</span><span class="sxs-lookup"><span data-stu-id="16458-482">AdoEnums.Schema.TABLES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-483">AdoEnums.Schema.TRANSLATIONS</span><span class="sxs-lookup"><span data-stu-id="16458-483">AdoEnums.Schema.TRANSLATIONS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-484">AdoEnums.Schema.TRUSTEES</span><span class="sxs-lookup"><span data-stu-id="16458-484">AdoEnums.Schema.TRUSTEES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-485">AdoEnums.Schema.USAGEPRIVILEGES</span><span class="sxs-lookup"><span data-stu-id="16458-485">AdoEnums.Schema.USAGEPRIVILEGES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-486">AdoEnums.Schema.VIEWCOLUMNUSAGE</span><span class="sxs-lookup"><span data-stu-id="16458-486">AdoEnums.Schema.VIEWCOLUMNUSAGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16458-487">AdoEnums.Schema.VIEWS</span><span class="sxs-lookup"><span data-stu-id="16458-487">AdoEnums.Schema.VIEWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16458-488">AdoEnums.Schema.VIEWTABLEUSAGE</span><span class="sxs-lookup"><span data-stu-id="16458-488">AdoEnums.Schema.VIEWTABLEUSAGE</span></span></p></td>
</tr>
</tbody>
</table>

