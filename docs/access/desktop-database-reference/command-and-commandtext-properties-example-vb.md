---
<span data-ttu-id="6d1ba-101"><<<<<<< 标头标题： Command 和 CommandText 属性示例 (VB) TOCTitle： 命令和 CommandText 属性示例 (VB) === 标题： Command 和 CommandText 属性示例 (VB) TOCTitle: Command 和 CommandText属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="6d1ba-101"><<<<<<< HEAD title: Command and CommandText Properties Example (VB) TOCTitle: Command and CommandText Properties Example (VB) ======= title: Command and CommandText properties example (VB) TOCTitle: Command and CommandText properties example (VB)</span></span>
>>>>>>> <span data-ttu-id="6d1ba-102">母版页 ms:assetid: 6bf35604-401b-0727-85e8-ac2ecda368df ms:mtpsurl: https://msdn.microsoft.com/library/JJ249425(v=office.15) ms:contentKeyID: 48545462 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="6d1ba-102">master ms:assetid: 6bf35604-401b-0727-85e8-ac2ecda368df ms:mtpsurl: https://msdn.microsoft.com/library/JJ249425(v=office.15) ms:contentKeyID: 48545462 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="6d1ba-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="6d1ba-103"><<<<<<< HEAD</span></span>
# <a name="command-and-commandtext-properties-example-vb"></a><span data-ttu-id="6d1ba-104">Command 和 CommandText 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="6d1ba-104">Command and CommandText Properties Example (VB)</span></span>
=======
# <a name="command-and-commandtext-properties-example-vb"></a><span data-ttu-id="6d1ba-105">Command 和 CommandText 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="6d1ba-105">Command and CommandText properties example (VB)</span></span>
>>>>>>> <span data-ttu-id="6d1ba-106">master</span><span class="sxs-lookup"><span data-stu-id="6d1ba-106">master</span></span>


<span data-ttu-id="6d1ba-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="6d1ba-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="6d1ba-108">下面的代码演示如何使用 [Command](command-property-adox.md) 属性更新过程的文本。</span><span class="sxs-lookup"><span data-stu-id="6d1ba-108">The following code demonstrates how to use the [Command](command-property-adox.md) property to update the text of a procedure.</span></span>

```vb 
 
' BeginProcedureTextVB 
Sub Main() 
 On Error GoTo ProcedureTextError 
 
 Dim cnn As New ADODB.Connection 
 Dim cat As New ADOX.Catalog 
 Dim cmd As New ADODB.Command 
 
 ' Open the Connection 
 cnn.Open "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
 "Data Source='c:\Program Files\Microsoft Office\" & _ 
 "Office\Samples\Northwind.mdb';" 
 
 ' Open the catalog 
 Set cat.ActiveConnection = cnn 
 
 ' Get the Command 
 Set cmd = cat.Procedures("CustomerById").Command 
 
 ' Update the CommandText 
 cmd.CommandText = "Select CustomerId, CompanyName, ContactName " & _ 
 "From Customers " & _ 
 "Where CustomerId = [CustId]" 
 
 ' Update the Procedure 
 Set cat.Procedures("CustomerById").Command = cmd 
 
 'Clean up 
 cnn.Close 
 Set cat = Nothing 
 Set cmd = Nothing 
 Set cnn = Nothing 
 Exit Sub 
 
ProcedureTextError: 
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
' EndProcedureTextVB 
```

