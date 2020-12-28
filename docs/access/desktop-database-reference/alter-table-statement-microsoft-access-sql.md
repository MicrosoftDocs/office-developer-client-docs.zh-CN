---
title: ALTER TABLE 语句 (Microsoft Access SQL)
TOCTitle: ALTER TABLE statement (Microsoft Access SQL)
ms:assetid: 78e6c92c-e88c-e55f-6b89-435360c166a6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196148(v=office.15)
ms:contentKeyID: 48545763
ms.date: 10/18/2018
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277560
dev_langs:
- sql
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: 07a83c16368caa6e5c05c7554300c5589a437067
ms.sourcegitcommit: 0419850d5c1b3439d9da59070201fb4952ca5d07
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/28/2020
ms.locfileid: "49734180"
---
# <a name="alter-table-statement-microsoft-access-sql"></a>ALTER TABLE 语句 (Microsoft Access SQL)

**适用于**：Access 2013、Office 2013

修改用 [CREATE TABLE](create-table-statement-microsoft-access-sql.md) 语句创建的表的设计。

> [!NOTE]
> [!注释] Microsoft Access 数据库引擎不支持使用 ALTER TABLE 语句或任何数据定义语言 (DDL) 语句。 请改为使用 DAO **Create** 方法。

## <a name="syntax"></a>语法

ALTER TABLE *table* {ADD {COLUMN *field type*\[(*size*)\] \[NOT NULL\] \[CONSTRAINT *index*\] | ALTER COLUMN *field type*\[(*size*)\] | CONSTRAINT *multifieldindex*} | DROP {COLUMN *field* I CONSTRAINT *indexname*} }

ALTER TABLE 语句包含以下部分：

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
<td><p><em>table</em></p></td>
<td><p>要更改的表名称。</p></td>
</tr>
<tr class="even">
<td><p><em>field</em></p></td>
<td><p>要添加到<em>表</em>中或要从中删除的字段名称。或要在<em>表</em>中更改的字段名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>type</em></p></td>
<td><p>
            <em>字段</em>的数据类型。</p></td>
</tr>
<tr class="even">
<td><p><em>size</em></p></td>
<td><p>以字符数为单位的字段大小（仅限于“文本”字段和“二进制”字段）。</p></td>
</tr>
<tr class="odd">
<td><p><em>index</em></p></td>
<td><p><em>字段</em>的索引。 有关如何构造此索引的详细信息，请参阅 <a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT 子句</a>。</p></td>
</tr>
<tr class="even">
<td><p><em>multifieldindex</em></p></td>
<td><p>要添加到<em>表</em>中的多字段索引的定义。 有关如何构造此索引的详细信息，请参阅 <a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT 子句</a>。</p></td>
</tr>
<tr class="odd">
<td><p><em>indexname</em></p></td>
<td><p>要删除的多字段索引的名称。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

使用 ALTER TABLE 语句能够以多种方式更改现有表。 您可以进行以下操作：

- 使用 ADD COLUMN 将新字段添加到表。指定字段名称、数据类型，以及（对于“文本”字段和“二进制”字段）可选尺寸。例如，以下语句将名为 Notes 的 25 个字符的 Text 字段添加到“员工”表中：
    
  ```sql
    ALTER TABLE Employees ADD COLUMN Notes TEXT(25)
  ```
    
  也可以在该字段上定义索引。 有关单字段索引的详细信息，请参阅 [CONSTRAINT 子句](constraint-clause-microsoft-access-sql.md)。
    
  如果为字段指定 NOT NULL，则需要新记录才能在该字段中包含有效数据。

- 使用 ALTER COLUMN 更改现有字段的数据类型。指定字段名称、新的字段类型以及“文本”字段和“二进制”字段的可选大小。例如，以下语句将“员工”表中名为 ZipCode 的某个字段的数据类型（最初定义为 Integer）更改为 10 个字符的 Text 字段：
    
  ```sql
    ALTER TABLE Employees ALTER COLUMN ZipCode TEXT(10)
  ```

- 使用 ADD CONSTRAINT 添加多字段索引。 有关多字段索引的详细信息，请参阅 [CONSTRAINT 子句](constraint-clause-microsoft-access-sql.md)。

- 使用 DROP COLUMN 删除字段。仅指定字段的名称。

- 使用 DROP CONSTRAINT 可删除多字段索引。只需在 CONSTRAINT 保留字后面指定索引名称。


> [!NOTE] 
> - 无法一次添加或删除多个字段或索引。
> - 可以使用 [CREATE INDEX](create-index-statement-microsoft-access-sql.md) 语句向表中添加单字段或多字段的索引，并且可以使用 ALTER TABLE 或者 [DROP](drop-statement-microsoft-access-sql.md) 语句删除使用 ALTER TABLE 或 CREATE INDEX 创建的索引。
> - 可以对单个字段或在应用于单个字段或多字段的命名 CONSTRAINT 的命名 CONSTRAINT 子句中使用 NOT NULL。 但是，仅可以对字段应用一次 NOT NULL 限制。 尝试多次应用此限制将造成运行时错误。

## <a name="example"></a>示例

以下示例向 Employees 表中添加数据类型为 **Money** 的 Salary 字段。

```vb
    Sub AlterTableX1() 
     
        Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Add the Salary field to the Employees table  
        ' and make it a Money data type. 
        dbs.Execute "ALTER TABLE Employees " _ 
            & "ADD COLUMN Salary MONEY;" 
     
        dbs.Close 
     
    End Sub 
```

<br/>

以下示例将 Salary 字段的数据类型从 **Money** 改为 **Char**。

```vb
    Sub AlterTableX2() 
     
        Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Modify the existing Salary field of the Employees table  
        ' by changing it to a CHAR data type. 
        dbs.Execute "ALTER TABLE Employees " _ 
            & "ALTER COLUMN Salary CHAR(20);" 
     
        dbs.Close 
     
    End Sub 
```

<br/>

以下示例从 Employees 表中删除 Salary 字段。

```vb
    Sub AlterTableX3() 
     
        Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Delete the Salary field from the Employees table. 
        dbs.Execute "ALTER TABLE Employees " _ 
            & "DROP COLUMN Salary;" 
     
        dbs.Close 
     
    End Sub
```

<br/>

本例向 Orders 表中添加一个外键。该外键基于 Employees 表的 EmployeeID 字段，并引用该字段。在本例的 REFERENCES 子句中，您不必在 Employees 表后列出 EmployeeID 字段，因为 EmployeeID 是 Employees 表的主键。

```vb
    Sub AlterTableX4() 
     
        Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Add a foreign key to the Orders table. 
        dbs.Execute "ALTER TABLE Orders " _ 
            & "ADD CONSTRAINT OrdersRelationship " _ 
            & "FOREIGN KEY (EmployeeID) " _ 
            & "REFERENCES Employees (EmployeeID);" 
     
        dbs.Close 
     
    End Sub 
```

<br/>

以下示例从 Orders 表中删除外键。

```vb
    Sub AlterTableX5() 
     
        Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Remove the OrdersRelationship foreign key from 
        ' the Orders table. 
        dbs.Execute "ALTER TABLE Orders " _ 
            & "DROP CONSTRAINT OrdersRelationship;" 
     
        dbs.Close 
     
    End Sub
```
