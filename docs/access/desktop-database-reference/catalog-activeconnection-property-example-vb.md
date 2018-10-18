---
<<<<<<< 标头标题： 目录 ActiveConnection 属性示例 (VB) TOCTitle： 目录 ActiveConnection 属性示例 (VB) === 标题： 目录 ActiveConnection 属性示例 (VB) TOCTitle： 目录 ActiveConnection属性示例 (VB)
>>>>>>> 母版页 ms:assetid: 12a34091-e451-dbd1-e7f3-f794b84ee5b0 ms:mtpsurl: https://msdn.microsoft.com/library/JJ248901(v=office.15) ms:contentKeyID: 48543348 ms.date: 09/18/2015 mtps_version: office.15.aspx
---

<<<<<<< 标头
# <a name="catalog-activeconnection-property-example-vb"></a>Catalog 的 ActiveConnection 属性示例 (VB)
=======
# <a name="catalog-activeconnection-property-example-vb"></a>Catalog 的 ActiveConnection 属性示例 (VB)
>>>>>>> master

**适用于**： Access 2013 |Office 2013

将 [ActiveConnection](activeconnection-property-adox.md) 属性设置为有效的打开连接将"打开"目录。从打开的目录中，可以访问该目录中包含的架构对象。

```vb 
 
    ' BeginOpenConnectionVB 
    Sub OpenConnection() 
    On Error GoTo OpenConnectionError 
    
    Dim cnn As New ADODB.Connection 
    Dim cat As New ADOX.Catalog 
    
    cnn.Open "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
    "Data Source= 'c:\Program Files\Microsoft Office\" & _ 
    "Office\Samples\Northwind.mdb';" 
    Set cat.ActiveConnection = cnn 
    Debug.Print cat.Tables(0).Type 
    
    'Clean up 
    cnn.Close 
    Set cat = Nothing 
    Set cnn = Nothing 
    Exit Sub 
    
    OpenConnectionError: 
    
    Set cat = Nothing 
    
    If Not cnn Is Nothing Then 
    If cnn.State = adStateOpen Then cnn.Close 
    End If 
    Set cnn = Nothing 
    
    If Err <> 0 Then 
    MsgBox Err.Source & "-->" & Err.Description, , "Error" 
    End If 
    End Sub 
    ' EndOpenConnectionVB 
```

将 **ActiveConnection** 属性设置为有效连接字符串也可"打开"目录。

```vb
    ' BeginOpenConnection2VB 
    Sub Main() 
     On Error GoTo OpenConnectionWithStringError 
     Dim cat As New ADOX.Catalog 
     
     cat.ActiveConnection = "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
     "Data Source='c:\Program Files\Microsoft Office\" & _ 
     "Office\Samples\Northwind.mdb';" 
     Debug.Print cat.Tables(0).Type 
     
     'Clean up 
     Set cat.ActiveConnection = Nothing 
     Exit Sub 
     
    OpenConnectionWithStringError: 
     Set cat = Nothing 
     
     If Err <> 0 Then 
     MsgBox Err.Source & "-->" & Err.Description, , "Error" 
     End If 
    End Sub 
    ' EndOpenConnection2VB
```
