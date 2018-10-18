---
<span data-ttu-id="8736b-101"><<<<<<< 标头标题： 群集属性示例 (VB) TOCTitle： 群集属性示例 (VB) === 标题： Clustered 的属性示例 (VB) TOCTitle: Clustered 的属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="8736b-101"><<<<<<< HEAD title: Clustered Property Example (VB) TOCTitle: Clustered Property Example (VB) ======= title: Clustered property example (VB) TOCTitle: Clustered property example (VB)</span></span>
>>>>>>> <span data-ttu-id="8736b-102">母版页 ms:assetid: 1065622d-9473-209a-95be-c4b0ab5b687a ms:mtpsurl: https://msdn.microsoft.com/library/JJ248872(v=office.15) ms:contentKeyID: 48543293 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="8736b-102">master ms:assetid: 1065622d-9473-209a-95be-c4b0ab5b687a ms:mtpsurl: https://msdn.microsoft.com/library/JJ248872(v=office.15) ms:contentKeyID: 48543293 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="8736b-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="8736b-103"><<<<<<< HEAD</span></span>
# <a name="clustered-property-example-vb"></a><span data-ttu-id="8736b-104">Clustered 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="8736b-104">Clustered Property Example (VB)</span></span>
=======
# <a name="clustered-property-example-vb"></a><span data-ttu-id="8736b-105">Clustered 的属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="8736b-105">Clustered property example (VB)</span></span>
>>>>>>> <span data-ttu-id="8736b-106">master</span><span class="sxs-lookup"><span data-stu-id="8736b-106">master</span></span>


<span data-ttu-id="8736b-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="8736b-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="8736b-108">本示例演示 [Index](clustered-property-adox.md) 的 [Clustered](index-object-adox.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="8736b-108">This example demonstrates the [Clustered](clustered-property-adox.md) property of an [Index](index-object-adox.md).</span></span> <span data-ttu-id="8736b-109">请注意，Microsoft Jet 数据库不支持聚簇的索引，因此本示例将返回**False**的**Clustered**属性的*Northwind*数据库中的所有索引。</span><span class="sxs-lookup"><span data-stu-id="8736b-109">Note that Microsoft Jet databases do not support clustered indexes, so this example will return **False** for the **Clustered** property of all indexes in the *Northwind* database.</span></span>

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

