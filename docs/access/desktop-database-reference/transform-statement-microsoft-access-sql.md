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
ms.openlocfilehash: 16b88f2cf441802c6246425d5bb7bb2efb71a679
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25861216"
---
# <a name="transform-statement-microsoft-access-sql"></a>TRANSFORM 语句 (Microsoft Access SQL)

**适用于**： Access 2013 |Office 2013

创建交叉表查询。

## <a name="syntax"></a>语法

TRANSFORM *aggfunctionselectstatement* PIVOT *pivotfield* \[IN (*value1*\[， *value2*\[，...\]\])\]

TRANSFORM 语句包含以下部分：

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
<td><p><em>aggfunction</em></p></td>
<td><p>对所选数据进行计算的 <a href="sql-aggregate-functions-sql.md">SQL 聚合函数</a>。</p></td>
</tr>
<tr class="even">
<td><p><em>selectstatement</em></p></td>
<td><p><a href="select-statement-microsoft-access-sql.md">SELECT</a> 语句。</p></td>
</tr>
<tr class="odd">
<td><p><em>pivotfield</em></p></td>
<td><p>希望用于创建查询结果集中列标题的字段或表达式。</p></td>
</tr>
<tr class="even">
<td><p><em>value1</em>、<em>value2</em></p></td>
<td><p>用于创建列标题的固定值。</p></td>
</tr>
</tbody>
</table>

## <a name="remarks"></a>说明

使用交叉表查询汇总数据时，将从作为列标题的指定字段或表达式中选择值，以便能够以一种比使用选择查询更紧凑的方式来查看数据。

TRANSFORM 是可选的，但如果包括它，则应为 SQL 字符串中的第一个语句。它在指定作为行标题的字段的 SELECT 语句之前，在指定行分组方法的 [GROUP BY](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/group-by-clause-microsoft-access-sql) 子句之前。您也可以包含其他子句（例如。指定其他选择或排序条件的 [WHERE](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/where-clause-microsoft-access-sql)）。还可以在交叉表查询中使用子查询作为谓词，特别是在 WHERE 子句中。

*pivotfield* 中返回的值作为查询结果集中的列标题。例如，在交叉表查询中如果依据月销售量来透视销售数据，将会创建 12 个列。可以约束 *pivotfield* 以便从可选 IN 子句中所列出的固定值（*value1*，*value2*）内选择标题。也可以包含固定值用于没有数据来创建其他列的情况。

## <a name="example"></a>示例

以下示例使用 SQL TRANSFORM 子句创建交叉表查询，以显示每个雇员在 1994 年的每个日历季度完成的订单数。运行此过程需要使用 SQLTRANSFORMOutput 函数。

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

以下示例使用 SQL TRANSFORM 子句创建一个稍微复杂的交叉表查询，以显示每个雇员在 1994 年的每个日历季度所完成的订单的总金额（美元）。运行此过程需要使用 SQLTRANSFORMOutput 函数。

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
