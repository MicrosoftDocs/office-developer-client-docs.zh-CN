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
ms.openlocfilehash: d865d005604ed7422c8e33ff8508551b720c30ba
ms.sourcegitcommit: 0419850d5c1b3439d9da59070201fb4952ca5d07
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/28/2020
ms.locfileid: "49734215"
---
# <a name="inner-join-operation-microsoft-access-sql"></a>INNER JOIN 操作 (Microsoft Access SQL)


**适用于**：Access 2013、Office 2013


当通用字段中存在匹配值时从两个表中合并记录。

## <a name="syntax"></a>语法

FROM *table1* INNER JOIN *table2* ON *table1*.*field1* *compopr table2*.*field2*

INNER JOIN 操作包含以下部分：

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
<td><p><em>table1</em>、<em>table2</em></p></td>
<td><p>对其中的记录进行组合的表的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>field1</em>、<em>field2</em></p></td>
<td><p>被联接的字段的名称。如果它们不是数字，则这些字段的数据类型必须相同，并且包含同类数据，但是，它们不必具有相同的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>compopr</em></p></td>
<td><p>任何关系比较运算符：“=”、“&quot;”、“&quot;”、“&lt;=”、“&gt;=”或“&lt;&gt;”。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

可以在任何 [FROM](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/from-clause-microsoft-access-sql) 子句中使用 INNER JOIN 操作。这是最常用的联接类型。只要两个表的公共字段上存在相匹配的值，Inner 联接就会组合这些表中的记录。

可以将 INNER JOIN 用于 Departments 及 Employees 表，以选择每个部门的所有雇员。相反，选择所有部门（即使某些部门中并没有分配雇员）或者所有雇员（即使某些雇员没有分配到任何部门），则可以使用 [LEFT JOIN 或 RIGHT JOIN](left-join-right-join-operations-microsoft-access-sql.md) 操作来创建外部联接。

如果尝试联接包含 Memo 或 OLE 对象数据的字段，则会出错。

可以联接 like 类型的任何两个数值字段。例如，可以联接 AutoNumber 和 Long 字段，因为它们为 like 类型。但是，无法联接 Single 和 Double 类型的字段。

以下示例显示如何在 CategoryID 字段上联接“类别”和“产品”表：

```sql
SELECT CategoryName, ProductName 
FROM Categories INNER JOIN Products 
ON Categories.CategoryID = Products.CategoryID;
```

在前面的示例中，CategoryID 是联接字段，但是它不包含在查询输出中，因为它不包含在 [SELECT](select-statement-microsoft-access-sql.md) 语句中。 若要包含联接字段，请在 SELECT 语句中包含该字段名，在本例中为 Categories.CategoryID。

也可以使用以下语法在 JOIN 语句中链接一些 ON 子句：

SELECT *fields* FROM *table1* INNER JOIN *table2* ON *table1*.*field1* *compopr* *table2*.*field1* AND ON *table1*.*field2* *compopr* *table2*.*field2* OR *table1*.*field3* *compopr* *table2*.*field3*;

也可以使用以下语法嵌套 JOIN 语句：

SELECT *fields* FROM *table1* INNER JOIN (*table2* INNER JOIN \[( \]*table3* \[INNER JOIN \[( \]*tablex* \[INNER JOIN …)\] ON *table3*.*field3* *compopr* *tablex*.*fieldx*)\] ON *table2*.*field2* *compopr* *table3*.*field3*) ON *table1*.*field1* *compopr* *table2*.*field2*;

LEFT JOIN 或 RIGHT JOIN 可以嵌套在 INNER JOIN 中，但 INNER JOIN 无法嵌套在 LEFT JOIN 或 RIGHT JOIN 中。

## <a name="example"></a>示例

本例创建两个等同联接：一个是 Order Details 表与 Orders 表之间的联接，另一个是 Orders 表与 Employees 表之间的联接。这是很有必要的，因为 Employees 表不包含销售数据，而 Order Details 表不包含雇员数据。查询将产生雇员及其总销售额的列表。

以下示例调用 EnumFields 过程，您可以在 SELECT 语句示例中找到该过程。

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
