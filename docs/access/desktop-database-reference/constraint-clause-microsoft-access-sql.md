---
title: CONSTRAINT 子句 (Microsoft Access SQL)
TOCTitle: CONSTRAINT clause (Microsoft Access SQL)
ms:assetid: f8e89a91-a69e-1811-42a7-921692110bcb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836971(v=office.15)
ms:contentKeyID: 48548797
ms.date: 10/18/2018
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277561
dev_langs:
- sql
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: 356620376658bb927c690056f4de9a01554aa47e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295644"
---
# <a name="constraint-clause-microsoft-access-sql"></a><span data-ttu-id="d8aeb-102">CONSTRAINT 子句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="d8aeb-102">CONSTRAINT Clause (Microsoft Access SQL)</span></span>

<span data-ttu-id="d8aeb-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="d8aeb-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="d8aeb-104">约束和索引相似，虽然它还可以用于建立和其他表的关系。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-104">A constraint is similar to an index, although it can also be used to establish a relationship with another table.</span></span>

<span data-ttu-id="d8aeb-p101">可以在 [ALTER TABLE](alter-table-statement-microsoft-access-sql.md) 和 [CREATE TABLE](create-table-statement-microsoft-access-sql.md) 语句中使用 CONSTRAINT 子句来创建或删除约束。有两种类型的 CONSTRAINT 子句：一个用于创建单字段的约束，另外一个用于创建多字段的约束。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-p101">You use the CONSTRAINT clause in [ALTER TABLE](alter-table-statement-microsoft-access-sql.md) and [CREATE TABLE](create-table-statement-microsoft-access-sql.md) statements to create or delete constraints. There are two types of CONSTRAINT clauses: one for creating a constraint on a single field and one for creating a constraint on more than one field.</span></span>

> [!NOTE]
> <span data-ttu-id="d8aeb-107">[!注释] Microsoft Access 数据库引擎不支持将 CONSTRAINT 或任何数据定义语言 (DDL) 语句用于非 Microsoft Access 数据库引擎数据库。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-107">The Microsoft Access database engine does not support the use of CONSTRAINT, or any of the data definition language (DDL) statements, with non-Microsoft Access database engine databases.</span></span> <span data-ttu-id="d8aeb-108">请改用 DAO **Create** 方法。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-108">Use the DAO Create methods instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="d8aeb-109">语法</span><span class="sxs-lookup"><span data-stu-id="d8aeb-109">Syntax</span></span>

### <a name="single-field-constraint"></a><span data-ttu-id="d8aeb-110">单字段约束</span><span class="sxs-lookup"><span data-stu-id="d8aeb-110">Single-field constraint:</span></span>

<span data-ttu-id="d8aeb-111">CONSTRAINT *name* {PRIMARY KEY | UNIQUE | NOT NULL | REFERENCES *foreigntable* \[(*foreignfield1, foreignfield2*)\] \[ON UPDATE CASCADE | SET NULL\] \[ON DELETE CASCADE | SET NULL\]}</span><span class="sxs-lookup"><span data-stu-id="d8aeb-111">CONSTRAINT name {PRIMARY KEY | UNIQUE | NOT NULL |
    REFERENCES foreigntable [(foreignfield1, foreignfield2)]
    [ON UPDATE CASCADE | SET NULL]
    [ON DELETE CASCADE | SET NULL]}</span></span>

### <a name="multiple-field-constraint"></a><span data-ttu-id="d8aeb-112">多字段约束</span><span class="sxs-lookup"><span data-stu-id="d8aeb-112">Multiple-field constraint:</span></span>

<span data-ttu-id="d8aeb-113">CONSTRAINT *name* {PRIMARY KEY (*primary1*\[, *primary2* \[, …\]\]) | UNIQUE (*unique1*\[, *unique2* \[, …\]\]) | NOT NULL (*notnull1*\[, *notnull2* \[, …\]\]) | FOREIGN KEY \[NO INDEX\] (*ref1*\[, *ref2* \[, …\]\]) REFERENCES *foreigntable* \[(*foreignfield1* \[, *foreignfield2* \[, …\]\])\] \[ON UPDATE CASCADE | SET NULL\] \[ON DELETE CASCADE | SET NULL\]}</span><span class="sxs-lookup"><span data-stu-id="d8aeb-113">CONSTRAINT *name* {PRIMARY KEY (*primary1*\[, *primary2* \[, …\]\]) | UNIQUE (*unique1*\[, *unique2* \[, …\]\]) | NOT NULL (*notnull1*\[, *notnull2* \[, …\]\]) | FOREIGN KEY \[NO INDEX\] (*ref1*\[, *ref2* \[, …\]\]) REFERENCES *foreigntable* \[(*foreignfield1* \[, *foreignfield2* \[, …\]\])\] \[ON UPDATE CASCADE | SET NULL\] \[ON DELETE CASCADE | SET NULL\]}</span></span>

<span data-ttu-id="d8aeb-114">CONSTRAINT 子句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="d8aeb-114">The CONSTRAINT clause has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="d8aeb-115">Part</span><span class="sxs-lookup"><span data-stu-id="d8aeb-115">Part</span></span></p></th>
<th><p><span data-ttu-id="d8aeb-116">说明</span><span class="sxs-lookup"><span data-stu-id="d8aeb-116">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8aeb-117"><em>name</em></span><span class="sxs-lookup"><span data-stu-id="d8aeb-117"><em>name</em></span></span></p></td>
<td><p><span data-ttu-id="d8aeb-118">要创建的约束的名称。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-118">The name of the constraint to be created.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8aeb-119"><em>primary1</em>、<em>primary2</em></span><span class="sxs-lookup"><span data-stu-id="d8aeb-119"><em>primary1</em>, <em>primary2</em></span></span></p></td>
<td><p><span data-ttu-id="d8aeb-120">要指定为主键的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-120">The name of the field or fields to be designated the primary key.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8aeb-121"><em>unique1</em>、<em>unique2</em></span><span class="sxs-lookup"><span data-stu-id="d8aeb-121"><em>unique1</em>, <em>unique2</em></span></span></p></td>
<td><p><span data-ttu-id="d8aeb-122">要指定为唯一键的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-122">The name of the field or fields to be designated as a unique key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8aeb-123"><em>notnull1, notnull2</em></span><span class="sxs-lookup"><span data-stu-id="d8aeb-123"><em>notnull1, notnull2</em></span></span></p></td>
<td><p><span data-ttu-id="d8aeb-124">限制为非 Null 值的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-124">The name of the field or fields that are restricted to non-Null values.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8aeb-125"><em>ref1</em>、<em>ref2</em></span><span class="sxs-lookup"><span data-stu-id="d8aeb-125"><em>ref1</em>, <em>ref2</em></span></span></p></td>
<td><p><span data-ttu-id="d8aeb-126">引用另一个表中的字段的外键字段的名称。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-126">The name of a foreign key field or fields that refer to fields in another table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8aeb-127"><em>foreigntable</em></span><span class="sxs-lookup"><span data-stu-id="d8aeb-127"><em>foreigntable</em></span></span></p></td>
<td><p><span data-ttu-id="d8aeb-128">包含了由 <em>foreignfield</em> 所指定的字段的外表的名称。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-128">The name of the foreign table containing the field or fields specified by <em>foreignfield</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8aeb-129"><em>foreignfield1</em>、<em>foreignfield2</em></span><span class="sxs-lookup"><span data-stu-id="d8aeb-129"><em>foreignfield1</em>, <em>foreignfield2</em></span></span></p></td>
<td><p><span data-ttu-id="d8aeb-p103">
            <em>foreigntable</em> 中由 <em>ref1</em>、<em>ref2</em> 指定的字段的名称。如果引用的字段是 <em>foreigntable</em> 的主键，则可省略此子句。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-p103">The name of the field or fields in <em>foreigntable</em> specified by <em>ref1</em>, <em>ref2</em>. You can omit this clause if the referenced field is the primary key of <em>foreigntable</em>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="d8aeb-132">说明</span><span class="sxs-lookup"><span data-stu-id="d8aeb-132">Remarks</span></span>

<span data-ttu-id="d8aeb-133">在 ALTER TABLE 或 CREATE TABLE 语句中，应紧随字段的数据类型规范后使用单字段约束的语法。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-133">You use the syntax for a single-field constraint in the field-definition clause of an ALTER TABLE or CREATE TABLE statement immediately following the specification of the field's data type.</span></span>

<span data-ttu-id="d8aeb-134">任何时候，只要在 ALTER TABLE 或 CREATE TABLE 语句中的字段定义子句以外使用保留字 CONSTRAINT，就可以将该语法用于多字段约束。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-134">You use the syntax for a multiple-field constraint whenever you use the reserved word CONSTRAINT outside a field-definition clause in an ALTER TABLE or CREATE TABLE statement.</span></span>

<span data-ttu-id="d8aeb-135">使用 CONSTRAINT 可将一个字段指定为以下类型的约束之一：</span><span class="sxs-lookup"><span data-stu-id="d8aeb-135">Using CONSTRAINT you can designate a field as one of the following types of constraints:</span></span>

- <span data-ttu-id="d8aeb-p104">可使用 UNIQUE 保留字将字段指定为唯一键。这意味着表中任意两个记录在此字段中的值都不相同。可将任何字段或字段列表约束为唯一键。如果将多字段约束指定为唯一键，则索引中所有字段的组合值必须是唯一的，即使两个或更多记录只有一个相同的字段值。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-p104">You can use the UNIQUE reserved word to designate a field as a unique key. This means that no two records in the table can have the same value in this field. You can constrain any field or list of fields as unique. If a multiple-field constraint is designated as a unique key, the combined values of all fields in the index must be unique, even if two or more records have the same value in just one of the fields.</span></span>

- <span data-ttu-id="d8aeb-p105">可使用 PRIMARY KEY 保留字将表中的一个或一组字段指定为主键。主键中的所有值都必须是唯一的，并且不为 **Null**，一个表只能有一个主键。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-p105">You can use the PRIMARY KEY reserved words to designate one field or set of fields in a table as a primary key. All values in the primary key must be unique and not **Null**, and there can be only one primary key for a table.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="d8aeb-142">请勿对已有主键的表设置 PRIMARY KEY 约束；这样做会出现错误。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-142">Do not set a PRIMARY KEY constraint on a table that already has a primary key; if you do, an error occurs.</span></span>

- <span data-ttu-id="d8aeb-p106">可以使用 FOREIGN KEY 保留字将某个字段指定为外键。如果外表的主键由多个字段组成，那么必须使用多字段约束定义，从而按照列出引用字段时的相同顺序来列出所有引用字段、外表名以及外表中被引用字段的名称。如果引用字段是外表的主键，则不必指定被引用字段。默认情况下，数据库引擎将外表的主键假设为被引用字段。 外键约束定义了当相应的主键值更改时所要执行的具体操作：</span><span class="sxs-lookup"><span data-stu-id="d8aeb-p106">You can use the FOREIGN KEY reserved words to designate a field as a foreign key. If the foreign table's primary key consists of more than one field, you must use a multiple-field constraint definition, listing all of the referencing fields, the name of the foreign table, and the names of the referenced fields in the foreign table in the same order that the referencing fields are listed. If the referenced field or fields are the foreign table's primary key, you do not have to specify the referenced fields. By default the database engine behaves as if the foreign table's primary key is the referenced fields. Foreign key constraints define specific actions to be performed when a corresponding primary key value is changed:</span></span>

- <span data-ttu-id="d8aeb-p107">可根据在定义了 CONSTRAINT 的表中主键执行的相应操作，指定对外表执行的操作。例如，请注意 Customers 表的以下定义：</span><span class="sxs-lookup"><span data-stu-id="d8aeb-p107">You can specify actions to be performed on the foreign table based on a corresponding action performed on a primary key in the table on which the CONSTRAINT is defined. For example, consider the following definition for the table Customers:</span></span>
    
  ``` sql
    CREATE TABLE Customers (CustId INTEGER PRIMARY KEY, CLstNm NCHAR VARYING (50))
  ```
    
  <span data-ttu-id="d8aeb-150">请注意 Orders 表的以下定义，其中定义的外键关系引用了 Customers 表的主键：</span><span class="sxs-lookup"><span data-stu-id="d8aeb-150">Consider the following definition of the table Orders, which defines a foreign key relationship referencing the primary key of the Customers table:</span></span>
    
  ``` sql
    CREATE TABLE Orders (OrderId INTEGER PRIMARY KEY, CustId INTEGER, OrderNotes NCHAR VARYING (255), CONSTRAINT FKOrdersCustId FOREIGN KEY (CustId) REFERENCES Customers ON UPDATE CASCADE ON DELETE CASCADE
  ```
    
  <span data-ttu-id="d8aeb-p108">两个 ON UPDATE CASCADE 和 ON DELETE CASCADE 子句都是针对外键进行的定义。ON UPDATE CASCADE 子句表示如果"客户"表中的一个顾客的标识 (CustId) 被更新，则该更新会级联应用于整个"订单"表。每一个包含了相应顾客标识值的订单将都会自动更新为新的值。ON DELETE CASCADE 子句表示如果有一个顾客从"客户"表中删除，那么在"订单"表中包含同一个顾客标识值的所有行也会被删除。 下面是对 Orders 表的不同定义，它使用了 SET NULL 操作来取代 CASCADE 操作：</span><span class="sxs-lookup"><span data-stu-id="d8aeb-p108">Both an ON UPDATE CASCADE and an ON DELETE CASCADE clause are defined on the foreign key. The ON UPDATE CASCADE clause means that if a customer's identifier (CustId) is updated in the Customer table, the update will be cascaded through the Orders table. Each order containing a corresponding customer identifier value will be updated automatically with the new value. The ON DELETE CASCADE clause means that if a customer is deleted from the Customer table, all rows in the Orders table containing the same customer identifier value will also be deleted. Consider the following different definition of the table Orders, using the SET NULL action instead of the CASCADE action:</span></span>
  
  ``` sql
    CREATE TABLE Orders (OrderId INTEGER PRIMARY KEY, CustId INTEGER, OrderNotes NCHAR VARYING (255), CONSTRAINT FKOrdersCustId FOREIGN KEY (CustId) REFERENCES Customers ON UPDATE SET NULL ON DELETE SET NULL
  ```
    
  <span data-ttu-id="d8aeb-p109">ON UPDATE SET NULL 子句意味着如果在客户表中更新了客户的标识符 (CustId)，则订单表中的相应外键值将自动设置为 NULL。同样，ON DELETE SET NULL 子句表示如果从 Customers 表中删除了客户，则 Orders 表中所有对应的外键都将自动设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-p109">The ON UPDATE SET NULL clause means that if a customer's identifier (CustId) is updated in the Customer table, the corresponding foreign key values in the Orders table will automatically be set to NULL. Similarly, the ON DELETE SET NULL clause means that if a customer is deleted from the Customer table, all corresponding foreign keys in the Orders table will automatically be set to NULL.</span></span>

<span data-ttu-id="d8aeb-p110">为防止自动创建外键索引，可使用修饰符 NO INDEX。仅应在要频繁复制生成的索引值时使用此形式的外键定义。如果要经常复制外键索引中的值，使用索引的效率可能比仅执行表扫描效率更低。如果保持使用此类索引，则在表中插入和删除行时，性能会降低并且没有任何好处。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-p110">To prevent the automatic creation of indexes for foreign keys, the modifier NO INDEX can be used. This form of foreign key definition should be used only in cases where the resulting index values would be frequently duplicated. Where the values in a foreign key index are frequently duplicated, using an index can be less efficient than simply performing a table scan. Maintaining this type of index, with rows inserted and deleted from the table, degrades performance and does not provide any benefit.</span></span>

## <a name="example"></a><span data-ttu-id="d8aeb-162">示例</span><span class="sxs-lookup"><span data-stu-id="d8aeb-162">Example</span></span>

<span data-ttu-id="d8aeb-163">以下示例创建一个名为 ThisTable 且包含两个文本字段的新表。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-163">This example creates a new table called ThisTable with two text fields.</span></span>

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

<span data-ttu-id="d8aeb-164">本例创建一个名为 MyTable 的新表，该表包含两个文本字段、一个"日期/时间"字段以及一个包含这三个字段的唯一索引。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-164">This example creates a new table called MyTable with two text fields, a Date/Time field, and a unique index made up of all three fields.</span></span>

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

<span data-ttu-id="d8aeb-p111">以下示例创建一个具有两个文本字段和一个 **Integer** 字段的新表。SSN 字段是主键。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-p111">This example creates a new table with two text fields and an **Integer** field. The SSN field is the primary key.</span></span>

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

