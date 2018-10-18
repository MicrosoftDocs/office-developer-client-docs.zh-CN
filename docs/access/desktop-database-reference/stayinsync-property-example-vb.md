---
<<<<<<< 标头标题： StayInSync 属性示例 (VB) TOCTitle: StayInSync 属性示例 (VB) === 标题： StayInSync 属性示例 (VB) TOCTitle: StayInSync 属性示例 (VB)
>>>>>>> 母版页 ms:assetid: 1b35f19a-0104-efd5-5222-55f92e08473b ms:mtpsurl: https://msdn.microsoft.com/library/JJ248952(v=office.15) ms:contentKeyID: 48543535 ms.date: 09/18/2015 mtps_version: office.15.aspx
---

<<<<<<< 标头
# <a name="stayinsync-property-example-vb"></a>StayInSync 属性示例 (VB)
=======
# <a name="stayinsync-property-example-vb"></a>StayInSync 属性示例 (VB)
>>>>>>> master


**适用于**： Access 2013 |Office 2013

本示例演示 [StayInSync](stayinsync-property-ado.md) 属性如何帮助访问分级 [Recordset](recordset-object-ado.md) 中的行。

外部循环显示每个作者的姓名、状态和 ID。每行的追加 **Recordset** 检索自 [Fields](fields-collection-ado.md) 集合并在父 **Recordset** 移至新行时通过 **StayInSync** 属性自动赋值给 **rstTitleAuthor** 。内部循环显示追加的记录集中每行的四个字段。

```vb 
 
'BeginStayInSyncVB 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 'To integrate this code create a DSN called Pubs 
 'with a user_id = sa and no password 
 
 Dim Cnxn As ADODB.Connection 
 Dim rst As ADODB.Recordset 
 Dim rstTitleAuthor As New ADODB.Recordset 
 Dim strCnxn As String 
 
 ' open connection with Data Shape attributes 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider=MSDataShape;Data Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' create recordset 
 Set rst = New ADODB.Recordset 
 rst.StayInSync = True 
 rst.Open "SHAPE {select * from Authors} " & _ 
 "APPEND ( { select * from titleauthor} AS chapTitleAuthor " & _ 
 "RELATE au_id TO au_id) ", Cnxn, , , adCmdText 
 
 Set rstTitleAuthor = rst("chapTitleAuthor").Value 
 Do Until rst.EOF 
 Debug.Print rst!au_fname & " " & rst!au_lname & " " & _ 
 rst!State & " " & rst!au_id 
 
 Do Until rstTitleAuthor.EOF 
 Debug.Print rstTitleAuthor(0) & " " & rstTitleAuthor(1) & " " & _ 
 rstTitleAuthor(2) & " " & rstTitleAuthor(3) 
 rstTitleAuthor.MoveNext 
 Loop 
 
 rst.MoveNext 
 Loop 
 
 ' clean up 
 rst.Close 
 Cnxn.Close 
 Set rst = Nothing 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rst Is Nothing Then 
 If rst.State = adStateOpen Then rst.Close 
 End If 
 Set rst = Nothing 
 
 If Not Cnxn Is Nothing Then 
 If Cnxn.State = adStateOpen Then Cnxn.Close 
 End If 
 Set Cnxn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndStayInSyncVB 
```

