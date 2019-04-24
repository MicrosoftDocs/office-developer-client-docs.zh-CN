---
title: Views 的 Delete 方法示例 (VB)
TOCTitle: Views Delete method example (VB)
ms:assetid: 423cd4e6-dfa5-8559-b1f3-b789a7aa9590
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249194(v=office.15)
ms:contentKeyID: 48544474
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4046c3142721ebb59d0ad467689e92e4ac587d74
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302763"
---
# <a name="views-delete-method-example-vb"></a>Views 的 Delete 方法示例 (VB)


**适用于**：Access 2013、Office 2013

下面的代码演示如何使用 [Delete](delete-method-adox-collections.md) 方法从目录中删除视图。

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

