---
title: CONSTRAINT 子句 (Microsoft Access SQL)
TOCTitle: CONSTRAINT Clause (Microsoft Access SQL)
ms:assetid: f8e89a91-a69e-1811-42a7-921692110bcb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836971(v=office.15)
ms:contentKeyID: 48548797
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277561
dev_langs:
- sql
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 7b26033c8026591c87e4d0f9e077380862e39f16
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465764"
---
# <a name="constraint-clause-microsoft-access-sql"></a>CONSTRAINT 子句 (Microsoft Access SQL)

**适用于**： Access 2013 |Office 2013

约束和索引相似，虽然它还可以用于建立和其他表的关系。

可以在 [ALTER TABLE](alter-table-statement-microsoft-access-sql.md) 和 [CREATE TABLE](create-table-statement-microsoft-access-sql.md) 语句中使用 CONSTRAINT 子句来创建或删除约束。有两种类型的 CONSTRAINT 子句：一个用于创建单字段的约束，另外一个用于创建多字段的约束。


> [!NOTE]
> [!注释] Microsoft Access 数据库引擎不支持将 CONSTRAINT 或任何数据定义语言 (DDL) 语句用于非 Microsoft Access 数据库引擎数据库。可以改用 DAO Create 方法。

## <a name="syntax"></a>语法

单字段约束：

约束*名称*{主键 |唯一 |不为 NULL |引用*foreigntable* \[（*foreignfield1、 foreignfield2*）\] \[ON 更新 CASCADE |设置为 NULL\] \[级联删除 |设置为 NULL\]}

多字段约束：

约束*名称*{PRIMARY KEY (*primary1*\[， *primary2* \[，...\]\]) |唯一 (*unique1*\[， *unique2* \[，...\]\]) |不为 NULL (*notnull1*\[， *notnull2* \[，...\]\]) |外键\[没有索引\](*ref1*\[， *ref2* \[，...\] \]) 引用*foreigntable* \[(*foreignfield1* \[， *foreignfield2* \[，...\] \])\] \[ON 更新 CASCADE |设置为 NULL\] \[级联删除 |设置为 NULL\]}

CONSTRAINT 子句包含以下部分：

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
<td><p><em>name</em></p></td>
<td><p>要创建的约束的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>primary1</em>、<em>primary2</em></p></td>
<td><p>要指定为主键的字段的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>unique1</em>、<em>unique2</em></p></td>
<td><p>要指定为唯一键的字段的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>notnull1、notnull2</em></p></td>
<td><p>限制为非 Null 值的字段的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>ref1</em>、<em>ref2</em></p></td>
<td><p>引用另一个表中的字段的外键字段的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>foreigntable</em></p></td>
<td><p>包含了由 <em>foreignfield</em> 所指定的字段的外表的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>foreignfield1</em>、<em>foreignfield2</em></p></td>
<td><p>由 <em>ref1</em>、<em>ref2</em> 指定 <em>foreigntable</em> 中的字段的名称。如果所引用字段是 <em>foreigntable</em> 的主键，可以忽略这个子句。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

在 ALTER TABLE 或 CREATE TABLE 语句的字段定义子句中，在紧随字段数据类型指定之后，可以将该语法用于单字段约束。

任何时候，只要在 ALTER TABLE 或 CREATE TABLE 语句中的字段定义子句以外使用保留字 CONSTRAINT，就可以将该语法用于多字段约束。

使用 CONSTRAINT 可以将字段指定为以下约束类型：

- 可以使用 UNIQUE 保留字将字段指定为唯一键。就是说，表中不存在两个记录在该字段上拥有相同的值。可以将任何字段或字段的列表约束为唯一项。如果一个多字段约束被指定为唯一键，那么，在索引中所有字段的组合值必须是唯一的，即使有两个或更多个记录的仅一个字段具有相同的值。

- 可以使用 PRIMARY KEY 保留字将表中的一个字段或一组字段指定为主键。主键中的所有值必须是唯一的，并且不为 **Null** ，并且一个表只能有一个主键。
    
  > [!NOTE]
  > [!注释] 不要对已有主键的表设置 PRIMARY KEY 约束；否则，会产生错误。

- 可以使用 FOREIGN KEY 保留字将某个字段指定为外键。如果外表的主键由多个字段组成，那么必须使用多字段约束定义，从而按照列出引用字段时的相同顺序来列出所有引用字段、外表名以及外表中被引用字段的名称。如果引用字段是外表的主键，则不必指定被引用字段。默认情况下，数据库引擎将外表的主键假设为被引用字段。 外键约束定义了当相应的主键值更改时所要执行的具体操作：

- 可以根据对在其上定义 CONSTRAINT 的表中的主键执行的相应操作，来指定要对外表执行的操作。例如，假设以下为 Customers 表的定义：
    
  ``` sql
    CREATE TABLE Customers (CustId INTEGER PRIMARY KEY, CLstNm NCHAR VARYING (50))
  ```
    
  假设以下是 Orders 表的定义，它定义了一个外键关系以引用 Customers 表的主键：
    
  ``` sql
    CREATE TABLE Orders (OrderId INTEGER PRIMARY KEY, CustId INTEGER, OrderNotes NCHAR VARYING (255), CONSTRAINT FKOrdersCustId FOREIGN KEY (CustId) REFERENCES Customers ON UPDATE CASCADE ON DELETE CASCADE
  ```
    
  两个 ON UPDATE CASCADE 和 ON DELETE CASCADE 子句都是针对外键进行的定义。ON UPDATE CASCADE 子句表示如果"客户"表中的一个顾客的标识 (CustId) 被更新，则该更新会级联应用于整个"订单"表。每一个包含了相应顾客标识值的订单将都会自动更新为新的值。ON DELETE CASCADE 子句表示如果有一个顾客从"客户"表中删除，那么在"订单"表中包含同一个顾客标识值的所有行也会被删除。 下面是对 Orders 表的不同定义，它使用了 SET NULL 操作来取代 CASCADE 操作：
  
  ``` sql
    CREATE TABLE Orders (OrderId INTEGER PRIMARY KEY, CustId INTEGER, OrderNotes NCHAR VARYING (255), CONSTRAINT FKOrdersCustId FOREIGN KEY (CustId) REFERENCES Customers ON UPDATE SET NULL ON DELETE SET NULL
  ```
    
  ON UPDATE SET NULL 子句表示：如果在"客户"表中有一个顾客的标识 (CustId) 被更新，那么在"订单"表中相应的外键值将会自动设置为空。同样，ON DELETE SET NULL 子句表示：如果有一个顾客从"客户"表中删除，所有"订单"表中相应的外键都将会自动设置为空。

若要防止自动创建外键的索引，可以使用修饰符 NO INDEX。这种外键定义方式只应该用在结果索引值会被频繁复制的情况下。在外键索引中的值需要频繁复制的地方，使用索引比仅仅执行表扫描低效。维持这种索引时，随着在表中插入行和删除行的次数的增加，性能将会降低，并且没有任何好处。

## <a name="example"></a>示例

以下示例创建一个名为 ThisTable 且包含两个文本字段的新表。

```vb 
 Sub CreateTableX1()    
Dim dbs As Database 
 
    ' Modify this line to include the path to Northwind 
    ' on your computer. 
    Set dbs = OpenDatabase("Northwind.mdb") 
 
    ' Create a table with two text fields. 
    dbs.Execute "CREATE TABLE ThisTable " _ 
        & "(FirstName CHAR, LastName CHAR);" 
 
    dbs.Close 
 
End Sub
```

<br/>

本例创建一个名为 MyTable 的新表，该表包含两个文本字段、一个"日期/时间"字段以及一个包含这三个字段的唯一索引。

```vb
    Sub CreateTableX2() 
     
        Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
     
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Create a table with three fields and a unique 
        ' index made up of all three fields. 
        dbs.Execute "CREATE TABLE MyTable " _ 
            & "(FirstName CHAR, LastName CHAR, " _ 
            & "DateOfBirth DATETIME, " _ 
            & "CONSTRAINT MyTableConstraint UNIQUE " _ 
            & "(FirstName, LastName, DateOfBirth));" 
     
        dbs.Close 
     
    End Sub
```

<br/>

以下示例创建一个具有两个文本字段和一个 **Integer** 字段的新表。SSN 字段是主键。

```vb
    Sub CreateTableX3() 
     
         Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Create a table with three fields and a primary 
        ' key. 
        dbs.Execute "CREATE TABLE NewTable " _ 
            & "(FirstName CHAR, LastName CHAR, " _ 
            & "SSN INTEGER CONSTRAINT MyFieldConstraint " _ 
            & "PRIMARY KEY);" 
     
        dbs.Close 
     
    End Sub
```

<br/>

