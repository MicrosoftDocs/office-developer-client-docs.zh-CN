---
title: Procedures 的 Refresh 方法示例 (VB)
TOCTitle: Procedures Refresh method example (VB)
ms:assetid: fd6d71cf-7a6b-49d7-220b-dd5b815a92ab
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250300(v=office.15)
ms:contentKeyID: 48548916
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b75b7de4e63c9083dff550c5362e48bf171ee5e2
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25887563"
---
# <a name="procedures-refresh-method-example-vb"></a><span data-ttu-id="d5efc-102">Procedures 的 Refresh 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="d5efc-102">Procedures Refresh method example (VB)</span></span>


<span data-ttu-id="d5efc-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="d5efc-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="d5efc-p101">下面的代码演示如何刷新 [Catalog](procedures-collection-adox.md) 的 [Procedures](catalog-object-adox.md) 集合。必须先执行该操作，然后才能访问 [Catalog](procedure-object-adox.md) 中的 **Procedure** 对象。</span><span class="sxs-lookup"><span data-stu-id="d5efc-p101">The following code shows how to refresh the [Procedures](procedures-collection-adox.md) collection of a [Catalog](catalog-object-adox.md). This is required before [Procedure](procedure-object-adox.md) objects from the **Catalog** can be accessed.</span></span>

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

