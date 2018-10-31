---
title: MoveFirst、MoveLast、MoveNext 和 MovePrevious 方法示例 (VB)
TOCTitle: MoveFirst, MoveLast, MoveNext, and MovePrevious methods example (VB)
ms:assetid: 61f82932-2ce9-341f-b120-168f786a9040
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249364(v=office.15)
ms:contentKeyID: 48545226
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 78525612215c4959cf77cc5e986c5724f7e26310
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25862683"
---
# <a name="movefirst-movelast-movenext-and-moveprevious-methods-example-vb"></a>MoveFirst、MoveLast、MoveNext 和 MovePrevious 方法示例 (VB)


**适用于**： Access 2013 |Office 2013

本示例使用 [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)、[MoveLast](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)、[MoveNext](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 和 [MovePrevious](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 方法基于提供的命令移动 [Recordset](recordset-object-ado.md) 的记录指针。若要使该过程运行，需要 MoveAny 过程。

```vb 
 
'BeginMoveFirstVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 ' connection and recordset variables 
 Dim rstAuthors As ADODB.Recordset 
 Dim Cnxn As ADODB.Connection 
 Dim strCnxn As String 
 Dim strSQLAuthors 
 ' record variables 
 Dim strMessage As String 
 Dim intCommand As Integer 
 
 ' Open connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' Open recordset from Authors table 
 Set rstAuthors = New ADODB.Recordset 
 rstAuthors.CursorLocation = adUseClient 
 ' Use client cursor to enable AbsolutePosition property 
 strSQLAuthors = "Authors" 
 rstAuthors.Open strSQLAuthors, Cnxn, adOpenStatic, adLockReadOnly, adCmdTable 
 
 ' Show current record information and get user's method choice 
 Do 
 strMessage = "Name: " & rstAuthors!au_fname & " " & _ 
 rstAuthors!au_lname & vbCr & "Record " & _ 
 rstAuthors.AbsolutePosition & " of " & _ 
 rstAuthors.RecordCount & vbCr & vbCr & _ 
 "[1 - MoveFirst, 2 - MoveLast, " & vbCr & _ 
 "3 - MoveNext, 4 - MovePrevious]" 
 intCommand = Val(Left(InputBox(strMessage), 1)) 
 
 ' for exiting the loop 
 If intCommand < 1 Or intCommand > 4 Then 
 MsgBox "You either entered a non-number or canceled the input box. Exit the application." 
 Exit Do 
 End If 
 
 ' Use specified method while trapping for BOF and EOF 
 Select Case intCommand 
 Case 1 
 rstAuthors.MoveFirst 
 Case 2 
 rstAuthors.MoveLast 
 Case 3 
 rstAuthors.MoveNext 
 If rstAuthors.EOF Then 
 MsgBox "Already at end of recordset!" 
 rstAuthors.MoveLast 
 End If 
 Case 4 
 rstAuthors.MovePrevious 
 If rstAuthors.BOF Then 
 MsgBox "Already at beginning of recordset!" 
 rstAuthors.MoveFirst 
 End If 
 End Select 
 Loop 
 
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
 
'EndMoveFirstVB 
```

