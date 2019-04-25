---
title: SELECT 语句 (Microsoft Access SQL)
TOCTitle: SELECT statement (Microsoft Access SQL)
ms:assetid: a5c9da94-5f9e-0fc0-767a-4117f38a5ef3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821148(v=office.15)
ms:contentKeyID: 48546837
ms.date: 10/18/2018
mtps_version: v=office.15
dev_langs:
- sql
localization_priority: Priority
ms.openlocfilehash: 962e425c2c69511b6d7770fb03e954588249cf2a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314635"
---
# <a name="select-statement-microsoft-access-sql"></a><span data-ttu-id="ed279-102">SELECT 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="ed279-102">SELECT Statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="ed279-103">**适用于**：Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="ed279-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ed279-104">指示 Microsoft Access 数据库引擎将数据库中的信息作为一组记录返回。</span><span class="sxs-lookup"><span data-stu-id="ed279-104">Instructs the Microsoft Access database engine to return information from the database as a set of records.</span></span>

## <a name="syntax"></a><span data-ttu-id="ed279-105">语法</span><span class="sxs-lookup"><span data-stu-id="ed279-105">Syntax</span></span>

<span data-ttu-id="ed279-106">SELECT \[*predicate*\] { \* | *table*.\* | \[*table*.\]*field1* \[AS *alias1*\] \[, \[*table*.\]*field2* \[AS *alias2*\] \[, …\]\]} FROM *tableexpression* \[, …\] \[IN *externaldatabase*\] \[WHERE…</span><span class="sxs-lookup"><span data-stu-id="ed279-106">SELECT \[*predicate*\] { \* | *table*.\* | \[*table*.\]*field1* \[AS *alias1*\] \[, \[*table*.\]*field2* \[AS *alias2*\] \[, …\]\]} FROM *tableexpression* \[, …\] \[IN *externaldatabase*\] \[WHERE…</span></span> <span data-ttu-id="ed279-107">\] \[GROUP BY…</span><span class="sxs-lookup"><span data-stu-id="ed279-107">GROUP BY</span></span> <span data-ttu-id="ed279-108">\] \[HAVING…</span><span class="sxs-lookup"><span data-stu-id="ed279-108">HAVING</span></span> <span data-ttu-id="ed279-109">\] \[ORDER BY…</span><span class="sxs-lookup"><span data-stu-id="ed279-109">ORDER BY</span></span> <span data-ttu-id="ed279-110">\] \[WITH OWNERACCESS OPTION\]</span><span class="sxs-lookup"><span data-stu-id="ed279-110">\] \[WITH OWNERACCESS OPTION\]</span></span>

<span data-ttu-id="ed279-111">SELECT 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="ed279-111">The SELECT statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ed279-112">部分</span><span class="sxs-lookup"><span data-stu-id="ed279-112">Part</span></span></p></th>
<th><p><span data-ttu-id="ed279-113">说明</span><span class="sxs-lookup"><span data-stu-id="ed279-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed279-114"><em>谓词</em></span><span class="sxs-lookup"><span data-stu-id="ed279-114"><em>predicate</em></span></span></p></td>
<td><p><span data-ttu-id="ed279-p102">下列谓词之一：<a href="https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/all-distinct-distinctrow-top-predicates-microsoft-access-sql">ALL、DISTINCT、DISTINCTROW 或 TOP</a>。可以使用谓词来限定返回记录的数量。如果没有指定谓词，则默认值为 ALL。</span><span class="sxs-lookup"><span data-stu-id="ed279-p102">One of the following predicates: <a href="https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/all-distinct-distinctrow-top-predicates-microsoft-access-sql">ALL, DISTINCT, DISTINCTROW, or TOP</a>. You use the predicate to restrict the number of records returned. If none is specified, the default is ALL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><em>*</em></p></td>
<td><p><span data-ttu-id="ed279-118">指定选择指定表中的所有字段。</span><span class="sxs-lookup"><span data-stu-id="ed279-118">Specifies that all fields from the specified table or tables are selected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed279-119"><em>table</em></span><span class="sxs-lookup"><span data-stu-id="ed279-119"><em>table</em></span></span></p></td>
<td><p><span data-ttu-id="ed279-120">表的名称，该表包含从中选择记录的字段。</span><span class="sxs-lookup"><span data-stu-id="ed279-120">The name of the table containing the fields from which records are selected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed279-121"><em>field1</em>、<em>field2</em></span><span class="sxs-lookup"><span data-stu-id="ed279-121"><em>field1</em>  ,  <em>field2</em></span></span></p></td>
<td><p><span data-ttu-id="ed279-p103">字段名，这些字段包含了要检索的数据。如果包括多个字段，将按它们的排列顺序对其进行检索。</span><span class="sxs-lookup"><span data-stu-id="ed279-p103">The names of the fields containing the data you want to retrieve. If you include more than one field, they are retrieved in the order listed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed279-124"><em>alias1</em> 和 <em>alias2</em></span><span class="sxs-lookup"><span data-stu-id="ed279-124"><em>alias1</em>  ,  <em>alias2</em></span></span></p></td>
<td><p><span data-ttu-id="ed279-125">用作列标题的名称，不是 <em>table</em> 中的原始列名。</span><span class="sxs-lookup"><span data-stu-id="ed279-125">The names to use as column headers instead of the original column names in <em>table</em>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed279-126"><em>tableexpression</em></span><span class="sxs-lookup"><span data-stu-id="ed279-126"><em>tableexpression</em></span></span></p></td>
<td><p><span data-ttu-id="ed279-127">表名称，其中包含要检索的数据。</span><span class="sxs-lookup"><span data-stu-id="ed279-127">The name of the table or tables containing the data you want to retrieve.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed279-128"><em>externaldatabase</em></span><span class="sxs-lookup"><span data-stu-id="ed279-128"><em>externaldatabase</em></span></span></p></td>
<td><p><span data-ttu-id="ed279-129">如果 <em>tableexpression</em> 中的表不在当前数据库中，则使用该参数指定该数据库名。</span><span class="sxs-lookup"><span data-stu-id="ed279-129">The name of the database containing the tables in <em>tableexpression</em> if they are not in the current database.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="ed279-130">说明</span><span class="sxs-lookup"><span data-stu-id="ed279-130">Remarks</span></span>

<span data-ttu-id="ed279-131">若要执行此项操作，Microsoft Jet 数据库引擎会搜索指定的一个或多个表，提取选定的列，选择符合条件的行，然后按指定的顺序对得到的行进行排序或分组。</span><span class="sxs-lookup"><span data-stu-id="ed279-131">To perform this operation, the Microsoft® Jet database engine searches the specified table or tables, extracts the chosen columns, selects rows that meet the criterion, and sorts or groups the resulting rows into the order specified.</span></span>

<span data-ttu-id="ed279-132">SELECT 语句不会更改数据库中的数据。</span><span class="sxs-lookup"><span data-stu-id="ed279-132">SELECT statements do not change data in the database.</span></span>

<span data-ttu-id="ed279-p104">SELECT 通常是 SQL 语句中的第一个词。大多数 SQL 语句都是 SELECT 或 [SELECT...INTO](select-into-statement-microsoft-access-sql.md) 语句。</span><span class="sxs-lookup"><span data-stu-id="ed279-p104">SELECT is usually the first word in an SQL statement. Most SQL statements are either SELECT or [SELECT…INTO](select-into-statement-microsoft-access-sql.md) statements.</span></span>

<span data-ttu-id="ed279-135">SELECT 语句最简化的语法为：</span><span class="sxs-lookup"><span data-stu-id="ed279-135">The minimum syntax for a SELECT statement is:</span></span>

<span data-ttu-id="ed279-136">SELECT *fields* FROM *table*</span><span class="sxs-lookup"><span data-stu-id="ed279-136">SELECT *fields* FROM *table*</span></span>

<span data-ttu-id="ed279-p105">可以通过星号 (\*) 来选择表中所有的字段。以下的示例选择在 Employees 表中的所有字段：</span><span class="sxs-lookup"><span data-stu-id="ed279-p105">You can use an asterisk (\*) to select all fields in a table. The following example selects all of the fields in the Employees table:</span></span>

```sql
SELECT * FROM Employees;
```

<span data-ttu-id="ed279-p106">如果一个字段名包括于 FROM 子句内的多个表中，请在该字段前面加上表名和 **.**（圆点）号。在下面的示例中，Department 字段同时存在于 Employees 表和 Supervisors 表中。SQL 语句从 Employees 表中选择出部门并从 Supervisors 表中选择出主管名：</span><span class="sxs-lookup"><span data-stu-id="ed279-p106">If a field name is included in more than one table in the FROM clause, precede it with the table name and the **.** (dot) operator. In the following example, the Department field is in both the Employees table and the Supervisors table. The SQL statement selects departments from the Employees table and supervisor names from the Supervisors table:</span></span>

```sql
SELECT Employees.Department, Supervisors.SupvName 
FROM Employees INNER JOIN Supervisors 
WHERE Employees.Department = Supervisors.Department;
```

<span data-ttu-id="ed279-p107">创建 **Recordset** 对象时，Microsoft Jet 数据库引擎将使用表的字段名作为 **Recordset** 对象中的 **Field** 对象名。如果需要其他字段名或者名称不适合用来生成该字段的表达式，请使用 AS 保留字。以下示例使用标题 Birth 来命名生成的 **Recordset** 对象中的返回 **Field** 对象：</span><span class="sxs-lookup"><span data-stu-id="ed279-p107">When a **Recordset** object is created, the Microsoft Jet database engine uses the table's field name as the **Field** object name in the **Recordset** object. If you want a different field name or a name is not implied by the expression used to generate the field, use the AS reserved word. The following example uses the title Birth to name the returned **Field** object in the resulting **Recordset** object:</span></span>

```sql
SELECT BirthDate 
AS Birth FROM Employees;
```

<span data-ttu-id="ed279-p108">只要使用的聚合函数或查询返回的是不明确的或重复的 **Field** 对象名称，就必须使用 AS 子句为该 **Field** 对象另外提供一个替代名称。下面的示例使用标题 HeadCount 来命名在结果 **Recordset** 对象中的返回 **Field** 对象：</span><span class="sxs-lookup"><span data-stu-id="ed279-p108">Whenever you use aggregate functions or queries that return ambiguous or duplicate **Field** object names, you must use the AS clause to provide an alternate name for the **Field** object. The following example uses the title HeadCount to name the returned **Field** object in the resulting **Recordset** object:</span></span>

```sql
SELECT COUNT(EmployeeID)
AS HeadCount FROM Employees;
```

<span data-ttu-id="ed279-p109">可以在 SELECT 语句中使用其他子句进一步约束和组织所返回的数据。有关详细信息，请参阅相应子句的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="ed279-p109">You can use the other clauses in a SELECT statement to further restrict and organize your returned data. For more information, see the Help topic for the clause you are using.</span></span>

<span data-ttu-id="ed279-150">**链接提供方：**[UtterAccess](https://www.utteraccess.com) 社区。</span><span class="sxs-lookup"><span data-stu-id="ed279-150">**Links provided by** the [UtterAccess](https://www.utteraccess.com) community.</span></span> <span data-ttu-id="ed279-151">UtterAccess 是主要的 Microsoft Access Wiki 和帮助论坛。</span><span class="sxs-lookup"><span data-stu-id="ed279-151">UtterAccess is the premier Microsoft Access wiki and help forum.</span></span>

- [<span data-ttu-id="ed279-152">SQL 到 VBA 格式化程序</span><span class="sxs-lookup"><span data-stu-id="ed279-152">SQL to VBA Formatter</span></span>](https://www.utteraccess.com/forum/sql-vba-formatter-t1165308.html)

- [<span data-ttu-id="ed279-153">查看定义范围内的记录</span><span class="sxs-lookup"><span data-stu-id="ed279-153">Viewing Records Within A Defined Range</span></span>](https://www.utteraccess.com/wiki/index.php/records_within_a_defined_range)

## <a name="example"></a><span data-ttu-id="ed279-154">示例</span><span class="sxs-lookup"><span data-stu-id="ed279-154">Example</span></span>

<span data-ttu-id="ed279-p111">下面的一些示例假定 Employees 表中存在一个假想的 Salary 字段。请注意，该字段实际并不存在于罗斯文数据库的 Employees 表中。</span><span class="sxs-lookup"><span data-stu-id="ed279-p111">Some of the following examples assume the existence of a hypothetical Salary field in an Employees table. Note that this field does not actually exist in the Northwind database Employees table.</span></span>

<span data-ttu-id="ed279-p112">本例基于 SQL 语句创建一个动态集类型的 **Recordset**，该语句选择 Employees 表中所有记录的 LastName 和 FirstName 字段。它调用 EnumFields 过程，该过程将 **Recordset** 对象的内容显示到调试窗口\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ed279-p112">This example creates a dynaset-type **Recordset** based on an SQL statement that selects the LastName and FirstName fields of all records in the Employees table. It calls the EnumFields procedure, which prints the contents of a **Recordset** object to the **Debug** window.</span></span>

```sql
    Sub SelectX1() 
     
        Dim dbs As Database, rst As Recordset 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Select the last name and first name values of all  
        ' records in the Employees table. 
        Set rst = dbs.OpenRecordset("SELECT LastName, " _ 
            & "FirstName FROM Employees;") 
     
        ' Populate the recordset. 
        rst.MoveLast 
     
        ' Call EnumFields to print the contents of the 
        ' Recordset. 
        EnumFields rst,12 
     
        dbs.Close 
     
    End Sub
```

<br/>

<span data-ttu-id="ed279-159">以下示例计算 PostalCode 字段中有条目的记录数，并将返回的字段命名为 Tally。</span><span class="sxs-lookup"><span data-stu-id="ed279-159">This example counts the number of records that have an entry in the PostalCode field and names the returned field Tally.</span></span>

```sql
    Sub SelectX2() 
     
        Dim dbs As Database, rst As Recordset 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Count the number of records with a PostalCode  
        ' value and return the total in the Tally field. 
        Set rst = dbs.OpenRecordset("SELECT Count " _ 
            & "(PostalCode) AS Tally FROM Customers;") 
     
        ' Populate the Recordset. 
        rst.MoveLast 
     
        ' Call EnumFields to print the contents of  
        ' the Recordset. Specify field width = 12. 
        EnumFields rst, 12 
     
        dbs.Close 
     
    End Sub 
```

<br/>

<span data-ttu-id="ed279-160">以下示例显示雇员数以及平均薪水和最高薪水。</span><span class="sxs-lookup"><span data-stu-id="ed279-160">This example shows the number of employees and the average and maximum salaries.</span></span>

```sql
    Sub SelectX3() 
     
        Dim dbs As Database, rst As Recordset 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Count the number of employees, calculate the  
        ' average salary, and return the highest salary. 
        Set rst = dbs.OpenRecordset("SELECT Count (*) " _ 
            & "AS TotalEmployees, Avg(Salary) " _ 
            & "AS AverageSalary, Max(Salary) " _ 
            & "AS MaximumSalary FROM Employees;") 
     
        ' Populate the Recordset. 
        rst.MoveLast 
     
        ' Call EnumFields to print the contents of 
        ' the Recordset. Pass the Recordset object and 
        ' desired field width. 
        EnumFields rst, 17 
     
        dbs.Close 
     
    End Sub 
```

<br/>

<span data-ttu-id="ed279-p113">The **Sub** procedure EnumFields is passed a **Recordset** object from the calling procedure. The procedure then formats and prints the fields of the **Recordset** to the **Debug** window. The variable is the desired printed field width. Some fields may be truncated.</span><span class="sxs-lookup"><span data-stu-id="ed279-p113">The **Sub** procedure EnumFields is passed a **Recordset** object from the calling procedure. The procedure then formats and prints the fields of the **Recordset** to the **Debug** window. The variable is the desired printed field width. Some fields may be truncated.</span></span>

```sql
    Sub EnumFields(rst As Recordset, intFldLen As Integer) 
     
        Dim lngRecords As Long, lngFields As Long 
        Dim lngRecCount As Long, lngFldCount As Long 
        Dim strTitle As String, strTemp As String 
     
        ' Set the lngRecords variable to the number of 
        ' records in the Recordset. 
        lngRecords = rst.RecordCount 
     
        ' Set the lngFields variable to the number of 
        ' fields in the Recordset. 
        lngFields = rst.Fields.Count 
     
        Debug.Print "There are " & lngRecords _ 
            & " records containing " & lngFields _ 
            & " fields in the recordset." 
        Debug.Print 
     
        ' Form a string to print the column heading. 
        strTitle = "Record  " 
        For lngFldCount = 0 To lngFields - 1 
            strTitle = strTitle _ 
            & Left(rst.Fields(lngFldCount).Name _ 
            & Space(intFldLen), intFldLen) 
        Next lngFldCount     
     
        ' Print the column heading. 
        Debug.Print strTitle 
        Debug.Print 
     
        ' Loop through the Recordset; print the record 
        ' number and field values. 
        rst.MoveFirst 
     
        For lngRecCount = 0 To lngRecords - 1 
            Debug.Print Right(Space(6) & _ 
                Str(lngRecCount), 6) & "  "; 
     
            For lngFldCount = 0 To lngFields - 1 
                ' Check for Null values. 
                If IsNull(rst.Fields(lngFldCount)) Then 
                    strTemp = "<null>" 
                Else 
                    ' Set strTemp to the field contents.  
                    Select Case _ 
                        rst.Fields(lngFldCount).Type 
                        Case 11 
                            strTemp = "" 
                        Case dbText, dbMemo 
                            strTemp = _ 
                                rst.Fields(lngFldCount) 
                        Case Else 
                            strTemp = _ 
                                str(rst.Fields(lngFldCount)) 
                    End Select 
                End If 
     
                Debug.Print Left(strTemp _  
                    & Space(intFldLen), intFldLen); 
            Next lngFldCount 
     
            Debug.Print 
     
            rst.MoveNext 
     
        Next lngRecCount 
     
    End Sub 
```




