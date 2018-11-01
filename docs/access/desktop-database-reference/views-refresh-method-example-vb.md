---
title: Views 的 Refresh 方法示例 (VB)
TOCTitle: Views Refresh method example (VB)
ms:assetid: 607b78d6-1b26-d643-9f97-f47b5f5cffc5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249352(v=office.15)
ms:contentKeyID: 48545182
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 167930a29c040f9394f72ee3b2be158555e96edf
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25866962"
---
# <a name="views-refresh-method-example-vb"></a><span data-ttu-id="c6fe0-102">Views 的 Refresh 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="c6fe0-102">Views Refresh method example (VB)</span></span>


<span data-ttu-id="c6fe0-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c6fe0-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c6fe0-p101">下面的代码演示如何刷新 [Catalog](views-collection-adox.md) 的 [Views](catalog-object-adox.md) 集合。必须先执行此操作，然后才能访问 [Catalog](view-object-adox.md) 中的 **View** 对象。</span><span class="sxs-lookup"><span data-stu-id="c6fe0-p101">The following code shows how to refresh the [Views](views-collection-adox.md) collection of a [Catalog](catalog-object-adox.md). This is required before [View](view-object-adox.md) objects from the **Catalog** can be accessed.</span></span>

```vb 
 
' BeginViewsRefreshVB 
Sub Main() 
 On Error GoTo ProcedureViewsRefreshError 
 
 Dim cat As New ADOX.Catalog 
 
 ' Open the Catalog 
 cat.ActiveConnection = "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
 "Data Source='c:\Program Files\" & _ 
 "Microsoft Office\Office\Samples\Northwind.mdb';" 
 
 ' Refresh the Procedures collection 
 cat.Views.Refresh 
 
 'Clean up 
 Set cat = Nothing 
 Exit Sub 
 
ProcedureViewsRefreshError: 
 
 If Not cat Is Nothing Then 
 Set cat = Nothing 
 End If 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
' EndViewsRefreshVB 
```

