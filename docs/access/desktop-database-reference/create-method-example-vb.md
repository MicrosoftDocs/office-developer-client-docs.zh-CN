---
title: Create 方法示例 (VB)
TOCTitle: Create method example (VB)
ms:assetid: 3e6a4f3d-3b25-2dfb-5ef3-6a4c5326b78f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249171(v=office.15)
ms:contentKeyID: 48544372
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b8fbc2edc5f01ed22c0a075178c9c33d01eaddc5
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25880689"
---
# <a name="create-method-example-vb"></a><span data-ttu-id="b6fb4-102">Create 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="b6fb4-102">Create method example (VB)</span></span>


<span data-ttu-id="b6fb4-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b6fb4-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b6fb4-104">下面的代码演示如何使用 [Create](create-method-adox.md) 方法创建新的 Microsoft Jet 数据库。</span><span class="sxs-lookup"><span data-stu-id="b6fb4-104">The following code shows how to create a new Microsoft Jet database with the [Create](create-method-adox.md) method.</span></span>

```vb 
 
' BeginCreateDatabseVB 
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

