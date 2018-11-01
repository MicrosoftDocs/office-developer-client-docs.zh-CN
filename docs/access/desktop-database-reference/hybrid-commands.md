---
title: 混合命令 （访问桌面数据库参考 （英文）
TOCTitle: Hybrid Commands
ms:assetid: 55654274-0494-349f-820d-92108284449d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249286(v=office.15)
ms:contentKeyID: 48544929
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 363f305fee12cb2e46ab9d4c628030f7dc4bcd78
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25873850"
---
# <a name="hybrid-commands"></a><span data-ttu-id="fd6c3-102">混合命令</span><span class="sxs-lookup"><span data-stu-id="fd6c3-102">Hybrid Commands</span></span>


<span data-ttu-id="fd6c3-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="fd6c3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="fd6c3-p101">混合命令是部分参数化的命令。例如：</span><span class="sxs-lookup"><span data-stu-id="fd6c3-p101">Hybrid commands are partially parameterized commands. For example:</span></span>

```vb 
 
SHAPE {select * from plants} 
 APPEND( {select * from customers where country = ?} 
 RELATE PlantCountry TO PARAMETER 0, 
 PlantRegion TO CustomerRegion ) 
```

<span data-ttu-id="fd6c3-106">混合命令的缓存行为与常规参数化命令相同。</span><span class="sxs-lookup"><span data-stu-id="fd6c3-106">The caching behavior for a hybrid command is the same as that of regular parameterized commands.</span></span>

