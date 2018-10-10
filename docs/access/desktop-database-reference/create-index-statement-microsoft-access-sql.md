---
title: CREATE INDEX 语句 (Microsoft Access SQL)
TOCTitle: CREATE INDEX Statement (Microsoft Access SQL)
ms:assetid: c5919ef4-a08d-df06-7078-5331adbcb45c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823109(v=office.15)
ms:contentKeyID: 48547612
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277562
f1_categories:
- Office.Version=v15
ms.openlocfilehash: ab501348d19ad8577bf1a55a3f37c6c3923381b1
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465913"
---
# <a name="create-index-statement-microsoft-access-sql"></a><span data-ttu-id="96f49-102">CREATE INDEX 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="96f49-102">CREATE INDEX Statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="96f49-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="96f49-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="96f49-104">对现有表创建一个新索引。</span><span class="sxs-lookup"><span data-stu-id="96f49-104">Creates a new index on an existing table.</span></span>

> [!NOTE]
> <span data-ttu-id="96f49-p101">[!注释] 对于非 Microsoft Access 数据库引擎的数据库，Microsoft Access 数据库引擎不支持使用 CREATE INDEX 语句（除了对 ODBC 链接表创建伪索引外）或者任何数据定义语言 (DDL) 语句。可以改用 DAO Create 方法。有关详细信息，请参阅"注解"部分。</span><span class="sxs-lookup"><span data-stu-id="96f49-p101">For non-Microsoft Access atabse engine databases, the Microsoft Access database engine does not support the use of CREATE INDEX (except to create a pseudo index on an ODBC linked table) or any of the data definition language (DDL) statements. Use the DAO Create methods instead. For more information see the Remarks section.</span></span>

## <a name="syntax"></a><span data-ttu-id="96f49-108">语法</span><span class="sxs-lookup"><span data-stu-id="96f49-108">Syntax</span></span>

<span data-ttu-id="96f49-109">创建\[唯一\]索引*索引*ON*表*(*域* \[ASC |DESC\]\[，*字段* \[ASC |DESC\]，...\]) \[WITH {主 |不允许 NULL |忽略 NULL}\]</span><span class="sxs-lookup"><span data-stu-id="96f49-109">CREATE \[ UNIQUE \] INDEX *index* ON *table* (*field* \[ASC|DESC\]\[, *field* \[ASC|DESC\], …\]) \[WITH { PRIMARY | DISALLOW NULL | IGNORE NULL }\]</span></span>

<span data-ttu-id="96f49-110">CREATE INDEX 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="96f49-110">The CREATE INDEX statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="96f49-111">部分</span><span class="sxs-lookup"><span data-stu-id="96f49-111">Part</span></span></p></th>
<th><p><span data-ttu-id="96f49-112">说明</span><span class="sxs-lookup"><span data-stu-id="96f49-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96f49-113"><em>index</em></span><span class="sxs-lookup"><span data-stu-id="96f49-113"><em>index</em></span></span></p></td>
<td><p><span data-ttu-id="96f49-114">将要创建的索引的名称。</span><span class="sxs-lookup"><span data-stu-id="96f49-114">The name of the index to be created.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96f49-115"><em>table</em></span><span class="sxs-lookup"><span data-stu-id="96f49-115"><em>table</em></span></span></p></td>
<td><p><span data-ttu-id="96f49-116">将包含该索引的现有表的名称。</span><span class="sxs-lookup"><span data-stu-id="96f49-116">The name of the existing table that will contain the index.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96f49-117"><em>field</em></span><span class="sxs-lookup"><span data-stu-id="96f49-117"><em>field</em></span></span></p></td>
<td><p><span data-ttu-id="96f49-p102">要索引的字段的名称。若要创建单字段索引，请在表名后面的圆括号里列出字段名称。若要创建多字段索引，请列出每一个将要包含在索引中的字段的名称。若要创建降序索引，请使用 DESC 保留字；否则，索引假定为升序。</span><span class="sxs-lookup"><span data-stu-id="96f49-p102">The name of the field or fields to be indexed. To create a single-field index, list the field name in parentheses following the table name. To create a multiple-field index, list the name of each field to be included in the index. To create descending indexes, use the DESC reserved word; otherwise, indexes are assumed to be ascending.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="96f49-122">注解</span><span class="sxs-lookup"><span data-stu-id="96f49-122">Remarks</span></span>

<span data-ttu-id="96f49-123">若要禁止在不同记录的被索引字段中的值重复，请使用 UNIQUE 保留字。</span><span class="sxs-lookup"><span data-stu-id="96f49-123">To prohibit duplicate values in the indexed field or fields of different records, use the UNIQUE reserved word.</span></span>

<span data-ttu-id="96f49-p103">在可选的 WITH 子句中可以实施数据有效性规则。您可以：</span><span class="sxs-lookup"><span data-stu-id="96f49-p103">In the optional WITH clause you can enforce data validation rules. You can:</span></span>

- <span data-ttu-id="96f49-126">使用 DISALLOW NULL 选项，以禁止在新记录的被索引字段中出现 Null 条目。</span><span class="sxs-lookup"><span data-stu-id="96f49-126">Prohibit Null entries in the indexed field or fields of new records by using the DISALLOW NULL option.</span></span>

- <span data-ttu-id="96f49-127">使用 IGNORE NULL 选项，以防止被索引字段中含有 **NULL** 值的记录被包含在索引中。</span><span class="sxs-lookup"><span data-stu-id="96f49-127">Prevent records with **Null** values in the indexed field or fields from being included in the index by using the IGNORE NULL option.</span></span>

- <span data-ttu-id="96f49-p104">使用 PRIMARY 保留字，将被索引字段指定为主键。这意味着该键是唯一的，所以可以省略 UNIQUE 保留字。</span><span class="sxs-lookup"><span data-stu-id="96f49-p104">Designate the indexed field or fields as the primary key by using the PRIMARY reserved word. This implies that the key is unique, so you can omit the UNIQUE reserved word.</span></span>

<span data-ttu-id="96f49-p105">可以使用 CREATE INDEX 对 ODBC 数据源（如 Microsoft® SQL Server）中不包含索引的链接表创建伪索引。创建伪索引不需要得到授权或者访问远程服务器，并且远程数据库不知情也不会受伪索引的影响。可以对链接表或本地表使用相同的语法。对通常为只读的表创建伪索引会很有用。</span><span class="sxs-lookup"><span data-stu-id="96f49-p105">You can use CREATE INDEX to create a pseudo index on a linked table in an ODBC data source, such as Microsoft® SQL Server™, that does not already have an index. You do not need permission or access to the remote server to create a pseudo index, and the remote database is unaware of and unaffected by the pseudo index. You use the same syntax for both linked and native tables. Creating a pseudo-index on a table that would ordinarily be read-only can be especially useful.</span></span>

<span data-ttu-id="96f49-134">也可以使用 [ALTER TABLE](alter-table-statement-microsoft-access-sql.md) 语句向表中添加单字段索引或多字段索引，还可以使用 ALTER TABLE 语句或 [DROP](drop-statement-microsoft-access-sql.md) 语句删除用 ALTER TABLE 或 CREATE INDEX 语句创建的索引。</span><span class="sxs-lookup"><span data-stu-id="96f49-134">You can also use the [ALTER TABLE](alter-table-statement-microsoft-access-sql.md) statement to add a single- or multiple-field index to a table, and you can use the ALTER TABLE statement or the [DROP](drop-statement-microsoft-access-sql.md) statement to remove an index created with ALTER TABLE or CREATE INDEX.</span></span>

> [!NOTE]
> <span data-ttu-id="96f49-135">[!注释] 如果对已包含主键的表创建一个新索引，请不要使用 PRIMARY 保留字；如果这样做，就会产生错误。</span><span class="sxs-lookup"><span data-stu-id="96f49-135">Do not use the PRIMARY reserved word when you create a new index on a table that already has a primary key; if you do, an error occurs.</span></span>

## <a name="example"></a><span data-ttu-id="96f49-136">示例</span><span class="sxs-lookup"><span data-stu-id="96f49-136">Example</span></span>

<span data-ttu-id="96f49-137">以下示例创建一个包含 Employees 表中的 Home Phone 和 Extension 字段的索引。</span><span class="sxs-lookup"><span data-stu-id="96f49-137">This example creates an index consisting of the fields Home Phone and Extension in the Employees table.</span></span>

```vb
    Sub CreateIndexX1() 
     
        Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Create the NewIndex index on the Employees table. 
        dbs.Execute "CREATE INDEX NewIndex ON Employees " _ 
            & "(HomePhone, Extension);" 
     
        dbs.Close 
     
    End Sub 
```

<br/>

<span data-ttu-id="96f49-p106">本例使用 CustomerID 字段在 Customers 表上创建索引。CustomerID 字段中任何两个记录的数据都不能相同，并且不允许存在 Null 值。</span><span class="sxs-lookup"><span data-stu-id="96f49-p106">This example creates an index on the Customers table using the CustomerID field. No two records can have the same data in the CustomerID field, and no Null values are allowed.</span></span>

```vb
    Sub CreateIndexX2() 
     
        Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Create a unique index, CustID, on the  
        ' CustomerID field. 
        dbs.Execute "CREATE UNIQUE INDEX CustID " _ 
            & "ON Customers (CustomerID) " _ 
            & "WITH DISALLOW NULL;" 
     
        dbs.Close 
     
    End Sub
```
