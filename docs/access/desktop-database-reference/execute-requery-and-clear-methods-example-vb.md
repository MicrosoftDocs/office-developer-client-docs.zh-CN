---
title: Execute、Requery 和 Clear 方法示例 (VB)
TOCTitle: Execute, Requery, and Clear methods example (VB)
ms:assetid: 6d700971-6b77-bd41-dd22-df53f902c0f2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249432(v=office.15)
ms:contentKeyID: 48545491
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9846ddcc06cf63093fdd23edf818e7266438fff3
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28703676"
---
# <a name="execute-requery-and-clear-methods-example-vb"></a><span data-ttu-id="5c25a-102">Execute、Requery 和 Clear 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="5c25a-102">Execute, Requery, and Clear methods example (VB)</span></span>


<span data-ttu-id="5c25a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="5c25a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="5c25a-p101">本示例演示同时从 **Command** 对象和 [Connection](command-object-ado.md) 对象运行时的 [Execute](connection-object-ado.md) 方法。本示例还使用 [Requery](requery-method-ado.md) 方法来检索 [Recordset](recordset-object-ado.md) 中的当前数据，并使用 [Clear](clear-method-ado.md) 方法来清除 [Errors](errors-collection-ado.md) 集合的内容。（可以通过 **Recordset** 的 **ActiveConnection** 属性的 [Connection](activeconnection-property-ado.md) 对象访问 [Errors](recordset-object-ado.md) 集合。若要使该过程运行，需要 ExecuteCommand 和 PrintOutput 过程。</span><span class="sxs-lookup"><span data-stu-id="5c25a-p101">This example demonstrates the **Execute** method when run from both a [Command](command-object-ado.md) object and a [Connection](connection-object-ado.md) object. It also uses the [Requery](requery-method-ado.md) method to retrieve current data in a [Recordset](recordset-object-ado.md), and the [Clear](clear-method-ado.md) method to clear the contents of the [Errors](errors-collection-ado.md) collection. (The **Errors** collection is accessed via the **Connection** object of the [ActiveConnection](activeconnection-property-ado.md) property of the [Recordset](recordset-object-ado.md).) The ExecuteCommand and PrintOutput procedures are required for this procedure to run.</span></span>

```vb 
 
'BeginExecuteVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo Err_Execute 
 
 ' connection, command, and recordset variables 
 Dim Cnxn As ADODB.Connection 
 Dim cmdChange As ADODB.Command 
 Dim rstTitles As ADODB.Recordset 
 Dim Err As ADODB.Error 
 Dim strSQLChange As String 
 Dim strSQLRestore As String 
 Dim strSQLTitles 
 Dim strCnxn As String 
 
 ' Define two SQL statements to execute as command text 
 strSQLChange = "UPDATE Titles SET Type = 'self_help' WHERE Type = 'psychology'" 
 strSQLRestore = "UPDATE Titles SET Type = 'psychology' WHERE Type = 'self_help'" 
 
 ' Open connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Set Cnxn = New ADODB.Connection 
 Cnxn.Open strCnxn 
 
 ' Create command object 
 Set cmdChange = New ADODB.Command 
 Set cmdChange.ActiveConnection = Cnxn 
 cmdChange.CommandText = strSQLChange 
 
 ' Open titles table 
 Set rstTitles = New ADODB.Recordset 
 strSQLTitles = "titles" 
 rstTitles.Open strSQLTitles, Cnxn, , , adCmdTable 
 
 ' Print report of original data 
 Debug.Print _ 
 "Data in Titles table before executing the query" 
 PrintOutput rstTitles 
 
 ' Call the ExecuteCommand subroutine below to execute cmdChange command 
 ExecuteCommand cmdChange, rstTitles 
 
 ' Print report of new data 
 Debug.Print _ 
 "Data in Titles table after executing the query" 
 PrintOutput rstTitles 
 
 ' Use the Connection object's execute method to 
 ' execute SQL statement to restore data and trap for 
 ' errors, checking the Errors collection if necessary 
 Cnxn.Execute strSQLRestore, , adExecuteNoRecords 
 
 ' Retrieve the current data by requerying the recordset 
 rstTitles.Requery 
 
 ' Print report of restored data using sub from below 
 Debug.Print "Data after executing the query to restore the original information " 
 PrintOutput rstTitles 
 
 ' clean up 
 rstTitles.Close 
 Cnxn.Close 
 Set rstTitles = Nothing 
 Set Cnxn = Nothing 
 Exit Sub 
 
Err_Execute: 
 ' Notify user of any errors that result from 
 ' executing the query 
 If rstTitles.ActiveConnection.Errors.Count >= 0 Then 
 For Each Err In rstTitles.ActiveConnection.Errors 
 MsgBox "Error number: " & Err.Number & vbCr & _ 
 Err.Description 
 Next Err 
 End If 
 
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
 
Public Sub ExecuteCommand(cmdTemp As ADODB.Command, rstTemp As ADODB.Recordset) 
 
 Dim Err As Error 
 
 ' Run the specified Command object and trap for 
 ' errors, checking the Errors collection 
 On Error GoTo Err_Execute 
 cmdTemp.Execute 
 On Error GoTo 0 
 
 ' Retrieve the current data by requerying the recordset 
 rstTemp.Requery 
 
 Exit Sub 
 
Err_Execute: 
 
 ' Notify user of any errors that result from 
 ' executing the query 
 If rstTemp.ActiveConnection.Errors.Count > 0 Then 
 For Each Err In rstTemp.ActiveConnection.Errors 
 MsgBox "Error number: " & Err.Number & vbCr & _ 
 Err.Description 
 Next Err 
 End If 
 
 Resume Next 
 
End Sub 
 
Public Sub PrintOutput(rstTemp As ADODB.Recordset) 
 
 ' Enumerate Recordset 
 Do While Not rstTemp.EOF 
 Debug.Print " " & rstTemp!Title & _ 
 ", " & rstTemp!Type 
 rstTemp.MoveNext 
 Loop 
 
End Sub 
'EndExecuteVB 
```

