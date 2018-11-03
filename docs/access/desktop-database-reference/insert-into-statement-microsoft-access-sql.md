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
ms.openlocfilehash: c20701e9863d72a9308679965425b74c9f9818ac
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25937636"
---
# <a name="insert-into-statement-microsoft-access-sql"></a><span data-ttu-id="c0ca2-102">INSERT INTO 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="c0ca2-102">INSERT INTO statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="c0ca2-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c0ca2-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c0ca2-p101">将一个或多个记录添加到表中。该语句称为追加查询。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-p101">Adds a record or multiple records to a table. This is referred to as an append query.</span></span>

## <a name="syntax"></a><span data-ttu-id="c0ca2-106">语法</span><span class="sxs-lookup"><span data-stu-id="c0ca2-106">Syntax</span></span>

### <a name="multiple-record-append-query"></a><span data-ttu-id="c0ca2-107">多记录追加查询</span><span class="sxs-lookup"><span data-stu-id="c0ca2-107">Multiple-record append query</span></span>

<span data-ttu-id="c0ca2-108">插入到*目标* \[(*field1*\[， *field2*\[，...\] \])\] \[IN *externaldatabase* \]选择\[*源*。\] *field1*\[， *field2*\[，...\] FROM *tableexpression*</span><span class="sxs-lookup"><span data-stu-id="c0ca2-108">INSERT INTO *target* \[(*field1*\[, *field2*\[, …\]\])\] \[IN *externaldatabase*\] SELECT \[*source*.\]*field1*\[, *field2*\[, …\] FROM *tableexpression*</span></span>

### <a name="single-record-append-query"></a><span data-ttu-id="c0ca2-109">单记录追加查询</span><span class="sxs-lookup"><span data-stu-id="c0ca2-109">Single-record append query</span></span>

<span data-ttu-id="c0ca2-110">插入到*目标* \[(*field1*\[， *field2*\[，...\] \])\]值 (*value1*\[， *value2*\[，...\])</span><span class="sxs-lookup"><span data-stu-id="c0ca2-110">INSERT INTO *target* \[(*field1*\[, *field2*\[, …\]\])\] VALUES (*value1*\[, *value2*\[, …\])</span></span>

<span data-ttu-id="c0ca2-111">INSERT INTO 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="c0ca2-111">The INSERT INTO statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c0ca2-112">部分</span><span class="sxs-lookup"><span data-stu-id="c0ca2-112">Part</span></span></p></th>
<th><p><span data-ttu-id="c0ca2-113">说明</span><span class="sxs-lookup"><span data-stu-id="c0ca2-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0ca2-114"><em>target</em></span><span class="sxs-lookup"><span data-stu-id="c0ca2-114"><em>target</em></span></span></p></td>
<td><p><span data-ttu-id="c0ca2-115">要追加记录的表或查询的名称。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-115">The name of the table or query to append records to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0ca2-116"><em>field1</em>、<em>field2</em></span><span class="sxs-lookup"><span data-stu-id="c0ca2-116"><em>field1</em>, <em>field2</em></span></span></p></td>
<td><p><span data-ttu-id="c0ca2-117">向其中追加数据的字段的名称（如果在 <em>target</em> 参数之后），或获取其中数据的字段的名称（如果在 <em>source</em> 参数之后）。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-117">Names of the fields to append data to, if following a <em>target</em> argument, or the names of fields to obtain data from, if following a <em>source</em> argument.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0ca2-118"><em>externaldatabase</em></span><span class="sxs-lookup"><span data-stu-id="c0ca2-118"><em>externaldatabase</em></span></span></p></td>
<td><p><span data-ttu-id="c0ca2-p102">外部数据库的路径。有关路径的说明，请参阅 <a href="https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/in-clause-microsoft-access-sql">IN</a> 子句。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-p102">The path to an external database. For a description of the path, see the <a href="https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/in-clause-microsoft-access-sql">IN</a> clause.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0ca2-121"><em>source</em></span><span class="sxs-lookup"><span data-stu-id="c0ca2-121"><em>source</em></span></span></p></td>
<td><p><span data-ttu-id="c0ca2-122">要复制其中记录的表或查询的名称。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-122">The name of the table or query to copy records from.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0ca2-123"><em>tableexpression</em></span><span class="sxs-lookup"><span data-stu-id="c0ca2-123"><em>tableexpression</em></span></span></p></td>
<td><p><span data-ttu-id="c0ca2-p103">作为插入记录来源的表的名称。该参数可以是单个表名或者是从 <a href="inner-join-operation-microsoft-access-sql.md">INNER JOIN</a>、<a href="left-join-right-join-operations-microsoft-access-sql.md">LEFT JOIN</a> 或 <a href="left-join-right-join-operations-microsoft-access-sql.md">RIGHT JOIN</a> 操作或保存的查询产生的组合结果。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-p103">The name of the table or tables from which records are inserted. This argument can be a single table name or a compound resulting from an <a href="inner-join-operation-microsoft-access-sql.md">INNER JOIN</a>, <a href="left-join-right-join-operations-microsoft-access-sql.md">LEFT JOIN</a>, or <a href="left-join-right-join-operations-microsoft-access-sql.md">RIGHT JOIN</a> operation or a saved query.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0ca2-126"><em>value1</em>、<em>value2</em></span><span class="sxs-lookup"><span data-stu-id="c0ca2-126"><em>value1</em>, <em>value2</em></span></span></p></td>
<td><p><span data-ttu-id="c0ca2-p104">要插入新记录特定字段中的值。每个值将插入到与该值在列表中的位置相对应的字段内：<em>value1</em> 将插入到新记录的 <em>field1</em> 字段，<em>value2</em> 插入到 <em>field2</em> 字段等等。这些值必须用逗号分隔，并且用引号 (' ') 引起来。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-p104">The values to insert into the specific fields of the new record. Each value is inserted into the field that corresponds to the value's position in the list: <em>value1</em> is inserted into <em>field1</em> of the new record, <em>value2</em> into <em>field2</em>, and so on. You must separate values with a comma, and enclose text fields in quotation marks (' ').</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="c0ca2-130">说明</span><span class="sxs-lookup"><span data-stu-id="c0ca2-130">Remarks</span></span>

<span data-ttu-id="c0ca2-p105">通过如上所述的单记录追加查询语法，可以使用 INSERT INTO 语句向表中追加单个记录。在这种情形下，代码要指定每个记录字段的名称和值。必须指定每一个将被赋值的记录字段，并且要给出该字段的值。如果没有指定每个字段的值，则在缺少值的列中插入默认值或 **Null** 值。记录将追加到表的末尾。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-p105">You can use the INSERT INTO statement to add a single record to a table using the single-record append query syntax as shown above. In this case, your code specifies the name and value for each field of the record. You must specify each of the fields of the record that a value is to be assigned to and a value for that field. When you do not specify each field, the default value or **Null** is inserted for missing columns. Records are added to the end of the table.</span></span>

<span data-ttu-id="c0ca2-136">通过如上所示的多字段追加查询语法的 SELECT ...</span><span class="sxs-lookup"><span data-stu-id="c0ca2-136">You can also use INSERT INTO to append a set of records from another table or query by using the SELECT …</span></span> <span data-ttu-id="c0ca2-137">FROM 子句，还可以使用 INSERT INTO 追加一组来自其他表或查询的记录。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-137">FROM clause as shown above in the multiple-record append query syntax.</span></span> <span data-ttu-id="c0ca2-138">在这种情况下，SELECT 子句指定要追加到指定的*目标*表的字段。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-138">In this case, the SELECT clause specifies the fields to append to the specified *target* table.</span></span>

<span data-ttu-id="c0ca2-139">*源*或*目标*表可以指定表或查询。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-139">The *source* or *target* table may specify a table or a query.</span></span> <span data-ttu-id="c0ca2-140">如果指定了查询，Microsoft Access 数据库引擎会将记录追加到查询指定的任何表或所有表中。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-140">If a query is specified, the Microsoft Access database engine appends records to any and all tables specified by the query.</span></span>

<span data-ttu-id="c0ca2-141">INSERT INTO 是可选的，但是如果包括它，应将它置于 [SELECT](select-statement-microsoft-access-sql.md) 语句前面。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-141">INSERT INTO is optional but when included, precedes the [SELECT](select-statement-microsoft-access-sql.md) statement.</span></span>

<span data-ttu-id="c0ca2-142">如果目标表中包含主键，请确保追加到主键字段中的值是唯一的、非 **Null** 的；否则，Microsoft Access 数据库引擎不会追加这些记录。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-142">If your destination table contains a primary key, make sure you append unique, non-**Null** values to the primary key field or fields; if you do not, the Microsoft Access database engine will not append the records.</span></span>

<span data-ttu-id="c0ca2-p108">如果将一个自动编号字段记录追加到一个表中，并且希望对该追加的记录重新编号，那么不要在查询语句中包含自动编号字段。如果希望保持字段的原始值，请务必在查询语句中包含自动编号字段。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-p108">If you append records to a table with an AutoNumber field and you want to renumber the appended records, do not include the AutoNumber field in your query. Do include the AutoNumber field in the query if you want to retain the original values from the field.</span></span>

<span data-ttu-id="c0ca2-145">通过 IN 子句可以将记录追加到其他数据库的表中。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-145">Use the IN clause to append records to a table in another database.</span></span>

<span data-ttu-id="c0ca2-146">若要新建表，请使用 [SELECT... INTO](select-into-statement-microsoft-access-sql.md) 语句来创建一个生成表查询。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-146">To create a new table, use the [SELECT… INTO](select-into-statement-microsoft-access-sql.md) statement instead to create a make-table query.</span></span>

<span data-ttu-id="c0ca2-147">若要在运行追加查询之前找出将要追加哪些记录，可以先执行使用同样选择条件的选择查询并查看其结果。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-147">To find out which records will be appended before you run the append query, first execute and view the results of a select query that uses the same selection criteria.</span></span>

<span data-ttu-id="c0ca2-p109">追加查询把记录从一个或多个表复制到其他表中。包含所追加的记录的表不会受追加查询影响。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-p109">An append query copies records from one or more tables to another. The tables that contain the records you append are not affected by the append query.</span></span>

<span data-ttu-id="c0ca2-p110">如果不想从其他表中追加现有记录，可以通过 VALUES 子句指定每个字段在新的单个记录中的值。如果忽略了字段列表，VALUES 子句必须包括该表中每个字段的值；否则，INSERT 操作将会失败。通过附加的带有 VALUES 子句的 INSERT INTO 语句，可以创建希望得到的每一个新增记录。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-p110">Instead of appending existing records from another table, you can specify the value for each field in a single new record using the VALUES clause. If you omit the field list, the VALUES clause must include a value for every field in the table; otherwise, the INSERT operation will fail. Use an additional INSERT INTO statement with a VALUES clause for each additional record you want to create.</span></span>

<span data-ttu-id="c0ca2-153">**链接提供** [UtterAccess](https://www.utteraccess.com)社区。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-153">**Links provided by** the [UtterAccess](https://www.utteraccess.com) community.</span></span> <span data-ttu-id="c0ca2-154">UtterAccess 是主要的 Microsoft Access Wiki 和帮助论坛。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-154">UtterAccess is the premier Microsoft Access wiki and help forum.</span></span>

- [<span data-ttu-id="c0ca2-155">生成 for 插入/更新语句的顺序编号</span><span class="sxs-lookup"><span data-stu-id="c0ca2-155">Generating sequential numbers for INSERT/UPDATE statements</span></span>](https://www.utteraccess.com/forum/generating-sequential-num-t446039.html)

- [<span data-ttu-id="c0ca2-156">SQL 到 VBA 格式化程序</span><span class="sxs-lookup"><span data-stu-id="c0ca2-156">SQL to VBA Formatter</span></span>](https://www.utteraccess.com/forum/sql-vba-formatter-t1165308.html)

## <a name="example"></a><span data-ttu-id="c0ca2-157">示例</span><span class="sxs-lookup"><span data-stu-id="c0ca2-157">Example</span></span>

<span data-ttu-id="c0ca2-p112">本例选择假想的 New Customers 表中的所有记录并将这些记录添加到 Customers 表。如果未指定各个列，那么 SELECT 中的表列名必须与 INSERT INTO 中的表列名完全匹配。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-p112">This example selects all records in a hypothetical New Customers table and adds them to the Customers table. When individual columns are not designated, the SELECT table column names must match exactly those in the INSERT INTO table.</span></span>

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

<span data-ttu-id="c0ca2-160">以下示例在 Employees 表中创建一个新记录。</span><span class="sxs-lookup"><span data-stu-id="c0ca2-160">This example creates a new record in the Employees table.</span></span>

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

