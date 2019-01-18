---
title: Views 的 Append 方法示例 (VB)
TOCTitle: Views Append method example (VB)
ms:assetid: 24536276-7da9-6ee8-2e27-39531b12b30f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249016(v=office.15)
ms:contentKeyID: 48543752
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 3816e1699865b1e58c745e9fb466c37885833802
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28706028"
---
# <a name="views-append-method-example-vb"></a><span data-ttu-id="63f8c-102">Views 的 Append 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="63f8c-102">Views Append method example (VB)</span></span>


<span data-ttu-id="63f8c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="63f8c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="63f8c-104">下面的代码演示如何使用 [Command](command-object-ado.md) 对象和 [Views](views-collection-adox.md) 集合的 [Append](append-method-adox-views.md) 方法在基础数据源中创建一个新视图。</span><span class="sxs-lookup"><span data-stu-id="63f8c-104">The following code demonstrates how to use a [Command](command-object-ado.md) object and the [Views](views-collection-adox.md) collection [Append](append-method-adox-views.md) method to create a new view in the underlying data source.</span></span>

```vb 
 
' BeginCreateViewVB 
Sub Main() 
 On Error GoTo CreateViewError 
 
 Dim cmd As New ADODB.Command 
 Dim cat As New ADOX.Catalog 
 
 ' Open the Catalog 
 cat.ActiveConnection = _ 
 "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
 "Data Source='c:\Program Files\Microsoft Office\" & _ 
 "Office\Samples\Northwind.mdb';" 
 
 ' Create the command representing the view. 
 cmd.CommandText = "Select * From Customers" 
 
 ' Create the new View 
 cat.Views.Append "AllCustomers", cmd 
 
 'Clean up 
 Set cat.ActiveConnection = Nothing 
 Set cat = Nothing 
 Set cmd = Nothing 
 Exit Sub 
 
CreateViewError: 
 
 Set cat = Nothing 
 Set cmd = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
' EndCreateViewVB 
```

