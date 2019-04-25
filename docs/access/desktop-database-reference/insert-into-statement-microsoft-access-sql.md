---
title: INSERT INTO 语句 (Microsoft Access SQL)
TOCTitle: INSERT INTO statement (Microsoft Access SQL)
ms:assetid: d3e44258-79f2-caba-8629-bde03f898f2d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834799(v=office.15)
ms:contentKeyID: 48547918
ms.date: 10/18/2018
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277575
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: 4fee5e9e8878274f2c20dd83a3dbedaf2903ca62
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291331"
---
# <a name="insert-into-statement-microsoft-access-sql"></a>INSERT INTO 语句 (Microsoft Access SQL)

**适用于**：Access 2013、Office 2013

向表中添加一个或多个记录。 该语句称为追加查询。

## <a name="syntax"></a>语法

### <a name="multiple-record-append-query"></a>多记录追加查询

INSERT INTO *target* \[(*field1*\[, *field2*\[, …\]\])\] \[IN *externaldatabase*\] SELECT \[*source*.\]*field1*\[, *field2*\[, …\] FROM *tableexpression*

### <a name="single-record-append-query"></a>单记录追加查询

INSERT INTO *target* \[(*field1*\[, *field2*\[, …\]\])\] VALUES (*value1*\[, *value2*\[, …\])

INSERT INTO 语句包含以下部分：

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
<td><p><em>target</em></p></td>
<td><p>要追加记录的表或查询的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>field1</em>, <em>field2</em></p></td>
<td><p>如果后跟一个 <em>target</em> 参数，为要追加数据的字段的名称；如果后跟一个 <em>source</em> 参数，则为要从中获取数据的字段的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>externaldatabase</em></p></td>
<td><p>外部数据库的路径。 有关路径的说明，请参阅 <a href="https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/in-clause-microsoft-access-sql">IN</a> 子句。</p></td>
</tr>
<tr class="even">
<td><p><em>source</em></p></td>
<td><p>要从中复制记录的表或查询的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>tableexpression</em></p></td>
<td><p>作为插入记录来源的表的名称。该参数可以是单个表名或者是从 <a href="inner-join-operation-microsoft-access-sql.md">INNER JOIN</a>、<a href="left-join-right-join-operations-microsoft-access-sql.md">LEFT JOIN</a> 或 <a href="left-join-right-join-operations-microsoft-access-sql.md">RIGHT JOIN</a> 操作或保存的查询产生的组合结果。</p></td>
</tr>
<tr class="even">
<td><p><em>value1</em>, <em>value2</em></p></td>
<td><p>要插入新记录的特定字段中的值。各值均插入与该值在列表中的位置相对应的字段：<em>value1</em> 插入新记录的 <em>field1</em> 中，<em>value2</em> 插入 <em>field2</em> 中，以此类推。需使用逗号隔开各值，并将文本字段放在引号 (' ') 中。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

通过如上所述的单记录追加查询语法，可以使用 INSERT INTO 语句向表中追加单个记录。在这种情形下，代码要指定每个记录字段的名称和值。必须指定每一个将被赋值的记录字段，并且要给出该字段的值。如果没有指定每个字段的值，则在缺少值的列中插入默认值或 **Null** 值。记录将追加到表的末尾。

通过如上所示的多字段追加查询语法的 SELECT ... FROM 子句，还可以使用 INSERT INTO 追加一组来自其他表或查询的记录。这种情形下，SELECT 子句指定将要追加到指定的 *target* 表中的字段。


            *source* 或 *target* 表可以指定一个表或一个查询。如果指定的是查询，Microsoft Access 数据库引擎将记录追加到该查询指定的任一个表或所有表中。

INSERT INTO 是可选的，但是如果包括它，应将它置于 [SELECT](select-statement-microsoft-access-sql.md) 语句前面。

如果目标表中包含主键，请确保追加到主键字段中的值是唯一的、非 **Null** 的；否则，Microsoft Access 数据库引擎不会追加这些记录。

如果向含 AutoNumber 字段的表追加记录，并需要给追加的记录重新编号，则不要在查询中包含 AutoNumber 字段。如果要获取 AutoNumber 字段中的原始值，则在查询中包含该字段。

使用 IN 子句将记录追加到另一个数据库的表中。

若要新建表，请使用 [SELECT... INTO](select-into-statement-microsoft-access-sql.md) 语句来创建一个生成表查询。

若要在运行追加查询之前找出将要追加哪些记录，可以先执行使用同样选择条件的选择查询并查看其结果。

追加查询将记录从一个或多个表复制到另一个表。含追加的记录的表不受该追加查询影响。

可以使用 VALUES 子句为一个新记录中的各字段指定值，而不是从另一个表追加现有的记录。如果省略字段列表，VALUES 子句必须为表中的每一个字段指定一个值；否则，INSERT 操作将失败。为要创建的每一条额外的记录分别再使用一个含 VALUES 子句的 INSERT INTO 语句。

**链接提供方：**[UtterAccess](https://www.utteraccess.com) 社区。 UtterAccess 是主要的 Microsoft Access Wiki 和帮助论坛。

- [为 INSERT/UPDATE 语句生成连续数字](https://www.utteraccess.com/forum/generating-sequential-num-t446039.html)

- [SQL to VBA Formatter](https://www.utteraccess.com/forum/sql-vba-formatter-t1165308.html)

## <a name="example"></a>示例

本例选择假想的 New Customers 表中的所有记录并将这些记录添加到 Customers 表。如果未指定各个列，那么 SELECT 中的表列名必须与 INSERT INTO 中的表列名完全匹配。

```vb
    Sub InsertIntoX1() 
     
        Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
         
        ' Select all records in the New Customers table  
        ' and add them to the Customers table. 
        dbs.Execute " INSERT INTO Customers " _ 
            & "SELECT * " _ 
            & "FROM [New Customers];" 
             
        dbs.Close 
     
    End Sub
```

<br/>

以下示例在 Employees 表中创建一个新记录。

```vb
    Sub InsertIntoX2() 
     
        Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
         
        ' Create a new record in the Employees table. The  
        ' first name is Harry, the last name is Washington,  
        ' and the job title is Trainee. 
        dbs.Execute " INSERT INTO Employees " _ 
            & "(FirstName,LastName, Title) VALUES " _ 
            & "('Harry', 'Washington', 'Trainee');" 
             
        dbs.Close 
     
    End Sub 
```

