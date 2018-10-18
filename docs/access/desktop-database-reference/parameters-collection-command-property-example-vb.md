---
<span data-ttu-id="b58fe-101"><<<<<<< 标头标题： Parameters 集合、 命令属性示例 (VB) TOCTitle: Parameters 集合、 命令属性示例 (VB) === 标题： Parameters 集合与 Command 属性示例 (VB) TOCTitle： 参数集合与 Command 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="b58fe-101"><<<<<<< HEAD title: Parameters Collection, Command Property Example (VB) TOCTitle: Parameters Collection, Command Property Example (VB) ======= title: Parameters Collection, Command property example (VB) TOCTitle: Parameters Collection, Command property example (VB)</span></span>
>>>>>>> <span data-ttu-id="b58fe-102">母版页 ms:assetid: 3bb3e6e1-0ee5-70bb-7f2c-beb461d3914a ms:mtpsurl: https://msdn.microsoft.com/library/JJ249151(v=office.15) ms:contentKeyID: 48544290 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="b58fe-102">master ms:assetid: 3bb3e6e1-0ee5-70bb-7f2c-beb461d3914a ms:mtpsurl: https://msdn.microsoft.com/library/JJ249151(v=office.15) ms:contentKeyID: 48544290 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="b58fe-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="b58fe-103"><<<<<<< HEAD</span></span>
# <a name="parameters-collection-command-property-example-vb"></a><span data-ttu-id="b58fe-104">Parameters 集合与 Command 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="b58fe-104">Parameters Collection, Command Property Example (VB)</span></span>
=======
# <a name="parameters-collection-command-property-example-vb"></a><span data-ttu-id="b58fe-105">Parameters 集合与 Command 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="b58fe-105">Parameters Collection, Command property example (VB)</span></span>
>>>>>>> <span data-ttu-id="b58fe-106">master</span><span class="sxs-lookup"><span data-stu-id="b58fe-106">master</span></span>


<span data-ttu-id="b58fe-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="b58fe-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="b58fe-108">下面的代码演示如何将 [Command](command-property-adox.md) 属性与 [Command](command-object-ado.md) 对象结合使用，以检索过程的参数信息。</span><span class="sxs-lookup"><span data-stu-id="b58fe-108">The following code demonstrates how to use the [Command](command-property-adox.md) property with the [Command](command-object-ado.md) object to retrieve parameter information for the procedure.</span></span>

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

