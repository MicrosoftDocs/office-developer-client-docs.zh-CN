---
title: Delete 方法示例 (VB)
TOCTitle: Delete Method Example (VB)
ms:assetid: cea540c1-8c42-4d50-9363-cde3329da7a5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250023(v=office.15)
ms:contentKeyID: 48547791
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2a0513089768dbdabcb60c30782d50a283ba8222
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25469013"
---
# <a name="delete-method-example-vb"></a><span data-ttu-id="9704b-102">Delete 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="9704b-102">Delete Method Example (VB)</span></span>


<span data-ttu-id="9704b-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="9704b-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="9704b-104">本示例使用 [Delete](delete-method-ado-recordset.md) 方法从 [Recordset](recordset-object-ado.md) 中删除指定的记录。</span><span class="sxs-lookup"><span data-stu-id="9704b-104">This example uses the [Delete](delete-method-ado-recordset.md) method to remove a specified record from a [Recordset](recordset-object-ado.md).</span></span>

```vb 
 
'BeginDeleteVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 Dim rstRoySched As ADODB.Recordset 
 Dim Cnxn As ADODB.Connection 
 Dim strCnxn As String 
 Dim strSQLRoySched As String 
 
 Dim strMsg As String 
 Dim strTitleID As String 
 Dim intLoRange As Integer 
 Dim intHiRange As Integer 
 Dim intRoyalty As Integer 
 
 ' open connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' open RoySched table with cursor client-side 
 Set rstRoySched = New ADODB.Recordset 
 rstRoySched.CursorLocation = adUseClient 
 rstRoySched.CursorType = adOpenStatic 
 rstRoySched.LockType = adLockBatchOptimistic 
 rstRoySched.Open "SELECT * FROM roysched WHERE royalty = 20", strCnxn, , , adCmdText 
 
 ' Prompt for a record to delete 
 strMsg = "Before delete there are " & rstRoySched.RecordCount & _ 
 " titles with 20 percent royalty:" & vbCr & vbCr 
 
 Do While Not rstRoySched.EOF 
 strMsg = strMsg & rstRoySched!title_id & vbCr 
 rstRoySched.MoveNext 
 Loop 
 
 strMsg = strMsg & vbCr & vbCr & "Enter the ID of a record to delete:" 
 strTitleID = UCase(InputBox(strMsg)) 
 
 If strTitleID = "" Then 
 Err.Raise 1, , "You didn't enter any value for the record ID." 
 End If 
 
 ' Move to the record and save data so it can be restored 
 rstRoySched.Filter = "title_id = '" & strTitleID & "'" 
 
 If rstRoySched.RecordCount < 1 Then 
 Err.Raise 1, , "There is no record for the record ID you entered." 
 End If 
 
 intLoRange = rstRoySched!lorange 
 intHiRange = rstRoySched!hirange 
 intRoyalty = rstRoySched!royalty 
 
 ' Delete the record 
 rstRoySched.Delete 
 rstRoySched.UpdateBatch 
 
 ' Show the results 
 rstRoySched.Filter = adFilterNone 
 rstRoySched.Requery 
 strMsg = "" 
 strMsg = "After delete there are " & rstRoySched.RecordCount & _ 
 " titles with 20 percent royalty:" & vbCr & vbCr 
 Do While Not rstRoySched.EOF 
 strMsg = strMsg & rstRoySched!title_id & vbCr 
 rstRoySched.MoveNext 
 Loop 
 MsgBox strMsg 
 
 ' Restore the data because this is a demonstration 
 rstRoySched.AddNew 
 rstRoySched!title_id = strTitleID 
 rstRoySched!lorange = intLoRange 
 rstRoySched!hirange = intHiRange 
 rstRoySched!royalty = intRoyalty 
 rstRoySched.UpdateBatch 
 
 ' clean up 
 rstRoySched.Close 
 Set rstRoySched = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rstRoySched Is Nothing Then 
 If rstRoySched.State = adStateOpen Then rstRoySched.Close 
 End If 
 Set rstRoySched = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndDeleteVB 
```

