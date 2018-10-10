---
title: SELECT 语句 (Microsoft Access SQL)
TOCTitle: SELECT Statement (Microsoft Access SQL)
ms:assetid: a5c9da94-5f9e-0fc0-767a-4117f38a5ef3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821148(v=office.15)
ms:contentKeyID: 48546837
ms.date: 09/18/2015
mtps_version: v=office.15
dev_langs:
- sql
ms.openlocfilehash: ae7a63a3fe7647dde117db80a52e2322b9af75b9
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466230"
---
# <a name="select-statement-microsoft-access-sql"></a>SELECT 语句 (Microsoft Access SQL)

**适用于：** Access 2013 |Office 2013

指示 Microsoft Access 数据库引擎将数据库中的信息作为一组记录返回。

## <a name="syntax"></a>语法

选择\[*谓词*\] { \*  | *表*。\* |  \[*表*。\] *field1* \[作为*alias1* \] \[， \[*表*。\] *field2* \[作为*和 alias2* \] \[，...\] \]} FROM *tableexpression* \[，...\] \[IN *externaldatabase* \] \[其中... \]\[的组... \]\[HAVING... \]\[的 ORDER BY... \]\[与 OWNERACCESS OPTION\]

SELECT 语句包含以下部分：

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
<td><p><em>predicate</em></p></td>
<td><p>下列谓词之一：<a href="https://msdn.microsoft.com/library/ff195711(v=office.15)">ALL、DISTINCT、DISTINCTROW 或 TOP</a>。可以使用谓词来限定返回记录的数量。如果没有指定谓词，则默认值为 ALL。  </p></td>
</tr>
<tr class="even">
<td><p><em>*</em></p></td>
<td><p>指定选择指定表中的所有字段。</p></td>
</tr>
<tr class="odd">
<td><p><em>table</em></p></td>
<td><p>表的名称，该表包含从中选择记录的字段。</p></td>
</tr>
<tr class="even">
<td><p><em>field1</em>、<em>field2</em></p></td>
<td><p>字段名，这些字段包含了要检索的数据。如果包括多个字段，将按它们的排列顺序对其进行检索。</p></td>
</tr>
<tr class="odd">
<td><p><em>alias1</em> 和 <em>alias2</em></p></td>
<td><p>用作列标题的名称，不是 <em>table</em> 中的原始列名。</p></td>
</tr>
<tr class="even">
<td><p><em>tableexpression</em></p></td>
<td><p>表名称，其中包含要检索的数据。</p></td>
</tr>
<tr class="odd">
<td><p><em>externaldatabase</em></p></td>
<td><p>如果当前数据库中不包含<em>tableexpression</em>中的表的数据库的名称。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

若要执行此项操作，Microsoft® Jet 数据库引擎会搜索指定的表，并提取选定的列，再选择符合条件的行，然后按指定的顺序对得到的行进行排序或分组。

SELECT 语句不会更改数据库中的数据。

SELECT 通常是 SQL 语句中的第一个词。大多数 SQL 语句都是 SELECT 或 [SELECT...INTO](select-into-statement-microsoft-access-sql.md) 语句。

SELECT 语句最简化的语法为：

SELECT *fields* FROM*表*

可以通过星号 (\*) 来选择表中所有的字段。以下的示例选择在 Employees 表中的所有字段：

```sql
SELECT * FROM Employees;
```

如果一个字段名包括于 FROM 子句内的多个表中，请在该字段前面加上表名和 **.** （圆点）号。在下面的示例中，Department 字段同时存在于 Employees 表和 Supervisors 表中。SQL 语句从 Employees 表中选择出部门并从 Supervisors 表中选择出主管名：

```sql
SELECT Employees.Department, Supervisors.SupvName 
FROM Employees INNER JOIN Supervisors 
WHERE Employees.Department = Supervisors.Department;
```

创建 **Recordset** 对象时，Microsoft Jet 数据库引擎将使用表的字段名作为 **Recordset** 对象中的 **Field** 对象名。如果需要其他字段名或者名称不适合用来生成该字段的表达式，请使用 AS 保留字。以下示例使用标题 Birth 来命名生成的 **Recordset** 对象中的返回 **Field** 对象：

```sql
SELECT BirthDate 
AS Birth FROM Employees;
```

只要使用的聚合函数或查询返回的是不明确的或重复的 **Field** 对象名称，就必须使用 AS 子句为该 **Field** 对象另外提供一个替代名称。下面的示例使用标题 HeadCount 来命名在结果 **Recordset** 对象中的返回 **Field** 对象：

```sql
SELECT COUNT(EmployeeID)
AS HeadCount FROM Employees;
```

可以在 SELECT 语句中使用其他子句进一步约束和组织所返回的数据。有关详细信息，请参阅相应子句的帮助主题。

**链接提供** [UtterAccess](https://www.utteraccess.com)社区。 UtterAccess 是主要的 Microsoft Access Wiki 和帮助论坛。

- [SQL 到 VBA 格式化程序](https://www.utteraccess.com/forum/sql-vba-formatter-t1165308.html)

- [查看定义范围内的记录](https://www.utteraccess.com/wiki/index.php/records_within_a_defined_range)

## <a name="example"></a>示例

下面的一些示例假定 Employees 表中存在一个假想的 Salary 字段。请注意，该字段实际并不存在于罗斯文数据库的 Employees 表中。

本示例创建一个动态集类型**Recordset** ，基于的 SQL 语句中的 Employees 表中选择的所有记录的 LastName 和 FirstName 字段。 调用 EnumFields 过程，打印到**调试**窗口的**Recordset**对象的内容。

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

以下示例计算 PostalCode 字段中有条目的记录数，并将返回的字段命名为 Tally。

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

以下示例显示雇员数以及平均薪水和最高薪水。

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

**Sub**过程 EnumFields 从调用过程传递**Recordset**对象。 过程然后格式，并打印到**调试**窗口的**Recordset**的字段。 该变量是所需的打印的字段宽度。 某些字段可能被截断。

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




