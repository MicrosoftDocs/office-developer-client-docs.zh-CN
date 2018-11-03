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
ms.openlocfilehash: 4beb013b09ce136d6ffa7558225e01fae80da645
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25937090"
---
# <a name="create-table-statement-microsoft-access-sql"></a>CREATE TABLE 语句 (Microsoft Access SQL)

**适用于**： Access 2013、 Office 2013

新建一个表。

> [!NOTE]
> [!注释] Microsoft Access 数据库引擎不支持对非 Microsoft Access 数据库引擎数据库使用 CREATE TABLE 或者任何 DDL 语句。 而是使用 DAO**创建**方法。

## <a name="syntax"></a>语法

创建\[临时\]表*表*(*field1 type* \[（*大小*）\] \[NOT NULL\] \[WITH COMPRESSION |与 COMP\] \[ *index1* \] \[， *field2* *类型* \[（*大小*）\] \[NOT NULL\] \[ *index2* \] \[，...\] \] \[，CONSTRAINT *multifieldindex* \[，...\]\])

CREATE TABLE 语句包含以下部分：

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
<td><p>要创建的表的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>field1</em>、<em>field2</em></p></td>
<td><p>要在新表中创建的字段的名称。必须创建至少一个字段。</p></td>
</tr>
<tr class="odd">
<td><p><em>类型</em></p></td>
<td><p>在新表中 <em>field</em> 的数据类型。</p></td>
</tr>
<tr class="even">
<td><p><em>size</em></p></td>
<td><p>以字符为单位的字段大小（仅限于文本和二进制字段）。</p></td>
</tr>
<tr class="odd">
<td><p><em>index1</em>、<em>index2</em></p></td>
<td><p>CONSTRAINT 子句定义单字段索引。 有关如何创建此索引的详细信息，请参阅<a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT 子句</a>。</p></td>
</tr>
<tr class="even">
<td><p><em>multifieldindex</em></p></td>
<td><p>CONSTRAINT 子句定义多字段索引。 有关如何创建此索引的详细信息，请参阅<a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT 子句</a>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

使用 CREATE TABLE 语句可以定义一个新表及其字段和字段约束。 如果没有为字段指定 NULL，新记录所需的字段中具有有效的数据。

CONSTRAINT 子句可建立对字段的各种约束，并且可用于建立主键。也可以使用 [CREATE INDEX](create-index-statement-microsoft-access-sql.md) 语句对现有表创建主键或其他索引。

在一个字段或一个名为 CONSTRAINT 的子句中可以使用 NOT NULL，该子句既可应用于单字段索引，也可应用于名为 CONSTRAINT 的多字段索引。但是，NOT NULL 限制一次只能应用于一个字段。多次应用此限制将导致运行时错误。

创建一个临时表后，它是可见的仅在其中创建会话中。 当会话终止时，该表会被自动删除。 临时表能够被多个用户访问。

WITH COMPRESSION 属性只能用于 CHARACTER 和 MEMO（也叫做 TEXT）数据类型以及它们的同义词。

由于 Unicode 字符表示格式发生的更改，属性 WITH COMPRESSION 被添加到 CHARACTER 列上。 Unicode 字符中每个字符一律需要两个字节。 对于包含主要用于字符数据的现有 Microsoft Jet 数据库，这可能意味着几乎双数据库文件会转换为 Microsoft Access 数据库引擎格式时的大小。 但是，可以很容易压缩的许多字符集，以前表示为单字节字符设置 (SBCS)，Unicode 表示形式，成一个字节。 如果使用该属性定义 CHARACTER 列，在该列中存储数据时，数据会自动进行压缩；从该列检索数据时，数据会自动解压缩。

MEMO 列也能定义为以压缩的格式来存储数据。但是，这样做是有限制的。进行压缩时，只有 MEMO 列实例的大小在 4096 字节以内，它才会被压缩。所有其他 MEMO 列实例仍然保持为未压缩格式。这意味着，对于指定表中的一个给定的 MEMO 列，一些数据可能被压缩，而一些数据则可能是未压缩的。

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
