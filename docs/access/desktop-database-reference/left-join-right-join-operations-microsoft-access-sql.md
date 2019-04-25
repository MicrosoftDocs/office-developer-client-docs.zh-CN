---
title: LEFT JOIN 和 RIGHT JOIN 运算 (Microsoft Access SQL)
TOCTitle: LEFT JOIN, RIGHT JOIN operations (Microsoft Access SQL)
ms:assetid: 9c10525f-98b1-fd4f-8b40-07a32c5c6502
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198084(v=office.15)
ms:contentKeyID: 48546586
ms.date: 09/18/2015
mtps_version: v=office.15
dev_langs:
- sql
localization_priority: Priority
ms.openlocfilehash: c6e37cd68d586e39a06fd650ccb453f35477253f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290143"
---
# <a name="left-join-right-join-operations-microsoft-access-sql"></a><span data-ttu-id="f710d-102">LEFT JOIN 和 RIGHT JOIN 运算 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="f710d-102">LEFT JOIN, RIGHT JOIN Operations (Microsoft Access SQL)</span></span>

<span data-ttu-id="f710d-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="f710d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f710d-104">在任何 [FROM](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/from-clause-microsoft-access-sql) 子句中用于组合源表记录。</span><span class="sxs-lookup"><span data-stu-id="f710d-104">Combines source-table records when used in any [FROM](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/from-clause-microsoft-access-sql) clause.</span></span>

## <a name="syntax"></a><span data-ttu-id="f710d-105">语法</span><span class="sxs-lookup"><span data-stu-id="f710d-105">Syntax</span></span>

<span data-ttu-id="f710d-106">FROM *table1* \[ LEFT | RIGHT \] JOIN *table2* ON *table1.field1* *compopr table2.field2*</span><span class="sxs-lookup"><span data-stu-id="f710d-106">FROM *table1* \[ [ LEFT | RIGHT ] JOIN *table2*
    ON \*table1.field1 \* *compopr table2.field2*</span></span>

<span data-ttu-id="f710d-107">LEFT JOIN 和 RIGHT JOIN 操作包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="f710d-107">The LEFT JOIN and RIGHT JOIN operations have these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f710d-108">Part</span><span class="sxs-lookup"><span data-stu-id="f710d-108">Part</span></span></p></th>
<th><p><span data-ttu-id="f710d-109">说明</span><span class="sxs-lookup"><span data-stu-id="f710d-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f710d-110"><em>table1</em>、<em>table2</em></span><span class="sxs-lookup"><span data-stu-id="f710d-110"><em>table1</em>  ,  <em>table2</em></span></span></p></td>
<td><p><span data-ttu-id="f710d-111">对其中的记录进行组合的表的名称。</span><span class="sxs-lookup"><span data-stu-id="f710d-111">The names of the tables from which records are combined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f710d-112"><em>field1</em>、<em>field2</em></span><span class="sxs-lookup"><span data-stu-id="f710d-112"><em>field1</em>  ,  <em>field2</em></span></span></p></td>
<td><p><span data-ttu-id="f710d-p101">被联接的字段的名称。这些字段必须具有相同的数据类型，并且包含相同类型的数据，但它们不必同名。</span><span class="sxs-lookup"><span data-stu-id="f710d-p101">The names of the fields that are joined. The fields must be of the same data type and contain the same kind of data, but they do not need to have the same name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f710d-115"><em>compopr</em></span><span class="sxs-lookup"><span data-stu-id="f710d-115"><em>compopr</em></span></span></p></td>
<td><p><span data-ttu-id="f710d-116">任何关系比较运算符：“=”、“&quot;”、“&quot;”、“&lt;=”、“&gt;=”或“&lt;&gt;”。</span><span class="sxs-lookup"><span data-stu-id="f710d-116">Any relational comparison operator: &quot;=,&quot; &quot;&lt;,&quot; &quot;&gt;,&quot; &quot;&lt;=,&quot; &quot;&gt;=,&quot; or &quot;&lt;&gt;.&quot;</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="f710d-117">说明</span><span class="sxs-lookup"><span data-stu-id="f710d-117">Remarks</span></span>

<span data-ttu-id="f710d-p102">通过 LEFT JOIN 操作可以创建一个左外部联接。左外部联接包含两个表中第一个（左）表中的所有记录，即使在第二个（右）表中没有匹配的记录值。</span><span class="sxs-lookup"><span data-stu-id="f710d-p102">Use a LEFT JOIN operation to create a left outer join. Left outer joins include all of the records from the first (left) of two tables, even if there are no matching values for records in the second (right) table.</span></span>

<span data-ttu-id="f710d-p103">通过 RIGHT JOIN 操作可以创建一个右外部联接。右外部联接包含两个表中第二个（右）表中的所有记录，即使在第一个（左）表中没有匹配的记录值。</span><span class="sxs-lookup"><span data-stu-id="f710d-p103">Use a RIGHT JOIN operation to create a right outer join. Right outer joins include all of the records from the second (right) of two tables, even if there are no matching values for records in the first (left) table.</span></span>

<span data-ttu-id="f710d-p104">例如，可以将 LEFT JOIN 用于“部门”表（左）和“员工”表（右），以选择所有部门，包括那些未分配有员工的部门。若要选择所有员工，包括那些未分配到任一部门的员工，就要使用 RIGHT JOIN。</span><span class="sxs-lookup"><span data-stu-id="f710d-p104">For example, you could use LEFT JOIN with the Departments (left) and Employees (right) tables to select all departments, including those that have no employees assigned to them. To select all employees, including those who are not assigned to a department, you would use RIGHT JOIN.</span></span>

<span data-ttu-id="f710d-p105">以下示例演示如何通过 CategoryID 字段将“类别”表和“产品”表联接起来。该查询会生成一个含所有类别的列表，包括那些不含任何产品的类别：</span><span class="sxs-lookup"><span data-stu-id="f710d-p105">The following example shows how you could join the Categories and Products tables on the CategoryID field. The query produces a list of all categories, including those that contain no products:</span></span>

```sql
SELECT CategoryName, 
ProductName 
FROM Categories LEFT JOIN Products 
ON Categories.CategoryID = Products.CategoryID;
```

<span data-ttu-id="f710d-126">在以下示例中，CategoryID 是联接字段，但是它不包括在查询结果中，因为它没有包括在 [SELECT](select-statement-microsoft-access-sql.md) 语句中。</span><span class="sxs-lookup"><span data-stu-id="f710d-126">In this example, CategoryID is the joined field, but it is not included in the query results because it is not included in the [SELECT](select-statement-microsoft-access-sql.md) statement.</span></span> <span data-ttu-id="f710d-127">若要包含联接字段，请在 SELECT 语句中输入该字段名，在本例中为 Categories.CategoryID。</span><span class="sxs-lookup"><span data-stu-id="f710d-127">To include the joined field, include the field name in the SELECT statement — in this case, Categories.CategoryID.</span></span>

> [!NOTE]
> - <span data-ttu-id="f710d-128">若要创建一个只包括在联接字段中具有相同数据的记录，请使用 [INNER JOIN](inner-join-operation-microsoft-access-sql.md) 操作。</span><span class="sxs-lookup"><span data-stu-id="f710d-128">To create a query that includes only records in which the data in the joined fields is the same, use an [INNER JOIN](inner-join-operation-microsoft-access-sql.md) operation.</span></span>
> - <span data-ttu-id="f710d-p107">LEFT JOIN 或 RIGHT JOIN 可以嵌套在 INNER JOIN 中，但 INNER JOIN 无法嵌套在 LEFT JOIN 或 RIGHT JOIN 中。请参阅 INNER JOIN 主题中有关嵌套的内容，了解如何将联接嵌套在其他联接中。</span><span class="sxs-lookup"><span data-stu-id="f710d-p107">A LEFT JOIN or a RIGHT JOIN can be nested inside an INNER JOIN, but an INNER JOIN cannot be nested inside a LEFT JOIN or a RIGHT JOIN. See the discussion of nesting in the INNER JOIN topic to see how to nest joins within other joins.</span></span>
> - <span data-ttu-id="f710d-p108">可以链接多个 ON 子句。请参阅 INNER JOIN 主题中有关链接字句的内容，了解如何链接字句。</span><span class="sxs-lookup"><span data-stu-id="f710d-p108">You can link multiple ON clauses. See the discussion of clause linking in the INNER JOIN topic to see how this is done.</span></span>
> - <span data-ttu-id="f710d-133">如果尝试联接包含 Memo 或 OLE 对象数据的字段，则会出错。</span><span class="sxs-lookup"><span data-stu-id="f710d-133">If you try to join fields containing Memo or OLE Object data, an error occurs.</span></span>

## <a name="example"></a><span data-ttu-id="f710d-134">示例</span><span class="sxs-lookup"><span data-stu-id="f710d-134">Example</span></span>

<span data-ttu-id="f710d-135">本示例：</span><span class="sxs-lookup"><span data-stu-id="f710d-135">This is an example.</span></span>
- <span data-ttu-id="f710d-136">假设 Employees 表中存在假想的 Department Name 和 Department ID 字段。</span><span class="sxs-lookup"><span data-stu-id="f710d-136">This example assumes the existence of hypothetical Department Name and Department ID fields in an Employees table.</span></span> <span data-ttu-id="f710d-137">请注意，这些字段实际上在 Northwind 数据库 Employees 表中不存在。</span><span class="sxs-lookup"><span data-stu-id="f710d-137">Note that these fields do not actually exist in the Northwind database Employees table.</span></span>

- <span data-ttu-id="f710d-138">选择所有部门，包括那些没有员工的部门。</span><span class="sxs-lookup"><span data-stu-id="f710d-138">This example selects all departments, including those without employees.</span></span>

- <span data-ttu-id="f710d-139">调用 EnumFields 过程，您可以在 SELECT 语句示例中找到该过程。</span><span class="sxs-lookup"><span data-stu-id="f710d-139">This example calls the EnumFields procedure, which you can find in the SELECT statement example.</span></span>


```vb
    Sub LeftRightJoinX() 
     
        Dim dbs As Database, rst As Recordset 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
         
        ' Select all departments, including those  
        ' without employees. 
        Set rst = dbs.OpenRecordset _ 
            ("SELECT [Department Name], " _ 
            & "FirstName & Chr(32) & LastName AS Name " _ 
            & "FROM Departments LEFT JOIN Employees " _ 
            & "ON Departments.[Department ID] = " _ 
            & "Employees.[Department ID] " _ 
            & "ORDER BY [Department Name];") 
         
        ' Populate the Recordset. 
        rst.MoveLast 
         
        ' Call EnumFields to print the contents of the  
        ' Recordset. Pass the Recordset object and desired 
        ' field width. 
        EnumFields rst, 20 
     
        dbs.Close 
     
    End Sub
```
