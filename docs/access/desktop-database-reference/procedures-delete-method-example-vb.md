---
title: Procedures 的 Delete 方法示例 (VB)
TOCTitle: Procedures Delete method example (VB)
ms:assetid: 1cbae0a2-0035-d03f-b9c6-5453ddd51ec4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248964(v=office.15)
ms:contentKeyID: 48543576
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ccee0f53b1c7406bcb31773d5504dc105c74a484
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25881529"
---
# <a name="procedures-delete-method-example-vb"></a><span data-ttu-id="799f1-102">Procedures 的 Delete 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="799f1-102">Procedures Delete method example (VB)</span></span>


<span data-ttu-id="799f1-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="799f1-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="799f1-104">下面的代码演示如何使用 [Procedures](procedures-collection-adox.md) 集合的 [Delete](delete-method-adox-collections.md) 方法删除过程。</span><span class="sxs-lookup"><span data-stu-id="799f1-104">The following code demonstrates how to delete a procedure using the [Procedures](procedures-collection-adox.md) collection [Delete](delete-method-adox-collections.md) method.</span></span>

```vb 
 
' BeginDeleteProcedureVB 
Sub Main() 
 On Error GoTo DeleteProcedureError 
 
 Dim cat As New ADOX.Catalog 
 
 ' Open the Catalog. 
 cat.ActiveConnection = _ 
 "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
 "Data Source='c:\Program Files\Microsoft Office\" & _ 
 "Office\Samples\Northwind.mdb';" 
 
 ' Delete the Procedure. 
 cat.Procedures.Delete "CustomerById" 
 
 'Clean up 
 Set cat.ActiveConnection = Nothing 
 Set cat = Nothing 
 Exit Sub 
 
DeleteProcedureError: 
 Set cat = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
' EndDeleteProcedureVB 
```

