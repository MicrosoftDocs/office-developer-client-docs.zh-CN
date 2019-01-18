---
title: NextRecordset 方法示例 (VB)
TOCTitle: NextRecordset method example (VB)
ms:assetid: f8d99670-3c28-1704-0ec1-34b06e7cd1b0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250265(v=office.15)
ms:contentKeyID: 48548795
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ab5dbff4c293bc9f44c3617a18d09a5e73cc16ec
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28707400"
---
# <a name="nextrecordset-method-example-vb"></a><span data-ttu-id="2e8fd-102">NextRecordset 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="2e8fd-102">NextRecordset method example (VB)</span></span>


<span data-ttu-id="2e8fd-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="2e8fd-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2e8fd-104">本示例使用 [NextRecordset](nextrecordset-method-ado.md) 方法来查看记录集中的数据，该方法使用由三个单独的 **SELECT** 语句构成的复合命令语句。</span><span class="sxs-lookup"><span data-stu-id="2e8fd-104">This example uses the [NextRecordset](nextrecordset-method-ado.md) method to view the data in a recordset that uses a compound command statement made up of three separate **SELECT** statements.</span></span>

```vb 
 
'BeginNextRecordsetVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 ' connection and recordset variables 
 Dim rstCompound As ADODB.Recordset 
 Dim Cnxn As ADODB.Connection 
 Dim strCnxn As String 
 Dim SQLCompound As String 
 
 Dim intCount As Integer 
 
 ' Open connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' Open compound recordset 
 Set rstCompound = New ADODB.Recordset 
 SQLCompound = "SELECT * FROM Authors; " & _ 
 "SELECT * FROM stores; " & _ 
 "SELECT * FROM jobs" 
 rstCompound.Open SQLCompound, Cnxn, adOpenStatic, adLockReadOnly, adCmdText 
 
 ' Display results from each SELECT statement 
 intCount = 1 
 Do Until rstCompound Is Nothing 
 Debug.Print "Contents of recordset #" & intCount 
 
 Do Until rstCompound.EOF 
 Debug.Print , rstCompound.Fields(0), rstCompound.Fields(1) 
 rstCompound.MoveNext 
 Loop 
 
 Set rstCompound = rstCompound.NextRecordset 
 intCount = intCount + 1 
 Loop 
 
 ' clean up 
 Cnxn.Close 
 Set rstCompound = Nothing 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rstCompound Is Nothing Then 
 If rstCompound.State = adStateOpen Then rstCompound.Close 
 End If 
 Set rstCompound = Nothing 
 
 If Not Cnxn Is Nothing Then 
 If Cnxn.State = adStateOpen Then Cnxn.Close 
 End If 
 Set Cnxn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndNextRecordsetVB 
```

