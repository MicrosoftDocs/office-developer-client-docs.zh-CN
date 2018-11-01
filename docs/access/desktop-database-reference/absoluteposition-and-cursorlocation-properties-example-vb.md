---
title: AbsolutePosition 和 CursorLocation 属性示例 (VB)
TOCTitle: AbsolutePosition and CursorLocation properties example (VB)
ms:assetid: 572c1a51-b7f4-5861-cfb9-960219e0a831
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249293(v=office.15)
ms:contentKeyID: 48544966
ms.date: 10/17/2018
mtps_version: v=office.15
ms.openlocfilehash: b1fb72b167ad24d2d5ef7acd1472d435381428c8
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25869643"
---
# <a name="absoluteposition-and-cursorlocation-properties-example-vb"></a>AbsolutePosition 和 CursorLocation 属性示例 (VB)


**适用于**： Access 2013、 Office 2013

此示例演示 [AbsolutePosition](absoluteposition-property-ado.md) 属性如何跟踪枚举 [Recordset](recordset-object-ado.md) 的所有记录的循环的进度。它使用 [CursorLocation](cursorlocation-property-ado.md) 属性通过将游标设置为客户端游标来启用 **AbsolutePosition** 属性。

```vb 
 
'BeginAbsolutePositionVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 'recordset and connection variables 
 Dim rstEmployees As ADODB.Recordset 
 Dim Cnxn As ADODB.Connection 
 Dim strCnxn As String 
 Dim strSQL As String 
 'record variables 
 Dim strMessage As String 
 
 'Open connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' Open Employee recordset with 
 ' Client-side cursor to enable AbsolutePosition property 
 Set rstEmployees = New ADODB.Recordset 
 strSQL = "employee" 
 rstEmployees.Open strSQL, strCnxn, adUseClient, adLockReadOnly, adCmdTable 
 
 ' Enumerate Recordset 
 Do While Not rstEmployees.EOF 
 ' Display current record information 
 strMessage = "Employee: " & rstEmployees!lname & vbCr & _ 
 "(record " & rstEmployees.AbsolutePosition & _ 
 " of " & rstEmployees.RecordCount & ")" 
 If MsgBox(strMessage, vbOKCancel) = vbCancel Then Exit Do 
 rstEmployees.MoveNext 
 Loop 
 
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
'EndAbsolutePositionVB 
```

