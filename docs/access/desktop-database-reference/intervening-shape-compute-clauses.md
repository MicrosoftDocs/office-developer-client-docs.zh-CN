---
title: 中间 Shape COMPUTE 子句
TOCTitle: Intervening Shape COMPUTE clauses
ms:assetid: 3e9dcef2-776c-0365-4a92-68e325f7dbb5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249174(v=office.15)
ms:contentKeyID: 48544380
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 456729bb93d6cfaf2844d71123cd850d7f719844
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28707911"
---
# <a name="intervening-shape-compute-clauses"></a><span data-ttu-id="72148-102">中间 Shape COMPUTE 子句</span><span class="sxs-lookup"><span data-stu-id="72148-102">Intervening Shape COMPUTE clauses</span></span>


<span data-ttu-id="72148-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="72148-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="72148-104">在参数化 Shape 命令中，在父和子之间嵌入一个或多个 COMPUTE 子句将是有效的，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="72148-104">It is valid to embed one or more COMPUTE clauses between the parent and child in a parameterized shape command, as in the following example:</span></span>

```vb 
 
SHAPE {select au_lname, state from authors} APPEND 
 ((SHAPE 
 (SHAPE 
 {select * from authors where state = ?} rs 
 COMPUTE rs, ANY(rs.state) state, ANY(rs.au_lname) au_lname 
 BY au_id) rs2 
 COMPUTE rs2, ANY(rs2.state) BY au_lname) 
RELATE state TO PARAMETER 0) 
```

