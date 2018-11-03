---
title: Connection 的 Close 方法、Table 的 Type 属性示例 (VB)
TOCTitle: Connection Close method, Table Type property example (VB)
ms:assetid: cd0bb6ad-af7b-fb9c-d45c-5d4b62459c03
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250019(v=office.15)
ms:contentKeyID: 48547754
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a4587cec98d6e1bd272c79428955ca422bb3eec0
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25947740"
---
# <a name="connection-close-method-table-type-property-example-vb"></a><span data-ttu-id="47fce-102">Connection 的 Close 方法、Table 的 Type 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="47fce-102">Connection Close method, Table Type property example (VB)</span></span>

<span data-ttu-id="47fce-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="47fce-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="47fce-p101">将 [ActiveConnection](activeconnection-property-adox.md) 属性设置为 **Nothing** 会"关闭"目录。关联的集合将为空。利用该目录中的架构对象创建的任何对象都将孤立。已被缓存的那些对象的属性仍然可用，但是试图读取需要调用提供程序的属性时会失败。</span><span class="sxs-lookup"><span data-stu-id="47fce-p101">Setting the [ActiveConnection](activeconnection-property-adox.md) property to **Nothing** should "close" the catalog. Associated collections will be empty. Any objects that were created from schema objects in the catalog will be orphaned. Any properties on those objects that have been cached will still be available, but attempting to read properties that require a call to the provider will fail.</span></span>

```vb 
 
    ' BeginCloseConnectionVB 
    Sub Main() 
    On Error GoTo CloseConnectionByNothingError 
    
    Dim cnn As New ADODB.Connection 
    Dim cat As New ADOX.Catalog 
    Dim tbl As ADOX.Table 
    
    cnn.Open "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
    "Data Source= 'c:\Program Files\Microsoft Office\" & _ 
    "Office\Samples\Northwind.mdb';" 
    Set cat.ActiveConnection = cnn 
    Set tbl = cat.Tables(0) 
    Debug.Print tbl.Type ' Cache tbl.Type info 
    Set cat.ActiveConnection = Nothing 
    Debug.Print tbl.Type ' tbl is orphaned 
    ' Previous line will succeed if this was cached 
    Debug.Print tbl.Columns(0).DefinedSize 
    ' Previous line will fail if this info has not been cached 
    
    'Clean up 
    cnn.Close 
    Set cat = Nothing 
    Set cnn = Nothing 
    Exit Sub 
    
    CloseConnectionByNothingError: 
    Set cat = Nothing 
    
    If Not cnn Is Nothing Then 
    If cnn.State = adStateOpen Then cnn.Close 
    End If 
    Set cnn = Nothing 
    
    If Err <> 0 Then 
    MsgBox Err.Source & "-->" & Err.Description, , "Error" 
    End If 
    End Sub 
    ' EndCloseConnectionVB 
```

<br/>

<span data-ttu-id="47fce-108">关闭用于"打开"目录的 [Connection](connection-object-ado.md) 对象应与将 **ActiveConnection** 属性设置为 **Nothing** 效果相同。</span><span class="sxs-lookup"><span data-stu-id="47fce-108">Closing a [Connection](connection-object-ado.md) object that was used to "open" the catalog should have the same effect as setting the **ActiveConnection** property to **Nothing**.</span></span>

```vb
    Sub CloseConnection() 
     On Error GoTo CloseConnectionError 
     
     Dim cnn As New ADODB.Connection 
     Dim cat As New ADOX.Catalog 
     Dim tbl As ADOX.Table 
     
     cnn.Open "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
     "Data Source= 'c:\Program Files\Microsoft Office\" & _ 
     "Office\Samples\Northwind.mdb';" 
     Set cat.ActiveConnection = cnn 
     Set tbl = cat.Tables(0) 
     Debug.Print tbl.Type ' Cache tbl.Type info 
     cnn.Close 
     Debug.Print tbl.Type ' tbl is orphaned 
     ' Previous line will succeed if this was cached 
     Debug.Print tbl.Columns(0).DefinedSize 
     ' Previous line will fail if this info has not been cached 
     
     'Clean up 
     Set cat = Nothing 
     Set cnn = Nothing 
     Exit Sub 
     
    CloseConnectionError: 
     
     Set cat = Nothing 
     
     If Not cnn Is Nothing Then 
     If cnn.State = adStateOpen Then cnn.Close 
     End If 
     Set cnn = Nothing 
     
     If Err <> 0 Then 
     MsgBox Err.Source & "-->" & Err.Description, , "Error" 
     End If 
    End Sub 
    ' EndCloseConnection2VB
```
