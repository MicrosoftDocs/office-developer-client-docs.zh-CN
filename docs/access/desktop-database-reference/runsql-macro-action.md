---
title: RunSQL 宏操作
TOCTitle: RunSQL macro action
ms:assetid: 3692142d-f8a8-e194-0b38-051167f46319
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192476(v=office.15)
ms:contentKeyID: 48544174
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm12983
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: f3ef598ad50747d99ca884043e03ebfabfef8f63
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308993"
---
# <a name="runsql-macro-action"></a><span data-ttu-id="9e3e9-102">RunSQL 宏操作</span><span class="sxs-lookup"><span data-stu-id="9e3e9-102">RunSQL macro action</span></span>

<span data-ttu-id="9e3e9-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="9e3e9-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9e3e9-104">您可以使用**RunSQL**操作来运行 Access 操作查询, 方法是使用相应的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="9e3e9-104">You can use the **RunSQL** action to run a Access action query by using the corresponding SQL statement.</span></span> <span data-ttu-id="9e3e9-105">还可以运行数据定义查询。</span><span class="sxs-lookup"><span data-stu-id="9e3e9-105">You can also run a data-definition query.</span></span>

> [!NOTE]
> <span data-ttu-id="9e3e9-106">[!注释] 如果数据库不受信任，将不允许此操作。</span><span class="sxs-lookup"><span data-stu-id="9e3e9-106">This action will not be allowed if the database is not trusted.</span></span> 

## <a name="setting"></a><span data-ttu-id="9e3e9-107">设置</span><span class="sxs-lookup"><span data-stu-id="9e3e9-107">Setting</span></span>

<span data-ttu-id="9e3e9-108">**RunSQL** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="9e3e9-108">The **RunSQL** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9e3e9-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="9e3e9-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="9e3e9-110">说明</span><span class="sxs-lookup"><span data-stu-id="9e3e9-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e3e9-111"><strong>SQL 语句</strong></span><span class="sxs-lookup"><span data-stu-id="9e3e9-111"><strong>SQL Statement</strong></span></span></p></td>
<td><p><span data-ttu-id="9e3e9-p102">要运行的动作查询或数据定义查询所对应的 SQL 语句。此语句的最大长度为 255 个字符。这是一个必选参数。</span><span class="sxs-lookup"><span data-stu-id="9e3e9-p102">The SQL statement for the action query or data-definition query you want to run. The maximum length of this statement is 255 characters. This is a required argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e3e9-115"><strong>使用事务</strong></span><span class="sxs-lookup"><span data-stu-id="9e3e9-115"><strong>Use Transaction</strong></span></span></p></td>
<td><p><span data-ttu-id="9e3e9-116">选择<strong>"是"</strong>将此查询包含在事务中。</span><span class="sxs-lookup"><span data-stu-id="9e3e9-116">Select <strong>Yes</strong> to include this query in a transaction.</span></span> <span data-ttu-id="9e3e9-117">如果您不想使用事务处理, 请选择 "<strong>否</strong>"。</span><span class="sxs-lookup"><span data-stu-id="9e3e9-117">Select <strong>No</strong> if you don't want to use a transaction.</span></span> <span data-ttu-id="9e3e9-118">默认值为 <strong>"是"</strong>。</span><span class="sxs-lookup"><span data-stu-id="9e3e9-118">The default is <strong>Yes</strong>.</span></span> <span data-ttu-id="9e3e9-119">如果为此参数选择 "<strong>否</strong>", 则查询可能会运行得更快。</span><span class="sxs-lookup"><span data-stu-id="9e3e9-119">If you select <strong>No</strong> for this argument, the query might run faster.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="9e3e9-120">注解</span><span class="sxs-lookup"><span data-stu-id="9e3e9-120">Remarks</span></span>

<span data-ttu-id="9e3e9-p104">使用动作查询可以追加、删除和更新记录并将查询的结果集另存为新表。使用数据定义查询可以创建、更改和删除表，还可以创建和删除索引。使用 **RunSQL** 操作可以从宏中直接执行这些操作，而无需使用存储的查询。</span><span class="sxs-lookup"><span data-stu-id="9e3e9-p104">You can use action queries to append, delete, and update records and to save a query's result set as a new table. You can use data-definition queries to create, alter, and delete tables, and to create and delete indexes. You can use the **RunSQL** action to perform these operations directly from a macro without having to use stored queries.</span></span>

<span data-ttu-id="9e3e9-p105">如果需要键入长度超过 255 个字符的 SQL 语句，请改用 Visual Basic for Applications (VBA) 模块中的 **DoCmd** 对象的 **RunSQL** 方法。在 VBA 中，可以键入长达 32,768 个字符的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="9e3e9-p105">If you need to type an SQL statement longer than 255 characters, use the **RunSQL** method of the **DoCmd** object in a Visual Basic for Applications (VBA) module instead. You can type SQL statements of up to 32,768 characters in VBA.</span></span>

<span data-ttu-id="9e3e9-p106">Access 查询实际上是 SQL 语句，这些语句是在您使用查询窗口中的设计网格设计查询时创建的。下表中显示了 Access 动作查询和数据定义查询以及与它们对应的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="9e3e9-p106">Access queries are actually SQL statements that are created when you design a query by using the design grid in the Query window. The following table shows the Access action queries and data-definition queries and their corresponding SQL statements.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9e3e9-128">查询类型</span><span class="sxs-lookup"><span data-stu-id="9e3e9-128">Query type</span></span></p></th>
<th><p><span data-ttu-id="9e3e9-129">SQL 语句</span><span class="sxs-lookup"><span data-stu-id="9e3e9-129">SQL statement</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e3e9-130"><strong>Action</strong></span><span class="sxs-lookup"><span data-stu-id="9e3e9-130"><strong>Action</strong></span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e3e9-131">Append</span><span class="sxs-lookup"><span data-stu-id="9e3e9-131">Append</span></span></p></td>
<td><p><span data-ttu-id="9e3e9-132">INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="9e3e9-132">INSERT INTO</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e3e9-133">删除</span><span class="sxs-lookup"><span data-stu-id="9e3e9-133">Delete</span></span></p></td>
<td><p><span data-ttu-id="9e3e9-134">DELETE</span><span class="sxs-lookup"><span data-stu-id="9e3e9-134">DELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e3e9-135">生成表</span><span class="sxs-lookup"><span data-stu-id="9e3e9-135">Make-table</span></span></p></td>
<td><p><span data-ttu-id="9e3e9-136">选择 .。。了解</span><span class="sxs-lookup"><span data-stu-id="9e3e9-136">SELECT...INTO</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e3e9-137">Update</span><span class="sxs-lookup"><span data-stu-id="9e3e9-137">Update</span></span></p></td>
<td><p><span data-ttu-id="9e3e9-138">更新</span><span class="sxs-lookup"><span data-stu-id="9e3e9-138">UPDATE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e3e9-139"><strong>数据定义 (特定于 SQL)</strong></span><span class="sxs-lookup"><span data-stu-id="9e3e9-139"><strong>Data-definition (SQL-specific)</strong></span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e3e9-140">创建表</span><span class="sxs-lookup"><span data-stu-id="9e3e9-140">Create a table</span></span></p></td>
<td><p><span data-ttu-id="9e3e9-141">创建表</span><span class="sxs-lookup"><span data-stu-id="9e3e9-141">CREATE TABLE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e3e9-142">更改表</span><span class="sxs-lookup"><span data-stu-id="9e3e9-142">Alter a table</span></span></p></td>
<td><p><span data-ttu-id="9e3e9-143">ALTER TABLE</span><span class="sxs-lookup"><span data-stu-id="9e3e9-143">ALTER TABLE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e3e9-144">删除表</span><span class="sxs-lookup"><span data-stu-id="9e3e9-144">Delete a table</span></span></p></td>
<td><p><span data-ttu-id="9e3e9-145">删除表</span><span class="sxs-lookup"><span data-stu-id="9e3e9-145">DROP TABLE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e3e9-146">创建索引</span><span class="sxs-lookup"><span data-stu-id="9e3e9-146">Create an index</span></span></p></td>
<td><p><span data-ttu-id="9e3e9-147">创建索引</span><span class="sxs-lookup"><span data-stu-id="9e3e9-147">CREATE INDEX</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e3e9-148">删除索引</span><span class="sxs-lookup"><span data-stu-id="9e3e9-148">Delete an index</span></span></p></td>
<td><p><span data-ttu-id="9e3e9-149">删除索引</span><span class="sxs-lookup"><span data-stu-id="9e3e9-149">DROP INDEX</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9e3e9-150">还可以将 IN 子句与这些语句一起使用，以修改另一个数据库中的数据。</span><span class="sxs-lookup"><span data-stu-id="9e3e9-150">You can also use an IN clause with these statements to modify data in another database.</span></span>

> [!NOTE]
> <span data-ttu-id="9e3e9-p107">[!注释] 要从宏中运行选择查询或交叉表查询，请使用 **OpenQuery** 操作的"视图"参数在数据表视图中打开一个现有的选择查询和交叉表查询。还可以用同样的方法运行现有的动作查询和 SQL 特定查询。</span><span class="sxs-lookup"><span data-stu-id="9e3e9-p107">To run a select query or crosstab query from a macro, use the View argument of the **OpenQuery** action to open an existing select query or crosstab query in Datasheet view. You can also run existing action queries and SQL-specific queries in the same way.</span></span>
