---
title: Procedures 的 Append 方法示例 (VB)
TOCTitle: Procedures Append Method Example (VB)
ms:assetid: fa6c5e7a-6764-2208-26c8-f7fe4140dec3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250279(v=office.15)
ms:contentKeyID: 48548843
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5c3ad4e79bee0434e2a16d1a4b703dde83a43f11
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466024"
---
# <a name="procedures-append-method-example-vb"></a>Procedures 的 Append 方法示例 (VB)


**适用于**： Access 2013 |Office 2013

下面的代码演示如何使用 [Command](command-object-ado.md) 对象和 [Procedures](procedures-collection-adox.md) 集合的 [Append](append-method-adox-procedures.md) 方法在基础数据源中创建一个新过程。

```vb 
 
' BeginCreateProcedureVB 
Sub Main() 
 On Error GoTo CreateProcedureError 
 
 Dim cnn As New ADODB.Connection 
 Dim cmd As New ADODB.Command 
 Dim prm As ADODB.Parameter 
 Dim cat As New ADOX.Catalog 
 
 ' Open the Connection 
 cnn.Open _ 
 "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
 "Data Source='c:\Program Files\Microsoft Office\" & _ 
 "Office\Samples\Northwind.mdb';" 
 
 ' Create the parameterized command (Microsoft Jet specific) 
 Set cmd.ActiveConnection = cnn 
 cmd.CommandText = "PARAMETERS [CustId] Text;" & _ 
 "Select * From Customers Where CustomerId = [CustId]" 
 
 ' Open the Catalog 
 Set cat.ActiveConnection = cnn 
 
 ' Create the new Procedure 
 cat.Procedures.Append "CustomerById", cmd 
 
 'Clean 
 cnn.Close 
 Set cat = Nothing 
 Set cmd = Nothing 
 Set cnn = Nothing 
 Exit Sub 
 
CreateProcedureError: 
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
' EndCreateProcedureVB 
```

