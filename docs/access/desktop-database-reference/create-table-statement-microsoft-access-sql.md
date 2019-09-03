---
title: CREATE TABLE 语句 (Microsoft Access SQL)
TOCTitle: CREATE TABLE statement (Microsoft Access SQL)
ms:assetid: fc45d36e-6e43-c030-5016-cca8bb1379fe
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837200(v=office.15)
ms:contentKeyID: 48548888
ms.date: 09/03/2019
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277563
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: dfcbbd55f2d20589849f63f260d40b507c8639f1
ms.sourcegitcommit: b27eedbc4538f78ee15134bf19abbc319605c3bc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2019
ms.locfileid: "36706171"
---
# <a name="create-table-statement-microsoft-access-sql"></a>CREATE TABLE 语句 (Microsoft Access SQL)

**适用于**：Access 2013、Office 2013

创建一个新表。

> [!NOTE]
> Microsoft Access 数据库引擎不支持将 CREATE TABLE 或任何 DDL 语句与非 Microsoft Access 数据库引擎数据库结合使用。 请改用 DAO **Create** 方法。

## <a name="syntax"></a>语法

CREATE \[TEMPORARY\] TABLE *table* (*field1 type* \[(*size*)\] \[NOT NULL\] \[WITH COMPRESSION | WITH COMP\] \[*index1*\] \[, *field2* *type* \[(*size*)\] \[NOT NULL\] \[*index2*\] \[, …\]\] \[, CONSTRAINT *multifieldindex* \[, …\]\])

CREATE TABLE 语句包含以下部分：

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
<td><p><em>table</em></p></td>
<td><p>要创建的表的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>field1</em>, <em>field2</em></p></td>
<td><p>字段或要在新表中创建的字段的名称。必须至少创建一个字段。</p></td>
</tr>
<tr class="odd">
<td><p><em>type</em></p></td>
<td><p>新表中<em>字段</em>的数据类型。</p></td>
</tr>
<tr class="even">
<td><p><em>size</em></p></td>
<td><p>以字符为单位的字段大小（仅限于文本和二进制字段）。</p></td>
</tr>
<tr class="odd">
<td><p><em>index1</em>, <em>index2</em></p></td>
<td><p>定义单字段索引的 CONSTRAINT 子句。 有关如何创建此索引的详细信息，请参阅 <a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT 子句</a>。</p></td>
</tr>
<tr class="even">
<td><p><em>multifieldindex</em></p></td>
<td><p>定义多字段索引的 CONSTRAINT 子句。 有关如何创建此索引的详细信息，请参阅 <a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT 子句</a>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

使用 CREATE TABLE 语句定义新表以及其字段和字段约束。 如果对字段指定了 NOT NULL，则新记录必须包含该字段的有效数据。

CONSTRAINT 子句可建立对字段的各种约束，并且可用于建立主键。也可以使用 [CREATE INDEX](create-index-statement-microsoft-access-sql.md) 语句对现有表创建主键或其他索引。

可以对单个字段或在应用于单个字段或多字段的命名 CONSTRAINT 的命名 CONSTRAINT 子句中使用 NOT NULL。但是，仅可以对字段应用一次 NOT NULL 限制。尝试多次应用此限制将造成运行时错误。

创建 TEMPORARY 表时，该表只能在创建它的会话中可见。 在会话终止后它会被自动删除。 临时表可由多名用户访问。

WITH COMPRESSION 特性仅能与 CHARACTER 和 MEMO（也称为 TEXT）数据类型和其同义词结合使用。

由于 Unicode 字符表示格式的更改，因此已为 CHARACTER 列添加了 WITH COMPRESSION 特性。 Unicode 字符一律需要要求每个字符具有两个字节。 对于主要包含字符数据的现有 Microsoft Jet 数据库，这可能意味着当转换为 Microsoft Access 数据库引擎格式时，数据库文件大小几乎会增大到两倍。 然而，许多以前称为单字节字符集 (SBCS) 的字符集的 Unicode 表示法能够被轻易地压缩成为单字节。 如果使用此属性定义 CHARACTER 列，存储数据时将自动压缩数据，从列中检索数据时则将自动解压。

也可以定义 MEMO 列以压缩格式存储数据。但是，此操作有一个限制。只有在压缩后的大小在 4096 字节内或更少的 MEMO 列的实例将会被压缩。MEMO 列的其他所有实例将保留为未压缩状态。这意味着在给定表内对于给定的 MEMO 列，一些数据可能会被压缩，而一些则不会被压缩。

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

以下示例创建一个名为 `~~Kitsch'n Sync` 的新表，该表演示所有不同的字段和索引类型。 “自动编号”字段是主键。

```vb
    Sub CreateTableX6()
        On Error Resume Next
        Application.CurrentDb.Execute "Drop Table [~~Kitsch'n Sync];"
        On Error GoTo 0
        
        'This example uses ADODB instead of the DAO shown in the previous
        'ones because DAO does not support the DECIMAL and GUID data types
        Dim con As ADODB.Connection
        Set con = CurrentProject.Connection
        con.Execute "" _
            & "CREATE TABLE [~~Kitsch'n Sync](" _
                & " [Auto]                  COUNTER" _
                & ",[Byte]                  BYTE" _
                & ",[Integer]               SMALLINT" _
                & ",[Long]                  INTEGER" _
                & ",[Single]                REAL" _
                & ",[Double]                FLOAT" _
                & ",[Decimal]               DECIMAL(18,5)" _
                & ",[Currency]              MONEY" _
                & ",[ShortText]             CHAR" _
                & ",[LongText]              MEMO" _
                & ",[PlaceHolder1]          MEMO" _
                & ",[DateTime]              DATETIME" _
                & ",[YesNo]                 BIT" _
                & ",[OleObject]             IMAGE" _
                & ",[ReplicationID]         UNIQUEIDENTIFIER" _
                & ",[Required]              INTEGER NOT NULL" _
                & ",[Unicode Compression]   MEMO WITH COMP" _
                & ",[Indexed]               INTEGER" _
                & ",CONSTRAINT [PrimaryKey] PRIMARY KEY ([Auto])" _
                & ",CONSTRAINT [Unique Index] UNIQUE ([Byte],[Integer],[Long])" _
            & ");"
        con.Execute "CREATE INDEX [Single-Field Index] ON [~~Kitsch'n Sync]([Indexed]);"
        con.Execute "CREATE INDEX [Multi-Field Index] ON [~~Kitsch'n Sync]([Auto],[Required]);"
        con.Execute "CREATE INDEX [IgnoreNulls Index] ON [~~Kitsch'n Sync]([Single],[Double]) WITH IGNORE NULL;"
        con.Execute "CREATE UNIQUE INDEX [Combined Index] ON [~~Kitsch'n Sync]([ShortText],[LongText]) WITH IGNORE NULL;"
        Set con = Nothing
    
        'Add a Hyperlink Field
        Dim AllDefs As DAO.TableDefs, TblDef As DAO.TableDef, Fld As DAO.Field
        Set AllDefs = Application.CurrentDb.TableDefs
        Set TblDef = AllDefs("~~Kitsch'n Sync")
        Set Fld = TblDef.CreateField("Hyperlink", dbMemo)
        Fld.Attributes = dbHyperlinkField + dbVariableField
        Fld.OrdinalPosition = 10
        TblDef.Fields.Append Fld
        
        DoCmd.RunSQL "ALTER TABLE [~~Kitsch'n Sync] DROP COLUMN [PlaceHolder1];"
    End Sub
```
