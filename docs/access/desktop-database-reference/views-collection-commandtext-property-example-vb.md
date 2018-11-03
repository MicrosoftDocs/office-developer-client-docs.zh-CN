---
title: Views 集合，CommandText 属性示例 (VB)
TOCTitle: Views Collection, CommandText property example (VB)
ms:assetid: 5dacd3c2-a1b2-57a7-1bac-ce0caa7c1a09
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249331(v=office.15)
ms:contentKeyID: 48545120
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1cec0b42dd6708e15ac20300850dd03d162683c6
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946354"
---
# <a name="views-collection-commandtext-property-example-vb"></a><span data-ttu-id="94bef-102">Views 集合与 CommandText 属性的示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="94bef-102">Views collection, CommandText property example (VB)</span></span>


<span data-ttu-id="94bef-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="94bef-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="94bef-104">下面的代码演示如何使用 [Command](command-property-adox.md) 属性更新视图的文本。</span><span class="sxs-lookup"><span data-stu-id="94bef-104">The following code demonstrates how to use the [Command](command-property-adox.md) property to update the text of a view.</span></span>

```vb 
 
' BeginViewsCollectionVB 
Sub Main() 
 On Error GoTo ViewTextError 
 
 Dim cnn As New ADODB.Connection 
 Dim cat As New ADOX.Catalog 
 Dim cmd As New ADODB.Command 
 
 ' Open the Connection 
 cnn.Open _ 
 "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
 "Data Source='c:\Program Files\Microsoft Office\" & _ 
 "Office\Samples\Northwind.mdb';" 
 
 ' Open the catalog 
 Set cat.ActiveConnection = cnn 
 
 ' Get the command 
 Set cmd = cat.Views("AllCustomers").Command 
 
 ' Update the CommandText of the Command 
 cmd.CommandText = _ 
 "Select CustomerId, CompanyName, ContactName From Customers" 
 
 ' Update the View 
 Set cat.Views("AllCustomers").Command = cmd 
 
 'Clean up 
 cnn.Close 
 Set cat = Nothing 
 Set cmd = Nothing 
 Set cnn = Nothing 
 Exit Sub 
 
ViewTextError: 
 
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
' EndViewsCollectionVB 
```

