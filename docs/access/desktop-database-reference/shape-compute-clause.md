---
title: Shape Compute 子句
TOCTitle: Shape Compute clause
ms:assetid: f4fee4a6-ec9e-c0b6-40e0-258f76c4696f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250245(v=office.15)
ms:contentKeyID: 48548699
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: eadc448d59814f0573a959c6c1038f9c4afdbac9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306452"
---
# <a name="shape-compute-clause"></a><span data-ttu-id="42e3e-102">Shape Compute 子句</span><span class="sxs-lookup"><span data-stu-id="42e3e-102">Shape Compute clause</span></span>

<span data-ttu-id="42e3e-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="42e3e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="42e3e-104">shape COMPUTE 子句可以生成父 **Recordset**，该记录集的列由以下项组成：对子 **Recordset** 的引用；其内容为章节列、新列或计算列的可选列，或者是对子 **Recordset** 或以前定形的 **Recordset** 执行聚合函数的结果；以及在可选的 BY 子句中列出的子 **Recordset** 中的任何列。</span><span class="sxs-lookup"><span data-stu-id="42e3e-104">A shape COMPUTE clause generates a parent **Recordset**, whose columns consist of a reference to the child **Recordset**; optional columns whose contents are chapter, new, or calculated columns, or the result of executing aggregate functions on the child **Recordset** or a previously shaped **Recordset**; and any columns from the child **Recordset** listed in the optional BY clause.</span></span>

## <a name="syntax"></a><span data-ttu-id="42e3e-105">语法</span><span class="sxs-lookup"><span data-stu-id="42e3e-105">Syntax</span></span>

```vb 
 
SHAPE child-command [AS] child-alias 
   COMPUTE child-alias [[AS] name], [appended-column-list] 
   [BY grp-field-list] 
```

## <a name="description"></a><span data-ttu-id="42e3e-106">说明</span><span class="sxs-lookup"><span data-stu-id="42e3e-106">Description</span></span>

<span data-ttu-id="42e3e-107">此子句的各部分如下所示：</span><span class="sxs-lookup"><span data-stu-id="42e3e-107">The parts of this clause are as follows:</span></span>

- <span data-ttu-id="42e3e-108">*child-command*</span><span class="sxs-lookup"><span data-stu-id="42e3e-108">*child-command*</span></span>

  - <span data-ttu-id="42e3e-109">由下列各项之一组成：</span><span class="sxs-lookup"><span data-stu-id="42e3e-109">Consists of one of the following:</span></span>
    
    - <span data-ttu-id="42e3e-110">一个返回子**Recordset**对象的大括号{}("") 内的查询命令。</span><span class="sxs-lookup"><span data-stu-id="42e3e-110">A query command within curly braces ("{}") that returns a child **Recordset** object.</span></span> <span data-ttu-id="42e3e-111">该命令向基础数据提供程序发出，其语法取决于该提供程序的要求。</span><span class="sxs-lookup"><span data-stu-id="42e3e-111">The command is issued to the underlying data provider, and its syntax depends on the requirements of that provider.</span></span> <span data-ttu-id="42e3e-112">这通常是 SQL 语言，但 ADO 不需要任何特定的查询语言。</span><span class="sxs-lookup"><span data-stu-id="42e3e-112">This will typically be the SQL language, although ADO does not require any particular query language.</span></span>
    
    - <span data-ttu-id="42e3e-113">现有已构形 **Recordset** 的名称。</span><span class="sxs-lookup"><span data-stu-id="42e3e-113">The name of an existing shaped **Recordset**.</span></span>
    
    - <span data-ttu-id="42e3e-114">另一个 Shape 命令。</span><span class="sxs-lookup"><span data-stu-id="42e3e-114">Another shape command.</span></span>
    
    - <span data-ttu-id="42e3e-115">TABLE 关键字，后跟数据提供程序中的表的名称。</span><span class="sxs-lookup"><span data-stu-id="42e3e-115">The TABLE keyword, followed by the name of a table in the data provider.</span></span>

- <span data-ttu-id="42e3e-116">*child-alias*</span><span class="sxs-lookup"><span data-stu-id="42e3e-116">*child-alias*</span></span>

  - <span data-ttu-id="42e3e-p102">别名，用于引用由 *child-command* 返回的 **Recordset**。*child-alias* 在 COMPUTE 子句的列的列表中是必需的，它定义了父和子 **Recordset** 对象之间的关系。</span><span class="sxs-lookup"><span data-stu-id="42e3e-p102">An alias used to refer to the **Recordset** returned by the *child-command.* The *child-alias* is required in the list of columns in the COMPUTE clause and defines the relation between the parent and child **Recordset** objects.</span></span>

- <span data-ttu-id="42e3e-119">*appended-column-list*</span><span class="sxs-lookup"><span data-stu-id="42e3e-119">*appended-column-list*</span></span>

  - <span data-ttu-id="42e3e-p103">列表，其中的每个元素定义了所生成的父记录集中的列。每个元素都包含章节列、新列、计算列或对子 **Recordset** 执行聚合函数得到的值。</span><span class="sxs-lookup"><span data-stu-id="42e3e-p103">A list in which each element defines a column in the generated parent. Each element contains either a chapter column, a new column, a calculated column, or a value resulting from an aggregate function on the child **Recordset**.</span></span>

- <span data-ttu-id="42e3e-122">*grp-field-list*</span><span class="sxs-lookup"><span data-stu-id="42e3e-122">*grp-field-list*</span></span>

  - <span data-ttu-id="42e3e-123">父和子 **Recordset** 对象中列的列表，用于指定在子记录集中应当如何对行进行分组。</span><span class="sxs-lookup"><span data-stu-id="42e3e-123">A list of columns in the parent and child **Recordset** objects that specifies how rows should be grouped in the child.</span></span> <span data-ttu-id="42e3e-124">对于 *grp-field-list* 中的每个列，在子和父 **Recordset** 对象中都有相应的列。</span><span class="sxs-lookup"><span data-stu-id="42e3e-124">For each column in the *grp-field-list,* there is a corresponding column in the child and parent **Recordset** objects.</span></span> <span data-ttu-id="42e3e-125">对于父 **Recordset** 中的每个行，*grp-field-list* 列都有唯一的值，父行所引用的子 **Recordset** 仅由其 *grp-field-list* 列与父行具有相同值的子行组成。</span><span class="sxs-lookup"><span data-stu-id="42e3e-125">For each row in the parent **Recordset**, the *grp-field-list* columns have unique values, and the child **Recordset** referenced by the parent row consists solely of child rows whose *grp-field-list* columns have the same values as the parent row.</span></span>

<span data-ttu-id="42e3e-p105">如果包含 BY 子句，将基于 COMPUTE 子句中的列对子 **Recordset** 的行进行分组。对于子 **Recordset** 中的每一组行，父 **Recordset** 将相应包含一行。</span><span class="sxs-lookup"><span data-stu-id="42e3e-p105">If the BY clause is included, the child **Recordset**'s rows will be grouped based on the columns in the COMPUTE clause. The parent **Recordset** will contain one row for each group of rows in the child **Recordset**.</span></span>

<span data-ttu-id="42e3e-p106">如果省略 BY 子句，则会将整个子 **Recordset** 视为单个组，并且父 **Recordset** 将只包含一行。该行将引用整个子 **Recordset** 。通过省略 BY 子句，可以对整个子 **Recordset** 计算"总计"聚合。</span><span class="sxs-lookup"><span data-stu-id="42e3e-p106">If the BY clause is omitted, the entire child **Recordset** is treated as a single group and the parent **Recordset** will contain exactly one row. That row will reference the entire child **Recordset**. Omitting the BY clause allows you to compute "grand total" aggregates over the entire child **Recordset**.</span></span>

<span data-ttu-id="42e3e-131">例如：</span><span class="sxs-lookup"><span data-stu-id="42e3e-131">For example:</span></span>

```vb
    SHAPE {select * from Orders} AS orders
       COMPUTE orders, SUM(orders.OrderAmount) as TotalSales
```

<span data-ttu-id="42e3e-p107">不管采用什么方式形成父 **Recordset**（使用 COMPUTE 或使用 APPEND），它都将包含用来将它与子 **Recordset** 相关的章节列。如果愿意，父 **Recordset** 所包含的列还可能包含针对子行的聚合（SUM、MIN、MAX 等）。父和子 **Recordset** 所包含的列都可能包含针对 **Recordset** 中的行的表达式，以及最初为空的新列。</span><span class="sxs-lookup"><span data-stu-id="42e3e-p107">Regardless of which way the parent **Recordset** is formed (using COMPUTE or using APPEND), it will contain a chapter column that is used to relate it to a child **Recordset**. If you wish, the parent **Recordset** may also contain columns that contain aggregates (SUM, MIN, MAX, and so on) over the child rows. Both the parent and the child **Recordset** may contain columns that contain an expression on the row in the **Recordset**, as well as columns that are new and initially empty.</span></span>

## <a name="operation"></a><span data-ttu-id="42e3e-135">Operation</span><span class="sxs-lookup"><span data-stu-id="42e3e-135">Operation</span></span>

<span data-ttu-id="42e3e-136">*child-command* 向提供程序发出，提供程序则返回子 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="42e3e-136">The *child-command* is issued to the provider, which returns a child **Recordset**.</span></span>

<span data-ttu-id="42e3e-p108">COMPUTE 子句指定父 **Recordset** 的列，而父记录集则可能是以下项：对子 **Recordset** 的引用、一个或多个聚合、计算表达式或新列。如果有 BY 子句，则它定义的列也将追加到父 **Recordset** 中。BY 子句指定如何对子 **Recordset** 的行进行分组。</span><span class="sxs-lookup"><span data-stu-id="42e3e-p108">The COMPUTE clause specifies the columns of the parent **Recordset**, which may be a reference to the child **Recordset**, one or more aggregates, a calculated expression, or new columns. If there is a BY clause, the columns it defines are also appended to the parent **Recordset**. The BY clause specifies how the rows of the child **Recordset** are grouped.</span></span>

<span data-ttu-id="42e3e-140">例如，假设有一个表 Demographics（人口统计）是由 State（省/市/自治区）、City（市/县）和 Population（人口）字段组成的（人口数字仅用于举例说明）。</span><span class="sxs-lookup"><span data-stu-id="42e3e-140">For example, assume you have a table — Demographics — consisting of State, City, and Population fields (the population figures are solely for illustration).</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="42e3e-141">状态</span><span class="sxs-lookup"><span data-stu-id="42e3e-141">State</span></span></p></th>
<th><p><span data-ttu-id="42e3e-142">城市</span><span class="sxs-lookup"><span data-stu-id="42e3e-142">City</span></span></p></th>
<th><p><span data-ttu-id="42e3e-143">带来</span><span class="sxs-lookup"><span data-stu-id="42e3e-143">Population</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42e3e-144">WA</span><span class="sxs-lookup"><span data-stu-id="42e3e-144">WA</span></span></p></td>
<td><p><span data-ttu-id="42e3e-145">」</span><span class="sxs-lookup"><span data-stu-id="42e3e-145">Seattle</span></span></p></td>
<td><p><span data-ttu-id="42e3e-146">700000</span><span class="sxs-lookup"><span data-stu-id="42e3e-146">700,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42e3e-147">OR</span><span class="sxs-lookup"><span data-stu-id="42e3e-147">OR</span></span></p></td>
<td><p><span data-ttu-id="42e3e-148">Medford</span><span class="sxs-lookup"><span data-stu-id="42e3e-148">Medford</span></span></p></td>
<td><p><span data-ttu-id="42e3e-149">200,000</span><span class="sxs-lookup"><span data-stu-id="42e3e-149">200,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42e3e-150">OR</span><span class="sxs-lookup"><span data-stu-id="42e3e-150">OR</span></span></p></td>
<td><p><span data-ttu-id="42e3e-151">波特兰</span><span class="sxs-lookup"><span data-stu-id="42e3e-151">Portland</span></span></p></td>
<td><p><span data-ttu-id="42e3e-152">400,000</span><span class="sxs-lookup"><span data-stu-id="42e3e-152">400,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42e3e-153">证书</span><span class="sxs-lookup"><span data-stu-id="42e3e-153">CA</span></span></p></td>
<td><p><span data-ttu-id="42e3e-154">Los Angeles</span><span class="sxs-lookup"><span data-stu-id="42e3e-154">Los Angeles</span></span></p></td>
<td><p><span data-ttu-id="42e3e-155">800000</span><span class="sxs-lookup"><span data-stu-id="42e3e-155">800,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42e3e-156">证书</span><span class="sxs-lookup"><span data-stu-id="42e3e-156">CA</span></span></p></td>
<td><p><span data-ttu-id="42e3e-157">San Diego</span><span class="sxs-lookup"><span data-stu-id="42e3e-157">San Diego</span></span></p></td>
<td><p><span data-ttu-id="42e3e-158">600,000</span><span class="sxs-lookup"><span data-stu-id="42e3e-158">600,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42e3e-159">WA</span><span class="sxs-lookup"><span data-stu-id="42e3e-159">WA</span></span></p></td>
<td><p><span data-ttu-id="42e3e-160">Tacoma</span><span class="sxs-lookup"><span data-stu-id="42e3e-160">Tacoma</span></span></p></td>
<td><p><span data-ttu-id="42e3e-161">500,000</span><span class="sxs-lookup"><span data-stu-id="42e3e-161">500,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42e3e-162">OR</span><span class="sxs-lookup"><span data-stu-id="42e3e-162">OR</span></span></p></td>
<td><p><span data-ttu-id="42e3e-163">Corvallis</span><span class="sxs-lookup"><span data-stu-id="42e3e-163">Corvallis</span></span></p></td>
<td><p><span data-ttu-id="42e3e-164">300000</span><span class="sxs-lookup"><span data-stu-id="42e3e-164">300,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="42e3e-165">现在，发出以下 Shape 命令：</span><span class="sxs-lookup"><span data-stu-id="42e3e-165">Now, issue this shape command:</span></span>

```vb 
 
rst.Open  "SHAPE {select * from demographics} AS rs "  & _ 
          "COMPUTE rs, SUM(rs.population) BY state", _ 
           objConnection 
```

<span data-ttu-id="42e3e-166">此命令将打开一个具有两个级别的已构形 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="42e3e-166">This command opens a shaped **Recordset** with two levels.</span></span> <span data-ttu-id="42e3e-167">父级别是一个生成的**记录集**, 其中包含聚合列 (SUM (rs-232c))、引用子**recordset**的列 (rs) 以及用于对子**recordset**进行分组的列 (state)。</span><span class="sxs-lookup"><span data-stu-id="42e3e-167">The parent level is a generated **Recordset** with an aggregate column (SUM(rs.population) ), a column referencing the child **Recordset** (rs ), and a column for grouping the child **Recordset** (state ).</span></span> <span data-ttu-id="42e3e-168">子级别是查询命令 ()、引用子**recordset** (rs) 的列和用于对子**recordset**进行分组的列 (状态) 的**记录集**。</span><span class="sxs-lookup"><span data-stu-id="42e3e-168">The child level is the **Recordset** returned by the query command (), a column referencing the child **Recordset** (rs ), and a column for grouping the child **Recordset** (state ).</span></span> <span data-ttu-id="42e3e-169">子级别是查询命令\*\*\*\* (从人口统计中选择\* ) 返回的 Recordset。</span><span class="sxs-lookup"><span data-stu-id="42e3e-169">The child level is the **Recordset** returned by the query command (select \* from demographics ).</span></span>

<span data-ttu-id="42e3e-p110">子 **Recordset** 明细行将按省/市/自治区进行分组，但在其他情况下并没有特定的顺序。就是说，组将不以字母或数字顺序分组。如果想让父 **Recordset** 排序，可以使用 **Recordset** 的 **Sort** 方法对父 **Recordset** 进行排序。</span><span class="sxs-lookup"><span data-stu-id="42e3e-p110">The child **Recordset** detail rows will be grouped by state, but otherwise in no particular order. That is, the groups will not be in alphabetical or numerical order. If you want the parent **Recordset** to be ordered, you can use the **Recordset** **Sort** method to order the parent **Recordset**.</span></span>

<span data-ttu-id="42e3e-p111">现在可以在打开的父 **Recordset** 中导航，并访问子明细 **Recordset** 对象。有关详细信息，请参阅 [访问分层记录集中的行](accessing-rows-in-a-hierarchical-recordset.md)。</span><span class="sxs-lookup"><span data-stu-id="42e3e-p111">You can now navigate the opened parent **Recordset** and access the child detail **Recordset** objects. For more information, see [Accessing Rows in a Hierarchical Recordset](accessing-rows-in-a-hierarchical-recordset.md).</span></span>

<span data-ttu-id="42e3e-175">**结果父和子明细记录集**</span><span class="sxs-lookup"><span data-stu-id="42e3e-175">**Resultant Parent and Child Detail Recordsets**</span></span>

<span data-ttu-id="42e3e-176">**Parent**</span><span class="sxs-lookup"><span data-stu-id="42e3e-176">**Parent**</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="42e3e-177">SUM (rs.Population)</span><span class="sxs-lookup"><span data-stu-id="42e3e-177">SUM (rs.Population)</span></span></p></th>
<th><p><span data-ttu-id="42e3e-178">rs</span><span class="sxs-lookup"><span data-stu-id="42e3e-178">rs</span></span></p></th>
<th><p><span data-ttu-id="42e3e-179">状态</span><span class="sxs-lookup"><span data-stu-id="42e3e-179">State</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42e3e-180">1300000</span><span class="sxs-lookup"><span data-stu-id="42e3e-180">1,300,000</span></span></p></td>
<td><p><span data-ttu-id="42e3e-181">引用 child1</span><span class="sxs-lookup"><span data-stu-id="42e3e-181">Reference to child1</span></span></p></td>
<td><p><span data-ttu-id="42e3e-182">证书</span><span class="sxs-lookup"><span data-stu-id="42e3e-182">CA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42e3e-183">1200000</span><span class="sxs-lookup"><span data-stu-id="42e3e-183">1,200,000</span></span></p></td>
<td><p><span data-ttu-id="42e3e-184">引用 child2</span><span class="sxs-lookup"><span data-stu-id="42e3e-184">Reference to child2</span></span></p></td>
<td><p><span data-ttu-id="42e3e-185">WA</span><span class="sxs-lookup"><span data-stu-id="42e3e-185">WA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42e3e-186">1100000</span><span class="sxs-lookup"><span data-stu-id="42e3e-186">1,100,000</span></span></p></td>
<td><p><span data-ttu-id="42e3e-187">引用 child3</span><span class="sxs-lookup"><span data-stu-id="42e3e-187">Reference to child3</span></span></p></td>
<td><p><span data-ttu-id="42e3e-188">OR</span><span class="sxs-lookup"><span data-stu-id="42e3e-188">OR</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="42e3e-189">**Child1**</span><span class="sxs-lookup"><span data-stu-id="42e3e-189">**Child1**</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="42e3e-190">状态</span><span class="sxs-lookup"><span data-stu-id="42e3e-190">State</span></span></p></th>
<th><p><span data-ttu-id="42e3e-191">城市</span><span class="sxs-lookup"><span data-stu-id="42e3e-191">City</span></span></p></th>
<th><p><span data-ttu-id="42e3e-192">带来</span><span class="sxs-lookup"><span data-stu-id="42e3e-192">Population</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42e3e-193">证书</span><span class="sxs-lookup"><span data-stu-id="42e3e-193">CA</span></span></p></td>
<td><p><span data-ttu-id="42e3e-194">Los Angeles</span><span class="sxs-lookup"><span data-stu-id="42e3e-194">Los Angeles</span></span></p></td>
<td><p><span data-ttu-id="42e3e-195">800000</span><span class="sxs-lookup"><span data-stu-id="42e3e-195">800,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42e3e-196">证书</span><span class="sxs-lookup"><span data-stu-id="42e3e-196">CA</span></span></p></td>
<td><p><span data-ttu-id="42e3e-197">San Diego</span><span class="sxs-lookup"><span data-stu-id="42e3e-197">San Diego</span></span></p></td>
<td><p><span data-ttu-id="42e3e-198">600,000</span><span class="sxs-lookup"><span data-stu-id="42e3e-198">600,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="42e3e-199">**Child2**</span><span class="sxs-lookup"><span data-stu-id="42e3e-199">**Child2**</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="42e3e-200">状态</span><span class="sxs-lookup"><span data-stu-id="42e3e-200">State</span></span></p></th>
<th><p><span data-ttu-id="42e3e-201">城市</span><span class="sxs-lookup"><span data-stu-id="42e3e-201">City</span></span></p></th>
<th><p><span data-ttu-id="42e3e-202">带来</span><span class="sxs-lookup"><span data-stu-id="42e3e-202">Population</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42e3e-203">WA</span><span class="sxs-lookup"><span data-stu-id="42e3e-203">WA</span></span></p></td>
<td><p><span data-ttu-id="42e3e-204">」</span><span class="sxs-lookup"><span data-stu-id="42e3e-204">Seattle</span></span></p></td>
<td><p><span data-ttu-id="42e3e-205">700000</span><span class="sxs-lookup"><span data-stu-id="42e3e-205">700,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42e3e-206">WA</span><span class="sxs-lookup"><span data-stu-id="42e3e-206">WA</span></span></p></td>
<td><p><span data-ttu-id="42e3e-207">Tacoma</span><span class="sxs-lookup"><span data-stu-id="42e3e-207">Tacoma</span></span></p></td>
<td><p><span data-ttu-id="42e3e-208">500,000</span><span class="sxs-lookup"><span data-stu-id="42e3e-208">500,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="42e3e-209">**Child3**</span><span class="sxs-lookup"><span data-stu-id="42e3e-209">**Child3**</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="42e3e-210">状态</span><span class="sxs-lookup"><span data-stu-id="42e3e-210">State</span></span></p></th>
<th><p><span data-ttu-id="42e3e-211">城市</span><span class="sxs-lookup"><span data-stu-id="42e3e-211">City</span></span></p></th>
<th><p><span data-ttu-id="42e3e-212">带来</span><span class="sxs-lookup"><span data-stu-id="42e3e-212">Population</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42e3e-213">OR</span><span class="sxs-lookup"><span data-stu-id="42e3e-213">OR</span></span></p></td>
<td><p><span data-ttu-id="42e3e-214">Medford</span><span class="sxs-lookup"><span data-stu-id="42e3e-214">Medford</span></span></p></td>
<td><p><span data-ttu-id="42e3e-215">200,000</span><span class="sxs-lookup"><span data-stu-id="42e3e-215">200,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42e3e-216">OR</span><span class="sxs-lookup"><span data-stu-id="42e3e-216">OR</span></span></p></td>
<td><p><span data-ttu-id="42e3e-217">波特兰</span><span class="sxs-lookup"><span data-stu-id="42e3e-217">Portland</span></span></p></td>
<td><p><span data-ttu-id="42e3e-218">400,000</span><span class="sxs-lookup"><span data-stu-id="42e3e-218">400,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42e3e-219">OR</span><span class="sxs-lookup"><span data-stu-id="42e3e-219">OR</span></span></p></td>
<td><p><span data-ttu-id="42e3e-220">Corvallis</span><span class="sxs-lookup"><span data-stu-id="42e3e-220">Corvallis</span></span></p></td>
<td><p><span data-ttu-id="42e3e-221">300000</span><span class="sxs-lookup"><span data-stu-id="42e3e-221">300,000</span></span></p></td>
</tr>
</tbody>
</table>

