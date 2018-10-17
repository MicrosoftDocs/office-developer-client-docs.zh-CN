---
title: Type 属性示例 (Field) (VB)
TOCTitle: Type Property Example (Field) (VB)
ms:assetid: ff9e26a8-898d-ec89-5093-69c66dbb05ba
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250314(v=office.15)
ms:contentKeyID: 48548966
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0206bf366cfa5ef21e1816a2dba2eaad8dbe67ab
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468002"
---
# <a name="type-property-example-field-vb"></a><span data-ttu-id="111b4-102">Type 属性示例 (Field) (VB)</span><span class="sxs-lookup"><span data-stu-id="111b4-102">Type Property Example (Field) (VB)</span></span>


<span data-ttu-id="111b4-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="111b4-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="111b4-p101">此示例通过显示与 ***Employees***（雇员）表中的所有 [Field](field-object-ado.md) 对象的 [Type](type-property-ado.md) 属性值对应的常量名称来演示 [Type](type-property-ado.md) 属性。若要运行此过程，必须使用 FieldType 函数。</span><span class="sxs-lookup"><span data-stu-id="111b4-p101">This example demonstrates the [Type](type-property-ado.md) property by displaying the name of the constant that corresponds to the value of the [Type](type-property-ado.md) property of all the [Field](field-object-ado.md) objects in the ***Employees*** table. The FieldType function is required for this procedure to run.</span></span>

```vb 
 
'BeginTypeFieldVB 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
 Dim Cnxn As ADODB.Connection 
 Dim rstEmployees As ADODB.Recordset 
 Dim fld As ADODB.Field 
 Dim strCnxn As String 
 Dim strSQLEmployee As String 
 Dim FieldType As String 
 
 ' Open connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' Open recordset with data from Employees table 
 Set rstEmployees = New ADODB.Recordset 
 strSQLEmployee = "employee" 
 rstEmployees.Open strSQLEmployee, Cnxn, , , adCmdTable 
 'rstEmployees.Open strSQLEmployee, Cnxn, adOpenStatic, adLockReadOnly, adCmdTable 
 ' the above two lines of code are identical 
 
 Debug.Print "Fields in Employees Table:" & vbCr 
 
 ' Enumerate Fields collection of Employees table 
 For Each fld In rstEmployees.Fields 
 ' translate field-type code to text 
 Select Case fld.Type 
 Case adChar 
 FieldType = "adChar" 
 Case adVarChar 
 FieldType = "adVarChar" 
 Case adSmallInt 
 FieldType = "adSmallInt" 
 Case adUnsignedTinyInt 
 FieldType = "adUnsignedTinyInt" 
 Case adDBTimeStamp 
 FieldType = "adDBTimeStamp" 
 End Select 
 ' show results 
 Debug.Print " Name: " & fld.Name & vbCr & _ 
 " Type: " & FieldType & vbCr 
 Next fld 
 
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
 
 Set fld = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndTypeFieldVB 
```
