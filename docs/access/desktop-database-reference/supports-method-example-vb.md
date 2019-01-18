---
title: Supports 方法示例 (VB)
TOCTitle: Supports method example (VB)
ms:assetid: 6ebeac50-59d1-41d0-b5ef-2be868182cc2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249438(v=office.15)
ms:contentKeyID: 48545518
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 5dc6035569abd42cd6a5f4ce44fcf0da550bf809
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28726321"
---
# <a name="supports-method-example-vb"></a><span data-ttu-id="b05bc-102">Supports 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="b05bc-102">Supports method example (VB)</span></span>


<span data-ttu-id="b05bc-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b05bc-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b05bc-p101">以下示例使用 [Supports](supports-method-ado.md) 方法显示用不同游标类型打开的记录集所支持的选项。此过程需要使用 DisplaySupport 过程才能运行。</span><span class="sxs-lookup"><span data-stu-id="b05bc-p101">This example uses the [Supports](supports-method-ado.md) method to display the options supported by a recordset opened with different cursor types. The DisplaySupport procedure is required for this procedure to run.</span></span>

```vb 
 
'BeginSupportsVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 ' recordset and connection variables 
 Dim rstTitles As ADODB.Recordset 
 Dim Cnxn As ADODB.Connection 
 Dim strCnxn As String 
 Dim strSQLTitles As String 
 ' array variables 
 Dim arrCursorType(4) As Integer 
 Dim intIndex As Integer 
 
 ' open connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' Fill array with CursorType constants 
 arrCursorType(0) = adOpenForwardOnly 
 arrCursorType(1) = adOpenKeyset 
 arrCursorType(2) = adOpenDynamic 
 arrCursorType(3) = adOpenStatic 
 
 ' open recordset using each CursorType and optimistic locking 
 For intIndex = 0 To 3 
 Set rstTitles = New ADODB.Recordset 
 rstTitles.CursorType = arrCursorType(intIndex) 
 rstTitles.LockType = adLockOptimistic 
 
 strSQLTitles = "Titles" 
 rstTitles.Open strSQLTitles, Cnxn, , , adCmdTable 
 
 Select Case arrCursorType(intIndex) 
 Case adOpenForwardOnly 
 Debug.Print "ForwardOnly cursor supports:" 
 Case adOpenKeyset 
 Debug.Print "Keyset cursor supports:" 
 Case adOpenDynamic 
 Debug.Print "Dynamic cursor supports:" 
 Case adOpenStatic 
 Debug.Print "Static cursor supports:" 
 End Select 
 
 ' call the DisplaySupport procedure from below 
 ' to display the supported options 
 DisplaySupport rstTitles 
 
 Next intIndex 
 
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
'EndSupportsVB 
 
 
 
'BeginSupports2VB 
Public Sub DisplaySupport(rstTemp As ADODB.Recordset) 
 
 Dim arrConstants(11) As Long 
 Dim blnSupports As Boolean 
 Dim intIndex As Integer 
 
 ' Fill array with cursor option constants 
 arrConstants(0) = adAddNew 
 arrConstants(1) = adApproxPosition 
 arrConstants(2) = adBookmark 
 arrConstants(3) = adDelete 
 arrConstants(4) = adFind 
 arrConstants(5) = adHoldRecords 
 arrConstants(6) = adMovePrevious 
 arrConstants(7) = adNotify 
 arrConstants(8) = adResync 
 arrConstants(9) = adUpdate 
 arrConstants(10) = adUpdateBatch 
 
 For intIndex = 0 To 10 
 blnSupports = _ 
 rstTemp.Supports(arrConstants(intIndex)) 
 If blnSupports Then 
 Select Case arrConstants(intIndex) 
 Case adAddNew 
 Debug.Print " AddNew" 
 Case adApproxPosition 
 Debug.Print " AbsolutePosition and AbsolutePage" 
 Case adBookmark 
 Debug.Print " blnkmark" 
 Case adDelete 
 Debug.Print " Delete" 
 Case adFind 
 Debug.Print " Find" 
 Case adHoldRecords 
 Debug.Print " Holding Records" 
 Case adMovePrevious 
 Debug.Print " MovePrevious and Move" 
 Case adNotify 
 Debug.Print " Notifications" 
 Case adResync 
 Debug.Print " Resyncing data" 
 Case adUpdate 
 Debug.Print " Update" 
 Case adUpdateBatch 
 Debug.Print " batch updating" 
 End Select 
 End If 
 Next intIndex 
 
End Sub 
'EndSupports2VB 
```

