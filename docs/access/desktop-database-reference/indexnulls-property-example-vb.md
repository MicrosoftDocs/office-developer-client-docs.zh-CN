---
title: IndexNulls 属性示例 (VB)
TOCTitle: IndexNulls Property Example (VB)
ms:assetid: 69b5661c-931e-3a1c-d60e-96a0f93b9494
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249414(v=office.15)
ms:contentKeyID: 48545417
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f35220f3c9426686a452e184330b8704fabb961a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468718"
---
# <a name="indexnulls-property-example-vb"></a><span data-ttu-id="e01b4-102">IndexNulls 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="e01b4-102">IndexNulls Property Example (VB)</span></span>

<span data-ttu-id="e01b4-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="e01b4-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="e01b4-104">本示例演示 [Index](indexnulls-property-adox.md) 的 [IndexNulls](index-object-adox.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="e01b4-104">This example demonstrates the [IndexNulls](indexnulls-property-adox.md) property of an [Index](index-object-adox.md).</span></span> <span data-ttu-id="e01b4-105">代码创建新的索引，并根据用户输入（来自名为 List1 的列表框）设置 **IndexNulls** 的值。</span><span class="sxs-lookup"><span data-stu-id="e01b4-105">The code creates a new index and sets the value of **IndexNulls** based on user input (from a list box named List1).</span></span> <span data-ttu-id="e01b4-106">然后，**索引**追加到*罗斯文*[目录](catalog-object-adox.md)中的**Employees** [表](table-object-adox.md)。</span><span class="sxs-lookup"><span data-stu-id="e01b4-106">Then, the **Index** is appended to the **Employees** [Table](table-object-adox.md) in the *Northwind* [Catalog](catalog-object-adox.md).</span></span> <span data-ttu-id="e01b4-107">新的 **Index** 应用于基于 [Employees](recordset-object-ado.md) （雇员）表的 **Recordset**，并且该 **Recordset** 被打开。</span><span class="sxs-lookup"><span data-stu-id="e01b4-107">The new **Index** is applied to a [Recordset](recordset-object-ado.md) based on the **Employees** table, and the **Recordset** is opened.</span></span> <span data-ttu-id="e01b4-108">有一条新记录添加到 **Employees** （雇员）表中，并且索引字段为 **Null** 值。</span><span class="sxs-lookup"><span data-stu-id="e01b4-108">A new record is added to the **Employees** table, with a **Null** value in the indexed field.</span></span> <span data-ttu-id="e01b4-109">此新记录是否显示取决于 **IndexNulls** 属性的设置。</span><span class="sxs-lookup"><span data-stu-id="e01b4-109">Whether this new record is displayed depends on the setting of the **IndexNulls** property.</span></span>

```vb
    ' IndexNullsVB 
    Sub Main() 
     On Error GoTo IndexNullsXError 
     
     Dim cnn As New ADODB.Connection 
     Dim catNorthwind As New ADOX.Catalog 
     Dim idxNew As New ADOX.Index 
     Dim rstEmployees As New ADODB.Recordset 
     Dim varBookmark As Variant 
     
     ' Connect the catalog. 
     cnn.Open "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
     "Data Source='c:\Program Files\" & _ 
     "Microsoft Office\Office\Samples\Northwind.mdb';" 
     
     Set catNorthwind.ActiveConnection = cnn 
     
     ' Append Country column to new index 
     idxNew.Columns.Append "Country" 
     idxNew.Name = "NewIndex" 
     
     Dim Response 
     Response = MsgBox("Allow 'Null' index? Otherwise ignore 'Null' index.", vbYesNo) 
     '"Allow 'Null' index? Otherwise ignore 'Null' index." 
     ', vbYesNo + vbCritical + vbDefaultButton2,,,, 
     If Response = vbYes Then ' User chose Yes. 
     idxNew.IndexNulls = adIndexNullsAllow 
     Else ' User chose No. 
     idxNew.IndexNulls = adIndexNullsIgnore 
     End If 
     
     'Append new index to Employees table 
     catNorthwind.Tables("Employees").Indexes.Append idxNew 
     
     rstEmployees.Index = idxNew.Name 
     rstEmployees.Open "Employees", cnn, adOpenKeyset, _ 
     adLockOptimistic, adCmdTableDirect 
     
     With rstEmployees 
     ' Add a new record to the Employees table. 
     .AddNew 
     !FirstName = "Gary" 
     !LastName = "Haarsager" 
     .Update 
     
     ' Bookmark the newly added record 
     varBookmark = .Bookmark 
     
     ' Use the new index to set the order of the records. 
     .MoveFirst 
     
     Debug.Print "Index = " & .Index & _ 
     ", IndexNulls = " & idxNew.IndexNulls 
     Debug.Print " Country - Name" 
     
     ' Enumerate the Recordset. The value of the 
     ' IndexNulls property will determine if the newly 
     ' added record appears in the output. 
     Do While Not .EOF 
     Debug.Print " " & _ 
     IIf(IsNull(!Country), "[Null]", !Country) & _ 
     " - " & !FirstName & " " & !LastName 
     .MoveNext 
     Loop 
     
     ' Delete new record because this is a demonstration. 
     .Bookmark = varBookmark 
     .Delete 
     
     .Close 
     End With 
     
     'Clean up 
     Set rstEmployees = Nothing 
     catNorthwind.Tables("Employees").Indexes.Delete idxNew.Name 
     cnn.Close 
     Set cnn = Nothing 
     Set catNorthwind = Nothing 
     Set idxNew = Nothing 
     Exit Sub 
     
    IndexNullsXError: 
     
     If Not rstEmployees Is Nothing Then 
     If rstEmployees.State = adStateOpen Then rstEmployees.Close 
     End If 
     Set rstEmployees = Nothing 
     
     ' Delete new Index because this is a demonstration. 
     If Not catNorthwind Is Nothing Then 
     catNorthwind.Tables("Employees").Indexes.Delete idxNew.Name 
     End If 
     
     If Not cnn Is Nothing Then 
     If cnn.State = adStateOpen Then cnn.Close 
     End If 
     Set cnn = Nothing 
     
     Set catNorthwind = Nothing 
     Set idxNew = Nothing 
     
     If Err <> 0 Then 
     MsgBox Err.Source & "-->" & Err.Description, , "Error" 
     End If 
     
    End Sub 
    ' EndIndexNullsVB
```