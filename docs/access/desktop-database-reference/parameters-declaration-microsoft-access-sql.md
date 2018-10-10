---
title: PARAMETERS 声明 (Microsoft Access SQL)
TOCTitle: PARAMETERS Declaration (Microsoft Access SQL)
ms:assetid: 0dcaad68-6a5f-93dc-e62a-b82b36e1e69c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845220(v=office.15)
ms:contentKeyID: 48543230
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277577
dev_langs:
- sql
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 8ef554aab94bd5771e1df3313d04a4fbe2c383b8
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467619"
---
# <a name="parameters-declaration-microsoft-access-sql"></a>PARAMETERS 声明 (Microsoft Access SQL)


**适用于**： Access 2013 |Office 2013

声明在参数查询中的每个参数的名称和数据类型。

## <a name="syntax"></a>语法

参数*名称 datatype* \[， *name datatype* \[，...\]\]

PARAMETERS 声明包含以下部分：

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
<td><p><em>name</em></p></td>
<td><p>参数的名称。该名称被赋给 <strong>Parameter</strong> 对象的 <strong>Name</strong> 属性，并且用来在 <strong>Parameters</strong> 集合中标识该参数。可以将 <em>name</em> 作为应用程序运行查询时在对话框中显示的字符串。请用方括号 ([ ]) 将包含空格或标点的文本括起来。例如，[Low price] 和 [Begin report with which month?] 都是有效的 <em>name</em> 参数。</p></td>
</tr>
<tr class="even">
<td><p><em>数据类型</em></p></td>
<td><p>主要 <a href="sql-data-types.md">Microsoft Access SQL 数据类型</a>或其同义词之一。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

对于定期运行的查询，可以通过 PARAMETERS 声明来创建一个参数查询。参数查询能够自动处理查询条件更改。若使用参数查询，在每次查询运行时代码都需要提供参数。

PARAMETERS 声明是可选的，但如果包含它，应将它置于任何其他语句（包括 [SELECT 语句](select-statement-microsoft-access-sql.md)）之前。

如果声明包含了多个参数，请用逗号分隔它们。以下的示例里包含了两个参数：

```sql
PARAMETERS [Low price] Currency, [Beginning date] DateTime;
```

您可以使用[其中](https://msdn.microsoft.com/library/ff195245\(v=office.15\))或[HAVING](https://msdn.microsoft.com/library/ff193795\(v=office.15\))子句中的*名称*，但不是*数据类型*。 以下的示例中要求提供两个参数，然后将该条件应用于 Orders 表的记录中：

```sql
PARAMETERS [Low price] Currency, 
[Beginning date] DateTime; 
SELECT OrderID, OrderAmount
FROM Orders 
WHERE OrderAmount > [Low price] 
AND OrderDate >= [Beginning date];
```

## <a name="example"></a>示例

本示例要求用户提供职务，然后使用该职务作为查询条件。

本示例调用 EnumFields 过程，您可以在 [SELECT 语句](select-statement-microsoft-access-sql.md)示例中找到该过程。

```vb
    Sub ParametersX() 
     
        Dim dbs As Database, qdf As QueryDef 
        Dim rst As Recordset 
        Dim strSql As String, strParm As String 
        Dim strMessage As String 
        Dim intCommand As Integer 
         
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("NorthWind.mdb") 
         
        ' Define the parameters clause. 
        strParm = "PARAMETERS [Employee Title] CHAR; " 
     
        ' Define an SQL statement with the parameters 
        ' clause. 
        strSql = strParm & "SELECT LastName, FirstName, " _ 
            & "EmployeeID " _ 
            & "FROM Employees " _ 
            & "WHERE Title =[Employee Title];" 
         
        ' Create a QueryDef object based on the  
        ' SQL statement. 
        Set qdf = dbs.CreateQueryDef _ 
            ("Find Employees", strSql) 
         
        Do While True 
            strMessage = "Find Employees by Job " _ 
                & "title:" & Chr(13) _ 
                & "  Choose Job Title:" & Chr(13) _ 
                & "   1 - Sales Manager" & Chr(13) _ 
                & "   2 - Sales Representative" & Chr(13) _ 
                & "   3 - Inside Sales Coordinator" 
             
            intCommand = Val(InputBox(strMessage)) 
             
            Select Case intCommand 
                Case 1 
                    qdf("Employee Title") = _ 
                        "Sales Manager" 
                Case 2 
                    qdf("Employee Title") = _ 
                        "Sales Representative" 
                Case 3 
                    qdf("Employee Title") = _ 
                        "Inside Sales Coordinator" 
                Case Else 
                    Exit Do 
            End Select 
             
            ' Create a temporary snapshot-type Recordset. 
            Set rst = qdf.OpenRecordset(dbOpenSnapshot) 
     
            ' Populate the Recordset. 
            rst.MoveLast 
                 
            ' Call EnumFields to print the contents of the  
            ' Recordset. Pass the Recordset object and desired 
            ' field width. 
            EnumFields rst, 12 
     
        Loop 
         
        ' Delete the QueryDef because this is a 
        ' demonstration. 
        dbs.QueryDefs.Delete "Find Employees" 
         
        dbs.Close 
     
    End Sub
```
