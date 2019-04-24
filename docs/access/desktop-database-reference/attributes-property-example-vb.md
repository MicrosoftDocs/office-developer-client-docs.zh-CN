---
title: Attributes 属性示例 (VB)
TOCTitle: Attributes property example (VB)
ms:assetid: bda5e445-6425-5daf-b182-b6f5ea044b04
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249918(v=office.15)
ms:contentKeyID: 48547442
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4d324ae976693e635222d2b8d4b4d4571c182fa6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296953"
---
# <a name="attributes-property-example-vb"></a><span data-ttu-id="0db9b-102">Attributes 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="0db9b-102">Attributes property example (VB)</span></span>


<span data-ttu-id="0db9b-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="0db9b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0db9b-p101">本示例演示 [Column](attributes-property-adox.md) 的 [Attributes](column-object-adox.md) 属性。将其设置为 **adColNullable** 将使用户可以把 [Recordset](recordset-object-ado.md)[Field](field-object-ado.md) 的值设置为空字符串。在这种情况下，用户可区分数据未知的记录和未应用数据的记录。</span><span class="sxs-lookup"><span data-stu-id="0db9b-p101">This example demonstrates the [Attributes](attributes-property-adox.md) property of a [Column](column-object-adox.md). Setting it to **adColNullable** allows the user to set the value of a [Recordset](recordset-object-ado.md)[Field](field-object-ado.md) to an empty string. In this situation, the user can distinguish between a record where data is not known and a record where the data does not apply.</span></span>

```vb 
 
' BeginAttributesVB 
Sub Main() 
 On Error GoTo AttributesXError 
 
 Dim cnn As New ADODB.Connection 
 Dim cat As New ADOX.Catalog 
 Dim colTemp As New ADOX.Column 
 Dim rstEmployees As New Recordset 
 Dim strMessage As String 
 Dim strInput As String 
 Dim tblEmp As ADOX.Table 
 
 ' Connect the catalog. 
 cnn.Open "Provider='Microsoft.Jet.OLEDB.4.0';data source=" & _ 
 "'c:\Program Files\Microsoft Office\Office\Samples\Northwind.mdb';" 
 Set cat.ActiveConnection = cnn 
 
 Set tblEmp = cat.Tables("Employees") 
 
 ' Create a new Field object and append it to the Fields 
 ' collection of the Employees table. 
 colTemp.Name = "FaxPhone" 
 colTemp.Type = adVarWChar 
 colTemp.DefinedSize = 24 
 colTemp.Attributes = adColNullable 
 cat.Tables("Employees").Columns.Append colTemp.Name, adWChar, 24 
 
 ' Open the Employees table for updating as a Recordset 
 rstEmployees.Open "Employees", cnn, adOpenKeyset, adLockOptimistic, adCmdTable 
 
 With rstEmployees 
 ' Get user input. 
 strMessage = "Enter fax number for " & _ 
 !FirstName & " " & !LastName & "." & vbCr & _ 
 "[? - unknown, X - has no fax]" 
 strInput = UCase(InputBox(strMessage)) 
 If strInput <> "" Then 
 Select Case strInput 
 Case "?" 
 !FaxPhone = Null 
 Case "X" 
 !FaxPhone = "" 
 Case Else 
 !FaxPhone = strInput 
 End Select 
 .Update 
 
 ' Print report. 
 Debug.Print "Name - Fax number" 
 Debug.Print !FirstName & " " & !LastName & " - "; 
 
 If IsNull(!FaxPhone) Then 
 Debug.Print "[Unknown]" 
 Else 
 If !FaxPhone = "" Then 
 Debug.Print "[Has no fax]" 
 Else 
 Debug.Print !FaxPhone 
 End If 
 End If 
 
 End If 
 
 .Close 
 End With 
 
 'Clean up 
 tblEmp.Columns.Delete colTemp.Name 
 cnn.Close 
 Set rstEmployees = Nothing 
 Set cat = Nothing 
 Set colTemp = Nothing 
 Set cnn = Nothing 
 Exit Sub 
 
AttributesXError: 
 
 If Not rstEmployees Is Nothing Then 
 If rstEmployees.State = adStateOpen Then rstEmployees.Close 
 End If 
 Set rstEmployees = Nothing 
 
 If Not tblEmp Is Nothing Then tblEmp.Columns.Delete colTemp.Name 
 
 Set cat = Nothing 
 Set colTemp = Nothing 
 
 If Not cnn Is Nothing Then 
 If cnn.State = adStateOpen Then cnn.Close 
 End If 
 Set cnn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
 
End Sub 
' EndAttributesVB 
```

