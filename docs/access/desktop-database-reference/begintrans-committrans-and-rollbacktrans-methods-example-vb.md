---
title: BeginTrans，CommitTrans RollbackTrans 方法示例 (VB)
TOCTitle: BeginTrans, CommitTrans, and RollbackTrans methods example (VB)
ms:assetid: 12fce322-dba7-9159-8a09-7f6daf1a80ed
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248904(v=office.15)
ms:contentKeyID: 48543357
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a97d461cfe42fc1824d9f04c4dcb6b9a91169566
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25860096"
---
# <a name="begintrans-committrans-and-rollbacktrans-methods-example-vb"></a><span data-ttu-id="3d267-102">BeginTrans、CommitTrans 和 RollbackTrans 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="3d267-102">BeginTrans, CommitTrans, and RollbackTrans methods example (VB)</span></span>


<span data-ttu-id="3d267-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="3d267-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="3d267-p101">以下示例更改数据库 ***Titles（标题）*** 表中所有心理学书籍的书籍类型。首先用 [BeginTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) 方法启动一个事务，隔离对 ***Titles（标题）*** 表进行的所有更改，然后用 [CommitTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) 方法保存更改。可以使用 [RollbackTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) 方法撤消用 [Update](update-method-ado.md) 方法保存的更改。</span><span class="sxs-lookup"><span data-stu-id="3d267-p101">This example changes the book type of all psychology books in the ***Titles*** table of the database. After the [BeginTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) method starts a transaction that isolates all the changes made to the ***Titles*** table, the [CommitTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) method saves the changes. You can use the [RollbackTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) method to undo changes that you saved using the [Update](update-method-ado.md) method.</span></span>

```vb 
 
'BeginBeginTransVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 'recordset and connection variables 
 Dim Cnxn As ADODB.Connection 
 Dim strCnxn As String 
 Dim rstTitles As ADODB.Recordset 
 Dim strSQLTitles As String 
 'record variables 
 Dim strTitle As String 
 Dim strMessage As String 
 
 ' Open connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Set Cnxn = New ADODB.Connection 
 Cnxn.Open strCnxn 
 
 ' Open recordset dynamic to allow for changes 
 Set rstTitles = New ADODB.Recordset 
 strSQLTitles = "Titles" 
 rstTitles.Open strSQLTitles, Cnxn, adOpenDynamic, adLockPessimistic, adCmdTable 
 
 Cnxn.BeginTrans 
 
 ' Loop through recordset and prompt user 
 ' to change the type for a specified title 
 
 rstTitles.MoveFirst 
 
 Do Until rstTitles.EOF 
 If Trim(rstTitles!Type) = "psychology" Then 
 strTitle = rstTitles!Title 
 strMessage = "Title: " & strTitle & vbCr & _ 
 "Change type to self help?" 
 
 ' If yes, change type for the specified title 
 If MsgBox(strMessage, vbYesNo) = vbYes Then 
 rstTitles!Type = "self_help" 
 rstTitles.Update 
 End If 
 End If 
 rstTitles.MoveNext 
 Loop 
 
 ' Prompt user to commit all changes made 
 If MsgBox("Save all changes?", vbYesNo) = vbYes Then 
 Cnxn.CommitTrans 
 Else 
 Cnxn.RollbackTrans 
 End If 
 
 ' Print recordset 
 rstTitles.Requery 
 rstTitles.MoveFirst 
 Do While Not rstTitles.EOF 
 Debug.Print rstTitles!Title & " - " & rstTitles!Type 
 rstTitles.MoveNext 
 Loop 
 
 ' Restore original data as this is a demo 
 rstTitles.MoveFirst 
 
 Do Until rstTitles.EOF 
 If Trim(rstTitles!Type) = "self_help" Then 
 rstTitles!Type = "psychology" 
 rstTitles.Update 
 End If 
 rstTitles.MoveNext 
 Loop 
 
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
 
 
'EndBeginTransVB 
```

