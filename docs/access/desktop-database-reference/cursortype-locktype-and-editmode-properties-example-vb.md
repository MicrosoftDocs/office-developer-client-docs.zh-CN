---
title: CursorType、LockType 和 EditMode 属性示例 (VB)
TOCTitle: CursorType, LockType, and EditMode properties example (VB)
ms:assetid: efe3f976-b095-c0ce-376a-693b07ec8e9d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250221(v=office.15)
ms:contentKeyID: 48548595
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1725c7b6c60df6151da6349f33de43319b912819
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25868320"
---
# <a name="cursortype-locktype-and-editmode-properties-example-vb"></a><span data-ttu-id="e2fa1-102">CursorType、LockType 和 EditMode 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="e2fa1-102">CursorType, LockType, and EditMode properties example (VB)</span></span>


<span data-ttu-id="e2fa1-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e2fa1-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e2fa1-p101">此示例演示如何在打开 [Recordset](cursortype-property-ado.md) 前设置 [CursorType](locktype-property-ado.md) 和 [LockType](recordset-object-ado.md) 属性。它还演示在各种情况下 [EditMode](editmode-property-ado.md) 属性的值。若要运行此过程，必须使用 **EditModeOutput** 函数。</span><span class="sxs-lookup"><span data-stu-id="e2fa1-p101">This example demonstrates setting the [CursorType](cursortype-property-ado.md) and [LockType](locktype-property-ado.md) properties before opening a [Recordset](recordset-object-ado.md). It also shows the value of the [EditMode](editmode-property-ado.md) property under various conditions. The **EditModeOutput** function is required for this procedure to run.</span></span>

```vb 
 
'BeginEditModeVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 ' recordset variables 
 Dim rstEmployees As ADODB.Recordset 
 Dim Cnxn As ADODB.Connection 
 Dim strCnxn As String 
 Dim SQLEmployees As String 
 
 ' open connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' set recordset properties through object refs 
 ' instead of through arguments to Open method 
 Set rstEmployees = New ADODB.Recordset 
 Set rstEmployees.ActiveConnection = Cnxn 
 rstEmployees.CursorLocation = adUseClient 
 rstEmployees.CursorType = adOpenStatic 
 rstEmployees.LockType = adLockBatchOptimistic 
 
 ' open recordset with data from Employee table 
 SQLEmployees = "employee" 
 rstEmployees.Open SQLEmployees, , , , adCmdTable 
 
 ' Show the EditMode property under different editing states 
 rstEmployees.AddNew 
 rstEmployees!emp_id = "T-T55555M" 
 rstEmployees!fname = "temp_fname" 
 rstEmployees!lname = "temp_lname" 
 'call function below 
 'to output results to debug window 
 EditModeOutput "After AddNew:", rstEmployees.EditMode 
 rstEmployees.UpdateBatch 
 EditModeOutput "After UpdateBatch:", rstEmployees.EditMode 
 rstEmployees!fname = "test" 
 EditModeOutput "After Edit:", rstEmployees.EditMode 
 rstEmployees.Close 
 
 ' Delete new record because this is a demonstration 
 Cnxn.Execute "DELETE FROM employee WHERE emp_id = 'T-T55555M'" 
 
 ' clean up 
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
 
Public Function EditModeOutput(strTemp As String, _ 
 intEditMode As Integer) 
 
 ' Print report based on the value of the EditMode 
 ' property 
 Debug.Print strTemp 
 Debug.Print " EditMode = "; 
 
 Select Case intEditMode 
 Case adEditNone 
 Debug.Print "adEditNone" 
 Case adEditInProgress 
 Debug.Print "adEditInProgress" 
 Case adEditAdd 
 Debug.Print "adEditAdd" 
 End Select 
 
End Function 
'EndEditModeVB 
```

