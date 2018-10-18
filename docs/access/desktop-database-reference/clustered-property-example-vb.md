---
<<<<<<< 标头标题： 群集属性示例 (VB) TOCTitle： 群集属性示例 (VB) === 标题： Clustered 的属性示例 (VB) TOCTitle: Clustered 的属性示例 (VB)
>>>>>>> 母版页 ms:assetid: 1065622d-9473-209a-95be-c4b0ab5b687a ms:mtpsurl: https://msdn.microsoft.com/library/JJ248872(v=office.15) ms:contentKeyID: 48543293 ms.date: 09/18/2015 mtps_version: office.15.aspx
---

<<<<<<< 标头
# <a name="clustered-property-example-vb"></a>Clustered 属性示例 (VB)
=======
# <a name="clustered-property-example-vb"></a>Clustered 的属性示例 (VB)
>>>>>>> master


**适用于**： Access 2013 |Office 2013

本示例演示 [Index](clustered-property-adox.md) 的 [Clustered](index-object-adox.md) 属性。 请注意，Microsoft Jet 数据库不支持聚簇的索引，因此本示例将返回**False**的**Clustered**属性的*Northwind*数据库中的所有索引。

```vb 
 
' BeginClusteredVB 
Sub Main() 
 On Error GoTo ClusteredXError 
 
 Dim cnn As New ADODB.Connection 
 Dim cat As New ADOX.Catalog 
 Dim tblLoop As ADOX.Table 
 Dim idxLoop As ADOX.Index 
 Dim strCnn As String 
 
 strCnn = "Provider='SQLOLEDB';Data Source='MySqlServer';Initial Catalog='pubs';" & _ 
 "Integrated Security='SSPI';" 
 ' Connect the catalog. 
 cnn.Open strCnn 
 cat.ActiveConnection = cnn 
 
 ' Enumerate Tables 
 For Each tblLoop In cat.Tables 
 'Enumerate Indexes 
 For Each idxLoop In tblLoop.Indexes 
 Debug.Print tblLoop.Name & " " & _ 
 idxLoop.Name & " " & idxLoop.Clustered 
 Next idxLoop 
 Next tblLoop 
 
 'Clean up 
 cnn.Close 
 Set cat = Nothing 
 Set cnn = Nothing 
 Exit Sub 
 
ClusteredXError: 
 
 Set cat = Nothing 
 
 If Not cnn Is Nothing Then 
 If cnn.State = adStateOpen Then cnn.Close 
 End If 
 Set cnn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
' EndClusteredVB 
```

