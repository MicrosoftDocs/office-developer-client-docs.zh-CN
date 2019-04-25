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
# <a name="left-join-right-join-operations-microsoft-access-sql"></a>LEFT JOIN 和 RIGHT JOIN 运算 (Microsoft Access SQL)

**适用于**：Access 2013、Office 2013

在任何 [FROM](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/from-clause-microsoft-access-sql) 子句中用于组合源表记录。

## <a name="syntax"></a>语法

FROM *table1* \[ LEFT | RIGHT \] JOIN *table2* ON *table1.field1* *compopr table2.field2*

LEFT JOIN 和 RIGHT JOIN 操作包含以下部分：

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
<td><p>被联接的字段的名称。这些字段必须具有相同的数据类型，并且包含相同类型的数据，但它们不必同名。</p></td>
</tr>
<tr class="odd">
<td><p><em>compopr</em></p></td>
<td><p>任何关系比较运算符：“=”、“&quot;”、“&quot;”、“&lt;=”、“&gt;=”或“&lt;&gt;”。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

通过 LEFT JOIN 操作可以创建一个左外部联接。左外部联接包含两个表中第一个（左）表中的所有记录，即使在第二个（右）表中没有匹配的记录值。

通过 RIGHT JOIN 操作可以创建一个右外部联接。右外部联接包含两个表中第二个（右）表中的所有记录，即使在第一个（左）表中没有匹配的记录值。

例如，可以将 LEFT JOIN 用于“部门”表（左）和“员工”表（右），以选择所有部门，包括那些未分配有员工的部门。若要选择所有员工，包括那些未分配到任一部门的员工，就要使用 RIGHT JOIN。

以下示例演示如何通过 CategoryID 字段将“类别”表和“产品”表联接起来。该查询会生成一个含所有类别的列表，包括那些不含任何产品的类别：

```sql
SELECT CategoryName, 
ProductName 
FROM Categories LEFT JOIN Products 
ON Categories.CategoryID = Products.CategoryID;
```

在以下示例中，CategoryID 是联接字段，但是它不包括在查询结果中，因为它没有包括在 [SELECT](select-statement-microsoft-access-sql.md) 语句中。 若要包含联接字段，请在 SELECT 语句中输入该字段名，在本例中为 Categories.CategoryID。

> [!NOTE]
> - 若要创建一个只包括在联接字段中具有相同数据的记录，请使用 [INNER JOIN](inner-join-operation-microsoft-access-sql.md) 操作。
> - LEFT JOIN 或 RIGHT JOIN 可以嵌套在 INNER JOIN 中，但 INNER JOIN 无法嵌套在 LEFT JOIN 或 RIGHT JOIN 中。请参阅 INNER JOIN 主题中有关嵌套的内容，了解如何将联接嵌套在其他联接中。
> - 可以链接多个 ON 子句。请参阅 INNER JOIN 主题中有关链接字句的内容，了解如何链接字句。
> - 如果尝试联接包含 Memo 或 OLE 对象数据的字段，则会出错。

## <a name="example"></a>示例

本示例：
- 假设 Employees 表中存在假想的 Department Name 和 Department ID 字段。 请注意，这些字段实际上在 Northwind 数据库 Employees 表中不存在。

- 选择所有部门，包括那些没有员工的部门。

- 调用 EnumFields 过程，您可以在 SELECT 语句示例中找到该过程。


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
