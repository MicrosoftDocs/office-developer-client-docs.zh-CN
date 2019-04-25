---
title: TRANSFORM 语句 (Microsoft Access SQL)
TOCTitle: TRANSFORM statement (Microsoft Access SQL)
ms:assetid: 419770b1-c833-959d-a84d-56c68764799f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192901(v=office.15)
ms:contentKeyID: 48544455
ms.date: 10/18/2018
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277581
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: 9abe91d4ce6996a725e246da6922015d15a8bd39
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314040"
---
# <a name="transform-statement-microsoft-access-sql"></a><span data-ttu-id="4930c-102">TRANSFORM 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="4930c-102">TRANSFORM Statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="4930c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="4930c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4930c-104">创建交叉表查询。</span><span class="sxs-lookup"><span data-stu-id="4930c-104">Creates a crosstab query.</span></span>

## <a name="syntax"></a><span data-ttu-id="4930c-105">语法</span><span class="sxs-lookup"><span data-stu-id="4930c-105">Syntax</span></span>

<span data-ttu-id="4930c-106">TRANSFORM *aggfunctionselectstatement* PIVOT *pivotfield* \[IN (*value1*\[, *value2*\[, …\]\])\]</span><span class="sxs-lookup"><span data-stu-id="4930c-106">TRANSFORM aggfunction selectstatement
    PIVOT pivotfield [IN (value1[, value2[, …]])]</span></span>

<span data-ttu-id="4930c-107">TRANSFORM 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="4930c-107">The TRANSFORM statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4930c-108">Part</span><span class="sxs-lookup"><span data-stu-id="4930c-108">Part</span></span></p></th>
<th><p><span data-ttu-id="4930c-109">说明</span><span class="sxs-lookup"><span data-stu-id="4930c-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4930c-110"><em>aggfunction</em></span><span class="sxs-lookup"><span data-stu-id="4930c-110"><em>aggfunction</em></span></span></p></td>
<td><p><span data-ttu-id="4930c-111">对所选数据进行计算的 <a href="sql-aggregate-functions-sql.md">SQL 聚合函数</a>。</span><span class="sxs-lookup"><span data-stu-id="4930c-111">An <a href="sql-aggregate-functions-sql.md">SQL aggregate function</a> that operates on the selected data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4930c-112"><em>selectstatement</em></span><span class="sxs-lookup"><span data-stu-id="4930c-112"><em>selectstatement</em></span></span></p></td>
<td><p><span data-ttu-id="4930c-113"><a href="select-statement-microsoft-access-sql.md">SELECT</a> 语句。</span><span class="sxs-lookup"><span data-stu-id="4930c-113">A <a href="select-statement-microsoft-access-sql.md">SELECT</a> statement.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4930c-114"><em>pivotfield</em></span><span class="sxs-lookup"><span data-stu-id="4930c-114"><em>PivotField</em></span></span></p></td>
<td><p><span data-ttu-id="4930c-115">希望用于创建查询结果集中列标题的字段或表达式。</span><span class="sxs-lookup"><span data-stu-id="4930c-115">The field or expression you want to use to create column headings in the query's result set.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4930c-116"><em>value1</em>, <em>value2</em></span><span class="sxs-lookup"><span data-stu-id="4930c-116"><em>value1</em>, <em>value2</em></span></span></p></td>
<td><p><span data-ttu-id="4930c-117">用于创建列标题的固定值。</span><span class="sxs-lookup"><span data-stu-id="4930c-117">Fixed values used to create column headings.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="remarks"></a><span data-ttu-id="4930c-118">说明</span><span class="sxs-lookup"><span data-stu-id="4930c-118">Remarks</span></span>

<span data-ttu-id="4930c-119">使用交叉表查询汇总数据时，将从作为列标题的指定字段或表达式中选择值，以便能够以一种比使用选择查询更紧凑的方式来查看数据。</span><span class="sxs-lookup"><span data-stu-id="4930c-119">When you summarize data using a crosstab query, you select values from specified fields or expressions as column headings so you can view data in a more compact format than with a select query.</span></span>

<span data-ttu-id="4930c-p101">TRANSFORM 是可选的，但如果包括它，则应为 SQL 字符串中的第一个语句。它在指定作为行标题的字段的 SELECT 语句之前，在指定行分组方法的 [GROUP BY](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/group-by-clause-microsoft-access-sql) 子句之前。您也可以包含其他子句（例如。指定其他选择或排序条件的 [WHERE](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/where-clause-microsoft-access-sql)）。还可以在交叉表查询中使用子查询作为谓词，特别是在 WHERE 子句中。</span><span class="sxs-lookup"><span data-stu-id="4930c-p101">TRANSFORM is optional but when included is the first statement in an SQL string. It precedes a SELECT statement that specifies the fields used as row headings and a [GROUP BY](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/group-by-clause-microsoft-access-sql) clause that specifies row grouping. Optionally, you can include other clauses, such as [WHERE](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/where-clause-microsoft-access-sql), that specify additional selection or sorting criteria. You can also use subqueries as predicates — specifically, those in the WHERE clause — in a crosstab query.</span></span>

<span data-ttu-id="4930c-p102">
            \*pivotfield\* 中返回的值用作查询结果集中的列标题。例如，在交叉表查询中切换销售月份的销售图表将创建 12 列。可将 \*pivotfield\* 限制为基于可选 IN 子句中列出的固定值（\*value1\*、\*value2\*）创建标题。还可以包含不存在数据的固定值以创建其他列。</span><span class="sxs-lookup"><span data-stu-id="4930c-p102">The values returned in *pivotfield* are used as column headings in the query's result set. For example, pivoting the sales figures on the month of the sale in a crosstab query would create 12 columns. You can restrict *pivotfield* to create headings from fixed values (*value1*, *value2* ) listed in the optional IN clause. You can also include fixed values for which no data exists to create additional columns.</span></span>

## <a name="example"></a><span data-ttu-id="4930c-128">示例</span><span class="sxs-lookup"><span data-stu-id="4930c-128">Example</span></span>

<span data-ttu-id="4930c-p103">以下示例使用 SQL TRANSFORM 子句创建交叉表查询，以显示每个雇员在 1994 年的每个日历季度完成的订单数。运行此过程需要使用 SQLTRANSFORMOutput 函数。</span><span class="sxs-lookup"><span data-stu-id="4930c-p103">This example uses the SQL TRANSFORM clause to create a crosstab query showing the number of orders taken by each employee for each calendar quarter of 1994. The SQLTRANSFORMOutput function is required for this procedure to run.</span></span>

```vb
    Sub TransformX1() 
     
        Dim dbs As Database 
        Dim strSQL As String 
        Dim qdfTRANSFORM As QueryDef 
     
        strSQL = "PARAMETERS prmYear SHORT; TRANSFORM " _ 
            & "Count(OrderID) " _ 
            & "SELECT FirstName & "" "" & LastName AS " _ 
            & "FullName FROM Employees INNER JOIN Orders " _ 
            & "ON Employees.EmployeeID = " _ 
            & "Orders.EmployeeID WHERE DatePart " _ 
            & "(""yyyy"", OrderDate) = [prmYear] " 
       
           strSQL = strSQL & "GROUP BY FirstName & " _ 
            & """ "" & LastName " _ 
            & "ORDER BY FirstName & "" "" & LastName " _ 
            & "PIVOT DatePart(""q"", OrderDate)" 
         
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        Set qdfTRANSFORM = dbs.CreateQueryDef _ 
            ("", strSQL) 
         
        SQLTRANSFORMOutput qdfTRANSFORM, 1994 
         
        dbs.Close 
     
    End Sub
```

<br/>

<span data-ttu-id="4930c-p104">以下示例使用 SQL TRANSFORM 子句创建一个稍微复杂的交叉表查询，以显示每个雇员在 1994 年的每个日历季度所完成的订单的总金额（美元）。运行此过程需要使用 SQLTRANSFORMOutput 函数。</span><span class="sxs-lookup"><span data-stu-id="4930c-p104">This example uses the SQL TRANSFORM clause to create a slightly more complex crosstab query showing the total dollar amount of orders taken by each employee for each calendar quarter of 1994. The SQLTRANSFORMOutput function is required for this procedure to run.</span></span>

```vb
    Sub TransformX2() 
     
        Dim dbs As Database 
        Dim strSQL As String 
        Dim qdfTRANSFORM As QueryDef 
     
        strSQL = "PARAMETERS prmYear SMALLINT; TRANSFORM " _ 
            & "Sum(Subtotal) SELECT FirstName & "" """ _ 
            & "& LastName AS FullName " _ 
            & "FROM Employees INNER JOIN " _ 
            & "(Orders INNER JOIN [Order Subtotals] " _ 
            & "ON Orders.OrderID = " _ 
            & "[Order Subtotals].OrderID) " _ 
            & "ON Employees.EmployeeID = " _ 
            & "Orders.EmployeeID WHERE DatePart" _ 
            & "(""yyyy"", OrderDate) = [prmYear] " 
        
           strSQL = strSQL & "GROUP BY FirstName & "" """ _ 
            & "& LastName " _ 
            & "ORDER BY FirstName & "" "" & LastName " _ 
            & "PIVOT DatePart(""q"",OrderDate)"         
             
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        Set qdfTRANSFORM = dbs.CreateQueryDef _ 
            ("", strSQL) 
         
        SQLTRANSFORMOutput qdfTRANSFORM, 1994 
         
        dbs.Close 
     
    End Sub 
     
    Function SQLTRANSFORMOutput(qdfTemp As QueryDef, _ 
        intYear As Integer) 
         
        Dim rstTRANSFORM As Recordset 
        Dim fldLoop As Field 
        Dim booFirst As Boolean 
     
        qdfTemp.PARAMETERS!prmYear = intYear 
        Set rstTRANSFORM = qdfTemp.OpenRecordset() 
         
        Debug.Print qdfTemp.SQL 
        Debug.Print 
        Debug.Print , , "Quarter" 
     
        With rstTRANSFORM 
            booFirst = True 
            For Each fldLoop In .Fields 
                If booFirst = True Then 
                    Debug.Print fldLoop.Name 
                    Debug.Print , ; 
                    booFirst = False 
                Else 
                    Debug.Print , fldLoop.Name; 
                End If 
            Next fldLoop 
            Debug.Print 
             
            Do While Not .EOF 
                booFirst = True 
                For Each fldLoop In .Fields 
                    If booFirst = True Then 
                        Debug.Print fldLoop 
                        Debug.Print , ; 
                        booFirst = False 
                    Else 
                        Debug.Print , fldLoop; 
                    End If 
                Next fldLoop 
                Debug.Print 
                .MoveNext 
            Loop 
        End With 
         
    End Function
```
