---
title: INNER JOIN 操作 (Microsoft Access SQL)
TOCTitle: INNER JOIN operation (Microsoft Access SQL)
ms:assetid: 8d16c74c-02c6-12b7-b180-3e7744ef65f3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197346(v=office.15)
ms:contentKeyID: 48546247
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277574
dev_langs:
- sql
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 4f9593e8bf0175ee6a25bd53d886c291eed6f75c
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25929433"
---
# <a name="inner-join-operation-microsoft-access-sql"></a><span data-ttu-id="26f88-102">INNER JOIN 操作 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="26f88-102">INNER JOIN operation (Microsoft Access SQL)</span></span>


<span data-ttu-id="26f88-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="26f88-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="26f88-104">只要两个表的公共字段有匹配值，就将这两个表中的记录组合起来。</span><span class="sxs-lookup"><span data-stu-id="26f88-104">Combines records from two tables whenever there are matching values in a common field.</span></span>

## <a name="syntax"></a><span data-ttu-id="26f88-105">语法</span><span class="sxs-lookup"><span data-stu-id="26f88-105">Syntax</span></span>

<span data-ttu-id="26f88-106">从*table1* INNER JOIN *table2*对*表 1*。*field1\*\*compopr table2*。*field2*</span><span class="sxs-lookup"><span data-stu-id="26f88-106">FROM *table1* INNER JOIN *table2* ON *table1*.*field1* *compopr table2*.*field2*</span></span>

<span data-ttu-id="26f88-107">INNER JOIN 操作包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="26f88-107">The INNER JOIN operation has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="26f88-108">部分</span><span class="sxs-lookup"><span data-stu-id="26f88-108">Part</span></span></p></th>
<th><p><span data-ttu-id="26f88-109">说明</span><span class="sxs-lookup"><span data-stu-id="26f88-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26f88-110"><em>table1</em>、<em>table2</em></span><span class="sxs-lookup"><span data-stu-id="26f88-110"><em>table1</em>, <em>table2</em></span></span></p></td>
<td><p><span data-ttu-id="26f88-111">要组合其中记录的表的名称。</span><span class="sxs-lookup"><span data-stu-id="26f88-111">The names of the tables from which records are combined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26f88-112"><em>field1</em>、<em>field2</em></span><span class="sxs-lookup"><span data-stu-id="26f88-112"><em>field1</em>, <em>field2</em></span></span></p></td>
<td><p><span data-ttu-id="26f88-p101">被联接的字段的名称。如果它们不是数字，则这些字段的数据类型必须相同，并且包含同类数据，但是，它们不必具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="26f88-p101">The names of the fields that are joined. If they are not numeric, the fields must be of the same data type and contain the same kind of data, but they do not have to have the same name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26f88-115"><em>compopr</em></span><span class="sxs-lookup"><span data-stu-id="26f88-115"><em>compopr</em></span></span></p></td>
<td><p><span data-ttu-id="26f88-116">任何关系比较运算符： &quot;= 和&quot; &quot; &lt;，&quot; &quot; &gt;，&quot; &quot; &lt;=&quot; &quot; &gt;=&quot;或&quot; &lt; &gt;。&quot;</span><span class="sxs-lookup"><span data-stu-id="26f88-116">Any relational comparison operator: &quot;=,&quot; &quot;&lt;,&quot; &quot;&gt;,&quot; &quot;&lt;=,&quot; &quot;&gt;=,&quot; or &quot;&lt;&gt;.&quot;</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="26f88-117">说明</span><span class="sxs-lookup"><span data-stu-id="26f88-117">Remarks</span></span>

<span data-ttu-id="26f88-p102">可以在任何 [FROM](https://msdn.microsoft.com/library/ff836674\(v=office.15\)) 子句中使用 INNER JOIN 操作。这是最常用的联接类型。只要两个表的公共字段上存在相匹配的值，Inner 联接就会组合这些表中的记录。</span><span class="sxs-lookup"><span data-stu-id="26f88-p102">You can use an INNER JOIN operation in any [FROM](https://msdn.microsoft.com/library/ff836674\(v=office.15\)) clause. This is the most common type of join. Inner joins combine records from two tables whenever there are matching values in a field common to both tables.</span></span>

<span data-ttu-id="26f88-p103">可以将 INNER JOIN 用于 Departments 及 Employees 表，以选择每个部门的所有雇员。相反，选择所有部门（即使某些部门中并没有分配雇员）或者所有雇员（即使某些雇员没有分配到任何部门），则可以使用 [LEFT JOIN 或 RIGHT JOIN](left-join-right-join-operations-microsoft-access-sql.md) 操作来创建外部联接。</span><span class="sxs-lookup"><span data-stu-id="26f88-p103">You can use INNER JOIN with the Departments and Employees tables to select all the employees in each department. In contrast, to select all departments (even if some have no employees assigned to them) or all employees (even if some are not assigned to a department), you can use a [LEFT JOIN or RIGHT JOIN](left-join-right-join-operations-microsoft-access-sql.md) operation to create an outer join.</span></span>

<span data-ttu-id="26f88-123">如果试图联接包含 Memo 或 OLE 对象数据的字段，将产生错误。</span><span class="sxs-lookup"><span data-stu-id="26f88-123">If you try to join fields containing Memo or OLE Object data, an error occurs.</span></span>

<span data-ttu-id="26f88-p104">可以联接任何两个相似类型的数字字段。例如，可以联接自动编号和长整型字段，因为它们均是相似类型。然而，不能联接单精度型和双精度型类型字段。</span><span class="sxs-lookup"><span data-stu-id="26f88-p104">You can join any two numeric fields of like types. For example, you can join on AutoNumber and Long fields because they are like types. However, you cannot join Single and Double types of fields.</span></span>

<span data-ttu-id="26f88-127">以下示例演示如何通过 CategoryID 字段联接 Categories 和 Products 表：</span><span class="sxs-lookup"><span data-stu-id="26f88-127">The following example shows how you could join the Categories and Products tables on the CategoryID field:</span></span>

```sql
SELECT CategoryName, ProductName 
FROM Categories INNER JOIN Products 
ON Categories.CategoryID = Products.CategoryID;
```

<span data-ttu-id="26f88-128">在前面的示例中，CategoryID 是联接字段，但是它不包含在查询输出中，因为它不包含在 [SELECT](select-statement-microsoft-access-sql.md) 语句中。</span><span class="sxs-lookup"><span data-stu-id="26f88-128">In the preceding example, CategoryID is the joined field, but it is not included in the query output because it is not included in the [SELECT](select-statement-microsoft-access-sql.md) statement.</span></span> <span data-ttu-id="26f88-129">若要包含的联接的字段，包括字段名称的 SELECT 语句中，在此情况下，Categories.CategoryID。</span><span class="sxs-lookup"><span data-stu-id="26f88-129">To include the joined field, include the field name in the SELECT statement — in this case, Categories.CategoryID.</span></span>

<span data-ttu-id="26f88-130">也可以在 JOIN 语句中链接多个 ON 子句，请使用如下语法：</span><span class="sxs-lookup"><span data-stu-id="26f88-130">You can also link several ON clauses in a JOIN statement, using the following syntax:</span></span>

<span data-ttu-id="26f88-131">选择*fields* FROM *table1* INNER JOIN *table2* ON *table1*。*field1**compopr**表 2*。*field1*和对*表 1*。*field2**compopr**表 2*。*field2*)或对*表 1*。*field3**compopr**表 2*。*field3*)\];</span><span class="sxs-lookup"><span data-stu-id="26f88-131">SELECT *fields* FROM *table1* INNER JOIN *table2* ON *table1*.*field1* *compopr* *table2*.*field1* AND ON *table1*.*field2* *compopr* *table2*.*field2*) OR ON *table1*.*field3* *compopr* *table2*.*field3*)\];</span></span>

<span data-ttu-id="26f88-132">也可以通过如下语法嵌套 JOIN 语句：</span><span class="sxs-lookup"><span data-stu-id="26f88-132">You can also nest JOIN statements using the following syntax:</span></span>

<span data-ttu-id="26f88-133">选择*fields* FROM *table1* INNER JOIN (*table2* INNER JOIN \[( \] *table3* \[INNER JOIN \[( \] *tablex* \[INNER JOIN...)\]上*table3*。*field3**compopr**tablex*。*fieldx*)\]上*表 2*。*field2**compopr**table3*。*field3*)对*表 1*。*field1**compopr**表 2*。*field2*;</span><span class="sxs-lookup"><span data-stu-id="26f88-133">SELECT *fields* FROM *table1* INNER JOIN (*table2* INNER JOIN \[( \]*table3* \[INNER JOIN \[( \]*tablex* \[INNER JOIN …)\] ON *table3*.*field3* *compopr* *tablex*.*fieldx*)\] ON *table2*.*field2* *compopr* *table3*.*field3*) ON *table1*.*field1* *compopr* *table2*.*field2*;</span></span>

<span data-ttu-id="26f88-134">LEFT JOIN 或 RIGHT JOIN 可以嵌套在 INNER JOIN 之中，但是 INNER JOIN 不能嵌套于 LEFT JOIN 或 RIGHT JOIN 之中。</span><span class="sxs-lookup"><span data-stu-id="26f88-134">A LEFT JOIN or a RIGHT JOIN may be nested inside an INNER JOIN, but an INNER JOIN may not be nested inside a LEFT JOIN or a RIGHT JOIN.</span></span>

## <a name="example"></a><span data-ttu-id="26f88-135">示例</span><span class="sxs-lookup"><span data-stu-id="26f88-135">Example</span></span>

<span data-ttu-id="26f88-p106">本例创建两个等同联接：一个是 Order Details 表与 Orders 表之间的联接，另一个是 Orders 表与 Employees 表之间的联接。这是很有必要的，因为 Employees 表不包含销售数据，而 Order Details 表不包含雇员数据。查询将产生雇员及其总销售额的列表。</span><span class="sxs-lookup"><span data-stu-id="26f88-p106">This example creates two equi-joins: one between the Order Details and Orders tables and another between the Orders and Employees tables. This is necessary because the Employees table does not contain sales data, and the Order Details table does not contain employee data. The query produces a list of employees and their total sales.</span></span>

<span data-ttu-id="26f88-139">以下示例调用 EnumFields 过程，您可以在 SELECT 语句示例中找到该过程。</span><span class="sxs-lookup"><span data-stu-id="26f88-139">This example calls the EnumFields procedure, which you can find in the SELECT statement example.</span></span>

```vb
    Sub InnerJoinX() 
     
        Dim dbs As Database, rst As Recordset 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
         
        ' Create a join between the Order Details and  
        ' Orders tables and another between the Orders and  
        ' Employees tables. Get a list of employees and  
        ' their total sales. 
        Set rst = dbs.OpenRecordset("SELECT DISTINCTROW " _ 
            & "Sum(UnitPrice * Quantity) AS Sales, " _ 
            & "(FirstName & Chr(32) & LastName) AS Name " _ 
            & "FROM Employees INNER JOIN(Orders " _ 
            & "INNER JOIN [Order Details] " _ 
            & "ON [Order Details].OrderID = " _ 
            & "Orders.OrderID ) " _ 
            & "ON Orders.EmployeeID = " _ 
            & "Employees.EmployeeID " _ 
            & "GROUP BY (FirstName & Chr(32) & LastName);") 
         
        ' Populate the Recordset. 
        rst.MoveLast 
         
        ' Call EnumFields to print the contents of the  
        ' Recordset. Pass the Recordset object and desired 
        ' field width. 
        EnumFields rst, 20 
     
        dbs.Close 
     
    End Sub
```
