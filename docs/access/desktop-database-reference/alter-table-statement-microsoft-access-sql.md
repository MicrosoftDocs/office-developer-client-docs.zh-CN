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
ms.openlocfilehash: f7dfaa7a8c3d6b3e41b2443bcca621d083c3a167
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25889628"
---
# <a name="alter-table-statement-microsoft-access-sql"></a>ALTER TABLE 语句 (Microsoft Access SQL)

**适用于**： Access 2013、 Office 2013

修改用 [CREATE TABLE](create-table-statement-microsoft-access-sql.md) 语句创建的表的设计。

> [!NOTE]
> [!注释] Microsoft Access 数据库引擎不支持使用 ALTER TABLE 语句或任何数据定义语言 (DDL) 语句。 而是使用**DAO 创建**方法。

## <a name="syntax"></a>语法

ALTER TABLE*表*{添加 {列*字段类型*\[（*大小*）\] \[NOT NULL\] \[约束*索引*\] |更改列*字段类型*\[（*大小*）\] |CONSTRAINT *multifieldindex*} |DROP {列*字段*我约束*indexname*}}

ALTER TABLE 语句有以下部分：

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
<td><p>要修改的表的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>field</em></p></td>
<td><p>要在 <em>table</em> 中添加或删除的字段的名称，或者是要在 <em>table</em> 中修改的字段的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>类型</em></p></td>
<td><p><em>field</em> 的数据类型。</p></td>
</tr>
<tr class="even">
<td><p><em>size</em></p></td>
<td><p>以字符为单位的字段大小（仅限于文本和二进制字段）。</p></td>
</tr>
<tr class="odd">
<td><p><em>index</em></p></td>
<td><p><em>字段</em>的索引。 有关如何构建该索引的详细信息，请参阅<a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT 子句</a>。</p></td>
</tr>
<tr class="even">
<td><p><em>multifieldindex</em></p></td>
<td><p>要添加到<em>表</em>多字段索引的定义。 有关如何构建该索引的详细信息，请参阅<a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT 子句</a>。</p></td>
</tr>
<tr class="odd">
<td><p><em>indexname</em></p></td>
<td><p>将要删除的多字段索引的名称。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

通过使用 ALTER TABLE 语句，可以修改现有表中有多种。 您可以：

- 使用 ADD COLUMN 向表中添加新字段。可以指定字段名称、数据类型和可选大小（对于文本和二进制字段）。例如，以下语句将具有 25 个字符的名为 Notes 的文本字段添加到 Employees 表中：
    
  ```sql
    ALTER TABLE Employees ADD COLUMN Notes TEXT(25)
  ```
    
  也可以定义该字段的索引。 有关单字段索引的详细信息，请参阅[CONSTRAINT 子句](constraint-clause-microsoft-access-sql.md)。
    
  如果指定的字段不为空，新记录需要该字段中具有有效的数据。

- 使用 ALTER COLUMN 可更改现有字段的数据类型。可以指定文本和二进制字段的字段名称、新的数据类型以及可选大小。例如，以下语句将 Employees 表中名为 ZipCode 字段的数据类型（原先定义为整型）更改为具有 10 个字符的文本字段：
    
  ```sql
    ALTER TABLE Employees ALTER COLUMN ZipCode TEXT(10)
  ```

- 使用 ADD CONSTRAINT 可添加多字段索引。 有关多字段索引的详细信息，请参阅[CONSTRAINT 子句](constraint-clause-microsoft-access-sql.md)。

- 使用 DROP COLUMN 可删除字段。只需指定字段的名称。

- 使用 DROP CONSTRAINT 可删除多字段索引。只需在 CONSTRAINT 保留字后面指定索引名称。


> [!NOTE] 
> - [!注释] 不能同时添加或删除多个字段或索引。
> - 可以使用 [CREATE INDEX](create-index-statement-microsoft-access-sql.md) 语句向表中添加单字段或多字段的索引，并且可以使用 ALTER TABLE 或者 [DROP](drop-statement-microsoft-access-sql.md) 语句删除使用 ALTER TABLE 或 CREATE INDEX 创建的索引。
> - 在一个字段或一个名为 CONSTRAINT 的子句中可以使用 NOT NULL，该子句既可应用于单字段索引，也可应用于名为 CONSTRAINT 的多字段索引。但是，NOT NULL 限制一次只能应用于一个字段。多次应用此限制将导致运行时错误。


## <a name="example"></a>示例

本例向 Employees 表中添加数据类型为 **Money** 的 Salary 字段。

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

本例将 Salary 字段的数据类型从 **Money** 更改为 **Char** 。

```vb
    Sub AlterTableX2() 
     
        Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Add the Salary field to the Employees table  
        ' and make it a Money data type. 
        dbs.Execute "ALTER TABLE Employees " _ 
            & "ALTER COLUMN Salary CHAR(20);" 
     
        dbs.Close 
     
    End Sub 
```

<br/>

本例从 Employees 表中删除 Salary 字段。

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

本例从 Orders 表中删除外键。

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
