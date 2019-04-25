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
ms.openlocfilehash: b8bd9abac3aee8be8fe52e555fcd5247e804f258
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297156"
---
# <a name="alter-table-statement-microsoft-access-sql"></a><span data-ttu-id="62eb7-102">ALTER TABLE 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="62eb7-102">ALTER TABLE Statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="62eb7-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="62eb7-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="62eb7-104">修改用 [CREATE TABLE](create-table-statement-microsoft-access-sql.md) 语句创建的表的设计。</span><span class="sxs-lookup"><span data-stu-id="62eb7-104">Modifies the design of a table after it has been created with the [CREATE TABLE](create-table-statement-microsoft-access-sql.md) statement.</span></span>

> [!NOTE]
> <span data-ttu-id="62eb7-105">[!注释] Microsoft Access 数据库引擎不支持使用 ALTER TABLE 语句或任何数据定义语言 (DDL) 语句。</span><span class="sxs-lookup"><span data-stu-id="62eb7-105">The Microsoft Access database engine does not support the use of ALTER TABLE, or any of the data definition language (DDL) statements, with non-Microsoft Access databases.</span></span> <span data-ttu-id="62eb7-106">请改为使用 DAO **Create** 方法。</span><span class="sxs-lookup"><span data-stu-id="62eb7-106">Use the DAO Create methods instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="62eb7-107">语法</span><span class="sxs-lookup"><span data-stu-id="62eb7-107">Syntax</span></span>

<span data-ttu-id="62eb7-108">ALTER TABLE *table* {ADD {COLUMN *field type*\[(*size*)\] \[NOT NULL\] \[CONSTRAINT *index*\] | ALTER COLUMN *field type*\[(*size*)\] | CONSTRAINT *multifieldindex*} | DROP {COLUMN *field* I CONSTRAINT *indexname*} }</span><span class="sxs-lookup"><span data-stu-id="62eb7-108">ALTER TABLE table {ADD {COLUMN field type[(size)] [NOT NULL]     [CONSTRAINT index] | 
    ALTER COLUMN field type[(size)] | 
    CONSTRAINT multifieldindex} | 
    DROP {COLUMN field I CONSTRAINT indexname} }</span></span>

<span data-ttu-id="62eb7-109">ALTER TABLE 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="62eb7-109">The ALTER TABLE statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="62eb7-110">部分</span><span class="sxs-lookup"><span data-stu-id="62eb7-110">Part</span></span></p></th>
<th><p><span data-ttu-id="62eb7-111">说明</span><span class="sxs-lookup"><span data-stu-id="62eb7-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62eb7-112"><em>table</em></span><span class="sxs-lookup"><span data-stu-id="62eb7-112"><em>table</em></span></span></p></td>
<td><p><span data-ttu-id="62eb7-113">要更改的表名称。</span><span class="sxs-lookup"><span data-stu-id="62eb7-113">The name of the table to be altered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62eb7-114"><em>field</em></span><span class="sxs-lookup"><span data-stu-id="62eb7-114"><em>field</em></span></span></p></td>
<td><p><span data-ttu-id="62eb7-p102">要添加到<em>表</em>中或要从中删除的字段名称。或要在<em>表</em>中更改的字段名称。</span><span class="sxs-lookup"><span data-stu-id="62eb7-p102">The name of the field to be added to or deleted from <em>table</em>. Or, the name of the field to be altered in <em>table</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62eb7-117"><em>type</em></span><span class="sxs-lookup"><span data-stu-id="62eb7-117"><em>type</em></span></span></p></td>
<td><p><span data-ttu-id="62eb7-118">
            <em>字段</em>的数据类型。</span><span class="sxs-lookup"><span data-stu-id="62eb7-118">The data type of <em>field</em>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62eb7-119"><em>size</em></span><span class="sxs-lookup"><span data-stu-id="62eb7-119"><em>size</em></span></span></p></td>
<td><p><span data-ttu-id="62eb7-120">以字符数为单位的字段大小（仅限于“文本”字段和“二进制”字段）。</span><span class="sxs-lookup"><span data-stu-id="62eb7-120">The field size in characters (Text and Binary fields only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62eb7-121"><em>index</em></span><span class="sxs-lookup"><span data-stu-id="62eb7-121"><em>index</em></span></span></p></td>
<td><p><span data-ttu-id="62eb7-122"><em>字段</em>的索引。</span><span class="sxs-lookup"><span data-stu-id="62eb7-122">The index for <em>field</em>.</span></span> <span data-ttu-id="62eb7-123">有关如何构造此索引的详细信息，请参阅 <a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT 子句</a>。</span><span class="sxs-lookup"><span data-stu-id="62eb7-123">For more information on how to construct this index see <a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT Clause</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62eb7-124"><em>multifieldindex</em></span><span class="sxs-lookup"><span data-stu-id="62eb7-124"><em>multifieldindex</em></span></span></p></td>
<td><p><span data-ttu-id="62eb7-125">要添加到<em>表</em>中的多字段索引的定义。</span><span class="sxs-lookup"><span data-stu-id="62eb7-125">The definition of a multiple-field index to be added to <em>table</em>.</span></span> <span data-ttu-id="62eb7-126">有关如何构造此索引的详细信息，请参阅 <a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT 子句</a>。</span><span class="sxs-lookup"><span data-stu-id="62eb7-126">For more information on how to construct this index see <a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT Clause</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62eb7-127"><em>indexname</em></span><span class="sxs-lookup"><span data-stu-id="62eb7-127"><em>indexname</em></span></span></p></td>
<td><p><span data-ttu-id="62eb7-128">要删除的多字段索引的名称。</span><span class="sxs-lookup"><span data-stu-id="62eb7-128">The name of the multiple-field index to be removed.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="62eb7-129">说明</span><span class="sxs-lookup"><span data-stu-id="62eb7-129">Remarks</span></span>

<span data-ttu-id="62eb7-130">使用 ALTER TABLE 语句能够以多种方式更改现有表。</span><span class="sxs-lookup"><span data-stu-id="62eb7-130">Using the ALTER TABLE statement you can alter an existing table in several ways.</span></span> <span data-ttu-id="62eb7-131">您可以进行以下操作：</span><span class="sxs-lookup"><span data-stu-id="62eb7-131">You can:</span></span>

- <span data-ttu-id="62eb7-p106">使用 ADD COLUMN 将新字段添加到表。指定字段名称、数据类型，以及（对于“文本”字段和“二进制”字段）可选尺寸。例如，以下语句将名为 Notes 的 25 个字符的 Text 字段添加到“员工”表中：</span><span class="sxs-lookup"><span data-stu-id="62eb7-p106">Use ADD COLUMN to add a new field to the table. You specify the field name, data type, and (for Text and Binary fields) an optional size. For example, the following statement adds a 25-character Text field called Notes to the Employees table:</span></span>
    
  ```sql
    ALTER TABLE Employees ADD COLUMN Notes TEXT(25)
  ```
    
  <span data-ttu-id="62eb7-135">也可以在该字段上定义索引。</span><span class="sxs-lookup"><span data-stu-id="62eb7-135">You can also define an index on that field.</span></span> <span data-ttu-id="62eb7-136">有关单字段索引的详细信息，请参阅 [CONSTRAINT 子句](constraint-clause-microsoft-access-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="62eb7-136">For more information on single-field indexes see [CONSTRAINT Clause](constraint-clause-microsoft-access-sql.md).</span></span>
    
  <span data-ttu-id="62eb7-137">如果为字段指定 NOT NULL，则需要新记录才能在该字段中包含有效数据。</span><span class="sxs-lookup"><span data-stu-id="62eb7-137">If you specify NOT NULL for a field then new records are required to have valid data in that field.</span></span>

- <span data-ttu-id="62eb7-p108">使用 ALTER COLUMN 更改现有字段的数据类型。指定字段名称、新的字段类型以及“文本”字段和“二进制”字段的可选大小。例如，以下语句将“员工”表中名为 ZipCode 的某个字段的数据类型（最初定义为 Integer）更改为 10 个字符的 Text 字段：</span><span class="sxs-lookup"><span data-stu-id="62eb7-p108">Use ALTER COLUMN to change the data type of an existing field. You specify the field name, the new data type, and an optional size for Text and Binary fields. For example, the following statement changes the data type of a field in the Employees table called ZipCode (originally defined as Integer) to a 10-character Text field:</span></span>
    
  ```sql
    ALTER TABLE Employees ALTER COLUMN ZipCode TEXT(10)
  ```

- <span data-ttu-id="62eb7-141">使用 ADD CONSTRAINT 添加多字段索引。</span><span class="sxs-lookup"><span data-stu-id="62eb7-141">Use ADD CONSTRAINT to add a multiple-field index.</span></span> <span data-ttu-id="62eb7-142">有关多字段索引的详细信息，请参阅 [CONSTRAINT 子句](constraint-clause-microsoft-access-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="62eb7-142">For more information on multiple-field indexes see [CONSTRAINT Clause](constraint-clause-microsoft-access-sql.md).</span></span>

- <span data-ttu-id="62eb7-p110">使用 DROP COLUMN 删除字段。仅指定字段的名称。</span><span class="sxs-lookup"><span data-stu-id="62eb7-p110">Use DROP COLUMN to delete a field. You specify only the name of the field.</span></span>

- <span data-ttu-id="62eb7-p111">使用 DROP CONSTRAINT 可删除多字段索引。只需在 CONSTRAINT 保留字后面指定索引名称。</span><span class="sxs-lookup"><span data-stu-id="62eb7-p111">Use DROP CONSTRAINT to delete a multiple-field index. You specify only the index name following the CONSTRAINT reserved word.</span></span>


> [!NOTE] 
> - <span data-ttu-id="62eb7-147">无法一次添加或删除多个字段或索引。</span><span class="sxs-lookup"><span data-stu-id="62eb7-147">You cannot add or delete more than one field or index at a time.</span></span>
> - <span data-ttu-id="62eb7-148">可以使用 [CREATE INDEX](create-index-statement-microsoft-access-sql.md) 语句向表中添加单字段或多字段的索引，并且可以使用 ALTER TABLE 或者 [DROP](drop-statement-microsoft-access-sql.md) 语句删除使用 ALTER TABLE 或 CREATE INDEX 创建的索引。</span><span class="sxs-lookup"><span data-stu-id="62eb7-148">You can use the [CREATE INDEX](create-index-statement-microsoft-access-sql.md) statement to add a single- or multiple-field index to a table, and you can use ALTER TABLE or the [DROP](drop-statement-microsoft-access-sql.md) statement to delete an index created with ALTER TABLE or CREATE INDEX.</span></span>
> - <span data-ttu-id="62eb7-149">可以对单个字段或在应用于单个字段或多字段的命名 CONSTRAINT 的命名 CONSTRAINT 子句中使用 NOT NULL。</span><span class="sxs-lookup"><span data-stu-id="62eb7-149">You can use NOT NULL on a single field or within a named CONSTRAINT clause that applies to either a single field or to a multiple-field named CONSTRAINT.</span></span> <span data-ttu-id="62eb7-150">但是，仅可以对字段应用一次 NOT NULL 限制。</span><span class="sxs-lookup"><span data-stu-id="62eb7-150">However, you can apply the NOT NULL restriction only once to a field.</span></span> <span data-ttu-id="62eb7-151">尝试多次应用此限制将造成运行时错误。</span><span class="sxs-lookup"><span data-stu-id="62eb7-151">Attempting to apply this restriction more than once restuls in a run-time error.</span></span>

## <a name="example"></a><span data-ttu-id="62eb7-152">示例</span><span class="sxs-lookup"><span data-stu-id="62eb7-152">Example</span></span>

<span data-ttu-id="62eb7-153">以下示例向 Employees 表中添加数据类型为 **Money** 的 Salary 字段。</span><span class="sxs-lookup"><span data-stu-id="62eb7-153">This example adds a Salary field with the data type **Money** to the Employees table.</span></span>

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

<span data-ttu-id="62eb7-154">以下示例将 Salary 字段的数据类型从 **Money** 改为 **Char**。</span><span class="sxs-lookup"><span data-stu-id="62eb7-154">This example changes the Salary field from the data type **Money** to the data type **Char**.</span></span>

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

<span data-ttu-id="62eb7-155">以下示例从 Employees 表中删除 Salary 字段。</span><span class="sxs-lookup"><span data-stu-id="62eb7-155">This example removes the Salary field from the Employees table.</span></span>

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

<span data-ttu-id="62eb7-p113">本例向 Orders 表中添加一个外键。该外键基于 Employees 表的 EmployeeID 字段，并引用该字段。在本例的 REFERENCES 子句中，您不必在 Employees 表后列出 EmployeeID 字段，因为 EmployeeID 是 Employees 表的主键。</span><span class="sxs-lookup"><span data-stu-id="62eb7-p113">This example adds a foreign key to the Orders table. The foreign key is based on the EmployeeID field and refers to the EmployeeID field of the Employees table. In this example, you do not have to list the EmployeeID field after the Employees table in the REFERENCES clause because EmployeeID is the primary key of the Employees table.</span></span>

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

<span data-ttu-id="62eb7-159">以下示例从 Orders 表中删除外键。</span><span class="sxs-lookup"><span data-stu-id="62eb7-159">This example removes the foreign key from the Orders table.</span></span>

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
