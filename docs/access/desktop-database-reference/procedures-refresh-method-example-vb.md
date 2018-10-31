---
title: Procedures 的 Refresh 方法示例 (VB)
TOCTitle: Procedures Refresh method example (VB)
ms:assetid: fd6d71cf-7a6b-49d7-220b-dd5b815a92ab
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250300(v=office.15)
ms:contentKeyID: 48548916
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ef872fbb5fed4c981f127c3fc98ea4656f0dab98
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25863015"
---
# <a name="procedures-refresh-method-example-vb"></a><span data-ttu-id="2f2bd-102">Procedures 的 Refresh 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="2f2bd-102">Procedures Refresh method example (VB)</span></span>


<span data-ttu-id="2f2bd-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="2f2bd-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="2f2bd-p101">下面的代码演示如何刷新 [Catalog](procedures-collection-adox.md) 的 [Procedures](catalog-object-adox.md) 集合。必须先执行该操作，然后才能访问 [Catalog](procedure-object-adox.md) 中的 **Procedure** 对象。</span><span class="sxs-lookup"><span data-stu-id="2f2bd-p101">The following code shows how to refresh the [Procedures](procedures-collection-adox.md) collection of a [Catalog](catalog-object-adox.md). This is required before [Procedure](procedure-object-adox.md) objects from the **Catalog** can be accessed.</span></span>

```vb 
 
' BeginProceduresRefreshVB 
Sub Main() 
 On Error GoTo ProcedureRefreshError 
 
 Dim cat As New ADOX.Catalog 
 
 ' Open the Catalog 
 cat.ActiveConnection = _ 
 "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
 "Data Source='c:\Program Files\" & _ 
 "Microsoft Office\Office\Samples\Northwind.mdb';" 
 
 ' Refresh the Procedures collection 
 cat.Procedures.Refresh 
 
 'Clean up 
 Set cat.ActiveConnection = Nothing 
 Set cat = Nothing 
 Exit Sub 
 
ProcedureRefreshError: 
 Set cat = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
' EndProceduresRefreshVB 
```

