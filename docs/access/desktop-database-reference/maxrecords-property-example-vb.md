---
title: MaxRecords 属性示例 (VB)
TOCTitle: MaxRecords property example (VB)
ms:assetid: e0b21025-3494-81a7-d656-03b85b0102d2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250142(v=office.15)
ms:contentKeyID: 48548241
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4ad7dc4370419c46a1f4d7a4b2511dd86795c323
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25876517"
---
# <a name="maxrecords-property-example-vb"></a><span data-ttu-id="190d0-102">MaxRecords 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="190d0-102">MaxRecords property example (VB)</span></span>


<span data-ttu-id="190d0-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="190d0-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="190d0-104">本示例使用 [MaxRecords](maxrecords-property-ado.md) 属性打开一个 [Recordset](recordset-object-ado.md)，该记录集包含 ***Titles***（书目）表中价格最贵的 10 本书的标题。</span><span class="sxs-lookup"><span data-stu-id="190d0-104">This example uses the [MaxRecords](maxrecords-property-ado.md) property to open a [Recordset](recordset-object-ado.md) containing the 10 most expensive titles in the ***Titles*** table.</span></span>

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

