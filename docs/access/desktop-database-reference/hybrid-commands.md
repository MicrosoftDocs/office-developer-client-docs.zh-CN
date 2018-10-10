---
title: 混合命令 （访问桌面数据库参考 （英文）
TOCTitle: Hybrid Commands
ms:assetid: 55654274-0494-349f-820d-92108284449d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249286(v=office.15)
ms:contentKeyID: 48544929
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: aa95956fb50a5cd15fa4415e65d4a701f2e48feb
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467266"
---
# <a name="hybrid-commands"></a><span data-ttu-id="1715f-102">混合命令</span><span class="sxs-lookup"><span data-stu-id="1715f-102">Hybrid Commands</span></span>


<span data-ttu-id="1715f-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="1715f-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="1715f-p101">混合命令是部分参数化的命令。例如：</span><span class="sxs-lookup"><span data-stu-id="1715f-p101">Hybrid commands are partially parameterized commands. For example:</span></span>

```vb 
 
SHAPE {select * from plants} 
 APPEND( {select * from customers where country = ?} 
 RELATE PlantCountry TO PARAMETER 0, 
 PlantRegion TO CustomerRegion ) 
```

<span data-ttu-id="1715f-106">混合命令的缓存行为与常规参数化命令相同。</span><span class="sxs-lookup"><span data-stu-id="1715f-106">The caching behavior for a hybrid command is the same as that of regular parameterized commands.</span></span>

