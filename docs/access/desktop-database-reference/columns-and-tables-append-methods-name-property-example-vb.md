---
<span data-ttu-id="17226-101"><<<<<<< 标头标题： 列和表格的 Append 方法，名称属性示例 (VB) TOCTitle： 列和表格的 Append 方法、 Name 属性示例 (VB) === 标题： 列和表格 Append 方法、 Name 属性示例 (VB)TOCTitle： 列和表格 Append 方法、 Name 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="17226-101"><<<<<<< HEAD title: Columns and Tables Append Methods, Name Property Example (VB) TOCTitle: Columns and Tables Append Methods, Name Property Example (VB) ======= title: Columns and Tables Append Methods, Name property example (VB) TOCTitle: Columns and Tables Append Methods, Name property example (VB)</span></span>
>>>>>>> <span data-ttu-id="17226-102">母版页 ms:assetid: 39458400-f30c-0636-19f2-c2c2788a6534 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249140(v=office.15) ms:contentKeyID: 48544238 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="17226-102">master ms:assetid: 39458400-f30c-0636-19f2-c2c2788a6534 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249140(v=office.15) ms:contentKeyID: 48544238 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="17226-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="17226-103"><<<<<<< HEAD</span></span>
# <a name="columns-and-tables-append-methods-name-property-example-vb"></a><span data-ttu-id="17226-104">Columns 和 Tables 的 Append 方法、Name 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="17226-104">Columns and Tables Append Methods, Name Property Example (VB)</span></span>
=======
# <a name="columns-and-tables-append-methods-name-property-example-vb"></a><span data-ttu-id="17226-105">Columns 和 Tables 的 Append 方法、 Name 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="17226-105">Columns and Tables Append Methods, Name property example (VB)</span></span>
>>>>>>> <span data-ttu-id="17226-106">master</span><span class="sxs-lookup"><span data-stu-id="17226-106">master</span></span>


<span data-ttu-id="17226-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="17226-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="17226-108">下面的代码演示如何创建新表。</span><span class="sxs-lookup"><span data-stu-id="17226-108">The following code demonstrates how to create a new table.</span></span>

```vb 
 
' BeginCreateTableVB 
Sub Main() 
 On Error GoTo CreateTableError 
 
 Dim tbl As New Table 
 Dim cat As New ADOX.Catalog 
 
 ' Open the Catalog. 
 cat.ActiveConnection = "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
 "Data Source='c:\Program Files\Microsoft Office\" & _ 
 "Office\Samples\Northwind.mdb';" 
 
 tbl.Name = "MyTable" 
 tbl.Columns.Append "Column1", adInteger 
 tbl.Columns.Append "Column2", adInteger 
 tbl.Columns.Append "Column3", adVarWChar, 50 
 cat.Tables.Append tbl 
 Debug.Print "Table 'MyTable' is added." 
 
 'Delete the table as this is a demonstration. 
 cat.Tables.Delete tbl.Name 
 Debug.Print "Table 'MyTable' is deleted." 
 
 'Clean up 
 Set cat.ActiveConnection = Nothing 
 Set cat = Nothing 
 Set tbl = Nothing 
 Exit Sub 
 
CreateTableError: 
 
 Set cat = Nothing 
 Set tbl = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
' EndCreateTableVB 
```

