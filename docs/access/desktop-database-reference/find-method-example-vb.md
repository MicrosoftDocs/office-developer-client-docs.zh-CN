---
title: Find 方法示例 (VB)
TOCTitle: Find Method Example (VB)
ms:assetid: 93fa7cab-e66d-7d9c-22bb-d73b44982649
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249657(v=office.15)
ms:contentKeyID: 48546408
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 89f6654f2749aab2f30e55c3543763da76e53a52
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468187"
---
# <a name="find-method-example-vb"></a><span data-ttu-id="2e9b8-102">Find 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="2e9b8-102">Find Method Example (VB)</span></span>


<span data-ttu-id="2e9b8-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="2e9b8-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="2e9b8-104">此示例使用[Recordset](recordset-object-ado.md)对象的[Find](find-method-ado.md)方法找到并***Pubs***数据库中的业务标题的计数。</span><span class="sxs-lookup"><span data-stu-id="2e9b8-104">This example uses the [Recordset](recordset-object-ado.md) object's [Find](find-method-ado.md) method to locate and count the number of business titles in the ***Pubs*** database.</span></span> <span data-ttu-id="2e9b8-105">本示例假设基础提供程序不支持类似功能。</span><span class="sxs-lookup"><span data-stu-id="2e9b8-105">The example assumes the underlying provider does not support similar functionality.</span></span>

```vb 
 
'BeginFindVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 ' connection and recordset variables 
 Dim Cnxn As New ADODB.Connection 
 Dim rstTitles As New ADODB.Recordset 
 Dim strCnxn As String 
 Dim strSQLTitles As String 
 
 ' record variables 
 Dim mark As Variant 
 Dim count As Integer 
 
 ' open connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' open recordset with default parameters which are 
 ' sufficient to search forward through a Recordset 
 Set rstTitles = New ADODB.Recordset 
 strSQLTitles = "SELECT title_id FROM titles" 
 rstTitles.Open strSQLTitles, Cnxn, adOpenStatic, adLockReadOnly, adCmdText 
 
 count = 0 
 rstTitles.Find "title_id LIKE 'BU%'" 
 
 Do While Not rstTitles.EOF 
 'continue if last find succeeded 
 Debug.Print "Title ID: "; rstTitles!title_id 
 'count the last title found 
 count = count + 1 
 ' note current position 
 mark = rstTitles.Bookmark 
 rstTitles.Find "title_id LIKE 'BU%'", 1, adSearchForward, mark 
 ' above code skips current record to avoid finding the same row repeatedly; 
 ' last arg (bookmark) is redundant because Find searches from current position 
 Loop 
 
 Debug.Print "The number of business titles is " & count 
 
 ' clean up 
 rstTitles.Close 
 Cnxn.Close 
 Set rstTitles = Nothing 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rstTitles Is Nothing Then 
 If rstTitles.State = adStateOpen Then rstTitles.Close 
 End If 
 Set rstTitles = Nothing 
 
 If Not Cnxn Is Nothing Then 
 If Cnxn.State = adStateOpen Then Cnxn.Close 
 End If 
 Set Cnxn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndFindVB 
```

