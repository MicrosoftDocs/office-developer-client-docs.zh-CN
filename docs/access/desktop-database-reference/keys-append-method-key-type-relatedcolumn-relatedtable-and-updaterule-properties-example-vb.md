---
title: Keys Append 方法、Key Type、RelatedColumn 属性示例 (VB)
TOCTitle: Keys Append Method, Key Type, RelatedColumn, RelatedTable and UpdateRule properties example (VB)
ms:assetid: d1b0508d-ab2c-eece-061c-09c67ea9ecae
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250047(v=office.15)
ms:contentKeyID: 48547871
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9120fa718544a0d1d7a132b197517aac955f5fc6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290629"
---
# <a name="keys-append-method-key-type-relatedcolumn-relatedtable-and-updaterule-properties-example-vb"></a><span data-ttu-id="382be-102">Keys Append 方法、Key Type、RelatedColumn、RelatedTable 和 UpdateRule 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="382be-102">Keys Append Method, Key Type, RelatedColumn, RelatedTable and UpdateRule properties example (VB)</span></span>


<span data-ttu-id="382be-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="382be-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="382be-104">下面的代码演示如何创建新的外键。</span><span class="sxs-lookup"><span data-stu-id="382be-104">The following code demonstrates how to create a new foreign key.</span></span> <span data-ttu-id="382be-105">它假设有两个表：**Customers**（客户）和 **Orders**（订单）。</span><span class="sxs-lookup"><span data-stu-id="382be-105">It assumes two tables (**Customers** and **Orders**) exist.</span></span>

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

