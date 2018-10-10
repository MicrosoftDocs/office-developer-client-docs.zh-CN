---
title: ActiveConnection，CommandText，CommandTimeout 属性示例 (VB)
TOCTitle: ActiveConnection, CommandText, CommandTimeout, CommandType, Size, and Direction Properties Example (VB)
ms:assetid: dc869f6b-3c48-9fc8-ae3a-5850ed5d3274
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250116(v=office.15)
ms:contentKeyID: 48548140
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c07f7f7cb1522f95a7ce64d0bc8e6b976ed8065f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467241"
---
# <a name="activeconnection-commandtext-commandtimeout-commandtype-size-and-direction-properties-example-vb"></a><span data-ttu-id="cdf2e-102">ActiveConnection、CommandText、CommandTimeout、CommandType、Size 和 Direction 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="cdf2e-102">ActiveConnection, CommandText, CommandTimeout, CommandType, Size, and Direction Properties Example (VB)</span></span>


<span data-ttu-id="cdf2e-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="cdf2e-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="cdf2e-104">此示例使用 [ActiveConnection](activeconnection-property-ado.md)、[CommandText](commandtext-property-ado.md)、[CommandTimeout](commandtimeout-property-ado.md)、[CommandType](commandtype-property-ado.md)、[Size](size-property-ado.md) 和 [Direction](direction-property-ado.md) 属性来执行存储过程。</span><span class="sxs-lookup"><span data-stu-id="cdf2e-104">This example uses the [ActiveConnection](activeconnection-property-ado.md), [CommandText](commandtext-property-ado.md), [CommandTimeout](commandtimeout-property-ado.md), [CommandType](commandtype-property-ado.md), [Size](size-property-ado.md), and [Direction](direction-property-ado.md) properties to execute a stored procedure.</span></span>

```vb 
 
'BeginActiveConnectionVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 'recordset, command and connection variables 
 Dim Cnxn As ADODB.Connection 
 Dim cmdByRoyalty As ADODB.Command 
 Dim prmByRoyalty As ADODB.Parameter 
 Dim rstByRoyalty As ADODB.Recordset 
 Dim rstAuthors As ADODB.Recordset 
 Dim strCnxn As String 
 Dim strSQLAuthors As String 
 Dim strSQLByRoyalty As String 
 'record variables 
 Dim intRoyalty As Integer 
 Dim strAuthorID As String 
 
 ' Define a command object for a stored procedure 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 Set cmdByRoyalty = New ADODB.Command 
 Set cmdByRoyalty.ActiveConnection = Cnxn 
 ' Set the criteria 
 strSQLByRoyalty = "byroyalty" 
 cmdByRoyalty.CommandText = strSQLByRoyalty 
 cmdByRoyalty.CommandType = adCmdStoredProc 
 cmdByRoyalty.CommandTimeout = 15 
 
 ' Define the stored procedure's input parameter 
 intRoyalty = Trim(InputBox("Enter royalty:")) 
 Set prmByRoyalty = New ADODB.Parameter 
 prmByRoyalty.Type = adInteger 
 prmByRoyalty.Size = 3 
 prmByRoyalty.Direction = adParamInput 
 prmByRoyalty.Value = intRoyalty 
 
 cmdByRoyalty.Parameters.Append prmByRoyalty 
 
 ' Create a recordset by executing the command. 
 Set rstByRoyalty = cmdByRoyalty.Execute() 
 
 ' Open the Authors Table to get author names for display 
 Set rstAuthors = New ADODB.Recordset 
 strSQLAuthors = "Authors" 
 
 'rstAuthors.Open strSQLAuthors, strCnxn, , , adCmdTable 
 rstAuthors.Open strSQLAuthors, strCnxn, adOpenForwardOnly, adLockReadOnly, adCmdTable 
 'the above two lines of code are identical as the default values for 
 'CursorType and LockType arguments match those shown 
 
 ' Print the recordset and add author names from Table 
 Debug.Print "Authors with " & intRoyalty & _ 
 " percent royalty" 
 
 Do Until rstByRoyalty.EOF 
 strAuthorID = rstByRoyalty!au_id 
 Debug.Print , rstByRoyalty!au_id & ", "; 
 rstAuthors.Filter = "au_id = '" & strAuthorID & "'" 
 Debug.Print rstAuthors!au_fname & " " & _ 
 rstAuthors!au_lname 
 rstByRoyalty.MoveNext 
 Loop 
 
 ' clean up 
 rstAuthors.Close 
 rstByRoyalty.Close 
 Cnxn.Close 
 Set rstAuthors = Nothing 
 Set rstByRoyalty = Nothing 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rstAuthors Is Nothing Then 
 If rstAuthors.State = adStateOpen Then rstAuthors.Close 
 End If 
 Set rstAuthors = Nothing 
 
 If Not rstByRoyalty Is Nothing Then 
 If rstByRoyalty.State = adStateOpen Then rstByRoyalty.Close 
 End If 
 Set rstByRoyalty = Nothing 
 
 If Not Cnxn Is Nothing Then 
 If Cnxn.State = adStateOpen Then Cnxn.Close 
 End If 
 Set Cnxn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndActiveConnectionVB 
```

