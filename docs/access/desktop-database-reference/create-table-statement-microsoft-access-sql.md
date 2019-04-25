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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295357"
---
# <a name="create-table-statement-microsoft-access-sql"></a><span data-ttu-id="3e89b-102">CREATE TABLE 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="3e89b-102">CREATE TABLE Statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="3e89b-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="3e89b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3e89b-104">创建一个新表。</span><span class="sxs-lookup"><span data-stu-id="3e89b-104">Creates a new table.</span></span>

> [!NOTE]
> <span data-ttu-id="3e89b-105">Microsoft Access 数据库引擎不支持将 CREATE TABLE 或任何 DDL 语句与非 Microsoft Access 数据库引擎数据库结合使用。</span><span class="sxs-lookup"><span data-stu-id="3e89b-105">The Microsoft Access database engine does not support the use of CREATE TABLE, or any of the DDL statements, with non-Microsoft Access database engine databases.</span></span> <span data-ttu-id="3e89b-106">请改用 DAO **Create** 方法。</span><span class="sxs-lookup"><span data-stu-id="3e89b-106">Use the DAO Create methods instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="3e89b-107">语法</span><span class="sxs-lookup"><span data-stu-id="3e89b-107">Syntax</span></span>

<span data-ttu-id="3e89b-108">CREATE \[TEMPORARY\] TABLE *table* (*field1 type* \[(*size*)\] \[NOT NULL\] \[WITH COMPRESSION | WITH COMP\] \[*index1*\] \[, *field2* *type* \[(*size*)\] \[NOT NULL\] \[*index2*\] \[, …\]\] \[, CONSTRAINT *multifieldindex* \[, …\]\])</span><span class="sxs-lookup"><span data-stu-id="3e89b-108">CREATE \[TEMPORARY\] TABLE *table* (*field1 type* \[(*size*)\] \[NOT NULL\] \[WITH COMPRESSION | WITH COMP\] \[*index1*\] \[, *field2* *type* \[(*size*)\] \[NOT NULL\] \[*index2*\] \[, …\]\] \[, CONSTRAINT *multifieldindex* \[, …\]\])</span></span>

<span data-ttu-id="3e89b-109">CREATE TABLE 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="3e89b-109">The CREATE TABLE statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="3e89b-110">Part</span><span class="sxs-lookup"><span data-stu-id="3e89b-110">Part</span></span></p></th>
<th><p><span data-ttu-id="3e89b-111">说明</span><span class="sxs-lookup"><span data-stu-id="3e89b-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e89b-112"><em>table</em></span><span class="sxs-lookup"><span data-stu-id="3e89b-112"><em>table</em></span></span></p></td>
<td><p><span data-ttu-id="3e89b-113">要创建的表的名称。</span><span class="sxs-lookup"><span data-stu-id="3e89b-113">The name of the table to be created.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e89b-114"><em>field1</em>, <em>field2</em></span><span class="sxs-lookup"><span data-stu-id="3e89b-114"><em>field1</em>  ,  <em>field2</em></span></span></p></td>
<td><p><span data-ttu-id="3e89b-p102">字段或要在新表中创建的字段的名称。必须至少创建一个字段。</span><span class="sxs-lookup"><span data-stu-id="3e89b-p102">The name of field or fields to be created in the new table. You must create at least one field.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e89b-117"><em>type</em></span><span class="sxs-lookup"><span data-stu-id="3e89b-117"><em>type</em></span></span></p></td>
<td><p><span data-ttu-id="3e89b-118">新表中<em>字段</em>的数据类型。</span><span class="sxs-lookup"><span data-stu-id="3e89b-118">The data type of <em>field</em> in the new table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e89b-119"><em>size</em></span><span class="sxs-lookup"><span data-stu-id="3e89b-119"><em>size</em></span></span></p></td>
<td><p><span data-ttu-id="3e89b-120">以字符为单位的字段大小（仅限于文本和二进制字段）。</span><span class="sxs-lookup"><span data-stu-id="3e89b-120">The field size in characters (Text and Binary fields only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e89b-121"><em>index1</em>, <em>index2</em></span><span class="sxs-lookup"><span data-stu-id="3e89b-121"><em>index1</em>, <em>index2</em></span></span></p></td>
<td><p><span data-ttu-id="3e89b-122">定义单字段索引的 CONSTRAINT 子句。</span><span class="sxs-lookup"><span data-stu-id="3e89b-122">A CONSTRAINT clause defining a single-field index.</span></span> <span data-ttu-id="3e89b-123">有关如何创建此索引的详细信息，请参阅 <a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT 子句</a>。</span><span class="sxs-lookup"><span data-stu-id="3e89b-123">For more information on how to create this index, see <a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT Clause</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e89b-124"><em>multifieldindex</em></span><span class="sxs-lookup"><span data-stu-id="3e89b-124"><em>multifieldindex</em></span></span></p></td>
<td><p><span data-ttu-id="3e89b-125">定义多字段索引的 CONSTRAINT 子句。</span><span class="sxs-lookup"><span data-stu-id="3e89b-125">A CONSTRAINT clause defining a multiple-field index.</span></span> <span data-ttu-id="3e89b-126">有关如何创建此索引的详细信息，请参阅 <a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT 子句</a>。</span><span class="sxs-lookup"><span data-stu-id="3e89b-126">For more information on how to create this index, see <a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT Clause</a>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="3e89b-127">说明</span><span class="sxs-lookup"><span data-stu-id="3e89b-127">Remarks</span></span>

<span data-ttu-id="3e89b-128">使用 CREATE TABLE 语句定义新表以及其字段和字段约束。</span><span class="sxs-lookup"><span data-stu-id="3e89b-128">Use the CREATE TABLE statement to define a new table and its fields and field constraints.</span></span> <span data-ttu-id="3e89b-129">如果对字段指定了 NOT NULL，则新记录必须包含该字段的有效数据。</span><span class="sxs-lookup"><span data-stu-id="3e89b-129">If NOT NULL is specified for a field, then new records are required to have valid data in that field.</span></span>

<span data-ttu-id="3e89b-p106">CONSTRAINT 子句可建立对字段的各种约束，并且可用于建立主键。也可以使用 [CREATE INDEX](create-index-statement-microsoft-access-sql.md) 语句对现有表创建主键或其他索引。</span><span class="sxs-lookup"><span data-stu-id="3e89b-p106">A CONSTRAINT clause establishes various restrictions on a field, and can be used to establish the primary key. You can also use the [CREATE INDEX](create-index-statement-microsoft-access-sql.md) statement to create a primary key or additional indexes on existing tables.</span></span>

<span data-ttu-id="3e89b-p107">可以对单个字段或在应用于单个字段或多字段的命名 CONSTRAINT 的命名 CONSTRAINT 子句中使用 NOT NULL。但是，仅可以对字段应用一次 NOT NULL 限制。尝试多次应用此限制将造成运行时错误。</span><span class="sxs-lookup"><span data-stu-id="3e89b-p107">You can use NOT NULL on a single field or within a named CONSTRAINT clause that applies to either a single field or to a multiple-field named CONSTRAINT. However, you can apply the NOT NULL restriction only once to a field. Attempting to apply this restriction more than once results in a run-time error.</span></span>

<span data-ttu-id="3e89b-135">创建 TEMPORARY 表时，该表只能在创建它的会话中可见。</span><span class="sxs-lookup"><span data-stu-id="3e89b-135">When a TEMPORARY table is created it is visible only within the session in which it was created.</span></span> <span data-ttu-id="3e89b-136">在会话终止后它会被自动删除。</span><span class="sxs-lookup"><span data-stu-id="3e89b-136">It is automatically deleted when the session is terminated.</span></span> <span data-ttu-id="3e89b-137">临时表可由多名用户访问。</span><span class="sxs-lookup"><span data-stu-id="3e89b-137">Temporary tables can be accessed by more than one user.</span></span>

<span data-ttu-id="3e89b-138">WITH COMPRESSION 特性仅能与 CHARACTER 和 MEMO（也称为 TEXT）数据类型和其同义词结合使用。</span><span class="sxs-lookup"><span data-stu-id="3e89b-138">The WITH COMPRESSION attribute can be used only with the CHARACTER and MEMO (also known as TEXT) data types and their synonyms.</span></span>

<span data-ttu-id="3e89b-139">由于 Unicode 字符表示格式的更改，因此已为 CHARACTER 列添加了 WITH COMPRESSION 特性。</span><span class="sxs-lookup"><span data-stu-id="3e89b-139">The WITH COMPRESSION attribute was added for CHARACTER columns because of the change to the Unicode character representation format.</span></span> <span data-ttu-id="3e89b-140">Unicode 字符一律需要要求每个字符具有两个字节。</span><span class="sxs-lookup"><span data-stu-id="3e89b-140">Unicode characters uniformly require two bytes for each character.</span></span> <span data-ttu-id="3e89b-141">对于主要包含字符数据的现有 Microsoft Jet 数据库，这可能意味着当转换为 Microsoft Access 数据库引擎格式时，数据库文件大小几乎会增大到两倍。</span><span class="sxs-lookup"><span data-stu-id="3e89b-141">For existing Microsoft® Jet databases that contain predominately character data, this could mean that the database file would nearly double in size when converted to the Microsoft Access database engine format.</span></span> <span data-ttu-id="3e89b-142">然而，许多以前称为单字节字符集 (SBCS) 的字符集的 Unicode 表示法能够被轻易地压缩成为单字节。</span><span class="sxs-lookup"><span data-stu-id="3e89b-142">However, Unicode representation of many character sets, those formerly denoted as Single-Byte Character Sets (SBCS) can easily be compressed to a single byte.</span></span> <span data-ttu-id="3e89b-143">如果使用此属性定义 CHARACTER 列，存储数据时将自动压缩数据，从列中检索数据时则将自动解压。</span><span class="sxs-lookup"><span data-stu-id="3e89b-143">If you define a CHARACTER column with this attribute, data will automatically be compressed as it is stored and uncompressed when retrieved from the column.</span></span>

<span data-ttu-id="3e89b-p110">也可以定义 MEMO 列以压缩格式存储数据。但是，此操作有一个限制。只有在压缩后的大小在 4096 字节内或更少的 MEMO 列的实例将会被压缩。MEMO 列的其他所有实例将保留为未压缩状态。这意味着在给定表内对于给定的 MEMO 列，一些数据可能会被压缩，而一些则不会被压缩。</span><span class="sxs-lookup"><span data-stu-id="3e89b-p110">MEMO columns can also be defined to store data in a compressed format. However, there is a limitation. Only instances of MEMO columns that, when compressed, will fit within 4096 bytes or less, will be compressed. All other instances of MEMO columns will remain uncompressed. This means that within a given table, for a given MEMO column, some data may be compressed and some data may not be compressed.</span></span>

## <a name="example"></a><span data-ttu-id="3e89b-149">示例</span><span class="sxs-lookup"><span data-stu-id="3e89b-149">Example</span></span>

<span data-ttu-id="3e89b-150">以下示例创建一个名为 ThisTable 且包含两个文本字段的新表。</span><span class="sxs-lookup"><span data-stu-id="3e89b-150">This example creates a new table called ThisTable with two text fields.</span></span>

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

<span data-ttu-id="3e89b-151">本例创建一个名为 MyTable 的新表，该表包含两个文本字段、一个"日期/时间"字段以及一个包含这三个字段的唯一索引。</span><span class="sxs-lookup"><span data-stu-id="3e89b-151">This example creates a new table called MyTable with two text fields, a Date/Time field, and a unique index made up of all three fields.</span></span>

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

<span data-ttu-id="3e89b-p111">以下示例创建一个具有两个文本字段和一个 **Integer** 字段的新表。SSN 字段是主键。</span><span class="sxs-lookup"><span data-stu-id="3e89b-p111">This example creates a new table with two text fields and an **Integer** field. The SSN field is the primary key.</span></span>

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
