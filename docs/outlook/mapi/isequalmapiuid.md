---
title: IsEqualMAPIUID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.IsEqualMAPIUID
api_type:
- COM
ms.assetid: 85d71b73-0630-4c5d-b0e3-b48d27a300d0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0c72164cac8a37d0372ac93f4ed6d3face966ddb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566661"
---
# <a name="isequalmapiuid"></a><span data-ttu-id="42ea8-103">IsEqualMAPIUID</span><span class="sxs-lookup"><span data-stu-id="42ea8-103">IsEqualMAPIUID</span></span>

  
  
<span data-ttu-id="42ea8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="42ea8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="42ea8-105">测试两个[MAPIUID](mapiuid.md)结构，以确定它们是否包含相同的标识符。</span><span class="sxs-lookup"><span data-stu-id="42ea8-105">Tests two [MAPIUID](mapiuid.md) structures to determine whether they contain the same identifier.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="42ea8-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="42ea8-106">Header file:</span></span>  <br/> |<span data-ttu-id="42ea8-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="42ea8-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="42ea8-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="42ea8-108">Related structure:</span></span>  <br/> |<span data-ttu-id="42ea8-109">**MAPIUID**</span><span class="sxs-lookup"><span data-stu-id="42ea8-109">**MAPIUID**</span></span> <br/> |
   
```cpp
IsEqualMAPIUID(lpuid1, lpuid2)
```

## <a name="parameters"></a><span data-ttu-id="42ea8-110">参数</span><span class="sxs-lookup"><span data-stu-id="42ea8-110">Parameters</span></span>

 <span data-ttu-id="42ea8-111">_lpuid1_</span><span class="sxs-lookup"><span data-stu-id="42ea8-111">_lpuid1_</span></span>
  
> <span data-ttu-id="42ea8-112">要测试的第一个**MAPIUID**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="42ea8-112">Pointer to the first **MAPIUID** structure to be tested.</span></span> 
    
 <span data-ttu-id="42ea8-113">_lpuid2_</span><span class="sxs-lookup"><span data-stu-id="42ea8-113">_lpuid2_</span></span>
  
> <span data-ttu-id="42ea8-114">指向要测试的第二个**MAPIUID**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="42ea8-114">Pointer to the second **MAPIUID** structure to be tested.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="42ea8-115">注解</span><span class="sxs-lookup"><span data-stu-id="42ea8-115">Remarks</span></span>

<span data-ttu-id="42ea8-116">如果两个**MAPIUID**结构包含相同标识符和 FALSE，如果未显示， **IsEqualMAPIUID**宏返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="42ea8-116">The **IsEqualMAPIUID** macro returns TRUE if the two **MAPIUID** structures contain the same identifier and FALSE if they do not.</span></span> 
  
<span data-ttu-id="42ea8-117">**IsEqualMAPIUID**宏要求的头文件 Memory.h 包含。</span><span class="sxs-lookup"><span data-stu-id="42ea8-117">The **IsEqualMAPIUID** macro requires that the header file Memory.h be included.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="42ea8-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42ea8-118">See also</span></span>



[<span data-ttu-id="42ea8-119">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="42ea8-119">MAPIUID</span></span>](mapiuid.md)


[<span data-ttu-id="42ea8-120">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="42ea8-120">Macros Related to Structures</span></span>](macros-related-to-structures.md)

