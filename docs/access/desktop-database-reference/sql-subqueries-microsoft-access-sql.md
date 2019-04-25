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
localization_priority: Priority
ms.openlocfilehash: 7beda04d1f18014101f00078de1d125c1fd67a69
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314565"
---
# <a name="sql-subqueries-microsoft-access-sql"></a>SQL 子查询 (Microsoft Access SQL)


**适用于**：Access 2013、Office 2013

子查询是一个 [SELECT](select-statement-microsoft-access-sql.md) 语句，它嵌套在 SELECT、[SELECT...INTO](select-into-statement-microsoft-access-sql.md)、[INSERT...INTO](insert-into-statement-microsoft-access-sql.md)、[DELETE](delete-statement-microsoft-access-sql.md) 或 [UPDATE](update-statement-microsoft-access-sql.md) 语句中，或嵌套在另一个子查询中。

## <a name="syntax"></a>语法

可以通过三种语法形式来创建子查询：

*comparison* \[ANY | ALL | SOME\] (*sqlstatement*)

*expression* \[NOT\] IN (*sqlstatement*)

\[NOT\] EXISTS (*sqlstatement*)

子查询语句包含了以下部分：

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Part</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>comparison</em></p></td>
<td><p>表达式和比较运算符，用于对表达式与子查询的结果进行比较。</p></td>
</tr>
<tr class="even">
<td><p><em>expression</em></p></td>
<td><p>表达式，用来搜索子查询的结果集。</p></td>
</tr>
<tr class="odd">
<td><p><em>sqlstatement</em></p></td>
<td><p>SELECT 语句，遵循和任何其他 SELECT 语句一样的格式和规则。 它必须用圆括号括起来。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

可以在 SELECT 语句的字段列表中、在 [WHERE](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/where-clause-microsoft-access-sql) 子句中或在 [HAVING](https://docs.microsoft.com/office/vba/access/concepts/structured-query-language/having-clause-microsoft-access-sql) 子句中使用子查询来代替表达式。在子查询中，可以使用 SELECT 语句来提供一组要在 WHERE 或 HAVING 子句表达式中计算的一个或多个特定值。

通过同义的 ANY 或 SOME 谓词，可以检索在主查询的记录中满足与子查询所检索出的任何记录进行比较的比较条件的记录。下面的示例返回那些单价高于以 25% 或更高折扣出售的任何产品的单价的产品：

```sql
SELECT * FROM Products 
WHERE UnitPrice > ANY 
(SELECT UnitPrice FROM OrderDetails 
WHERE Discount >= .25);
```

使用 [ALL](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/all-distinct-distinctrow-top-predicates-microsoft-access-sql) 谓词可以在主查询中只检索满足子查询中检索的所有记录的比较条件的记录。如果将前面的示例中的 ANY 改为 ALL，查询将只返回那些单价高于以 25% 或更高折扣出售的所有产品单价的产品。它的限制性更强。

通过 IN 谓词可以只检索出在主查询的记录中作为子查询的一部分记录而包含相同值的记录。下面的示例返回所有以 25% 或更高折扣出售的所有产品：

```sql
SELECT * FROM Products 
WHERE ProductID IN 
(SELECT ProductID FROM OrderDetails 
WHERE Discount >= .25);
```

相应地，可以使用 NOT IN 来仅检索出在主查询的记录中作为子查询的记录而不包含相同值的记录。

在 True/False 比较条件中使用 EXISTS 谓词（带有可选的 NOT 保留字）可确定子查询是否返回任何记录。

也可以在子查询中使用表名的别名来引用在子查询外部的 [FROM](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/from-clause-microsoft-access-sql) 子句中列出的表。以下示例返回薪水等于或高于具有同等职称的所有雇员平均薪水的雇员的姓名。Employees 表别名为"T1"：

```sql
SELECT LastName,
FirstName, Title, Salary 
FROM Employees AS T1 
WHERE Salary >= (SELECT Avg(Salary) 
FROM Employees 
WHERE T1.Title = Employees.Title) Order by Title;
```

在前面的示例中，AS 保留字是可选的。

允许一些子查询用在交叉表查询中，特别是作为谓词（在 WHERE 子句中的谓词）。不允许将作为输出的子查询（在 SELECT 列表中）用在交叉表查询中。

## <a name="example"></a>示例

以下示例列出在 1995 年第二季度下过订单的每个客户的名称和联系人。 它调用 EnumFields 过程，您可以在 SELECT 语句示例中找到该过程。

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
