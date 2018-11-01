---
title: Optimize 属性示例 (VB)
TOCTitle: Optimize property example (VB)
ms:assetid: f4576247-6057-c1fe-013d-74feaab33174
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250240(v=office.15)
ms:contentKeyID: 48548686
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a52eae197f2be1f6ed6825dc5c6c9fd3a785451c
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25871449"
---
# <a name="optimize-property-example-vb"></a><span data-ttu-id="40d3d-102">Optimize 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="40d3d-102">Optimize property example (VB)</span></span>


<span data-ttu-id="40d3d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="40d3d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="40d3d-104">本示例演示 [Field](field-object-ado.md) 对象动态 Optimize 属性。</span><span class="sxs-lookup"><span data-stu-id="40d3d-104">This example demonstrates the [Field](field-object-ado.md) objects dynamic Optimize property.</span></span> <span data-ttu-id="40d3d-105">***Pubs***数据库中的***作者***表的***zip***字段不编制索引。</span><span class="sxs-lookup"><span data-stu-id="40d3d-105">The ***zip*** field of the ***Authors*** table in the ***Pubs*** database is not indexed.</span></span> <span data-ttu-id="40d3d-106">对***zip***字段[Optimize](optimize-property-dynamic-ado.md)属性设置为**True**授权 ADO 建立索引的提高性能的[Find](find-method-ado.md)方法。</span><span class="sxs-lookup"><span data-stu-id="40d3d-106">Setting the [Optimize](optimize-property-dynamic-ado.md) property to **True** on the ***zip*** field authorizes ADO to build an index that improves the performance of the [Find](find-method-ado.md) method.</span></span>

```vb 
 
'BeginOptimizeVB 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
 ' recordset and connection variables 
 Dim Cnxn As ADODB.Connection 
 Dim rstAuthors As ADODB.Recordset 
 Dim strCnxn As String 
 Dim strSQLAuthors As String 
 
 ' Open connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Set Cnxn = New ADODB.Connection 
 Cnxn.Open strCnxn 
 
 ' open recordset client-side to enable index creation 
 Set rstAuthors = New ADODB.Recordset 
 rstAuthors.CursorLocation = adUseClient 
 strSQLAuthors = "SELECT * FROM Authors" 
 rstAuthors.Open strSQLAuthors, Cnxn, adOpenStatic, adLockReadOnly, adCmdText 
 ' Create the index 
 rstAuthors!zip.Properties("Optimize") = True 
 ' Find Akiko Yokomoto 
 rstAuthors.Find "zip = '94595'" 
 
 ' show results 
 Debug.Print rstAuthors!au_fname & " " & rstAuthors!au_lname & " " & _ 
 rstAuthors!address & " " & rstAuthors!city & " " & rstAuthors!State 
 rstAuthors!zip.Properties("Optimize") = False 'Delete the index 
 
 ' clean up 
 rstAuthors.Close 
 Cnxn.Close 
 Set rstAuthors = Nothing 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rstAuthors Is Nothing Then 
 If rstAuthors.State = adStateOpen Then rstAuthors.Close 
 End If 
 Set rstAuthors = Nothing 
 
 If Not Cnxn Is Nothing Then 
 If Cnxn.State = adStateOpen Then Cnxn.Close 
 End If 
 Set Cnxn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndOptimizeVB 
```

