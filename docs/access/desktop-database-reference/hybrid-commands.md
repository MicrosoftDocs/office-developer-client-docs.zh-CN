---
title: 混合命令 (Access 桌面数据库参考)
TOCTitle: Hybrid commands
ms:assetid: 55654274-0494-349f-820d-92108284449d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249286(v=office.15)
ms:contentKeyID: 48544929
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 7fe3e6d0afbba82cacd5a55c630f1ca41f3e318a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291906"
---
# <a name="hybrid-commands"></a><span data-ttu-id="7399f-102">混合命令</span><span class="sxs-lookup"><span data-stu-id="7399f-102">Hybrid commands</span></span>


<span data-ttu-id="7399f-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="7399f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7399f-p101">混合命令是部分参数化的命令。例如：</span><span class="sxs-lookup"><span data-stu-id="7399f-p101">Hybrid commands are partially parameterized commands. For example:</span></span>

```vb 
 
SHAPE {select * from plants} 
 APPEND( {select * from customers where country = ?} 
 RELATE PlantCountry TO PARAMETER 0, 
 PlantRegion TO CustomerRegion ) 
```

<span data-ttu-id="7399f-106">混合命令的缓存行为与常规参数化命令相同。</span><span class="sxs-lookup"><span data-stu-id="7399f-106">The caching behavior for a hybrid command is the same as that of regular parameterized commands.</span></span>

