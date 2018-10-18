---
<<<<<<< 标头标题： Parameters 集合、 命令属性示例 (VB) TOCTitle: Parameters 集合、 命令属性示例 (VB) === 标题： Parameters 集合与 Command 属性示例 (VB) TOCTitle： 参数集合与 Command 属性示例 (VB)
>>>>>>> 母版页 ms:assetid: 3bb3e6e1-0ee5-70bb-7f2c-beb461d3914a ms:mtpsurl: https://msdn.microsoft.com/library/JJ249151(v=office.15) ms:contentKeyID: 48544290 ms.date: 09/18/2015 mtps_version: office.15.aspx
---

<<<<<<< 标头
# <a name="parameters-collection-command-property-example-vb"></a>Parameters 集合与 Command 属性示例 (VB)
=======
# <a name="parameters-collection-command-property-example-vb"></a>Parameters 集合与 Command 属性示例 (VB)
>>>>>>> master


**适用于**： Access 2013 |Office 2013

下面的代码演示如何将 [Command](command-property-adox.md) 属性与 [Command](command-object-ado.md) 对象结合使用，以检索过程的参数信息。

```vb 
 
' BeginParametersVB 
Sub Main() 
 On Error GoTo ProcedureParametersError 
 
 Dim cnn As New ADODB.Connection 
 Dim cmd As ADODB.Command 
 Dim prm As ADODB.Parameter 
 Dim cat As New ADOX.Catalog 
 
 ' Open the Connection 
 cnn.Open _ 
 "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
 "Data Source='c:\Program Files\Microsoft Office\" & _ 
 "Office\Samples\Northwind.mdb';" 
 
 ' Open the catalog 
 Set cat.ActiveConnection = cnn 
 
 ' Get the command object 
 Set cmd = cat.Procedures("CustomerById").Command 
 
 ' Retrieve Parameter information 
 cmd.Parameters.Refresh 
 For Each prm In cmd.Parameters 
 Debug.Print prm.Name & ":" & prm.Type 
 Next 
 
 'Clean up 
 cnn.Close 
 Set cat = Nothing 
 Set cmd = Nothing 
 Set cnn = Nothing 
 Exit Sub 
 
ProcedureParametersError: 
 
 Set cat = Nothing 
 Set cmd = Nothing 
 
 If Not cnn Is Nothing Then 
 If cnn.State = adStateOpen Then cnn.Close 
 End If 
 Set cnn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
' EndParametersVB 
```

