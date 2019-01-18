---
title: LEFT JOIN，RIGHT JOIN 操作 (Microsoft Access SQL)
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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28704719"
---
# <a name="left-join-right-join-operations-microsoft-access-sql"></a>LEFT JOIN，RIGHT JOIN 操作 (Microsoft Access SQL)

**适用于**： Access 2013、 Office 2013

在任何 [FROM](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/from-clause-microsoft-access-sql) 子句中用于组合源表记录。

## <a name="syntax"></a>语法

*TABLE1* \[左 |右\]上*table1.field1* *compopr table2.field2*联接*表 2*

LEFT JOIN 和 RIGHT JOIN 操作包含以下部分：

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>部分</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>table1</em>、<em>table2</em></p></td>
<td><p>要组合其中记录的表的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>field1</em>、<em>field2</em></p></td>
<td><p>被联接的字段的名称。这些字段必须具有相同的数据类型，并且包含相同类型的数据，但它们不必同名。</p></td>
</tr>
<tr class="odd">
<td><p><em>compopr</em></p></td>
<td><p>任何关系比较运算符： &quot;= 和&quot; &quot; &lt;，&quot; &quot; &gt;，&quot; &quot; &lt;=&quot; &quot; &gt;=&quot;或&quot; &lt; &gt;。&quot;</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

通过 LEFT JOIN 操作可以创建一个左外部联接。左外部联接包含两个表中第一个（左）表中的所有记录，即使在第二个（右）表中没有匹配的记录值。

通过 RIGHT JOIN 操作可以创建一个右外部联接。右外部联接包含两个表中第二个（右）表中的所有记录，即使在第一个（左）表中没有匹配的记录值。

例如，可以将 LEFT JOIN 用于 Departments（左）和 Employees（右）表以选择所有部门，包括那些没有被分配雇员的部门。若要选择所有雇员，包括那些没有被分配到任何部门的雇员，可以使用 RIGHT JOIN。

下面的示例展示了如何通过 CategoryID 字段联接 Categories 表和 Products 表。该查询将产生一个所有分类的列表，其中包括不包含任何产品的分类：

```sql
SELECT CategoryName, 
ProductName 
FROM Categories LEFT JOIN Products 
ON Categories.CategoryID = Products.CategoryID;
```

在以下示例中，CategoryID 是联接字段，但是它不包括在查询结果中，因为它没有包括在 [SELECT](select-statement-microsoft-access-sql.md) 语句中。 若要包含的联接的字段，输入的 SELECT 语句中的字段名称 — 在此情况下，Categories.CategoryID。

> [!NOTE]
> - 若要创建一个只包括在联接字段中具有相同数据的记录，请使用 [INNER JOIN](inner-join-operation-microsoft-access-sql.md) 操作。
> - LEFT JOIN 或 RIGHT JOIN 可以嵌套到 INNER JOIN 语句中，但是 INNER JOIN 语句不能嵌套到 LEFT JOIN 或 RIGHT JOIN 语句中。请参阅 INNER JOIN 主题中有关嵌套的讨论，以了解如何在其他联接中嵌套联接。
> - 可以链接多个 ON 子句。请参阅 INNER JOIN 主题中有关子句链接的讨论，以了解如何操作。
> - 如果试图联接包含 Memo 或 OLE 对象数据的字段，将产生错误。

## <a name="example"></a>示例

此示例中：
- 假定存在的 Employees 表中的假想部门名称和部门 ID 字段。 请注意，这些字段并不实际存在于 Northwind 数据库的 Employees 表中。

- 选择所有部门，包括那些没有雇员。

- 调用 EnumFields 过程，您可以在 SELECT 语句示例中找到。


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
