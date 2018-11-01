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
ms.openlocfilehash: 24212ce3a29c0e30fae1dad7566ef93815f8a03f
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25876774"
---
# <a name="parameters-declaration-microsoft-access-sql"></a><span data-ttu-id="6d018-102">PARAMETERS 声明 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="6d018-102">PARAMETERS Declaration (Microsoft Access SQL)</span></span>


<span data-ttu-id="6d018-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="6d018-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6d018-104">声明在参数查询中的每个参数的名称和数据类型。</span><span class="sxs-lookup"><span data-stu-id="6d018-104">Declares the name and data type of each parameter in a parameter query.</span></span>

## <a name="syntax"></a><span data-ttu-id="6d018-105">语法</span><span class="sxs-lookup"><span data-stu-id="6d018-105">Syntax</span></span>

<span data-ttu-id="6d018-106">参数*名称 datatype* \[， *name datatype* \[，...\]\]</span><span class="sxs-lookup"><span data-stu-id="6d018-106">PARAMETERS *name datatype* \[, *name datatype* \[, …\]\]</span></span>

<span data-ttu-id="6d018-107">PARAMETERS 声明包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="6d018-107">The PARAMETERS declaration has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6d018-108">部分</span><span class="sxs-lookup"><span data-stu-id="6d018-108">Part</span></span></p></th>
<th><p><span data-ttu-id="6d018-109">说明</span><span class="sxs-lookup"><span data-stu-id="6d018-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d018-110"><em>name</em></span><span class="sxs-lookup"><span data-stu-id="6d018-110"><em>name</em></span></span></p></td>
<td><p><span data-ttu-id="6d018-p101">参数的名称。该名称被赋给 <strong>Parameter</strong> 对象的 <strong>Name</strong> 属性，并且用来在 <strong>Parameters</strong> 集合中标识该参数。可以将 <em>name</em> 作为应用程序运行查询时在对话框中显示的字符串。请用方括号 ([ ]) 将包含空格或标点的文本括起来。例如，[Low price] 和 [Begin report with which month?] 都是有效的 <em>name</em> 参数。</span><span class="sxs-lookup"><span data-stu-id="6d018-p101">The name of the parameter. Assigned to the <strong>Name</strong> property of the <strong>Parameter</strong> object and used to identify this parameter in the <strong>Parameters</strong> collection. You can use <em>name</em> as a string that is displayed in a dialog box while your application runs the query. Use brackets ([ ]) to enclose text that contains spaces or punctuation. For example, [Low price] and [Begin report with which month?] are valid <em>name</em> arguments.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d018-116"><em>数据类型</em></span><span class="sxs-lookup"><span data-stu-id="6d018-116"><em>datatype</em></span></span></p></td>
<td><p><span data-ttu-id="6d018-117">主要 <a href="sql-data-types.md">Microsoft Access SQL 数据类型</a>或其同义词之一。</span><span class="sxs-lookup"><span data-stu-id="6d018-117">One of the primary <a href="sql-data-types.md">Microsoft Access SQL data types</a> or their synonyms.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="6d018-118">说明</span><span class="sxs-lookup"><span data-stu-id="6d018-118">Remarks</span></span>

<span data-ttu-id="6d018-p102">对于定期运行的查询，可以通过 PARAMETERS 声明来创建一个参数查询。参数查询能够自动处理查询条件更改。若使用参数查询，在每次查询运行时代码都需要提供参数。</span><span class="sxs-lookup"><span data-stu-id="6d018-p102">For queries that you run regularly, you can use a PARAMETERS declaration to create a parameter query. A parameter query can help automate the process of changing query criteria. With a parameter query, your code will need to provide the parameters each time the query is run.</span></span>

<span data-ttu-id="6d018-122">PARAMETERS 声明是可选的，但如果包含它，应将它置于任何其他语句（包括 [SELECT 语句](select-statement-microsoft-access-sql.md)）之前。</span><span class="sxs-lookup"><span data-stu-id="6d018-122">The PARAMETERS declaration is optional but when included precedes any other statement, including [SELECT](select-statement-microsoft-access-sql.md).</span></span>

<span data-ttu-id="6d018-p103">如果声明包含了多个参数，请用逗号分隔它们。以下的示例里包含了两个参数：</span><span class="sxs-lookup"><span data-stu-id="6d018-p103">If the declaration includes more than one parameter, separate them with commas. The following example includes two parameters:</span></span>

```sql
PARAMETERS [Low price] Currency, [Beginning date] DateTime;
```

<span data-ttu-id="6d018-125">您可以使用[其中](https://msdn.microsoft.com/library/ff195245\(v=office.15\))或[HAVING](https://msdn.microsoft.com/library/ff193795\(v=office.15\))子句中的*名称*，但不是*数据类型*。</span><span class="sxs-lookup"><span data-stu-id="6d018-125">You can use *name* but not *datatype* in a [WHERE](https://msdn.microsoft.com/library/ff195245\(v=office.15\)) or [HAVING](https://msdn.microsoft.com/library/ff193795\(v=office.15\)) clause.</span></span> <span data-ttu-id="6d018-126">以下的示例中要求提供两个参数，然后将该条件应用于 Orders 表的记录中：</span><span class="sxs-lookup"><span data-stu-id="6d018-126">The following example expects two parameters to be provided and then applies the criteria to records in the Orders table:</span></span>

```sql
PARAMETERS [Low price] Currency, 
[Beginning date] DateTime; 
SELECT OrderID, OrderAmount
FROM Orders 
WHERE OrderAmount > [Low price] 
AND OrderDate >= [Beginning date];
```

## <a name="example"></a><span data-ttu-id="6d018-127">示例</span><span class="sxs-lookup"><span data-stu-id="6d018-127">Example</span></span>

<span data-ttu-id="6d018-128">本示例要求用户提供职务，然后使用该职务作为查询条件。</span><span class="sxs-lookup"><span data-stu-id="6d018-128">This example requires the user to provide a job title and then uses that job title as the criteria for the query.</span></span>

<span data-ttu-id="6d018-129">本示例调用 EnumFields 过程，您可以在 [SELECT 语句](select-statement-microsoft-access-sql.md)示例中找到该过程。</span><span class="sxs-lookup"><span data-stu-id="6d018-129">This example calls the EnumFields procedure, which you can find in the [SELECT statement](select-statement-microsoft-access-sql.md) example.</span></span>

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
