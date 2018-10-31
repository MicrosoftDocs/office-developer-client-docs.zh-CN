---
title: GetString 方法示例 (VB)
TOCTitle: GetString method example (VB)
ms:assetid: fa954e48-0810-9d71-4e24-f3ae2839105a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250280(v=office.15)
ms:contentKeyID: 48548849
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9431711e3a3e2b39d6d59165650bb32e85e84f4a
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25861860"
---
# <a name="getstring-method-example-vb"></a>GetString 方法示例 (VB)


**适用于**： Access 2013 |Office 2013

本示例演示 [GetString](getstring-method-ado.md) 方法。

假设您正在调试某个数据访问问题，并且需要一种快速、简便的方法来显示较小 [Recordset](recordset-object-ado.md) 的当前内容。

```vb 
 
'BeginGetStringVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 ' connection variables 
 Dim Cnxn As ADODB.Connection 
 Dim rstAuthors As ADODB.Recordset 
 Dim strCnxn As String 
 Dim strSQLAuthors As String 
 Dim varOutput As Variant 
 
 ' specific variables 
 Dim strPrompt As String 
 Dim strState As String 
 
 ' open connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' get user input 
 strPrompt = "Enter a state (CA, IN, KS, MD, MI, OR, TN, UT): " 
 strState = Trim(InputBox(strPrompt, "GetString Example")) 
 
 ' open recordset 
 Set rstAuthors = New ADODB.Recordset 
 strSQLAuthors = "SELECT au_fname, au_lname, address, city FROM Authors " & _ 
 "WHERE state = '" & strState & "'" 
 rstAuthors.Open strSQLAuthors, Cnxn, adOpenStatic, adLockReadOnly, adCmdText 
 
 If Not rstAuthors.EOF Then 
 ' Use all defaults: get all rows, TAB as column delimiter, 
 ' CARRIAGE RETURN as row delimiter, EMPTY-string as null delimiter 
 varOutput = rstAuthors.GetString(adClipString) 
 ' print output 
 Debug.Print "State = '" & strState & "'" 
 Debug.Print "Name Address City" & vbCr 
 Debug.Print varOutput 
 Else 
 Debug.Print "No rows found for state = '" & strState & "'" & vbCr 
 End If 
 
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
'EndGetStringVB 
```

