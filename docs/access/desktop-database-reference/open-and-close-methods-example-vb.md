---
title: Open 和 Close 方法示例 (VB)
TOCTitle: Open and Close methods example (VB)
ms:assetid: 5c000d5f-2560-2530-fe36-163f6600f3cc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249319(v=office.15)
ms:contentKeyID: 48545078
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 30723e912fa6807136d37e4cbbf4077b22f1d615
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25862189"
---
# <a name="open-and-close-methods-example-vb"></a><span data-ttu-id="c7a12-102">Open 和 Close 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="c7a12-102">Open and Close methods example (VB)</span></span>


<span data-ttu-id="c7a12-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c7a12-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c7a12-104">本示例对已打开的 **Recordset** 和 [Connection](close-method-ado.md) 对象使用 [Open](recordset-object-ado.md) 和 [Close](connection-object-ado.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="c7a12-104">This example uses the **Open** and [Close](close-method-ado.md) methods on both [Recordset](recordset-object-ado.md) and [Connection](connection-object-ado.md) objects that have been opened.</span></span>

```vb 
 
'BeginOpenVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub OpenX() 
 On Error GoTo ErrorHandler 
 
 Dim Cnxn As ADODB.Connection 
 Dim rstEmployees As ADODB.Recordset 
 Dim strCnxn As String 
 Dim strSQLEmployees As String 
 Dim varDate As Variant 
 
 ' Open connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Set Cnxn = New ADODB.Connection 
 Cnxn.Open strCnxn 
 
 ' Open employee table 
 Set rstEmployees = New ADODB.Recordset 
 strSQLEmployees = "employee" 
 rstEmployees.Open strSQLEmployees, Cnxn, adOpenKeyset, adLockOptimistic, adCmdTable 
 
 ' Assign the first employee record's hire date 
 ' to a variable, then change the hire date 
 varDate = rstEmployees!hire_date 
 Debug.Print "Original data" 
 Debug.Print " Name - Hire Date" 
 Debug.Print " " & rstEmployees!fname & " " & _ 
 rstEmployees!lname & " - " & rstEmployees!hire_date 
 rstEmployees!hire_date = #1/1/1900# 
 rstEmployees.Update 
 Debug.Print "Changed data" 
 Debug.Print " Name - Hire Date" 
 Debug.Print " " & rstEmployees!fname & " " & _ 
 rstEmployees!lname & " - " & rstEmployees!hire_date 
 
 ' Requery Recordset and reset the hire date 
 rstEmployees.Requery 
 rstEmployees!hire_date = varDate 
 rstEmployees.Update 
 Debug.Print "Data after reset" 
 Debug.Print " Name - Hire Date" 
 Debug.Print " " & rstEmployees!fname & " " & _ 
 rstEmployees!lname & " - " & rstEmployees!hire_date 
 
 ' clean up 
 rstEmployees.Close 
 Cnxn.Close 
 Set rstEmployees = Nothing 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rstEmployees Is Nothing Then 
 If rstEmployees.State = adStateOpen Then rstEmployees.Close 
 End If 
 Set rstEmployees = Nothing 
 
 If Not Cnxn Is Nothing Then 
 If Cnxn.State = adStateOpen Then Cnxn.Close 
 End If 
 Set Cnxn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndOpenVB 
```

