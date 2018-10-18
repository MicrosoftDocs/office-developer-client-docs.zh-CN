---
<span data-ttu-id="50c23-101"><<<<<<< 标头标题： Keys 的 Append 方法，密钥类型 RelatedColumn 属性示例 (VB) TOCTitle: Keys 的 Append 方法、 密钥类型、 RelatedColumn、 RelatedTable 和 UpdateRule 属性示例 (VB) === 标题： Keys 的 Append 方法、 键类型、 RelatedColumn 属性示例 (VB) TOCTitle: Keys 的 Append 方法、 密钥类型、 RelatedColumn、 RelatedTable 和 UpdateRule 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="50c23-101"><<<<<<< HEAD title: Keys Append Method, Key Type, RelatedColumn Properties Example (VB) TOCTitle: Keys Append Method, Key Type, RelatedColumn, RelatedTable and UpdateRule Properties Example (VB) ======= title: Keys Append Method, Key Type, RelatedColumn properties example (VB) TOCTitle: Keys Append Method, Key Type, RelatedColumn, RelatedTable and UpdateRule properties example (VB)</span></span>
>>>>>>> <span data-ttu-id="50c23-102">母版页 ms:assetid: d1b0508d-ab2c-eece-061c-09c67ea9ecae ms:mtpsurl: https://msdn.microsoft.com/library/JJ250047(v=office.15) ms:contentKeyID: 48547871 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="50c23-102">master ms:assetid: d1b0508d-ab2c-eece-061c-09c67ea9ecae ms:mtpsurl: https://msdn.microsoft.com/library/JJ250047(v=office.15) ms:contentKeyID: 48547871 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="50c23-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="50c23-103"><<<<<<< HEAD</span></span>
# <a name="keys-append-method-key-type-relatedcolumn-relatedtable-and-updaterule-properties-example-vb"></a><span data-ttu-id="50c23-104">Keys 的 Append 方法、Key 的 Type、RelatedColumn、RelatedTable 和 UpdateRule 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="50c23-104">Keys Append Method, Key Type, RelatedColumn, RelatedTable and UpdateRule Properties Example (VB)</span></span>
=======
# <a name="keys-append-method-key-type-relatedcolumn-relatedtable-and-updaterule-properties-example-vb"></a><span data-ttu-id="50c23-105">Keys 的 Append 方法，密钥类型 RelatedColumn、 RelatedTable 和 UpdateRule 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="50c23-105">Keys Append Method, Key Type, RelatedColumn, RelatedTable and UpdateRule properties example (VB)</span></span>
>>>>>>> <span data-ttu-id="50c23-106">master</span><span class="sxs-lookup"><span data-stu-id="50c23-106">master</span></span>


<span data-ttu-id="50c23-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="50c23-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="50c23-108">下面的代码演示如何创建新的外键。</span><span class="sxs-lookup"><span data-stu-id="50c23-108">The following code demonstrates how to create a new foreign key.</span></span> <span data-ttu-id="50c23-109">该示例假定存在两个表 （**客户**和**订单**）。</span><span class="sxs-lookup"><span data-stu-id="50c23-109">It assumes two tables (**Customers** and **Orders**) exist.</span></span>

```vb 
 
' BeginCreateKeyVB 
Sub Main() 
 On Error GoTo CreateKeyError 
 
 Dim kyForeign As New ADOX.Key 
 Dim cat As New ADOX.Catalog 
 
 ' Connect the catalog 
 cat.ActiveConnection = "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
 "Data Source='c:\Program Files\Microsoft Office\" & _ 
 "Office\Samples\Northwind.mdb';" 
 
 ' Define the foreign key 
 kyForeign.Name = "CustOrder" 
 kyForeign.Type = adKeyForeign 
 kyForeign.RelatedTable = "Customers" 
 kyForeign.Columns.Append "CustomerId" 
 kyForeign.Columns("CustomerId").RelatedColumn = "CustomerId" 
 kyForeign.UpdateRule = adRICascade 
 
 ' Append the foreign key 
 cat.Tables("Orders").Keys.Append kyForeign 
 
 'Delete the Key as this is a demonstration 
 cat.Tables("Orders").Keys.Delete kyForeign.Name 
 
 'Clean up 
 Set cat.ActiveConnection = Nothing 
 Set cat = Nothing 
 Set kyForeign = Nothing 
 Exit Sub 
 
CreateKeyError: 
 Set cat = Nothing 
 Set kyForeign = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
 
End Sub 
' EndCreateKeyVB 
```

