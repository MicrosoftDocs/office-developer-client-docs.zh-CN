---
title: 混合命令 （访问桌面数据库参考 （英文）
TOCTitle: Hybrid commands
ms:assetid: 55654274-0494-349f-820d-92108284449d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249286(v=office.15)
ms:contentKeyID: 48544929
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 046d005eb4a9e1c8097908e0104b8d1e5c76e2af
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946909"
---
# <a name="hybrid-commands"></a><span data-ttu-id="59b9a-102">混合命令</span><span class="sxs-lookup"><span data-stu-id="59b9a-102">Hybrid commands</span></span>


<span data-ttu-id="59b9a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="59b9a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="59b9a-p101">混合命令是部分参数化的命令。例如：</span><span class="sxs-lookup"><span data-stu-id="59b9a-p101">Hybrid commands are partially parameterized commands. For example:</span></span>

```vb 
 
SHAPE {select * from plants} 
 APPEND( {select * from customers where country = ?} 
 RELATE PlantCountry TO PARAMETER 0, 
 PlantRegion TO CustomerRegion ) 
```

<span data-ttu-id="59b9a-106">混合命令的缓存行为与常规参数化命令相同。</span><span class="sxs-lookup"><span data-stu-id="59b9a-106">The caching behavior for a hybrid command is the same as that of regular parameterized commands.</span></span>

