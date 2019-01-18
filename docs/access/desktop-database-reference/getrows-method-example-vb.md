---
title: GetRows 方法示例 (VB)
TOCTitle: GetRows method example (VB)
ms:assetid: 5a4e03de-0c89-ed93-7fe8-685906878e60
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249311(v=office.15)
ms:contentKeyID: 48545041
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 27bdc82b1ea8cd3fc019b036de98a921dd7bc9bb
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28698699"
---
# <a name="getrows-method-example-vb"></a><span data-ttu-id="0c7a5-102">GetRows 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="0c7a5-102">GetRows method example (VB)</span></span>


<span data-ttu-id="0c7a5-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="0c7a5-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0c7a5-p101">以下示例使用 [GetRows](getrows-method-ado.md) 方法从 [Recordset](recordset-object-ado.md) 中检索指定行数，并使用生成的数据填充数组。 **GetRows** 方法在以下两种情况下返回的行数少于所需的行数：已到达 [EOF](bof-eof-properties-ado.md)，或 **GetRows** 尝试检索已被其他用户删除的记录。只有当发生第二种情况时，函数才返回 **False**。若要使该过程运行，需要使用 GetRowsOK 函数。</span><span class="sxs-lookup"><span data-stu-id="0c7a5-p101">This example uses the [GetRows](getrows-method-ado.md) method to retrieve a specified number of rows from a [Recordset](recordset-object-ado.md) and to fill an array with the resulting data. The **GetRows** method will return fewer than the desired number of rows in two cases: either if [EOF](bof-eof-properties-ado.md) has been reached, or if **GetRows** tried to retrieve a record that was deleted by another user. The function returns **False** only if the second case occurs. The GetRowsOK function is required for this procedure to run.</span></span>

```vb 
 
'BeginGetRowsVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 ' connection and recordset variables 
 Dim rstEmployees As ADODB.Recordset 
 Dim Cnxn As ADODB.Connection 
 Dim strSQLEmployees As String 
 Dim strCnxn As String 
 ' array variable 
 Dim arrEmployees As Variant 
 ' detail variables 
 Dim strMessage As String 
 Dim intRows As Integer 
 Dim intRecord As Integer 
 
 ' open connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' open recordset client-side to enable RecordCount 
 Set rstEmployees = New ADODB.Recordset 
 strSQLEmployees = "SELECT fName, lName, hire_date FROM Employee ORDER BY lName" 
 rstEmployees.Open strSQLEmployees, Cnxn, adOpenStatic, adLockReadOnly, adCmdText 
 
 ' get user input for number of rows 
 Do 
 strMessage = "Enter number of rows to retrieve:" 
 intRows = Val(InputBox(strMessage)) 
 
 ' if bad user input exit the loop 
 If intRows <= 0 Then 
 MsgBox "Please enter a positive number", vbOKOnly, "Not less than zero!" 
 ' if number of requested records is over the total 
 ElseIf intRows > rstEmployees.RecordCount Then 
 MsgBox "Not enough records in Recordset to retrieve " & intRows & " rows.", _ 
 vbOKOnly, "Over the available total" 
 Else 
 Exit Do 
 End If 
 Loop 
 
 ' else put the data in an array and print 
 arrEmployees = rstEmployees.GetRows(intRows) 
 
 Dim x As Integer, y As Integer 
 
 For x = 0 To intRows - 1 
 For y = 0 To 2 
 Debug.Print arrEmployees(y, x) & " "; 
 Next y 
 Debug.Print vbCrLf 
 Next x 
 
 ' clean up 
 rstEmployees.Close 
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
'EndGetRowsVB 
```

