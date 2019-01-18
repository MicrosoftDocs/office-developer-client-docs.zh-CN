---
title: Create 方法示例 (VB)
TOCTitle: Create method example (VB)
ms:assetid: 3e6a4f3d-3b25-2dfb-5ef3-6a4c5326b78f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249171(v=office.15)
ms:contentKeyID: 48544372
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 325551763f8edded4fd6ed5c7191d827c339ddf4
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28710690"
---
# <a name="create-method-example-vb"></a><span data-ttu-id="93313-102">Create 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="93313-102">Create method example (VB)</span></span>


<span data-ttu-id="93313-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="93313-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="93313-104">下面的代码演示如何使用 [Create](create-method-adox.md) 方法创建新的 Microsoft Jet 数据库。</span><span class="sxs-lookup"><span data-stu-id="93313-104">The following code shows how to create a new Microsoft Jet database with the [Create](create-method-adox.md) method.</span></span>

```vb 
 
' BeginCreateDatabaseVB 
Sub CreateDatabase() 
 On Error GoTo CreateDatabaseError 
 
 Dim cat As New ADOX.Catalog 
 cat.Create "Provider='Microsoft.Jet.OLEDB.4.0';Data Source='c:\new.mdb'" 
 
 'Clean up 
 Set cat = Nothing 
 Exit Sub 
 
CreateDatabaseError: 
 Set cat = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
' EndCreateDatabaseVB 
```

