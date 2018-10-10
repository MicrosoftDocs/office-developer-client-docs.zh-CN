---
title: ALTER TABLE 语句 (Microsoft Access SQL)
TOCTitle: ALTER TABLE Statement (Microsoft Access SQL)
ms:assetid: 78e6c92c-e88c-e55f-6b89-435360c166a6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196148(v=office.15)
ms:contentKeyID: 48545763
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277560
dev_langs:
- sql
f1_categories:
- Office.Version=v15
ms.openlocfilehash: b8fc826d438973b4d079e9b90d3663ab755821cc
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468507"
---
# <a name="alter-table-statement-microsoft-access-sql"></a><span data-ttu-id="53a84-102">ALTER TABLE 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="53a84-102">ALTER TABLE Statement (Microsoft Access SQL)</span></span>


<span data-ttu-id="53a84-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="53a84-103">**Applies to**: Access 2013 | Office 2013</span></span>



<span data-ttu-id="53a84-104">修改用 [CREATE TABLE](create-table-statement-microsoft-access-sql.md) 语句创建的表的设计。</span><span class="sxs-lookup"><span data-stu-id="53a84-104">Modifies the design of a table after it has been created with the [CREATE TABLE](create-table-statement-microsoft-access-sql.md) statement.</span></span>


> [!NOTE]
> <span data-ttu-id="53a84-p101">[!注释] Microsoft Access 数据库引擎不支持使用 ALTER TABLE 语句或任何数据定义语言 (DDL) 语句。可以改用 DAO Create 方法。</span><span class="sxs-lookup"><span data-stu-id="53a84-p101">The Microsoft Access database engine does not support the use of ALTER TABLE, or any of the data definition language (DDL) statements, with non-Microsoft Access databases. Use the DAO Create methods instead.</span></span>



## <a name="syntax"></a><span data-ttu-id="53a84-107">语法</span><span class="sxs-lookup"><span data-stu-id="53a84-107">Syntax</span></span>

<span data-ttu-id="53a84-108">ALTER TABLE*表*{添加 {列*字段类型*\[（*大小*）\] \[NOT NULL\] \[约束*索引*\] |更改列*字段类型*\[（*大小*）\] |CONSTRAINT *multifieldindex*} |DROP {列*字段*我约束*indexname*}}</span><span class="sxs-lookup"><span data-stu-id="53a84-108">ALTER TABLE *table* {ADD {COLUMN *field type*\[(*size*)\] \[NOT NULL\] \[CONSTRAINT *index*\] | ALTER COLUMN *field type*\[(*size*)\] | CONSTRAINT *multifieldindex*} | DROP {COLUMN *field* I CONSTRAINT *indexname*} }</span></span>

<span data-ttu-id="53a84-109">ALTER TABLE 语句有以下部分：</span><span class="sxs-lookup"><span data-stu-id="53a84-109">The ALTER TABLE statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="53a84-110">部分</span><span class="sxs-lookup"><span data-stu-id="53a84-110">Part</span></span></p></th>
<th><p><span data-ttu-id="53a84-111">说明</span><span class="sxs-lookup"><span data-stu-id="53a84-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53a84-112"><em>table</em></span><span class="sxs-lookup"><span data-stu-id="53a84-112"><em>table</em></span></span></p></td>
<td><p><span data-ttu-id="53a84-113">要修改的表的名称。</span><span class="sxs-lookup"><span data-stu-id="53a84-113">The name of the table to be altered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a84-114"><em>field</em></span><span class="sxs-lookup"><span data-stu-id="53a84-114"><em>field</em></span></span></p></td>
<td><p><span data-ttu-id="53a84-p102">要在 <em>table</em> 中添加或删除的字段的名称，或者是要在 <em>table</em> 中修改的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="53a84-p102">The name of the field to be added to or deleted from <em>table</em>. Or, the name of the field to be altered in <em>table</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a84-117"><em>类型</em></span><span class="sxs-lookup"><span data-stu-id="53a84-117"><em>type</em></span></span></p></td>
<td><p><span data-ttu-id="53a84-118"><em>field</em> 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="53a84-118">The data type of <em>field</em>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a84-119"><em>size</em></span><span class="sxs-lookup"><span data-stu-id="53a84-119"><em>size</em></span></span></p></td>
<td><p><span data-ttu-id="53a84-120">以字符为单位的字段大小（仅限于文本和二进制字段）。</span><span class="sxs-lookup"><span data-stu-id="53a84-120">The field size in characters (Text and Binary fields only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a84-121"><em>index</em></span><span class="sxs-lookup"><span data-stu-id="53a84-121"><em>index</em></span></span></p></td>
<td><p><span data-ttu-id="53a84-p103"><em>field</em> 的索引。有关如何构造此索引的详细信息，请参阅 <a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT 子句</a>。</span><span class="sxs-lookup"><span data-stu-id="53a84-p103">The index for <em>field</em>. For more information on how to construct this index see <a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT Clause</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a84-124"><em>multifieldindex</em></span><span class="sxs-lookup"><span data-stu-id="53a84-124"><em>multifieldindex</em></span></span></p></td>
<td><p><span data-ttu-id="53a84-p104">要添加到 <em>table</em> 中的多字段索引的定义。有关如何构造此索引的详细信息，请参阅 <a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT 子句</a>。</span><span class="sxs-lookup"><span data-stu-id="53a84-p104">The definition of a multiple-field index to be added to <em>table</em>. For more information on how to construct this index see <a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT Clause</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a84-127"><em>indexname</em></span><span class="sxs-lookup"><span data-stu-id="53a84-127"><em>indexname</em></span></span></p></td>
<td><p><span data-ttu-id="53a84-128">将要删除的多字段索引的名称。</span><span class="sxs-lookup"><span data-stu-id="53a84-128">The name of the multiple-field index to be removed.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="53a84-129">说明</span><span class="sxs-lookup"><span data-stu-id="53a84-129">Remarks</span></span>

<span data-ttu-id="53a84-p105">使用 ALTER TABLE 语句可以通过多种方法修改现有表。您可以：</span><span class="sxs-lookup"><span data-stu-id="53a84-p105">Using the ALTER TABLE statement you can alter an existing table in several ways. You can:</span></span>

  - <span data-ttu-id="53a84-p106">使用 ADD COLUMN 向表中添加新字段。可以指定字段名称、数据类型和可选大小（对于文本和二进制字段）。例如，以下语句将具有 25 个字符的名为 Notes 的文本字段添加到 Employees 表中：</span><span class="sxs-lookup"><span data-stu-id="53a84-p106">Use ADD COLUMN to add a new field to the table. You specify the field name, data type, and (for Text and Binary fields) an optional size. For example, the following statement adds a 25-character Text field called Notes to the Employees table:</span></span>
    
    ```sql
    ALTER TABLE Employees ADD COLUMN Notes TEXT(25)
    ```
    
    <span data-ttu-id="53a84-p107">也可以定义该字段的索引。有关单字段索引的详细信息，请参阅 [CONSTRAINT 子句](constraint-clause-microsoft-access-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="53a84-p107">You can also define an index on that field. For more information on single-field indexes see [CONSTRAINT Clause](constraint-clause-microsoft-access-sql.md).</span></span>
    
    <span data-ttu-id="53a84-137">如果指定一个字段为 NOT NULL，那么新记录的该字段必需有有效数据。</span><span class="sxs-lookup"><span data-stu-id="53a84-137">If you specify NOT NULL for a field then new records are required to have valid data in that field.</span></span>

  - <span data-ttu-id="53a84-p108">使用 ALTER COLUMN 可更改现有字段的数据类型。可以指定文本和二进制字段的字段名称、新的数据类型以及可选大小。例如，以下语句将 Employees 表中名为 ZipCode 字段的数据类型（原先定义为整型）更改为具有 10 个字符的文本字段：</span><span class="sxs-lookup"><span data-stu-id="53a84-p108">Use ALTER COLUMN to change the data type of an existing field. You specify the field name, the new data type, and an optional size for Text and Binary fields. For example, the following statement changes the data type of a field in the Employees table called ZipCode (originally defined as Integer) to a 10-character Text field:</span></span>
    
    ```sql
    ALTER TABLE Employees ALTER COLUMN ZipCode TEXT(10)
    ```

  - <span data-ttu-id="53a84-p109">使用 ADD CONSTRAINT 可添加多字段索引。有关多字段索引的详细信息，请参阅 [CONSTRAINT 子句](constraint-clause-microsoft-access-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="53a84-p109">Use ADD CONSTRAINT to add a multiple-field index. For more information on multiple-field indexes see [CONSTRAINT Clause](constraint-clause-microsoft-access-sql.md).</span></span>

  - <span data-ttu-id="53a84-p110">使用 DROP COLUMN 可删除字段。只需指定字段的名称。</span><span class="sxs-lookup"><span data-stu-id="53a84-p110">Use DROP COLUMN to delete a field. You specify only the name of the field.</span></span>

  - <span data-ttu-id="53a84-p111">使用 DROP CONSTRAINT 可删除多字段索引。只需在 CONSTRAINT 保留字后面指定索引名称。</span><span class="sxs-lookup"><span data-stu-id="53a84-p111">Use DROP CONSTRAINT to delete a multiple-field index. You specify only the index name following the CONSTRAINT reserved word.</span></span>


> [!NOTE]
> <UL>
> <LI>
> <P><span data-ttu-id="53a84-147">[!注释] 不能同时添加或删除多个字段或索引。</span><span class="sxs-lookup"><span data-stu-id="53a84-147">You cannot add or delete more than one field or index at a time.</span></span></P>
> <LI>
> <P><span data-ttu-id="53a84-148">可以使用 <A href="create-index-statement-microsoft-access-sql.md">CREATE INDEX</A> 语句向表中添加单字段或多字段的索引，并且可以使用 ALTER TABLE 或者 <A href="drop-statement-microsoft-access-sql.md">DROP</A> 语句删除使用 ALTER TABLE 或 CREATE INDEX 创建的索引。</span><span class="sxs-lookup"><span data-stu-id="53a84-148">You can use the <A href="create-index-statement-microsoft-access-sql.md">CREATE INDEX</A> statement to add a single- or multiple-field index to a table, and you can use ALTER TABLE or the <A href="drop-statement-microsoft-access-sql.md">DROP</A> statement to delete an index created with ALTER TABLE or CREATE INDEX.</span></span></P>
> <LI>
> <P><span data-ttu-id="53a84-p112">在一个字段或一个名为 CONSTRAINT 的子句中可以使用 NOT NULL，该子句既可应用于单字段索引，也可应用于名为 CONSTRAINT 的多字段索引。但是，NOT NULL 限制一次只能应用于一个字段。多次应用此限制将导致运行时错误。
</span><span class="sxs-lookup"><span data-stu-id="53a84-p112">You can use NOT NULL on a single field or within a named CONSTRAINT clause that applies to either a single field or to a multiple-field named CONSTRAINT. However, you can apply the NOT NULL restriction only once to a field. Attempting to apply this restriction more than once restuls in a run-time error.</span></span></P></LI></UL>



## <a name="example"></a><span data-ttu-id="53a84-152">示例</span><span class="sxs-lookup"><span data-stu-id="53a84-152">Example</span></span>

<span data-ttu-id="53a84-153">本例向 Employees 表中添加数据类型为 **Money** 的 Salary 字段。</span><span class="sxs-lookup"><span data-stu-id="53a84-153">This example adds a Salary field with the data type **Money** to the Employees table.</span></span>

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

<span data-ttu-id="53a84-154">本例将 Salary 字段的数据类型从 **Money** 更改为 **Char** 。</span><span class="sxs-lookup"><span data-stu-id="53a84-154">This example changes the Salary field from the data type **Money** to the data type **Char**.</span></span>

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

<span data-ttu-id="53a84-155">本例从 Employees 表中删除 Salary 字段。</span><span class="sxs-lookup"><span data-stu-id="53a84-155">This example removes the Salary field from the Employees table.</span></span>

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

<span data-ttu-id="53a84-p113">本例向 Orders 表中添加一个外键。该外键基于 Employees 表的 EmployeeID 字段，并引用该字段。在本例的 REFERENCES 子句中，您不必在 Employees 表后列出 EmployeeID 字段，因为 EmployeeID 是 Employees 表的主键。</span><span class="sxs-lookup"><span data-stu-id="53a84-p113">This example adds a foreign key to the Orders table. The foreign key is based on the EmployeeID field and refers to the EmployeeID field of the Employees table. In this example, you do not have to list the EmployeeID field after the Employees table in the REFERENCES clause because EmployeeID is the primary key of the Employees table.</span></span>

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

<span data-ttu-id="53a84-159">本例从 Orders 表中删除外键。</span><span class="sxs-lookup"><span data-stu-id="53a84-159">This example removes the foreign key from the Orders table.</span></span>

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
