---
title: Resync 方法示例 (VB)
TOCTitle: Resync method example (VB)
ms:assetid: 831341e9-1aef-cd51-bc49-d3d70fd61471
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249571(v=office.15)
ms:contentKeyID: 48546001
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 49c41a2d6f7e90f4e40da5ba932f66fc9976eba8
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25863407"
---
# <a name="resync-method-example-vb"></a><span data-ttu-id="2d296-102">Resync 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="2d296-102">Resync method example (VB)</span></span>


<span data-ttu-id="2d296-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="2d296-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="2d296-104">以下示例演示了如何使用 [Resync](resync-method-ado.md) 方法刷新静态记录集中的数据。</span><span class="sxs-lookup"><span data-stu-id="2d296-104">This example demonstrates using the [Resync](resync-method-ado.md) method to refresh data in a static recordset.</span></span>

```vb 
 
'BeginResyncVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection strings 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 'connection and recordset variables 
 Dim Cnxn As ADODB.Connection 
 Dim rstTitles As ADODB.Recordset 
 Dim strCnxn As String 
 Dim strSQLTitles As String 
 
 ' Open connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' Open recordset using object refs to set properties 
 ' that allow for updates to the database 
 Set rstTitles = New ADODB.Recordset 
 Set rstTitles.ActiveConnection = Cnxn 
 rstTitles.CursorType = adOpenKeyset 
 rstTitles.LockType = adLockOptimistic 
 
 strSQLTitles = "titles" 
 rstTitles.Open strSQLTitles 
 
 'rstTitles.Open strSQLTitles, Cnxn, adOpenKeyset, adLockPessimistic, adCmdTable 
 'the above line of code passes the same refs as the object refs listed above 
 
 ' Change the type of the first title in the recordset 
 rstTitles!Type = "database" 
 
 ' Display the results of the change 
 MsgBox "Before resync: " & vbCr & vbCr & _ 
 "Title - " & rstTitles!Title & vbCr & _ 
 "Type - " & rstTitles!Type 
 
 ' Resync with database and redisplay results 
 rstTitles.Resync 
 MsgBox "After resync: " & vbCr & vbCr & _ 
 "Title - " & rstTitles!Title & vbCr & _ 
 "Type - " & rstTitles!Type 
 
 ' clean up 
 rstTitles.CancelBatch 
 rstTitles.Close 
 Cnxn.Close 
 Set rstTitles = Nothing 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rstTitles Is Nothing Then 
 If rstTitles.State = adStateOpen Then 
 rstTitles.CancelBatch 
 rstTitles.Close 
 End If 
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
'EndResyncVB 
```

