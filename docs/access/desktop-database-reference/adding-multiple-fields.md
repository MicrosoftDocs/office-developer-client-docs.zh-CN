---
title: 添加多个字段
TOCTitle: Adding multiple fields
ms:assetid: 81b2f9de-4805-4494-9990-09ffda1b2068
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249560(v=office.15)
ms:contentKeyID: 48545961
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: bc9822f2055e7cdfd9a2ef5fe9d2312fc5622ac7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280586"
---
# <a name="adding-multiple-fields"></a>添加多个字段

**适用于**：Access 2013、Office 2013

有时，将字段及其相应值的数组传递到 **AddNew** 方法要比多次为每个新字段设置 **Value** 更加有效率。如果 *FieldList* 是一个数组，*Values* 必须也是一个具有相同数目成员的数组；否则会出现错误。在每个数组中，字段名称的顺序必须与字段值的顺序相匹配。以下代码将字段的数组和值的数组传递到 **AddNew** 方法。

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

