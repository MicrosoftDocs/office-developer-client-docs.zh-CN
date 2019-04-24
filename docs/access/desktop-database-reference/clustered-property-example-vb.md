---
title: Clustered 属性示例 (VB)
TOCTitle: Clustered property example (VB)
ms:assetid: 1065622d-9473-209a-95be-c4b0ab5b687a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248872(v=office.15)
ms:contentKeyID: 48543293
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 75556927bc5d3e10526da6a45bfe1e4f6d8abea2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296267"
---
# <a name="clustered-property-example-vb"></a><span data-ttu-id="07baf-102">Clustered 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="07baf-102">Clustered property example (VB)</span></span>


<span data-ttu-id="07baf-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="07baf-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="07baf-p101">本示例演示 [Index](index-object-adox.md) 的 [Clustered](clustered-property-adox.md) 属性。注意，Microsoft Jet 数据库不支持聚集索引，因此本示例对于 *Northwind* 数据库中的所有索引的 **Clustered** 属性返回 **False**。</span><span class="sxs-lookup"><span data-stu-id="07baf-p101">This example demonstrates the [Clustered](clustered-property-adox.md) property of an [Index](index-object-adox.md). Note that Microsoft Jet databases do not support clustered indexes, so this example will return **False** for the **Clustered** property of all indexes in the *Northwind* database.</span></span>

```vb 
 
' BeginClusteredVB 
Sub Main() 
 On Error GoTo ClusteredXError 
 
 Dim cnn As New ADODB.Connection 
 Dim cat As New ADOX.Catalog 
 Dim tblLoop As ADOX.Table 
 Dim idxLoop As ADOX.Index 
 Dim strCnn As String 
 
 strCnn = "Provider='SQLOLEDB';Data Source='MySqlServer';Initial Catalog='pubs';" & _ 
 "Integrated Security='SSPI';" 
 ' Connect the catalog. 
 cnn.Open strCnn 
 cat.ActiveConnection = cnn 
 
 ' Enumerate Tables 
 For Each tblLoop In cat.Tables 
 'Enumerate Indexes 
 For Each idxLoop In tblLoop.Indexes 
 Debug.Print tblLoop.Name & " " & _ 
 idxLoop.Name & " " & idxLoop.Clustered 
 Next idxLoop 
 Next tblLoop 
 
 'Clean up 
 cnn.Close 
 Set cat = Nothing 
 Set cnn = Nothing 
 Exit Sub 
 
ClusteredXError: 
 
 Set cat = Nothing 
 
 If Not cnn Is Nothing Then 
 If cnn.State = adStateOpen Then cnn.Close 
 End If 
 Set cnn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
' EndClusteredVB 
```

