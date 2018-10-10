---
title: 添加多个字段
TOCTitle: Adding Multiple Fields
ms:assetid: 81b2f9de-4805-4494-9990-09ffda1b2068
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249560(v=office.15)
ms:contentKeyID: 48545961
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b9bca4035917f4376ccf69201d79894a0273ceb9
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467562"
---
# <a name="adding-multiple-fields"></a><span data-ttu-id="8f725-102">添加多个字段</span><span class="sxs-lookup"><span data-stu-id="8f725-102">Adding Multiple Fields</span></span>


<span data-ttu-id="8f725-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="8f725-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="8f725-104">有时，将字段及其相应值的数组传递到 **AddNew** 方法要比多次为每个新字段设置 **Value** 更加有效率。</span><span class="sxs-lookup"><span data-stu-id="8f725-104">Occasionally, it might be more efficient to pass in an array of fields and their corresponding values to the **AddNew** method, rather than setting **Value** multiple times for each new field.</span></span> <span data-ttu-id="8f725-105">如果*FieldList*是一个数组，*值*还必须具有相同数量的成员; 数组否则，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="8f725-105">If *FieldList* is an array, *Values* must also be an array with the same number of members; otherwise, an error occurs.</span></span> <span data-ttu-id="8f725-106">在每个数组中，字段名称的顺序必须与字段值的顺序相匹配。</span><span class="sxs-lookup"><span data-stu-id="8f725-106">The order of field names must match the order of field values in each array.</span></span> <span data-ttu-id="8f725-107">以下代码将字段的数组和值的数组传递到 **AddNew** 方法。</span><span class="sxs-lookup"><span data-stu-id="8f725-107">The following code passes an array of fields and an array of values to the **AddNew** method.</span></span>

```vb 
 
'BeginAddNew2 
 Dim avarFldNames As Variant 
 Dim avarFldValues As Variant 
 
 avarFldNames = Array("CompanyName", "Phone") 
 avarFldValues = Array("Sample Shipper 2", "(931) 555-6334") 
 
 If objRs1.Supports(adAddNew) Then 
 objRs1.AddNew avarFldNames, avarFldValues 
 End If 
 
 'Re-establish a Connection and update 
 Set objRs1.ActiveConnection = GetNewConnection 
 objRs1.UpdateBatch 
'EndAddNew2 
```

