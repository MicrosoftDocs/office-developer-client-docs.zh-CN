---
title: Views 的 Delete 方法示例 (VB)
TOCTitle: Views Delete Method Example (VB)
ms:assetid: 423cd4e6-dfa5-8559-b1f3-b789a7aa9590
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249194(v=office.15)
ms:contentKeyID: 48544474
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 87efa9fa63fd9561ab27c4a11062e3af6a5f5817
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466372"
---
# <a name="views-delete-method-example-vb"></a><span data-ttu-id="99bc9-102">Views 的 Delete 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="99bc9-102">Views Delete Method Example (VB)</span></span>


<span data-ttu-id="99bc9-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="99bc9-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="99bc9-104">下面的代码演示如何使用 [Delete](delete-method-adox-collections.md) 方法从目录中删除视图。</span><span class="sxs-lookup"><span data-stu-id="99bc9-104">The following code shows how to use the [Delete](delete-method-adox-collections.md) method to delete a view from the catalog.</span></span>

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

