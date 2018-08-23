---
title: SizedADRLIST
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedADRLIST
api_type:
- COM
ms.assetid: 5c64d74a-83a7-4122-b1d1-fcca0f4a6cdb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 62911e0dec15002f39fff81e8c517c1cb11d0183
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574739"
---
# <a name="sizedadrlist"></a><span data-ttu-id="4562d-103">SizedADRLIST</span><span class="sxs-lookup"><span data-stu-id="4562d-103">SizedADRLIST</span></span>

<span data-ttu-id="4562d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4562d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4562d-105">定义具有指定名称，其中包含指定的数目的[ADRENTRY](adrentry.md)结构[ADRLIST](adrlist.md)结构。</span><span class="sxs-lookup"><span data-stu-id="4562d-105">Defines an [ADRLIST](adrlist.md) structure with the specified name that contains a specified number of [ADRENTRY](adrentry.md) structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4562d-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="4562d-106">Header file:</span></span>  <br/> |<span data-ttu-id="4562d-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4562d-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="4562d-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="4562d-108">Related structure:</span></span>  <br/> |<span data-ttu-id="4562d-109">**ADRLIST**</span><span class="sxs-lookup"><span data-stu-id="4562d-109">**ADRLIST**</span></span> <br/> |
   
```cpp
SizedADRLIST (_centries,_name)
```

## <a name="parameters"></a><span data-ttu-id="4562d-110">参数</span><span class="sxs-lookup"><span data-stu-id="4562d-110">Parameters</span></span>

<span data-ttu-id="4562d-111">__centries_</span><span class="sxs-lookup"><span data-stu-id="4562d-111">__centries_</span></span>
  
> <span data-ttu-id="4562d-112">要包含在新的**ADRLIST**结构**ADRENTRY**结构的计数。</span><span class="sxs-lookup"><span data-stu-id="4562d-112">Count of **ADRENTRY** structures to be included in the new **ADRLIST** structure.</span></span> 
    
<span data-ttu-id="4562d-113">__名称_</span><span class="sxs-lookup"><span data-stu-id="4562d-113">__name_</span></span>
  
> <span data-ttu-id="4562d-114">新**ADRLIST**结构的的名称。</span><span class="sxs-lookup"><span data-stu-id="4562d-114">Name for the new **ADRLIST** structure.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="4562d-115">注解</span><span class="sxs-lookup"><span data-stu-id="4562d-115">Remarks</span></span>

<span data-ttu-id="4562d-116">**SizedADRLIST**宏可以定义时已知数组长度要求具有显式边界的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="4562d-116">The **SizedADRLIST** macro lets you define a recipient list that has explicit bounds when array length requirements are known.</span></span> <span data-ttu-id="4562d-117">下面的代码演示如何强制转换为**ADRLIST**结构指针**SizedADRLIST**宏的结果：</span><span class="sxs-lookup"><span data-stu-id="4562d-117">The following code shows how to cast the result of the **SizedADRLIST** macro to an **ADRLIST** structure pointer:</span></span> 
  
```cpp
lpADRList = (LPADRLIST) &SizedADRList;
```

## <a name="see-also"></a><span data-ttu-id="4562d-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4562d-118">See also</span></span>

- [<span data-ttu-id="4562d-119">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="4562d-119">ADRLIST</span></span>](adrlist.md)
- [<span data-ttu-id="4562d-120">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="4562d-120">ADRENTRY</span></span>](adrentry.md)
- [<span data-ttu-id="4562d-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="4562d-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

