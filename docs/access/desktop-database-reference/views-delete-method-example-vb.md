---
title: Views 的 Delete 方法示例 (VB)
TOCTitle: Views Delete method example (VB)
ms:assetid: 423cd4e6-dfa5-8559-b1f3-b789a7aa9590
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249194(v=office.15)
ms:contentKeyID: 48544474
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4a016a0be48dfd91ad288937584b0d928c960e01
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25868670"
---
# <a name="views-delete-method-example-vb"></a><span data-ttu-id="44104-102">Views 的 Delete 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="44104-102">Views Delete method example (VB)</span></span>


<span data-ttu-id="44104-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="44104-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="44104-104">下面的代码演示如何使用 [Delete](delete-method-adox-collections.md) 方法从目录中删除视图。</span><span class="sxs-lookup"><span data-stu-id="44104-104">The following code shows how to use the [Delete](delete-method-adox-collections.md) method to delete a view from the catalog.</span></span>

```vb 
 
' BeginDeleteViewVB 
Sub Main() 
 On Error GoTo DeleteViewError 
 
 Dim cat As New ADOX.Catalog 
 
 ' Open the catalog 
 cat.ActiveConnection = "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
 "Data Source='c:\Program Files\Microsoft Office\" & _ 
 "Office\Samples\Northwind.mdb';" 
 
 'Delete the View 
 cat.Views.Delete "AllCustomers" 
 
 'Clean up 
 Set cat.ActiveConnection = Nothing 
 Set cat = Nothing 
 Exit Sub 
 
DeleteViewError: 
 Set cat = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
' EndDeleteViewVB 
```

