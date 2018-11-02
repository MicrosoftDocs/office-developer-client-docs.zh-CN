---
title: SQL 子查询 (Microsoft Access SQL)
TOCTitle: SQL subqueries (Microsoft Access SQL)
ms:assetid: 3b6c0a5d-ab24-e1cf-0175-3f8e68c2dfbf
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192664(v=office.15)
ms:contentKeyID: 48544285
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277580
dev_langs:
- sql
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 72d9d9d27ac128ec587621231b5c899bc89c2752
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25925946"
---
# <a name="sql-subqueries-microsoft-access-sql"></a><span data-ttu-id="2b6be-102">SQL 子查询 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="2b6be-102">SQL subqueries (Microsoft Access SQL)</span></span>


<span data-ttu-id="2b6be-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="2b6be-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2b6be-104">子查询是一个 [SELECT](select-statement-microsoft-access-sql.md) 语句，它嵌套在 SELECT、 [SELECT...INTO](select-into-statement-microsoft-access-sql.md)、[INSERT...INTO](insert-into-statement-microsoft-access-sql.md)、[DELETE](delete-statement-microsoft-access-sql.md) 或 [UPDATE](update-statement-microsoft-access-sql.md) 语句中，或嵌套在另一个子查询中。</span><span class="sxs-lookup"><span data-stu-id="2b6be-104">A subquery is a [SELECT](select-statement-microsoft-access-sql.md) statement nested inside a SELECT, [SELECT…INTO](select-into-statement-microsoft-access-sql.md), [INSERT…INTO](insert-into-statement-microsoft-access-sql.md), [DELETE](delete-statement-microsoft-access-sql.md), or [UPDATE](update-statement-microsoft-access-sql.md) statement or inside another subquery.</span></span>

## <a name="syntax"></a><span data-ttu-id="2b6be-105">语法</span><span class="sxs-lookup"><span data-stu-id="2b6be-105">Syntax</span></span>

<span data-ttu-id="2b6be-106">可以通过三种语法形式来创建子查询：</span><span class="sxs-lookup"><span data-stu-id="2b6be-106">You can use three forms of syntax to create a subquery:</span></span>

<span data-ttu-id="2b6be-107">*比较*\[ANY |所有 |一些\](*sqlstatement*)</span><span class="sxs-lookup"><span data-stu-id="2b6be-107">*comparison* \[ANY | ALL | SOME\] (*sqlstatement*)</span></span>

<span data-ttu-id="2b6be-108">*表达式*\[不\]中 (*sqlstatement*)</span><span class="sxs-lookup"><span data-stu-id="2b6be-108">*expression* \[NOT\] IN (*sqlstatement*)</span></span>

<span data-ttu-id="2b6be-109">\[不\]EXISTS (*sqlstatement*)</span><span class="sxs-lookup"><span data-stu-id="2b6be-109">\[NOT\] EXISTS (*sqlstatement*)</span></span>

<span data-ttu-id="2b6be-110">子查询语句包含了以下部分：</span><span class="sxs-lookup"><span data-stu-id="2b6be-110">A subquery has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2b6be-111">部分</span><span class="sxs-lookup"><span data-stu-id="2b6be-111">Part</span></span></p></th>
<th><p><span data-ttu-id="2b6be-112">说明</span><span class="sxs-lookup"><span data-stu-id="2b6be-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b6be-113"><em>comparison</em></span><span class="sxs-lookup"><span data-stu-id="2b6be-113"><em>comparison</em></span></span></p></td>
<td><p><span data-ttu-id="2b6be-114">表达式和比较运算符，用于对表达式与子查询的结果进行比较。</span><span class="sxs-lookup"><span data-stu-id="2b6be-114">An expression and a comparison operator that compares the expression with the results of the subquery.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b6be-115"><em>expression</em></span><span class="sxs-lookup"><span data-stu-id="2b6be-115"><em>expression</em></span></span></p></td>
<td><p><span data-ttu-id="2b6be-116">表达式，用来搜索子查询的结果集。</span><span class="sxs-lookup"><span data-stu-id="2b6be-116">An expression for which the result set of the subquery is searched.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b6be-117"><em>sqlstatement</em></span><span class="sxs-lookup"><span data-stu-id="2b6be-117"><em>sqlstatement</em></span></span></p></td>
<td><p><span data-ttu-id="2b6be-p101">SELECT 语句，遵循和任何其他 SELECT 语句一样的格式和规则。它必须用圆括号括起来。</span><span class="sxs-lookup"><span data-stu-id="2b6be-p101">A SELECT statement, following the same format and rules as any other SELECT statement. It must be enclosed in parentheses.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="2b6be-120">注解</span><span class="sxs-lookup"><span data-stu-id="2b6be-120">Remarks</span></span>

<span data-ttu-id="2b6be-p102">可以在 SELECT 语句的字段列表中、在 [WHERE](https://msdn.microsoft.com/library/ff195245\(v=office.15\)) 子句中或在 [HAVING](https://msdn.microsoft.com/library/ff193795\(v=office.15\)) 子句中使用子查询来代替表达式。在子查询中，可以使用 SELECT 语句来提供一组要在 WHERE 或 HAVING 子句表达式中计算的一个或多个特定值。</span><span class="sxs-lookup"><span data-stu-id="2b6be-p102">You can use a subquery instead of an expression in the field list of a SELECT statement or in a [WHERE](https://msdn.microsoft.com/library/ff195245\(v=office.15\)) or [HAVING](https://msdn.microsoft.com/library/ff193795\(v=office.15\)) clause. In a subquery, you use a SELECT statement to provide a set of one or more specific values to evaluate in the WHERE or HAVING clause expression.</span></span>

<span data-ttu-id="2b6be-p103">通过同义的 ANY 或 SOME 谓词，可以检索在主查询的记录中满足与子查询所检索出的任何记录进行比较的比较条件的记录。下面的示例返回那些单价高于以 25% 或更高折扣出售的任何产品的单价的产品：</span><span class="sxs-lookup"><span data-stu-id="2b6be-p103">Use the ANY or SOME predicate, which are synonymous, to retrieve records in the main query that satisfy the comparison with any records retrieved in the subquery. The following example returns all products whose unit price is greater than that of any product sold at a discount of 25 percent or more:</span></span>

```sql
SELECT * FROM Products 
WHERE UnitPrice > ANY 
(SELECT UnitPrice FROM OrderDetails 
WHERE Discount >= .25);
```

<span data-ttu-id="2b6be-p104">使用 [ALL](https://msdn.microsoft.com/library/ff195711\(v=office.15\)) 谓词可以在主查询中只检索满足子查询中检索的所有记录的比较条件的记录。如果将前面的示例中的 ANY 改为 ALL，查询将只返回那些单价高于以 25% 或更高折扣出售的所有产品单价的产品。它的限制性更强。</span><span class="sxs-lookup"><span data-stu-id="2b6be-p104">Use the [ALL](https://msdn.microsoft.com/library/ff195711\(v=office.15\)) predicate to retrieve only those records in the main query that satisfy the comparison with all records retrieved in the subquery. If you changed ANY to ALL in the previous example, the query would return only those products whose unit price is greater than that of all products sold at a discount of 25 percent or more. This is much more restrictive.</span></span>

<span data-ttu-id="2b6be-p105">通过 IN 谓词可以只检索出在主查询的记录中作为子查询的一部分记录而包含相同值的记录。下面的示例返回所有以 25% 或更高折扣出售的所有产品：</span><span class="sxs-lookup"><span data-stu-id="2b6be-p105">Use the IN predicate to retrieve only those records in the main query for which some record in the subquery contains an equal value. The following example returns all products with a discount of 25 percent or more:</span></span>

```sql
SELECT * FROM Products 
WHERE ProductID IN 
(SELECT ProductID FROM OrderDetails 
WHERE Discount >= .25);
```

<span data-ttu-id="2b6be-130">相应地，可以使用 NOT IN 来仅检索出在主查询的记录中作为子查询的记录而不包含相同值的记录。</span><span class="sxs-lookup"><span data-stu-id="2b6be-130">Conversely, you can use NOT IN to retrieve only those records in the main query for which no record in the subquery contains an equal value.</span></span>

<span data-ttu-id="2b6be-131">在 True/False 比较条件中使用 EXISTS 谓词（带有可选的 NOT 保留字）可确定子查询是否返回任何记录。</span><span class="sxs-lookup"><span data-stu-id="2b6be-131">Use the EXISTS predicate (with the optional NOT reserved word) in true/false comparisons to determine whether the subquery returns any records.</span></span>

<span data-ttu-id="2b6be-p106">也可以在子查询中使用表名的别名来引用在子查询外部的 [FROM](https://msdn.microsoft.com/library/ff836674\(v=office.15\)) 子句中列出的表。以下示例返回薪水等于或高于具有同等职称的所有雇员平均薪水的雇员的姓名。Employees 表别名为"T1"：</span><span class="sxs-lookup"><span data-stu-id="2b6be-p106">You can also use table name aliases in a subquery to refer to tables listed in a [FROM](https://msdn.microsoft.com/library/ff836674\(v=office.15\)) clause outside the subquery. The following example returns the names of employees whose salaries are equal to or greater than the average salary of all employees having the same job title. The Employees table is given the alias "T1":</span></span>

```sql
SELECT LastName,
FirstName, Title, Salary 
FROM Employees AS T1 
WHERE Salary >= (SELECT Avg(Salary) 
FROM Employees 
WHERE T1.Title = Employees.Title) Order by Title;
```

<span data-ttu-id="2b6be-135">在前面的示例中，AS 保留字是可选的。</span><span class="sxs-lookup"><span data-stu-id="2b6be-135">In the preceding example, the AS reserved word is optional.</span></span>

<span data-ttu-id="2b6be-p107">允许一些子查询用在交叉表查询中，特别是作为谓词（在 WHERE 子句中的谓词）。不允许将作为输出的子查询（在 SELECT 列表中）用在交叉表查询中。</span><span class="sxs-lookup"><span data-stu-id="2b6be-p107">Some subqueries are allowed in crosstab queries— specifically, as predicates (those in the WHERE clause). Subqueries as output (those in the SELECT list) are not allowed in crosstab queries.</span></span>

## <a name="example"></a><span data-ttu-id="2b6be-138">示例</span><span class="sxs-lookup"><span data-stu-id="2b6be-138">Example</span></span>

<span data-ttu-id="2b6be-139">以下示例列出在 1995 年第二季度下过订单的每个客户的名称和联系人。</span><span class="sxs-lookup"><span data-stu-id="2b6be-139">This example lists the name and contact of every customer who placed an order in the second quarter of 1995.</span></span>

<span data-ttu-id="2b6be-140">以下示例调用 EnumFields 过程，您可以在 SELECT 语句示例中找到该过程。</span><span class="sxs-lookup"><span data-stu-id="2b6be-140">This example calls the EnumFields procedure, which you can find in the SELECT statement example.</span></span>

```vb
    Sub SubQueryX() 
     
        Dim dbs As Database, rst As Recordset 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
         
        ' List the name and contact of every customer  
        ' who placed an order in the second quarter of 
        ' 1995. 
        Set rst = dbs.OpenRecordset("SELECT ContactName," _ 
            & " CompanyName, ContactTitle, Phone" _ 
            & " FROM Customers" _ 
            & " WHERE CustomerID" _ 
            & " IN (SELECT CustomerID FROM Orders" _ 
            & " WHERE OrderDate Between #04/1/95#" _ 
            & " And #07/1/95#);") 
         
        ' Populate the Recordset. 
        rst.MoveLast 
         
        ' Call EnumFields to print the contents of the  
        ' Recordset. Pass the Recordset object and desired 
        ' field width. 
        EnumFields rst, 25 
     
        dbs.Close 
     
    End Sub
```
