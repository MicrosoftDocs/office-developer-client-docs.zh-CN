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
localization_priority: Priority
ms.openlocfilehash: 6ff2ad40d318801ecec2332b53b41f327c20fbc5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291398"
---
# <a name="inner-join-operation-microsoft-access-sql"></a><span data-ttu-id="cf3d8-102">INNER JOIN 操作 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="cf3d8-102">INNER JOIN Operation (Microsoft Access SQL)</span></span>


<span data-ttu-id="cf3d8-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="cf3d8-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="cf3d8-104">当通用字段中存在匹配值时从两个表中合并记录。</span><span class="sxs-lookup"><span data-stu-id="cf3d8-104">Combines records from two tables whenever there are matching values in a common field.</span></span>

## <a name="syntax"></a><span data-ttu-id="cf3d8-105">语法</span><span class="sxs-lookup"><span data-stu-id="cf3d8-105">Syntax</span></span>

<span data-ttu-id="cf3d8-106">FROM *table1* INNER JOIN *table2* ON *table1*.*field1* *compopr table2*.*field2*</span><span class="sxs-lookup"><span data-stu-id="cf3d8-106">FROM *table1* INNER JOIN *table2* ON *table1*.\*field1 \**compopr table2*.*field2*</span></span>

<span data-ttu-id="cf3d8-107">INNER JOIN 操作包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="cf3d8-107">The INNER JOIN operation has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="cf3d8-108">Part</span><span class="sxs-lookup"><span data-stu-id="cf3d8-108">Part</span></span></p></th>
<th><p><span data-ttu-id="cf3d8-109">说明</span><span class="sxs-lookup"><span data-stu-id="cf3d8-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf3d8-110"><em>table1</em>、<em>table2</em></span><span class="sxs-lookup"><span data-stu-id="cf3d8-110"><em>table1</em>  ,  <em>table2</em></span></span></p></td>
<td><p><span data-ttu-id="cf3d8-111">对其中的记录进行组合的表的名称。</span><span class="sxs-lookup"><span data-stu-id="cf3d8-111">The names of the tables from which records are combined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf3d8-112"><em>field1</em>、<em>field2</em></span><span class="sxs-lookup"><span data-stu-id="cf3d8-112"><em>field1</em>  ,  <em>field2</em></span></span></p></td>
<td><p><span data-ttu-id="cf3d8-p101">被联接的字段的名称。如果它们不是数字，则这些字段的数据类型必须相同，并且包含同类数据，但是，它们不必具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="cf3d8-p101">The names of the fields that are joined. If they are not numeric, the fields must be of the same data type and contain the same kind of data, but they do not have to have the same name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf3d8-115"><em>compopr</em></span><span class="sxs-lookup"><span data-stu-id="cf3d8-115"><em>compopr</em></span></span></p></td>
<td><p><span data-ttu-id="cf3d8-116">任何关系比较运算符：“=”、“&quot;”、“&quot;”、“&lt;=”、“&gt;=”或“&lt;&gt;”。</span><span class="sxs-lookup"><span data-stu-id="cf3d8-116">Any relational comparison operator: &quot;=,&quot; &quot;&lt;,&quot; &quot;&gt;,&quot; &quot;&lt;=,&quot; &quot;&gt;=,&quot; or &quot;&lt;&gt;.&quot;</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="cf3d8-117">说明</span><span class="sxs-lookup"><span data-stu-id="cf3d8-117">Remarks</span></span>

<span data-ttu-id="cf3d8-p102">可以在任何 [FROM](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/from-clause-microsoft-access-sql) 子句中使用 INNER JOIN 操作。这是最常用的联接类型。只要两个表的公共字段上存在相匹配的值，Inner 联接就会组合这些表中的记录。</span><span class="sxs-lookup"><span data-stu-id="cf3d8-p102">You can use an INNER JOIN operation in any [FROM](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/from-clause-microsoft-access-sql) clause. This is the most common type of join. Inner joins combine records from two tables whenever there are matching values in a field common to both tables.</span></span>

<span data-ttu-id="cf3d8-p103">可以将 INNER JOIN 用于 Departments 及 Employees 表，以选择每个部门的所有雇员。相反，选择所有部门（即使某些部门中并没有分配雇员）或者所有雇员（即使某些雇员没有分配到任何部门），则可以使用 [LEFT JOIN 或 RIGHT JOIN](left-join-right-join-operations-microsoft-access-sql.md) 操作来创建外部联接。</span><span class="sxs-lookup"><span data-stu-id="cf3d8-p103">You can use INNER JOIN with the Departments and Employees tables to select all the employees in each department. In contrast, to select all departments (even if some have no employees assigned to them) or all employees (even if some are not assigned to a department), you can use a [LEFT JOIN or RIGHT JOIN](left-join-right-join-operations-microsoft-access-sql.md) operation to create an outer join.</span></span>

<span data-ttu-id="cf3d8-123">如果尝试联接包含 Memo 或 OLE 对象数据的字段，则会出错。</span><span class="sxs-lookup"><span data-stu-id="cf3d8-123">If you try to join fields containing Memo or OLE Object data, an error occurs.</span></span>

<span data-ttu-id="cf3d8-p104">可以联接 like 类型的任何两个数值字段。例如，可以联接 AutoNumber 和 Long 字段，因为它们为 like 类型。但是，无法联接 Single 和 Double 类型的字段。</span><span class="sxs-lookup"><span data-stu-id="cf3d8-p104">You can join any two numeric fields of like types. For example, you can join on AutoNumber and Long fields because they are like types. However, you cannot join Single and Double types of fields.</span></span>

<span data-ttu-id="cf3d8-127">以下示例显示如何在 CategoryID 字段上联接“类别”和“产品”表：</span><span class="sxs-lookup"><span data-stu-id="cf3d8-127">The following example shows how you could join the Categories and Products tables on the CategoryID field:</span></span>

```sql
SELECT CategoryName, ProductName 
FROM Categories INNER JOIN Products 
ON Categories.CategoryID = Products.CategoryID;
```

<span data-ttu-id="cf3d8-128">在前面的示例中，CategoryID 是联接字段，但是它不包含在查询输出中，因为它不包含在 [SELECT](select-statement-microsoft-access-sql.md) 语句中。</span><span class="sxs-lookup"><span data-stu-id="cf3d8-128">In the preceding example, CategoryID is the joined field, but it is not included in the query output because it is not included in the [SELECT](select-statement-microsoft-access-sql.md) statement.</span></span> <span data-ttu-id="cf3d8-129">若要包含联接字段，请在 SELECT 语句中包含该字段名，在本例中为 Categories.CategoryID。</span><span class="sxs-lookup"><span data-stu-id="cf3d8-129">To include the joined field, include the field name in the SELECT statement — in this case, Categories.CategoryID.</span></span>

<span data-ttu-id="cf3d8-130">也可以使用以下语法在 JOIN 语句中链接一些 ON 子句：</span><span class="sxs-lookup"><span data-stu-id="cf3d8-130">You can also link several ON clauses in a JOIN statement, using the following syntax:</span></span>

<span data-ttu-id="cf3d8-131">SELECT *fields* FROM *table1* INNER JOIN *table2* ON *table1*.*field1* *compopr* *table2*.*field1* AND ON *table1*.*field2* *compopr* *table2*.*field2*) OR ON *table1*.*field3* *compopr* *table2*.*field3*)\];</span><span class="sxs-lookup"><span data-stu-id="cf3d8-131">SELECT *fields* 
FROM *table1* INNER JOIN *table2* 
ON *table1*.*field1 \* *compopr \* *table2*.*field1* AND 
ON *table1*.*field2 \* *compopr \* *table2*.*field2*) OR 
ON *table1*.*field3 \* *compopr \* *table2*.*field3*)];</span></span>

<span data-ttu-id="cf3d8-132">也可以使用以下语法嵌套 JOIN 语句：</span><span class="sxs-lookup"><span data-stu-id="cf3d8-132">You can also nest JOIN statements using the following syntax:</span></span>

<span data-ttu-id="cf3d8-133">SELECT *fields* FROM *table1* INNER JOIN (*table2* INNER JOIN \[( \]*table3* \[INNER JOIN \[( \]*tablex* \[INNER JOIN …)\] ON *table3*.*field3* *compopr* *tablex*.*fieldx*)\] ON *table2*.*field2* *compopr* *table3*.*field3*) ON *table1*.*field1* *compopr* *table2*.*field2*;</span><span class="sxs-lookup"><span data-stu-id="cf3d8-133">SELECT fields 
FROM table1 INNER JOIN 
(table2 INNER JOIN [( ]table3 
[INNER JOIN [( ]tablex [INNER JOIN …)]  
ON table3.field3  compopr  tablex.fieldx)] 
ON table2.field2  compopr  table3.field3)  
ON table1.field1  compopr  table2.field2;</span></span>

<span data-ttu-id="cf3d8-134">LEFT JOIN 或 RIGHT JOIN 可以嵌套在 INNER JOIN 中，但 INNER JOIN 无法嵌套在 LEFT JOIN 或 RIGHT JOIN 中。</span><span class="sxs-lookup"><span data-stu-id="cf3d8-134">A LEFT JOIN or a RIGHT JOIN may be nested inside an INNER JOIN, but an INNER JOIN may not be nested inside a LEFT JOIN or a RIGHT JOIN.</span></span>

## <a name="example"></a><span data-ttu-id="cf3d8-135">示例</span><span class="sxs-lookup"><span data-stu-id="cf3d8-135">Example</span></span>

<span data-ttu-id="cf3d8-p106">本例创建两个等同联接：一个是 Order Details 表与 Orders 表之间的联接，另一个是 Orders 表与 Employees 表之间的联接。这是很有必要的，因为 Employees 表不包含销售数据，而 Order Details 表不包含雇员数据。查询将产生雇员及其总销售额的列表。</span><span class="sxs-lookup"><span data-stu-id="cf3d8-p106">This example creates two equi-joins: one between the Order Details and Orders tables and another between the Orders and Employees tables. This is necessary because the Employees table does not contain sales data, and the Order Details table does not contain employee data. The query produces a list of employees and their total sales.</span></span>

<span data-ttu-id="cf3d8-139">以下示例调用 EnumFields 过程，您可以在 SELECT 语句示例中找到该过程。</span><span class="sxs-lookup"><span data-stu-id="cf3d8-139">This example calls the EnumFields procedure, which you can find in the SELECT statement example.</span></span>

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
