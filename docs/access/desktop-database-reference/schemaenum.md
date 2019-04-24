---
title: SchemaEnum (Access desktop database reference)
TOCTitle: SchemaEnum
ms:assetid: 6147b682-3c4f-ea91-fff6-ac73107d206d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249359(v=office.15)
ms:contentKeyID: 48545208
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: aa70f275de164716b5b3975b56588e9dc4aec1a5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308861"
---
# <a name="schemaenum"></a><span data-ttu-id="1711c-102">SchemaEnum</span><span class="sxs-lookup"><span data-stu-id="1711c-102">SchemaEnum</span></span>

<span data-ttu-id="1711c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="1711c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1711c-104">指定 **OpenSchema** 方法所检索的架构 [Recordset](openschema-method-ado.md) 的类型。</span><span class="sxs-lookup"><span data-stu-id="1711c-104">Specifies the type of schema **Recordset** that the [OpenSchema](openschema-method-ado.md) method retrieves.</span></span>

## <a name="remarks"></a><span data-ttu-id="1711c-105">注解</span><span class="sxs-lookup"><span data-stu-id="1711c-105">Remarks</span></span>

<span data-ttu-id="1711c-106">有关此函数以及为每个 ADO 常量返回的列的附加信息，请参阅 *《OLE DB 程序员参考》* 附录 B 中的主题。</span><span class="sxs-lookup"><span data-stu-id="1711c-106">Additional information about the function and columns returned for each ADO constant can be found in topics of Appendix B of the *OLE DB Programmers Reference*.</span></span> <span data-ttu-id="1711c-107">下表的 "说明" 部分的圆括号中列出了每个主题的名称。</span><span class="sxs-lookup"><span data-stu-id="1711c-107">The name of each topic is listed in parentheses in the Description section of the following table.</span></span>

<span data-ttu-id="1711c-108">有关此函数以及为每个 ADO MD 常量返回的列的附加信息，请参阅 *《OLE DB for OLAP》* 文档第 23 章中的主题。</span><span class="sxs-lookup"><span data-stu-id="1711c-108">Additional information about the function and columns returned for each ADO MD constant can be found in topics of Chapter 23 of the *OLE DB for OLAP* documentation.</span></span> <span data-ttu-id="1711c-109">下表的 "说明" 列中列出了每个主题的名称\*并在括号中标记了星号 ()。</span><span class="sxs-lookup"><span data-stu-id="1711c-109">The name of each topic is listed in parentheses and marked with an asterisk (\*) in the Description column of the following table.</span></span>

<span data-ttu-id="1711c-110">通过引用 ADO [DataTypeEnum](datatypeenum.md) 主题的“说明”列，将 OLE DB 文档中的列的数据类型转换为 ADO 数据类型。</span><span class="sxs-lookup"><span data-stu-id="1711c-110">Translate the data types of columns in the OLE DB documentation to ADO data types by referring to the Description column of the ADO [DataTypeEnum](datatypeenum.md) topic.</span></span> <span data-ttu-id="1711c-111">例如, **\_DBTYPE WSTR**的 OLE DB 数据类型等效于 ADO 数据类型为**adWChar**。</span><span class="sxs-lookup"><span data-stu-id="1711c-111">For example, an OLE DB data type of **DBTYPE\_WSTR** is equivalent to an ADO data type of **adWChar**.</span></span>

<span data-ttu-id="1711c-112">对于常量 **adSchemaDBInfoKeywords** 和 **adSchemaDBInfoLiterals**，ADO 生成类似架构的结果。</span><span class="sxs-lookup"><span data-stu-id="1711c-112">ADO generates schema-like results for the constants, **adSchemaDBInfoKeywords** and **adSchemaDBInfoLiterals**.</span></span> <span data-ttu-id="1711c-113">ADO 创建一个**记录集**, 然后使用**IDBInfo:: GetKeywords**和**IDBInfo:: GetLiteralInfo**方法分别返回的值填充每个行。</span><span class="sxs-lookup"><span data-stu-id="1711c-113">ADO creates a **Recordset**, and then fills each row with the values returned respectively by the **IDBInfo::GetKeywords** and **IDBInfo::GetLiteralInfo** methods.</span></span> <span data-ttu-id="1711c-114">有关这些方法的其他信息, 请参阅《 *OLE DB 程序员参考*》的 IDBInfo 部分。</span><span class="sxs-lookup"><span data-stu-id="1711c-114">Additional information about these methods can be found in the IDBInfo section of the *OLE DB Programmer's Reference*.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1711c-115">常量</span><span class="sxs-lookup"><span data-stu-id="1711c-115">Constant</span></span></p></th>
<th><p><span data-ttu-id="1711c-116">值</span><span class="sxs-lookup"><span data-stu-id="1711c-116">Value</span></span></p></th>
<th><p><span data-ttu-id="1711c-117">说明</span><span class="sxs-lookup"><span data-stu-id="1711c-117">Description</span></span></p></th>
<th><p><span data-ttu-id="1711c-118">约束列</span><span class="sxs-lookup"><span data-stu-id="1711c-118">Constraint columns</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1711c-119"><strong>adSchemaAsserts</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-119"><strong>adSchemaAsserts</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-120">0</span><span class="sxs-lookup"><span data-stu-id="1711c-120">0</span></span></p></td>
<td><p><span data-ttu-id="1711c-121">返回在目录中定义的、由指定用户拥有的声明。</span><span class="sxs-lookup"><span data-stu-id="1711c-121">Returns the assertions defined in the catalog that are owned by a given user.</span></span> <span data-ttu-id="1711c-122">（ASSERTIONS 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-122">(ASSERTIONS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-123">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-123">CONSTRAINT_CATALOG</span></span><br />
<span data-ttu-id="1711c-124">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-124">CONSTRAINT_SCHEMA</span></span><br />
<span data-ttu-id="1711c-125">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-125">CONSTRAINT_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-126"><strong>adSchemaCatalogs</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-126"><strong>adSchemaCatalogs</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-127">1</span><span class="sxs-lookup"><span data-stu-id="1711c-127">1</span></span></p></td>
<td><p><span data-ttu-id="1711c-128">返回与目录关联的、可从 DBMS 访问的物理属性。</span><span class="sxs-lookup"><span data-stu-id="1711c-128">Returns the physical attributes associated with catalogs accessible from the DBMS.</span></span> <span data-ttu-id="1711c-129">（CATALOGS 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-129">(CATALOGS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-130">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-130">CATALOG_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-131"><strong>adSchemaCharacterSets</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-131"><strong>adSchemaCharacterSets</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-132">双面</span><span class="sxs-lookup"><span data-stu-id="1711c-132">2</span></span></p></td>
<td><p><span data-ttu-id="1711c-133">访问在目录中定义的、可供指定用户访问的字符集。</span><span class="sxs-lookup"><span data-stu-id="1711c-133">Returns the character sets defined in the catalog that are accessible to a given user.</span></span> <span data-ttu-id="1711c-134">（CHARACTER_SETS 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-134">(CHARACTER_SETS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-135">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-135">CHARACTER_SET_CATALOG</span></span><br />
<span data-ttu-id="1711c-136">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-136">CHARACTER_SET_SCHEMA</span></span><br />
<span data-ttu-id="1711c-137">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-137">CHARACTER_SET_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-138"><strong>adSchemaCheckConstraints</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-138"><strong>adSchemaCheckConstraints</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-139">5</span><span class="sxs-lookup"><span data-stu-id="1711c-139">5</span></span></p></td>
<td><p><span data-ttu-id="1711c-140">返回在目录中定义的、由指定用户拥有的检查约束。</span><span class="sxs-lookup"><span data-stu-id="1711c-140">Returns the check constraints defined in the catalog that are owned by a given user.</span></span> <span data-ttu-id="1711c-141">（CHECK_CONSTRAINTS 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-141">(CHECK_CONSTRAINTS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-142">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-142">CONSTRAINT_CATALOG</span></span><br />
<span data-ttu-id="1711c-143">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-143">CONSTRAINT_SCHEMA</span></span><br />
<span data-ttu-id="1711c-144">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-144">CONSTRAINT_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-145"><strong>adSchemaCollations</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-145"><strong>adSchemaCollations</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-146">第三章</span><span class="sxs-lookup"><span data-stu-id="1711c-146">3</span></span></p></td>
<td><p><span data-ttu-id="1711c-147">访问在目录中定义的、可供指定用户访问的字符排序规则。</span><span class="sxs-lookup"><span data-stu-id="1711c-147">Returns the character collations defined in the catalog that are accessible to a given user.</span></span> <span data-ttu-id="1711c-148">（COLLATIONS 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-148">(COLLATIONS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-149">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-149">COLLATION_CATALOG</span></span><br />
<span data-ttu-id="1711c-150">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-150">COLLATION_SCHEMA</span></span><br />
<span data-ttu-id="1711c-151">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-151">COLLATION_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-152"><strong>adSchemaColumnPrivileges</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-152"><strong>adSchemaColumnPrivileges</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-153">13</span><span class="sxs-lookup"><span data-stu-id="1711c-153">13</span></span></p></td>
<td><p><span data-ttu-id="1711c-154">返回在目录中定义的、可用于指定用户或由指定用户授权的表列上的权限。</span><span class="sxs-lookup"><span data-stu-id="1711c-154">Returns the privileges on columns of tables defined in the catalog that are available to, or granted by, a given user.</span></span> <span data-ttu-id="1711c-155">（COLUMN_PRIVILEGES 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-155">(COLUMN_PRIVILEGES Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-156">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-156">TABLE_CATALOG</span></span><br />
<span data-ttu-id="1711c-157">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-157">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="1711c-158">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-158">TABLE_NAME</span></span><br />
<span data-ttu-id="1711c-159">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-159">COLUMN_NAME</span></span><br />
<span data-ttu-id="1711c-160">方</span><span class="sxs-lookup"><span data-stu-id="1711c-160">GRANTOR</span></span><br />
<span data-ttu-id="1711c-161">授权</span><span class="sxs-lookup"><span data-stu-id="1711c-161">GRANTEE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-162"><strong>adSchemaColumns</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-162"><strong>adSchemaColumns</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-163">4</span><span class="sxs-lookup"><span data-stu-id="1711c-163">4</span></span></p></td>
<td><p><span data-ttu-id="1711c-164">访问在目录中定义的、可供指定用户访问的表列（包括视图）。</span><span class="sxs-lookup"><span data-stu-id="1711c-164">Returns the columns of tables (including views) defined in the catalog that are accessible to a given user.</span></span> <span data-ttu-id="1711c-165">（COLUMNS 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-165">(COLUMNS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-166">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-166">TABLE_CATALOG</span></span><br />
<span data-ttu-id="1711c-167">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-167">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="1711c-168">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-168">TABLE_NAME</span></span><br />
<span data-ttu-id="1711c-169">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-169">COLUMN_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-170"><strong>adSchemaColumnsDomainUsage</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-170"><strong>adSchemaColumnsDomainUsage</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-171">11x17</span><span class="sxs-lookup"><span data-stu-id="1711c-171">11</span></span></p></td>
<td><p><span data-ttu-id="1711c-172">返回在目录中定义的、依赖在目录中定义的域且由指定用户拥有的列。</span><span class="sxs-lookup"><span data-stu-id="1711c-172">Returns the columns defined in the catalog that are dependent on a domain defined in the catalog and owned by a given user.</span></span> <span data-ttu-id="1711c-173">（COLUMN_DOMAIN_USAGE 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-173">(COLUMN_DOMAIN_USAGE Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-174">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-174">DOMAIN_CATALOG</span></span><br />
<span data-ttu-id="1711c-175">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-175">DOMAIN_SCHEMA</span></span><br />
<span data-ttu-id="1711c-176">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-176">DOMAIN_NAME</span></span><br />
<span data-ttu-id="1711c-177">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-177">COLUMN_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-178"><strong>adSchemaConstraintColumnUsage</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-178"><strong>adSchemaConstraintColumnUsage</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-179">型</span><span class="sxs-lookup"><span data-stu-id="1711c-179">6</span></span></p></td>
<td><p><span data-ttu-id="1711c-180">返回由在目录中定义的且由指定用户拥有的引用约束、唯一约束、检查约束和声明所使用的列。</span><span class="sxs-lookup"><span data-stu-id="1711c-180">Returns the columns used by referential constraints, unique constraints, check constraints, and assertions, defined in the catalog and owned by a given user.</span></span> <span data-ttu-id="1711c-181">（CONSTRAINT_COLUMN_USAGE 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-181">(CONSTRAINT_COLUMN_USAGE Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-182">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-182">TABLE_CATALOG</span></span><br />
<span data-ttu-id="1711c-183">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-183">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="1711c-184">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-184">TABLE_NAME</span></span><br />
<span data-ttu-id="1711c-185">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-185">COLUMN_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-186"><strong>adSchemaConstraintTableUsage</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-186"><strong>adSchemaConstraintTableUsage</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-187">步</span><span class="sxs-lookup"><span data-stu-id="1711c-187">7</span></span></p></td>
<td><p><span data-ttu-id="1711c-188">返回由在目录中定义的且由指定用户拥有的引用约束、唯一约束、检查约束和声明所使用的表。</span><span class="sxs-lookup"><span data-stu-id="1711c-188">Returns the tables that are used by referential constraints, unique constraints, check constraints, and assertions defined in the catalog and owned by a given user.</span></span> <span data-ttu-id="1711c-189">（CONSTRAINT_TABLE_USAGE 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-189">(CONSTRAINT_TABLE_USAGE Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-190">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-190">TABLE_CATALOG</span></span><br />
<span data-ttu-id="1711c-191">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-191">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="1711c-192">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-192">TABLE_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-193"><strong>adSchemaCubes</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-193"><strong>adSchemaCubes</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-194">32</span><span class="sxs-lookup"><span data-stu-id="1711c-194">32</span></span></p></td>
<td><p><span data-ttu-id="1711c-195">返回有关架构（或目录，如果提供程序不支持架构）中的可用多维数据集的信息。</span><span class="sxs-lookup"><span data-stu-id="1711c-195">Returns information about the available cubes in a schema (or the catalog, if the provider does not support schemas).</span></span> <span data-ttu-id="1711c-196">（CUBES 行集\*）</span><span class="sxs-lookup"><span data-stu-id="1711c-196">(CUBES Rowset\*)</span></span></p></td>
<td><p><span data-ttu-id="1711c-197">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-197">CATALOG_NAME</span></span><br />
<span data-ttu-id="1711c-198">SCHEMA_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-198">SCHEMA_NAME</span></span><br />
<span data-ttu-id="1711c-199">CUBE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-199">CUBE_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-200"><strong>adSchemaDBInfoKeywords</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-200"><strong>adSchemaDBInfoKeywords</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-201">30</span><span class="sxs-lookup"><span data-stu-id="1711c-201">30</span></span></p></td>
<td><p><span data-ttu-id="1711c-202">返回提供程序特定的关键字列表。</span><span class="sxs-lookup"><span data-stu-id="1711c-202">Returns a list of provider-specific keywords.</span></span> <span data-ttu-id="1711c-203">(IDBInfo:: GetKeywords \*)</span><span class="sxs-lookup"><span data-stu-id="1711c-203">(IDBInfo::GetKeywords \*)</span></span></p></td>
<td><p><span data-ttu-id="1711c-204">&lt;无&gt;</span><span class="sxs-lookup"><span data-stu-id="1711c-204">&lt;None&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-205"><strong>adSchemaDBInfoLiterals</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-205"><strong>adSchemaDBInfoLiterals</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-206">31</span><span class="sxs-lookup"><span data-stu-id="1711c-206">31</span></span></p></td>
<td><p><span data-ttu-id="1711c-207">返回文本命令中使用的提供程序特定的文字列表。</span><span class="sxs-lookup"><span data-stu-id="1711c-207">Returns a list of provider-specific literals used in text commands.</span></span> <span data-ttu-id="1711c-208">(IDBInfo:: GetLiteralInfo \*)</span><span class="sxs-lookup"><span data-stu-id="1711c-208">(IDBInfo::GetLiteralInfo \*)</span></span></p></td>
<td><p><span data-ttu-id="1711c-209">&lt;无&gt;</span><span class="sxs-lookup"><span data-stu-id="1711c-209">&lt;None&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-210"><strong>adSchemaDimensions</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-210"><strong>adSchemaDimensions</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-211">33</span><span class="sxs-lookup"><span data-stu-id="1711c-211">33</span></span></p></td>
<td><p><span data-ttu-id="1711c-212">返回有关指定多维数据集中的维的信息。</span><span class="sxs-lookup"><span data-stu-id="1711c-212">Returns information about the dimensions in a given cube.</span></span> <span data-ttu-id="1711c-213">对于每个维都包含一行。</span><span class="sxs-lookup"><span data-stu-id="1711c-213">It has one row for each dimension.</span></span> <span data-ttu-id="1711c-214">（DIMENSIONS 行集\*）</span><span class="sxs-lookup"><span data-stu-id="1711c-214">(DIMENSIONS Rowset \*)</span></span></p></td>
<td><p><span data-ttu-id="1711c-215">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-215">CATALOG_NAME</span></span><br />
<span data-ttu-id="1711c-216">SCHEMA_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-216">SCHEMA_NAME</span></span><br />
<span data-ttu-id="1711c-217">CUBE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-217">CUBE_NAME</span></span><br />
<span data-ttu-id="1711c-218">DIMENSION_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-218">DIMENSION_NAME</span></span><br />
<span data-ttu-id="1711c-219">DIMENSION_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-219">DIMENSION_UNIQUE_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-220"><strong>adSchemaForeignKeys</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-220"><strong>adSchemaForeignKeys</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-221">27</span><span class="sxs-lookup"><span data-stu-id="1711c-221">27</span></span></p></td>
<td><p><span data-ttu-id="1711c-222">返回由指定用户在目录中定义的外键列。</span><span class="sxs-lookup"><span data-stu-id="1711c-222">Returns the foreign key columns defined in the catalog by a given user.</span></span> <span data-ttu-id="1711c-223">（FOREIGN_KEYS 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-223">(FOREIGN_KEYS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-224">PK_TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-224">PK_TABLE_CATALOG</span></span><br />
<span data-ttu-id="1711c-225">PK_TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-225">PK_TABLE_SCHEMA</span></span><br />
<span data-ttu-id="1711c-226">PK_TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-226">PK_TABLE_NAME</span></span><br />
<span data-ttu-id="1711c-227">FK_TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-227">FK_TABLE_CATALOG</span></span><br />
<span data-ttu-id="1711c-228">FK_TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-228">FK_TABLE_SCHEMA</span></span><br />
<span data-ttu-id="1711c-229">FK_TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-229">FK_TABLE_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-230"><strong>adSchemaHierarchies</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-230"><strong>adSchemaHierarchies</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-231">34</span><span class="sxs-lookup"><span data-stu-id="1711c-231">34</span></span></p></td>
<td><p><span data-ttu-id="1711c-232">返回有关维中可用的层次结构的信息。</span><span class="sxs-lookup"><span data-stu-id="1711c-232">Returns information about the hierarchies available in a dimension.</span></span> <span data-ttu-id="1711c-233">（HIERARCHIES 行集\*）</span><span class="sxs-lookup"><span data-stu-id="1711c-233">(HIERARCHIES Rowset \*)</span></span></p></td>
<td><p><span data-ttu-id="1711c-234">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-234">CATALOG_NAME</span></span><br />
<span data-ttu-id="1711c-235">SCHEMA_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-235">SCHEMA_NAME</span></span><br />
<span data-ttu-id="1711c-236">CUBE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-236">CUBE_NAME</span></span><br />
<span data-ttu-id="1711c-237">DIMENSION_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-237">DIMENSION_UNIQUE_NAME</span></span><br />
<span data-ttu-id="1711c-238">HIERARCHY_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-238">HIERARCHY_NAME</span></span><br />
<span data-ttu-id="1711c-239">HIERARCHY_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-239">HIERARCHY_UNIQUE_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-240"><strong>adSchemaIndexes</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-240"><strong>adSchemaIndexes</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-241">12</span><span class="sxs-lookup"><span data-stu-id="1711c-241">12</span></span></p></td>
<td><p><span data-ttu-id="1711c-242">返回在目录中定义的由指定用户拥有的索引。</span><span class="sxs-lookup"><span data-stu-id="1711c-242">Returns the indexes defined in the catalog that are owned by a given user.</span></span> <span data-ttu-id="1711c-243">（INDEXES 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-243">(INDEXES Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-244">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-244">TABLE_CATALOG</span></span><br />
<span data-ttu-id="1711c-245">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-245">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="1711c-246">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-246">INDEX_NAME</span></span><br />
<span data-ttu-id="1711c-247">类型</span><span class="sxs-lookup"><span data-stu-id="1711c-247">TYPE</span></span><br />
<span data-ttu-id="1711c-248">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-248">TABLE_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-249"><strong>adSchemaKeyColumnUsage</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-249"><strong>adSchemaKeyColumnUsage</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-250">utf-8</span><span class="sxs-lookup"><span data-stu-id="1711c-250">8</span></span></p></td>
<td><p><span data-ttu-id="1711c-251">返回在目录中定义的、由指定用户约束为键的列。</span><span class="sxs-lookup"><span data-stu-id="1711c-251">Returns the columns defined in the catalog that are constrained as keys by a given user.</span></span> <span data-ttu-id="1711c-252">（KEY_COLUMN_USAGE Rowset 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-252">(KEY_COLUMN_USAGE Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-253">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-253">CONSTRAINT_CATALOG</span></span><br />
<span data-ttu-id="1711c-254">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-254">CONSTRAINT_SCHEMA</span></span><br />
<span data-ttu-id="1711c-255">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-255">CONSTRAINT_NAME</span></span><br />
<span data-ttu-id="1711c-256">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-256">TABLE_CATALOG</span></span><br />
<span data-ttu-id="1711c-257">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-257">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="1711c-258">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-258">TABLE_NAME</span></span><br />
<span data-ttu-id="1711c-259">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-259">COLUMN_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-260"><strong>adSchemaLevels</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-260"><strong>adSchemaLevels</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-261">35</span><span class="sxs-lookup"><span data-stu-id="1711c-261">35</span></span></p></td>
<td><p><span data-ttu-id="1711c-262">返回有关维中可用的级别的信息。</span><span class="sxs-lookup"><span data-stu-id="1711c-262">Returns information about the levels available in a dimension.</span></span> <span data-ttu-id="1711c-263">（LEVELS 行集\*）</span><span class="sxs-lookup"><span data-stu-id="1711c-263">(LEVELS Rowset\*)</span></span></p></td>
<td><p><span data-ttu-id="1711c-264">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-264">CATALOG_NAME</span></span><br />
<span data-ttu-id="1711c-265">SCHEMA_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-265">SCHEMA_NAME</span></span><br />
<span data-ttu-id="1711c-266">CUBE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-266">CUBE_NAME</span></span><br />
<span data-ttu-id="1711c-267">DIMENSION_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-267">DIMENSION_UNIQUE_NAME</span></span><br />
<span data-ttu-id="1711c-268">HIERARCHY_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-268">HIERARCHY_UNIQUE_NAME</span></span><br />
<span data-ttu-id="1711c-269">LEVEL_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-269">LEVEL_NAME</span></span><br />
<span data-ttu-id="1711c-270">LEVEL_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-270">LEVEL_UNIQUE_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-271"><strong>adSchemaMeasures</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-271"><strong>adSchemaMeasures</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-272">36</span><span class="sxs-lookup"><span data-stu-id="1711c-272">36</span></span></p></td>
<td><p><span data-ttu-id="1711c-273">返回有关可用度量的信息。</span><span class="sxs-lookup"><span data-stu-id="1711c-273">Returns information about the available measures.</span></span> <span data-ttu-id="1711c-274">（MEASURES 行集\*）</span><span class="sxs-lookup"><span data-stu-id="1711c-274">(MEASURES Rowset \*)</span></span></p></td>
<td><p><span data-ttu-id="1711c-275">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-275">CATALOG_NAME</span></span><br />
<span data-ttu-id="1711c-276">SCHEMA_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-276">SCHEMA_NAME</span></span><br />
<span data-ttu-id="1711c-277">CUBE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-277">CUBE_NAME</span></span><br />
<span data-ttu-id="1711c-278">MEASURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-278">MEASURE_NAME</span></span><br />
<span data-ttu-id="1711c-279">MEASURE_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-279">MEASURE_UNIQUE_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-280"><strong>adSchemaMembers</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-280"><strong>adSchemaMembers</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-281">38</span><span class="sxs-lookup"><span data-stu-id="1711c-281">38</span></span></p></td>
<td><p><span data-ttu-id="1711c-282">返回有关可用成员的信息。</span><span class="sxs-lookup"><span data-stu-id="1711c-282">Returns information about the available members.</span></span> <span data-ttu-id="1711c-283">（MEMBERS 行集\*）</span><span class="sxs-lookup"><span data-stu-id="1711c-283">(MEMBERS Rowset \*)</span></span></p></td>
<td><p><span data-ttu-id="1711c-284">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-284">CATALOG_NAME</span></span><br />
<span data-ttu-id="1711c-285">SCHEMA_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-285">SCHEMA_NAME</span></span><br />
<span data-ttu-id="1711c-286">CUBE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-286">CUBE_NAME</span></span><br />
<span data-ttu-id="1711c-287">DIMENSION_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-287">DIMENSION_UNIQUE_NAME</span></span><br />
<span data-ttu-id="1711c-288">HIERARCHY_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-288">HIERARCHY_UNIQUE_NAME</span></span><br />
<span data-ttu-id="1711c-289">LEVEL_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-289">LEVEL_UNIQUE_NAME</span></span><br />
<span data-ttu-id="1711c-290">LEVEL_NUMBER</span><span class="sxs-lookup"><span data-stu-id="1711c-290">LEVEL_NUMBER</span></span><br />
<span data-ttu-id="1711c-291">MEMBER_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-291">MEMBER_NAME</span></span><br />
<span data-ttu-id="1711c-292">MEMBER_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-292">MEMBER_UNIQUE_NAME</span></span><br />
<span data-ttu-id="1711c-293">MEMBER_CAPTION</span><span class="sxs-lookup"><span data-stu-id="1711c-293">MEMBER_CAPTION</span></span><br />
<span data-ttu-id="1711c-294">MEMBER_TYPE</span><span class="sxs-lookup"><span data-stu-id="1711c-294">MEMBER_TYPE</span></span><br />
<span data-ttu-id="1711c-295">Tree 运算符 (有关详细信息, 请参阅 OLE DB For OLAP 文档。)</span><span class="sxs-lookup"><span data-stu-id="1711c-295">Tree operator (For more information, see the OLE DB for OLAP documentation.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-296"><strong>adSchemaPrimaryKeys</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-296"><strong>adSchemaPrimaryKeys</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-297">28</span><span class="sxs-lookup"><span data-stu-id="1711c-297">28</span></span></p></td>
<td><p><span data-ttu-id="1711c-298">返回由指定用户在目录中定义的主键列。</span><span class="sxs-lookup"><span data-stu-id="1711c-298">Returns the primary key columns defined in the catalog by a given user.</span></span> <span data-ttu-id="1711c-299">（PRIMARY_KEYS 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-299">(PRIMARY_KEYS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-300">PK_TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-300">PK_TABLE_CATALOG</span></span><br />
<span data-ttu-id="1711c-301">PK_TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-301">PK_TABLE_SCHEMA</span></span><br />
<span data-ttu-id="1711c-302">PK_TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-302">PK_TABLE_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-303"><strong>adSchemaProcedureColumns</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-303"><strong>adSchemaProcedureColumns</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-304">29</span><span class="sxs-lookup"><span data-stu-id="1711c-304">29</span></span></p></td>
<td><p><span data-ttu-id="1711c-305">返回由过程返回的行集的列的信息。</span><span class="sxs-lookup"><span data-stu-id="1711c-305">Returns information about the columns of rowsets returned by procedures.</span></span> <span data-ttu-id="1711c-306">（PROCEDURE_COLUMNS 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-306">(PROCEDURE_COLUMNS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-307">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-307">PROCEDURE_CATALOG</span></span><br />
<span data-ttu-id="1711c-308">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-308">PROCEDURE_SCHEMA</span></span><br />
<span data-ttu-id="1711c-309">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-309">PROCEDURE_NAME</span></span><br />
<span data-ttu-id="1711c-310">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-310">COLUMN_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-311"><strong>adSchemaProcedureParameters</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-311"><strong>adSchemaProcedureParameters</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-312">26</span><span class="sxs-lookup"><span data-stu-id="1711c-312">26</span></span></p></td>
<td><p><span data-ttu-id="1711c-313">返回有关过程的参数和返回代码的信息。</span><span class="sxs-lookup"><span data-stu-id="1711c-313">Returns information about the parameters and return codes of procedures.</span></span> <span data-ttu-id="1711c-314">（PROCEDURE_PARAMETERS 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-314">(PROCEDURE_PARAMETERS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-315">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-315">PROCEDURE_CATALOG</span></span><br />
<span data-ttu-id="1711c-316">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-316">PROCEDURE_SCHEMA</span></span><br />
<span data-ttu-id="1711c-317">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-317">PROCEDURE_NAME</span></span><br />
<span data-ttu-id="1711c-318">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-318">PARAMETER_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-319"><strong>adSchemaProcedures</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-319"><strong>adSchemaProcedures</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-320">位</span><span class="sxs-lookup"><span data-stu-id="1711c-320">16</span></span></p></td>
<td><p><span data-ttu-id="1711c-321">返回在目录中定义的、由指定用户拥有的过程。</span><span class="sxs-lookup"><span data-stu-id="1711c-321">Returns the procedures defined in the catalog that are owned by a given user.</span></span> <span data-ttu-id="1711c-322">（PROCEDURES 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-322">(PROCEDURES Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-323">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-323">PROCEDURE_CATALOG</span></span><br />
<span data-ttu-id="1711c-324">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-324">PROCEDURE_SCHEMA</span></span><br />
<span data-ttu-id="1711c-325">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-325">PROCEDURE_NAME</span></span><br />
<span data-ttu-id="1711c-326">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1711c-326">PROCEDURE_TYPE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-327"><strong>adSchemaProperties</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-327"><strong>adSchemaProperties</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-328">37</span><span class="sxs-lookup"><span data-stu-id="1711c-328">37</span></span></p></td>
<td><p><span data-ttu-id="1711c-329">返回有关维的每个级别的可用属性的信息。</span><span class="sxs-lookup"><span data-stu-id="1711c-329">Returns information about the available properties for each level of the dimension.</span></span> <span data-ttu-id="1711c-330">（PROPERTIES 行集\*）</span><span class="sxs-lookup"><span data-stu-id="1711c-330">(PROPERTIES Rowset \*)</span></span></p></td>
<td><p><span data-ttu-id="1711c-331">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-331">CATALOG_NAME</span></span><br />
<span data-ttu-id="1711c-332">SCHEMA_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-332">SCHEMA_NAME</span></span><br />
<span data-ttu-id="1711c-333">CUBE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-333">CUBE_NAME</span></span><br />
<span data-ttu-id="1711c-334">DIMENSION_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-334">DIMENSION_UNIQUE_NAME</span></span><br />
<span data-ttu-id="1711c-335">HIERARCHY_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-335">HIERARCHY_UNIQUE_NAME</span></span><br />
<span data-ttu-id="1711c-336">LEVEL_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-336">LEVEL_UNIQUE_NAME</span></span><br />
<span data-ttu-id="1711c-337">MEMBER_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-337">MEMBER_UNIQUE_NAME</span></span><br />
<span data-ttu-id="1711c-338">PROPERTY_TYPE</span><span class="sxs-lookup"><span data-stu-id="1711c-338">PROPERTY_TYPE</span></span><br />
<span data-ttu-id="1711c-339">PROPERTY_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-339">PROPERTY_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-340"><strong>adSchemaProviderSpecific</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-340"><strong>adSchemaProviderSpecific</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-341">-1</span><span class="sxs-lookup"><span data-stu-id="1711c-341">-1</span></span></p></td>
<td><p><span data-ttu-id="1711c-342">当提供程序定义其自己的非标准架构查询时使用。</span><span class="sxs-lookup"><span data-stu-id="1711c-342">Used if the provider defines its own nonstandard schema queries.</span></span></p></td>
<td><p><span data-ttu-id="1711c-343">&lt;提供程序特定&gt;</span><span class="sxs-lookup"><span data-stu-id="1711c-343">&lt;Provider specific&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-344"><strong>adSchemaProviderTypes</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-344"><strong>adSchemaProviderTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-345">22</span><span class="sxs-lookup"><span data-stu-id="1711c-345">22</span></span></p></td>
<td><p><span data-ttu-id="1711c-346">返回数据提供程序支持的（基础）数据类型。</span><span class="sxs-lookup"><span data-stu-id="1711c-346">Returns the (base) data types supported by the data provider.</span></span> <span data-ttu-id="1711c-347">（PROVIDER_TYPES 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-347">(PROVIDER_TYPES Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-348">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1711c-348">DATA_TYPE</span></span><br />
<span data-ttu-id="1711c-349">BEST_MATCH</span><span class="sxs-lookup"><span data-stu-id="1711c-349">BEST_MATCH</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-350"><strong>AdSchemaReferentialConstraints</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-350"><strong>AdSchemaReferentialConstraints</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-351">第</span><span class="sxs-lookup"><span data-stu-id="1711c-351">9</span></span></p></td>
<td><p><span data-ttu-id="1711c-352">返回在目录中定义的、由指定用户拥有的引用约束。</span><span class="sxs-lookup"><span data-stu-id="1711c-352">Returns the referential constraints defined in the catalog that are owned by a given user.</span></span> <span data-ttu-id="1711c-353">（REFERENTIAL_CONSTRAINTS 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-353">(REFERENTIAL_CONSTRAINTS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-354">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-354">CONSTRAINT_CATALOG</span></span><br />
<span data-ttu-id="1711c-355">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-355">CONSTRAINT_SCHEMA</span></span><br />
<span data-ttu-id="1711c-356">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-356">CONSTRAINT_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-357"><strong>adSchemaSchemata</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-357"><strong>adSchemaSchemata</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-358">×</span><span class="sxs-lookup"><span data-stu-id="1711c-358">17</span></span></p></td>
<td><p><span data-ttu-id="1711c-359">返回由指定用户拥有的架构（数据库对象）。</span><span class="sxs-lookup"><span data-stu-id="1711c-359">Returns the schemas (database objects) that are owned by a given user.</span></span> <span data-ttu-id="1711c-360">（SCHEMATA 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-360">(SCHEMATA Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-361">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-361">CATALOG_NAME</span></span><br />
<span data-ttu-id="1711c-362">SCHEMA_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-362">SCHEMA_NAME</span></span><br />
<span data-ttu-id="1711c-363">SCHEMA_OWNER</span><span class="sxs-lookup"><span data-stu-id="1711c-363">SCHEMA_OWNER</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-364"><strong>adSchemaSQLLanguages</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-364"><strong>adSchemaSQLLanguages</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-365">18</span><span class="sxs-lookup"><span data-stu-id="1711c-365">18</span></span></p></td>
<td><p><span data-ttu-id="1711c-366">返回由目录中定义的 SQL 实现处理数据支持的一致性级别、选项和语句编写。</span><span class="sxs-lookup"><span data-stu-id="1711c-366">Returns the conformance levels, options, and dialects supported by the SQL-implementation processing data defined in the catalog.</span></span> <span data-ttu-id="1711c-367">（SQL_LANGUAGES 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-367">(SQL_LANGUAGES Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-368">&lt;无&gt;</span><span class="sxs-lookup"><span data-stu-id="1711c-368">&lt;None&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-369"><strong>adSchemaStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-369"><strong>adSchemaStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-370">合</span><span class="sxs-lookup"><span data-stu-id="1711c-370">19</span></span></p></td>
<td><p><span data-ttu-id="1711c-371">返回在目录中定义的、由指定用户拥有的统计信息。</span><span class="sxs-lookup"><span data-stu-id="1711c-371">Returns the statistics defined in the catalog that are owned by a given user.</span></span> <span data-ttu-id="1711c-372">（STATISTICS 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-372">(STATISTICS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-373">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-373">TABLE_CATALOG</span></span><br />
<span data-ttu-id="1711c-374">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-374">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="1711c-375">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-375">TABLE_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-376"><strong>adSchemaTableConstraints</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-376"><strong>adSchemaTableConstraints</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-377">10</span><span class="sxs-lookup"><span data-stu-id="1711c-377">10</span></span></p></td>
<td><p><span data-ttu-id="1711c-378">返回在目录中定义的、由指定用户拥有的表约束。</span><span class="sxs-lookup"><span data-stu-id="1711c-378">Returns the table constraints defined in the catalog that are owned by a given user.</span></span> <span data-ttu-id="1711c-379">（TABLE_CONSTRAINTS 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-379">(TABLE_CONSTRAINTS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-380">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-380">CONSTRAINT_CATALOG</span></span><br />
<span data-ttu-id="1711c-381">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-381">CONSTRAINT_SCHEMA</span></span><br />
<span data-ttu-id="1711c-382">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-382">CONSTRAINT_NAME</span></span><br />
<span data-ttu-id="1711c-383">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-383">TABLE_CATALOG</span></span><br />
<span data-ttu-id="1711c-384">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-384">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="1711c-385">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-385">TABLE_NAME</span></span><br />
<span data-ttu-id="1711c-386">CONSTRAINT_TYPE</span><span class="sxs-lookup"><span data-stu-id="1711c-386">CONSTRAINT_TYPE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-387"><strong>adSchemaTablePrivileges</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-387"><strong>adSchemaTablePrivileges</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-388">日</span><span class="sxs-lookup"><span data-stu-id="1711c-388">14</span></span></p></td>
<td><p><span data-ttu-id="1711c-389">返回在目录中定义的、可用于指定用户或由指定用户授权的表上的权限。</span><span class="sxs-lookup"><span data-stu-id="1711c-389">Returns the privileges on tables defined in the catalog that are available to, or granted by, a given user.</span></span> <span data-ttu-id="1711c-390">（TABLE_PRIVILEGES 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-390">(TABLE_PRIVILEGES Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-391">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-391">TABLE_CATALOG</span></span><br />
<span data-ttu-id="1711c-392">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-392">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="1711c-393">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-393">TABLE_NAME</span></span><br />
<span data-ttu-id="1711c-394">方</span><span class="sxs-lookup"><span data-stu-id="1711c-394">GRANTOR</span></span><br />
<span data-ttu-id="1711c-395">授权</span><span class="sxs-lookup"><span data-stu-id="1711c-395">GRANTEE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-396"><strong>adSchemaTables</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-396"><strong>adSchemaTables</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-397">20</span><span class="sxs-lookup"><span data-stu-id="1711c-397">20</span></span></p></td>
<td><p><span data-ttu-id="1711c-398">返回在目录中定义的、可供指定用户访问的表（包括视图）。</span><span class="sxs-lookup"><span data-stu-id="1711c-398">Returns the tables (including views) defined in the catalog that are accessible to a given user.</span></span> <span data-ttu-id="1711c-399">（TABLES 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-399">(TABLES Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-400">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-400">TABLE_CATALOG</span></span><br />
<span data-ttu-id="1711c-401">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-401">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="1711c-402">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-402">TABLE_NAME</span></span><br />
<span data-ttu-id="1711c-403">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1711c-403">TABLE_TYPE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-404"><strong>adSchemaTranslations</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-404"><strong>adSchemaTranslations</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-405">不足</span><span class="sxs-lookup"><span data-stu-id="1711c-405">21</span></span></p></td>
<td><p><span data-ttu-id="1711c-406">返回在目录中定义的、可供指定用户访问的字符转换。</span><span class="sxs-lookup"><span data-stu-id="1711c-406">Returns the character translations defined in the catalog that are accessible to a given user.</span></span> <span data-ttu-id="1711c-407">（TRANSLATIONS 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-407">(TRANSLATIONS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-408">TRANSLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-408">TRANSLATION_CATALOG</span></span><br />
<span data-ttu-id="1711c-409">TRANSLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-409">TRANSLATION_SCHEMA</span></span><br />
<span data-ttu-id="1711c-410">TRANSLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-410">TRANSLATION_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-411"><strong>adSchemaTrustees</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-411"><strong>adSchemaTrustees</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-412">39</span><span class="sxs-lookup"><span data-stu-id="1711c-412">39</span></span></p></td>
<td><p><span data-ttu-id="1711c-413">保留以备将来使用。</span><span class="sxs-lookup"><span data-stu-id="1711c-413">Reserved for future use.</span></span></p></td>
<td><p><br />
</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-414"><strong>adSchemaUsagePrivileges</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-414"><strong>adSchemaUsagePrivileges</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-415">个</span><span class="sxs-lookup"><span data-stu-id="1711c-415">15</span></span></p></td>
<td><p><span data-ttu-id="1711c-416">返回在目录中定义的、可用于指定用户或由指定用户授权的对象上的 USAGE 权限。</span><span class="sxs-lookup"><span data-stu-id="1711c-416">Returns the USAGE privileges on objects defined in the catalog that are available to, or granted by, a given user.</span></span> <span data-ttu-id="1711c-417">（USAGE_PRIVILEGES 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-417">(USAGE_PRIVILEGES Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-418">OBJECT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-418">OBJECT_CATALOG</span></span><br />
<span data-ttu-id="1711c-419">OBJECT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-419">OBJECT_SCHEMA</span></span><br />
<span data-ttu-id="1711c-420">OBJECT_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-420">OBJECT_NAME</span></span><br />
<span data-ttu-id="1711c-421">OBJECT_TYPE</span><span class="sxs-lookup"><span data-stu-id="1711c-421">OBJECT_TYPE</span></span><br />
<span data-ttu-id="1711c-422">方</span><span class="sxs-lookup"><span data-stu-id="1711c-422">GRANTOR</span></span><br />
<span data-ttu-id="1711c-423">授权</span><span class="sxs-lookup"><span data-stu-id="1711c-423">GRANTEE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-424"><strong>adSchemaViewColumnUsage</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-424"><strong>adSchemaViewColumnUsage</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-425">24</span><span class="sxs-lookup"><span data-stu-id="1711c-425">24</span></span></p></td>
<td><p><span data-ttu-id="1711c-426">返回在目录中定义的、由指定用户拥有的被查看表所依赖的列。</span><span class="sxs-lookup"><span data-stu-id="1711c-426">Returns the columns on which viewed tables, defined in the catalog and owned by a given user, are dependent.</span></span> <span data-ttu-id="1711c-427">（VIEW_COLUMN_USAGE 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-427">(VIEW_COLUMN_USAGE Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-428">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-428">VIEW_CATALOG</span></span><br />
<span data-ttu-id="1711c-429">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-429">VIEW_SCHEMA</span></span><br />
<span data-ttu-id="1711c-430">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-430">VIEW_NAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-431"><strong>adSchemaViews</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-431"><strong>adSchemaViews</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-432">上午</span><span class="sxs-lookup"><span data-stu-id="1711c-432">23</span></span></p></td>
<td><p><span data-ttu-id="1711c-433">访问在目录中定义的、可供指定用户访问的视图。</span><span class="sxs-lookup"><span data-stu-id="1711c-433">Returns the views defined in the catalog that are accessible to a given user.</span></span> <span data-ttu-id="1711c-434">（VIEWS 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-434">(VIEWS Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-435">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-435">TABLE_CATALOG</span></span><br />
<span data-ttu-id="1711c-436">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-436">TABLE_SCHEMA</span></span><br />
<span data-ttu-id="1711c-437">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-437">TABLE_NAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-438"><strong>adSchemaViewTableUsage</strong></span><span class="sxs-lookup"><span data-stu-id="1711c-438"><strong>adSchemaViewTableUsage</strong></span></span></p></td>
<td><p><span data-ttu-id="1711c-439">word</span><span class="sxs-lookup"><span data-stu-id="1711c-439">25</span></span></p></td>
<td><p><span data-ttu-id="1711c-440">返回在目录中定义的、由指定用户拥有的被查看表所依赖的表。</span><span class="sxs-lookup"><span data-stu-id="1711c-440">Returns the tables on which viewed tables, defined in the catalog and owned by a given user, are dependent.</span></span> <span data-ttu-id="1711c-441">（VIEW_TABLE_USAGE 行集）</span><span class="sxs-lookup"><span data-stu-id="1711c-441">(VIEW_TABLE_USAGE Rowset)</span></span></p></td>
<td><p><span data-ttu-id="1711c-442">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1711c-442">VIEW_CATALOG</span></span><br />
<span data-ttu-id="1711c-443">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1711c-443">VIEW_SCHEMA</span></span><br />
<span data-ttu-id="1711c-444">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="1711c-444">VIEW_NAME</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="1711c-445">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="1711c-445">ADO/WFC equivalent</span></span>

<span data-ttu-id="1711c-446">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="1711c-446">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1711c-447">常量</span><span class="sxs-lookup"><span data-stu-id="1711c-447">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1711c-448">AdoEnums</span><span class="sxs-lookup"><span data-stu-id="1711c-448">AdoEnums.Schema.ASSERTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-449">AdoEnums</span><span class="sxs-lookup"><span data-stu-id="1711c-449">AdoEnums.Schema.CATALOGS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-450">AdoEnums CHARACTERSETS</span><span class="sxs-lookup"><span data-stu-id="1711c-450">AdoEnums.Schema.CHARACTERSETS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-451">AdoEnums CHECKCONSTRAINTS</span><span class="sxs-lookup"><span data-stu-id="1711c-451">AdoEnums.Schema.CHECKCONSTRAINTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-452">AdoEnums 排序规则</span><span class="sxs-lookup"><span data-stu-id="1711c-452">AdoEnums.Schema.COLLATIONS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-453">AdoEnums COLUMNPRIVILEGES</span><span class="sxs-lookup"><span data-stu-id="1711c-453">AdoEnums.Schema.COLUMNPRIVILEGES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-454">AdoEnums</span><span class="sxs-lookup"><span data-stu-id="1711c-454">AdoEnums.Schema.COLUMNS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-455">AdoEnums COLUMNSDOMAINUSAGE</span><span class="sxs-lookup"><span data-stu-id="1711c-455">AdoEnums.Schema.COLUMNSDOMAINUSAGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-456">AdoEnums CONSTRAINTCOLUMNUSAGE</span><span class="sxs-lookup"><span data-stu-id="1711c-456">AdoEnums.Schema.CONSTRAINTCOLUMNUSAGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-457">AdoEnums CONSTRAINTTABLEUSAGE</span><span class="sxs-lookup"><span data-stu-id="1711c-457">AdoEnums.Schema.CONSTRAINTTABLEUSAGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-458">AdoEnums</span><span class="sxs-lookup"><span data-stu-id="1711c-458">AdoEnums.Schema.CUBES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-459">AdoEnums DBINFOKEYWORDS</span><span class="sxs-lookup"><span data-stu-id="1711c-459">AdoEnums.Schema.DBINFOKEYWORDS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-460">AdoEnums DBINFOLITERALS</span><span class="sxs-lookup"><span data-stu-id="1711c-460">AdoEnums.Schema.DBINFOLITERALS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-461">AdoEnums</span><span class="sxs-lookup"><span data-stu-id="1711c-461">AdoEnums.Schema.DIMENSIONS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-462">AdoEnums FOREIGNKEYS</span><span class="sxs-lookup"><span data-stu-id="1711c-462">AdoEnums.Schema.FOREIGNKEYS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-463">AdoEnums</span><span class="sxs-lookup"><span data-stu-id="1711c-463">AdoEnums.Schema.HIERARCHIES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-464">AdoEnums</span><span class="sxs-lookup"><span data-stu-id="1711c-464">AdoEnums.Schema.INDEXES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-465">AdoEnums KEYCOLUMNUSAGE</span><span class="sxs-lookup"><span data-stu-id="1711c-465">AdoEnums.Schema.KEYCOLUMNUSAGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-466">AdoEnums</span><span class="sxs-lookup"><span data-stu-id="1711c-466">AdoEnums.Schema.LEVELS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-467">AdoEnums</span><span class="sxs-lookup"><span data-stu-id="1711c-467">AdoEnums.Schema.MEASURES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-468">AdoEnums 成员</span><span class="sxs-lookup"><span data-stu-id="1711c-468">AdoEnums.Schema.MEMBERS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-469">AdoEnums PRIMARYKEYS</span><span class="sxs-lookup"><span data-stu-id="1711c-469">AdoEnums.Schema.PRIMARYKEYS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-470">AdoEnums PROCEDURECOLUMNS</span><span class="sxs-lookup"><span data-stu-id="1711c-470">AdoEnums.Schema.PROCEDURECOLUMNS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-471">AdoEnums PROCEDUREPARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1711c-471">AdoEnums.Schema.PROCEDUREPARAMETERS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-472">AdoEnums 过程</span><span class="sxs-lookup"><span data-stu-id="1711c-472">AdoEnums.Schema.PROCEDURES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-473">AdoEnums</span><span class="sxs-lookup"><span data-stu-id="1711c-473">AdoEnums.Schema.PROPERTIES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-474">AdoEnums PROVIDERSPECIFIC</span><span class="sxs-lookup"><span data-stu-id="1711c-474">AdoEnums.Schema.PROVIDERSPECIFIC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-475">AdoEnums PROVIDERTYPES</span><span class="sxs-lookup"><span data-stu-id="1711c-475">AdoEnums.Schema.PROVIDERTYPES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-476">AdoEnums REFERENTIALCONTRAINTS</span><span class="sxs-lookup"><span data-stu-id="1711c-476">AdoEnums.Schema.REFERENTIALCONTRAINTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-477">AdoEnums</span><span class="sxs-lookup"><span data-stu-id="1711c-477">AdoEnums.Schema.SCHEMATA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-478">AdoEnums SQLLANGUAGES</span><span class="sxs-lookup"><span data-stu-id="1711c-478">AdoEnums.Schema.SQLLANGUAGES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-479">AdoEnums 统计信息</span><span class="sxs-lookup"><span data-stu-id="1711c-479">AdoEnums.Schema.STATISTICS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-480">AdoEnums TABLECONSTRAINTS</span><span class="sxs-lookup"><span data-stu-id="1711c-480">AdoEnums.Schema.TABLECONSTRAINTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-481">AdoEnums TABLEPRIVILEGES</span><span class="sxs-lookup"><span data-stu-id="1711c-481">AdoEnums.Schema.TABLEPRIVILEGES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-482">AdoEnums</span><span class="sxs-lookup"><span data-stu-id="1711c-482">AdoEnums.Schema.TABLES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-483">AdoEnums</span><span class="sxs-lookup"><span data-stu-id="1711c-483">AdoEnums.Schema.TRANSLATIONS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-484">AdoEnums</span><span class="sxs-lookup"><span data-stu-id="1711c-484">AdoEnums.Schema.TRUSTEES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-485">AdoEnums USAGEPRIVILEGES</span><span class="sxs-lookup"><span data-stu-id="1711c-485">AdoEnums.Schema.USAGEPRIVILEGES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-486">AdoEnums VIEWCOLUMNUSAGE</span><span class="sxs-lookup"><span data-stu-id="1711c-486">AdoEnums.Schema.VIEWCOLUMNUSAGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711c-487">AdoEnums</span><span class="sxs-lookup"><span data-stu-id="1711c-487">AdoEnums.Schema.VIEWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711c-488">AdoEnums VIEWTABLEUSAGE</span><span class="sxs-lookup"><span data-stu-id="1711c-488">AdoEnums.Schema.VIEWTABLEUSAGE</span></span></p></td>
</tr>
</tbody>
</table>

