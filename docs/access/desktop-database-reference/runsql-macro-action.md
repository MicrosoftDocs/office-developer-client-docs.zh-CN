---
title: RunSQL 宏操作
TOCTitle: RunSQL Macro Action
ms:assetid: 3692142d-f8a8-e194-0b38-051167f46319
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192476(v=office.15)
ms:contentKeyID: 48544174
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm12983
f1_categories:
- Office.Version=v15
ms.openlocfilehash: ff4a363f6fbb05af582767f4b664f71f34d23357
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465575"
---
# <a name="runsql-macro-action"></a><span data-ttu-id="342bd-102">RunSQL 宏操作</span><span class="sxs-lookup"><span data-stu-id="342bd-102">RunSQL Macro Action</span></span>


<span data-ttu-id="342bd-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="342bd-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="342bd-104">**RunSQL**操作可用于通过使用相应的 SQL 语句中运行访问动作查询。</span><span class="sxs-lookup"><span data-stu-id="342bd-104">You can use the **RunSQL** action to run a Access action query by using the corresponding SQL statement.</span></span> <span data-ttu-id="342bd-105">还可以运行数据定义查询。</span><span class="sxs-lookup"><span data-stu-id="342bd-105">You can also run a data-definition query.</span></span>


> [!NOTE]
> <P><span data-ttu-id="342bd-p102">[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</span><span class="sxs-lookup"><span data-stu-id="342bd-p102">This action will not be allowed if the database is not trusted. For more information about enabling macros, see the links in the See Also section of this article.</span></span></P>



## <a name="setting"></a><span data-ttu-id="342bd-108">设置</span><span class="sxs-lookup"><span data-stu-id="342bd-108">Setting</span></span>

<span data-ttu-id="342bd-109">**RunSQL** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="342bd-109">The **RunSQL** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="342bd-110">操作参数</span><span class="sxs-lookup"><span data-stu-id="342bd-110">Action argument</span></span></p></th>
<th><p><span data-ttu-id="342bd-111">说明</span><span class="sxs-lookup"><span data-stu-id="342bd-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="342bd-112"><strong>SQL 语句</strong></span><span class="sxs-lookup"><span data-stu-id="342bd-112"><strong>SQL Statement</strong></span></span></p></td>
<td><p><span data-ttu-id="342bd-p103">要运行的动作查询或数据定义查询所对应的 SQL 语句。此语句的最大长度为 255 个字符。这是一个必选参数。</span><span class="sxs-lookup"><span data-stu-id="342bd-p103">The SQL statement for the action query or data-definition query you want to run. The maximum length of this statement is 255 characters. This is a required argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="342bd-116"><strong>使用事务</strong></span><span class="sxs-lookup"><span data-stu-id="342bd-116"><strong>Use Transaction</strong></span></span></p></td>
<td><p><span data-ttu-id="342bd-p104">选择<strong>“是”</strong>可将此查询包括在事务中。如果不想使用事务，请选择<strong>“否”</strong>。默认值为<strong>“是”</strong>。如果为此参数选择<strong>“否”</strong>，查询可能运行得更快。</span><span class="sxs-lookup"><span data-stu-id="342bd-p104">Select <strong>Yes</strong> to include this query in a transaction. Select <strong>No</strong> if you don't want to use a transaction. The default is <strong>Yes</strong>. If you select <strong>No</strong> for this argument, the query might run faster.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="342bd-121">说明</span><span class="sxs-lookup"><span data-stu-id="342bd-121">Remarks</span></span>

<span data-ttu-id="342bd-p105">使用动作查询可以追加、删除和更新记录并将查询的结果集另存为新表。使用数据定义查询可以创建、更改和删除表，还可以创建和删除索引。使用 **RunSQL** 操作可以从宏中直接执行这些操作，而无需使用存储的查询。</span><span class="sxs-lookup"><span data-stu-id="342bd-p105">You can use action queries to append, delete, and update records and to save a query's result set as a new table. You can use data-definition queries to create, alter, and delete tables, and to create and delete indexes. You can use the **RunSQL** action to perform these operations directly from a macro without having to use stored queries.</span></span>

<span data-ttu-id="342bd-p106">如果需要键入长度超过 255 个字符的 SQL 语句，请改用 Visual Basic for Applications (VBA) 模块中的 **DoCmd** 对象的 **RunSQL** 方法。在 VBA 中，可以键入长达 32,768 个字符的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="342bd-p106">If you need to type an SQL statement longer than 255 characters, use the **RunSQL** method of the **DoCmd** object in a Visual Basic for Applications (VBA) module instead. You can type SQL statements of up to 32,768 characters in VBA.</span></span>

<span data-ttu-id="342bd-p107">Access 查询实际上是 SQL 语句，这些语句是在您使用查询窗口中的设计网格设计查询时创建的。下表中显示了 Access 动作查询和数据定义查询以及与它们对应的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="342bd-p107">Access queries are actually SQL statements that are created when you design a query by using the design grid in the Query window. The following table shows the Access action queries and data-definition queries and their corresponding SQL statements.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="342bd-129">查询类型</span><span class="sxs-lookup"><span data-stu-id="342bd-129">Query type</span></span></p></th>
<th><p><span data-ttu-id="342bd-130">SQL 语句</span><span class="sxs-lookup"><span data-stu-id="342bd-130">SQL statement</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="342bd-131"><strong>操作</strong></span><span class="sxs-lookup"><span data-stu-id="342bd-131"><strong>Action</strong></span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="342bd-132">追加查询</span><span class="sxs-lookup"><span data-stu-id="342bd-132">Append</span></span></p></td>
<td><p><span data-ttu-id="342bd-133">INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="342bd-133">INSERT INTO</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="342bd-134">删除查询</span><span class="sxs-lookup"><span data-stu-id="342bd-134">Delete</span></span></p></td>
<td><p><span data-ttu-id="342bd-135">DELETE</span><span class="sxs-lookup"><span data-stu-id="342bd-135">DELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="342bd-136">生成表查询</span><span class="sxs-lookup"><span data-stu-id="342bd-136">Make-table</span></span></p></td>
<td><p><span data-ttu-id="342bd-137">选择...到</span><span class="sxs-lookup"><span data-stu-id="342bd-137">SELECT...INTO</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="342bd-138">更新查询</span><span class="sxs-lookup"><span data-stu-id="342bd-138">Update</span></span></p></td>
<td><p><span data-ttu-id="342bd-139">UPDATE</span><span class="sxs-lookup"><span data-stu-id="342bd-139">UPDATE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="342bd-140"><strong>数据定义（特定于 SQL）</strong></span><span class="sxs-lookup"><span data-stu-id="342bd-140"><strong>Data-definition (SQL-specific)</strong></span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="342bd-141">创建表</span><span class="sxs-lookup"><span data-stu-id="342bd-141">Create a table</span></span></p></td>
<td><p><span data-ttu-id="342bd-142">CREATE TABLE</span><span class="sxs-lookup"><span data-stu-id="342bd-142">CREATE TABLE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="342bd-143">更改表</span><span class="sxs-lookup"><span data-stu-id="342bd-143">Alter a table</span></span></p></td>
<td><p><span data-ttu-id="342bd-144">ALTER TABLE</span><span class="sxs-lookup"><span data-stu-id="342bd-144">ALTER TABLE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="342bd-145">删除表</span><span class="sxs-lookup"><span data-stu-id="342bd-145">Delete a table</span></span></p></td>
<td><p><span data-ttu-id="342bd-146">DROP TABLE</span><span class="sxs-lookup"><span data-stu-id="342bd-146">DROP TABLE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="342bd-147">创建索引</span><span class="sxs-lookup"><span data-stu-id="342bd-147">Create an index</span></span></p></td>
<td><p><span data-ttu-id="342bd-148">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="342bd-148">CREATE INDEX</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="342bd-149">删除索引</span><span class="sxs-lookup"><span data-stu-id="342bd-149">Delete an index</span></span></p></td>
<td><p><span data-ttu-id="342bd-150">DROP INDEX</span><span class="sxs-lookup"><span data-stu-id="342bd-150">DROP INDEX</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="342bd-151">还可以将 IN 子句与这些语句一起使用，以修改另一个数据库中的数据。</span><span class="sxs-lookup"><span data-stu-id="342bd-151">You can also use an IN clause with these statements to modify data in another database.</span></span>


> [!NOTE]
> <P><span data-ttu-id="342bd-p108">[!注释] 要从宏中运行选择查询或交叉表查询，请使用 <STRONG>OpenQuery</STRONG> 操作的"视图"参数在数据表视图中打开一个现有的选择查询和交叉表查询。还可以用同样的方法运行现有的动作查询和 SQL 特定查询。</span><span class="sxs-lookup"><span data-stu-id="342bd-p108">To run a select query or crosstab query from a macro, use the View argument of the <STRONG>OpenQuery</STRONG> action to open an existing select query or crosstab query in Datasheet view. You can also run existing action queries and SQL-specific queries in the same way.</span></span></P>


