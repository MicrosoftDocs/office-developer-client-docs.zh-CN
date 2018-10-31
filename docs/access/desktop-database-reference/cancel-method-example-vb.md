---
title: Cancel 方法示例 (VB)
TOCTitle: Cancel method example (VB)
ms:assetid: 80851036-3627-87c2-60ca-65629136bf28
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249547(v=office.15)
ms:contentKeyID: 48545926
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e449c6b94dfb20bacdb75efb821818a3f0c3a485
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25860117"
---
# <a name="cancel-method-example-vb"></a>Cancel 方法示例 (VB)


**适用于**： Access 2013 |Office 2013

以下示例使用 [Cancel](cancel-method-ado.md) 方法取消当连接处于忙碌状态时对 [Connection](connection-object-ado.md) 对象执行的命令。

```vb 
 
'BeginCancelVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 'recordset and connection variables 
 Dim Cnxn As ADODB.Connection 
 Dim strCnxn As String 
 Dim strCmdChange As String 
 Dim strCmdRestore As String 
 'record variables 
 Dim blnChanged As Boolean 
 
 ' Open a connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' Define command strings 
 strCmdChange = "UPDATE titles SET type = 'self_help' WHERE type = 'psychology'" 
 strCmdRestore = "UPDATE titles SET type = 'psychology' " & _ 
 "WHERE type = 'self_help'" 
 
 ' Begin a transaction, then execute a command asynchronously 
 Cnxn.BeginTrans 
 Cnxn.Execute strCmdChange, , adAsyncExecute 
 ' do something else for a little while – 
 ' use i = 1 to 32000 to allow completion 
 Dim i As Integer 
 For i = 1 To 1000 
 i = i + i 
 Debug.Print i 
 Next i 
 
 ' If the command has NOT completed, cancel the execute and 
 ' roll back the transaction; otherwise, commit the transaction 
 If CBool(Cnxn.State And adStateExecuting) Then 
 Cnxn.Cancel 
 Cnxn.RollbackTrans 
 blnChanged = False 
 MsgBox "Update canceled." 
 Else 
 Cnxn.CommitTrans 
 blnChanged = True 
 MsgBox "Update complete." 
 End If 
 
 ' If the change was made, restore the data 
 ' because this is only a demo 
 If blnChanged Then 
 Cnxn.Execute strCmdRestore 
 MsgBox "Data restored." 
 End If 
 
 ' clean up 
 Cnxn.Close 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 If Not Cnxn Is Nothing Then 
 If Cnxn.State = adStateOpen Then Cnxn.Close 
 End If 
 Set Cnxn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndCancelVB 
```

