---
title: MaxRecords 属性示例 (VB)
TOCTitle: MaxRecords Property Example (VB)
ms:assetid: e0b21025-3494-81a7-d656-03b85b0102d2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250142(v=office.15)
ms:contentKeyID: 48548241
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8ac83b701603996da2a143dcd26567d3f1ece51e
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466749"
---
# <a name="maxrecords-property-example-vb"></a>MaxRecords 属性示例 (VB)


**适用于**： Access 2013 |Office 2013

本示例使用 [MaxRecords](maxrecords-property-ado.md) 属性打开一个 [Recordset](recordset-object-ado.md)，该记录集包含 ***Titles***（书目）表中价格最贵的 10 本书的标题。

```vb 
 
'BeginMaxRecordsVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 Dim rstTitles As ADODB.Recordset 
 Dim Cnxn As ADODB.Connection 
 Dim strCnxn As String 
 Dim strSQLTitles As String 
 
 ' Open a connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' Open recordset containing the 10 most expensive 
 ' titles in the Titles table 
 Set rstTitles = New ADODB.Recordset 
 rstTitles.MaxRecords = 10 
 
 strSQLTitles = "SELECT Title, Price FROM Titles ORDER BY Price DESC" 
 rstTitles.Open strSQLTitles, strCnxn, adOpenStatic, adLockReadOnly, adCmdText 
 
 ' Display the contents of the recordset 
 Debug.Print "Top Ten Titles by Price:" 
 
 Do Until rstTitles.EOF 
 Debug.Print " " & rstTitles!Title & " - " & rstTitles!Price 
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
'EndMaxRecordsVB 
```

