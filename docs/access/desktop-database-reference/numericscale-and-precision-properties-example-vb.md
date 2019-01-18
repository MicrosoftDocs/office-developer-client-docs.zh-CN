---
title: NumericScale 和 Precision 属性示例 (VB)
TOCTitle: NumericScale and Precision properties example (VB)
ms:assetid: 728a76a3-1f80-935b-b6c7-94255ffe0160
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249462(v=office.15)
ms:contentKeyID: 48545610
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e067c2ae893d19efdbcdc160fc7a7d54b9682297
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28721337"
---
# <a name="numericscale-and-precision-properties-example-vb"></a><span data-ttu-id="b90a2-102">NumericScale 和 Precision 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="b90a2-102">NumericScale and Precision properties example (VB)</span></span>


<span data-ttu-id="b90a2-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b90a2-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b90a2-104">本示例演示 [Column](numericscale-property-adox.md) 对象的 [NumericScale](precision-property-adox.md) 和 [Precision](column-object-adox.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="b90a2-104">This example demonstrates the [NumericScale](numericscale-property-adox.md) and [Precision](precision-property-adox.md) properties of the [Column](column-object-adox.md) object.</span></span> <span data-ttu-id="b90a2-105">此代码将显示*Northwind*数据库的**订单明细**表及其值。</span><span class="sxs-lookup"><span data-stu-id="b90a2-105">This code displays their value for the **Order Details** table of the *Northwind* database.</span></span>

```vb 
 
' BeginNumericScalePrecVB 
Sub Main() 
 On Error GoTo NumericScalePrecXError 
 
 Dim cnn As New ADODB.Connection 
 Dim cat As New ADOX.Catalog 
 Dim tblOD As ADOX.Table 
 Dim colLoop As ADOX.Column 
 
 ' Connect the catalog. 
 cnn.Open "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
 "data source='c:\Program Files\" & _ 
 "Microsoft Office\Office\Samples\Northwind.mdb';" 
 Set cat.ActiveConnection = cnn 
 
 ' Retrieve the Order Details table 
 Set tblOD = cat.Tables("Order Details") 
 
 ' Display numeric scale and precision of 
 ' small integer fields. 
 For Each colLoop In tblOD.Columns 
 If colLoop.Type = adSmallInt Then 
 MsgBox "Column: " & colLoop.Name & vbCr & _ 
 "Numeric scale: " & _ 
 colLoop.NumericScale & vbCr & _ 
 "Precision: " & colLoop.Precision 
 End If 
 Next colLoop 
 
 'Clean up 
 cnn.Close 
 Set cat = Nothing 
 Set cnn = Nothing 
 Exit Sub 
 
NumericScalePrecXError: 
 Set cat = Nothing 
 
 If Not cnn Is Nothing Then 
 If cnn.State = adStateOpen Then cnn.Close 
 End If 
 Set cnn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
' EndNumericScalePrecVB 
```

