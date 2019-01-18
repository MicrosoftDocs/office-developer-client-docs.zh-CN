---
title: Columns 和 Tables 的 Append 方法、 Name 属性示例 (VB)
TOCTitle: Columns and Tables Append Methods, Name property example (VB)
ms:assetid: 39458400-f30c-0636-19f2-c2c2788a6534
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249140(v=office.15)
ms:contentKeyID: 48544238
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d68078c24f2bee9f935b71d60cb15986d26d00ac
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28721519"
---
# <a name="columns-and-tables-append-methods-name-property-example-vb"></a><span data-ttu-id="016de-102">Columns 和 Tables 的 Append 方法、 Name 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="016de-102">Columns and Tables Append Methods, Name property example (VB)</span></span>


<span data-ttu-id="016de-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="016de-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="016de-104">下面的代码演示如何创建新表。</span><span class="sxs-lookup"><span data-stu-id="016de-104">The following code demonstrates how to create a new table.</span></span>

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

