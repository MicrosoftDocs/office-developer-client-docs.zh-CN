---
title: CREATE TABLE 语句 (Microsoft Access SQL)
TOCTitle: CREATE TABLE statement (Microsoft Access SQL)
ms:assetid: fc45d36e-6e43-c030-5016-cca8bb1379fe
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837200(v=office.15)
ms:contentKeyID: 48548888
ms.date: 10/18/2018
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277563
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: 296e1405245d6204d136888e78b6a3846b468a1f
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28710935"
---
# <a name="create-table-statement-microsoft-access-sql"></a><span data-ttu-id="02761-102">CREATE TABLE 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="02761-102">CREATE TABLE statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="02761-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="02761-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="02761-104">新建一个表。</span><span class="sxs-lookup"><span data-stu-id="02761-104">Creates a new table.</span></span>

> [!NOTE]
> <span data-ttu-id="02761-105">[!注释] Microsoft Access 数据库引擎不支持对非 Microsoft Access 数据库引擎数据库使用 CREATE TABLE 或者任何 DDL 语句。</span><span class="sxs-lookup"><span data-stu-id="02761-105">The Microsoft Access database engine does not support the use of CREATE TABLE, or any of the DDL statements, with non-Microsoft Access database engine databases.</span></span> <span data-ttu-id="02761-106">而是使用 DAO**创建**方法。</span><span class="sxs-lookup"><span data-stu-id="02761-106">Use the DAO **Create** methods instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="02761-107">语法</span><span class="sxs-lookup"><span data-stu-id="02761-107">Syntax</span></span>

<span data-ttu-id="02761-108">创建\[临时\]表*表*(*field1 type* \[（*大小*）\] \[NOT NULL\] \[WITH COMPRESSION |与 COMP\] \[ *index1* \] \[， *field2* *类型* \[（*大小*）\] \[NOT NULL\] \[ *index2* \] \[，...\] \] \[，CONSTRAINT *multifieldindex* \[，...\]\])</span><span class="sxs-lookup"><span data-stu-id="02761-108">CREATE \[TEMPORARY\] TABLE *table* (*field1 type* \[(*size*)\] \[NOT NULL\] \[WITH COMPRESSION | WITH COMP\] \[*index1*\] \[, *field2* *type* \[(*size*)\] \[NOT NULL\] \[*index2*\] \[, …\]\] \[, CONSTRAINT *multifieldindex* \[, …\]\])</span></span>

<span data-ttu-id="02761-109">CREATE TABLE 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="02761-109">The CREATE TABLE statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="02761-110">部分</span><span class="sxs-lookup"><span data-stu-id="02761-110">Part</span></span></p></th>
<th><p><span data-ttu-id="02761-111">说明</span><span class="sxs-lookup"><span data-stu-id="02761-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02761-112"><em>table</em></span><span class="sxs-lookup"><span data-stu-id="02761-112"><em>table</em></span></span></p></td>
<td><p><span data-ttu-id="02761-113">要创建的表的名称。</span><span class="sxs-lookup"><span data-stu-id="02761-113">The name of the table to be created.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02761-114"><em>field1</em>、<em>field2</em></span><span class="sxs-lookup"><span data-stu-id="02761-114"><em>field1</em>, <em>field2</em></span></span></p></td>
<td><p><span data-ttu-id="02761-p102">要在新表中创建的字段的名称。必须创建至少一个字段。</span><span class="sxs-lookup"><span data-stu-id="02761-p102">The name of field or fields to be created in the new table. You must create at least one field.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02761-117"><em>type</em></span><span class="sxs-lookup"><span data-stu-id="02761-117"><em>type</em></span></span></p></td>
<td><p><span data-ttu-id="02761-118">在新表中 <em>field</em> 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="02761-118">The data type of <em>field</em> in the new table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02761-119"><em>size</em></span><span class="sxs-lookup"><span data-stu-id="02761-119"><em>size</em></span></span></p></td>
<td><p><span data-ttu-id="02761-120">以字符为单位的字段大小（仅限于文本和二进制字段）。</span><span class="sxs-lookup"><span data-stu-id="02761-120">The field size in characters (Text and Binary fields only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02761-121"><em>index1</em>、<em>index2</em></span><span class="sxs-lookup"><span data-stu-id="02761-121"><em>index1</em>, <em>index2</em></span></span></p></td>
<td><p><span data-ttu-id="02761-122">CONSTRAINT 子句定义单字段索引。</span><span class="sxs-lookup"><span data-stu-id="02761-122">A CONSTRAINT clause defining a single-field index.</span></span> <span data-ttu-id="02761-123">有关如何创建此索引的详细信息，请参阅<a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT 子句</a>。</span><span class="sxs-lookup"><span data-stu-id="02761-123">For more information about how to create this index, see <a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT clause</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02761-124"><em>multifieldindex</em></span><span class="sxs-lookup"><span data-stu-id="02761-124"><em>multifieldindex</em></span></span></p></td>
<td><p><span data-ttu-id="02761-125">CONSTRAINT 子句定义多字段索引。</span><span class="sxs-lookup"><span data-stu-id="02761-125">A CONSTRAINT clause defining a multiple-field index.</span></span> <span data-ttu-id="02761-126">有关如何创建此索引的详细信息，请参阅<a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT 子句</a>。</span><span class="sxs-lookup"><span data-stu-id="02761-126">For more information about how to create this index, see <a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT clause</a>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="02761-127">说明</span><span class="sxs-lookup"><span data-stu-id="02761-127">Remarks</span></span>

<span data-ttu-id="02761-128">使用 CREATE TABLE 语句可以定义一个新表及其字段和字段约束。</span><span class="sxs-lookup"><span data-stu-id="02761-128">Use the CREATE TABLE statement to define a new table and its fields and field constraints.</span></span> <span data-ttu-id="02761-129">如果没有为字段指定 NULL，新记录所需的字段中具有有效的数据。</span><span class="sxs-lookup"><span data-stu-id="02761-129">If NOT NULL is specified for a field, new records are required to have valid data in that field.</span></span>

<span data-ttu-id="02761-p106">CONSTRAINT 子句可建立对字段的各种约束，并且可用于建立主键。也可以使用 [CREATE INDEX](create-index-statement-microsoft-access-sql.md) 语句对现有表创建主键或其他索引。</span><span class="sxs-lookup"><span data-stu-id="02761-p106">A CONSTRAINT clause establishes various restrictions on a field, and can be used to establish the primary key. You can also use the [CREATE INDEX](create-index-statement-microsoft-access-sql.md) statement to create a primary key or additional indexes on existing tables.</span></span>

<span data-ttu-id="02761-p107">在一个字段或一个名为 CONSTRAINT 的子句中可以使用 NOT NULL，该子句既可应用于单字段索引，也可应用于名为 CONSTRAINT 的多字段索引。但是，NOT NULL 限制一次只能应用于一个字段。多次应用此限制将导致运行时错误。</span><span class="sxs-lookup"><span data-stu-id="02761-p107">You can use NOT NULL on a single field or within a named CONSTRAINT clause that applies to either a single field or to a multiple-field named CONSTRAINT. However, you can apply the NOT NULL restriction only once to a field. Attempting to apply this restriction more than once results in a run-time error.</span></span>

<span data-ttu-id="02761-135">创建一个临时表后，它是可见的仅在其中创建会话中。</span><span class="sxs-lookup"><span data-stu-id="02761-135">When a TEMPORARY table is created, it is visible only within the session in which it was created.</span></span> <span data-ttu-id="02761-136">当会话终止时，该表会被自动删除。</span><span class="sxs-lookup"><span data-stu-id="02761-136">It is automatically deleted when the session is terminated.</span></span> <span data-ttu-id="02761-137">临时表能够被多个用户访问。</span><span class="sxs-lookup"><span data-stu-id="02761-137">Temporary tables can be accessed by more than one user.</span></span>

<span data-ttu-id="02761-138">WITH COMPRESSION 属性只能用于 CHARACTER 和 MEMO（也叫做 TEXT）数据类型以及它们的同义词。</span><span class="sxs-lookup"><span data-stu-id="02761-138">The WITH COMPRESSION attribute can be used only with the CHARACTER and MEMO (also known as TEXT) data types and their synonyms.</span></span>

<span data-ttu-id="02761-139">由于 Unicode 字符表示格式发生的更改，属性 WITH COMPRESSION 被添加到 CHARACTER 列上。</span><span class="sxs-lookup"><span data-stu-id="02761-139">The WITH COMPRESSION attribute was added for CHARACTER columns because of the change to the Unicode character representation format.</span></span> <span data-ttu-id="02761-140">Unicode 字符中每个字符一律需要两个字节。</span><span class="sxs-lookup"><span data-stu-id="02761-140">Unicode characters uniformly require two bytes for each character.</span></span> <span data-ttu-id="02761-141">对于包含主要用于字符数据的现有 Microsoft Jet 数据库，这可能意味着几乎双数据库文件会转换为 Microsoft Access 数据库引擎格式时的大小。</span><span class="sxs-lookup"><span data-stu-id="02761-141">For existing Microsoft Jet databases that contain predominately character data, this could mean that the database file would nearly double in size when converted to the Microsoft Access database engine format.</span></span> <span data-ttu-id="02761-142">但是，可以很容易压缩的许多字符集，以前表示为单字节字符设置 (SBCS)，Unicode 表示形式，成一个字节。</span><span class="sxs-lookup"><span data-stu-id="02761-142">However, Unicode representation of many character sets, those formerly denoted as Single-Byte Character Sets (SBCS), can easily be compressed to a single byte.</span></span> <span data-ttu-id="02761-143">如果使用该属性定义 CHARACTER 列，在该列中存储数据时，数据会自动进行压缩；从该列检索数据时，数据会自动解压缩。</span><span class="sxs-lookup"><span data-stu-id="02761-143">If you define a CHARACTER column with this attribute, data will automatically be compressed as it is stored and uncompressed when retrieved from the column.</span></span>

<span data-ttu-id="02761-p110">MEMO 列也能定义为以压缩的格式来存储数据。但是，这样做是有限制的。进行压缩时，只有 MEMO 列实例的大小在 4096 字节以内，它才会被压缩。所有其他 MEMO 列实例仍然保持为未压缩格式。这意味着，对于指定表中的一个给定的 MEMO 列，一些数据可能被压缩，而一些数据则可能是未压缩的。</span><span class="sxs-lookup"><span data-stu-id="02761-p110">MEMO columns can also be defined to store data in a compressed format. However, there is a limitation. Only instances of MEMO columns that, when compressed, will fit within 4096 bytes or less, will be compressed. All other instances of MEMO columns will remain uncompressed. This means that within a given table, for a given MEMO column, some data may be compressed and some data may not be compressed.</span></span>

## <a name="example"></a><span data-ttu-id="02761-149">示例</span><span class="sxs-lookup"><span data-stu-id="02761-149">Example</span></span>

<span data-ttu-id="02761-150">以下示例创建一个名为 ThisTable 且包含两个文本字段的新表。</span><span class="sxs-lookup"><span data-stu-id="02761-150">This example creates a new table called ThisTable with two text fields.</span></span>

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

<span data-ttu-id="02761-151">本例创建一个名为 MyTable 的新表，该表包含两个文本字段、一个"日期/时间"字段以及一个包含这三个字段的唯一索引。</span><span class="sxs-lookup"><span data-stu-id="02761-151">This example creates a new table called MyTable with two text fields, a Date/Time field, and a unique index made up of all three fields.</span></span>

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

<span data-ttu-id="02761-p111">以下示例创建一个具有两个文本字段和一个 **Integer** 字段的新表。SSN 字段是主键。</span><span class="sxs-lookup"><span data-stu-id="02761-p111">This example creates a new table with two text fields and an **Integer** field. The SSN field is the primary key.</span></span>

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
