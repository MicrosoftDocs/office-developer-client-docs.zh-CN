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
ms.openlocfilehash: 44e3613338c8932bc80dd1150392033dfa3cd050
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426931"
---
# <a name="isequalmapiuid"></a><span data-ttu-id="00e3e-103">IsEqualMAPIUID</span><span class="sxs-lookup"><span data-stu-id="00e3e-103">IsEqualMAPIUID</span></span>

  
  
<span data-ttu-id="00e3e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="00e3e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="00e3e-105">测试两 [个 MAPIUID](mapiuid.md) 结构以确定它们是否包含同一标识符。</span><span class="sxs-lookup"><span data-stu-id="00e3e-105">Tests two [MAPIUID](mapiuid.md) structures to determine whether they contain the same identifier.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="00e3e-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="00e3e-106">Header file:</span></span>  <br/> |<span data-ttu-id="00e3e-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="00e3e-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="00e3e-108">相关结构：</span><span class="sxs-lookup"><span data-stu-id="00e3e-108">Related structure:</span></span>  <br/> |<span data-ttu-id="00e3e-109">**MAPIUID**</span><span class="sxs-lookup"><span data-stu-id="00e3e-109">**MAPIUID**</span></span> <br/> |
   
```cpp
IsEqualMAPIUID(lpuid1, lpuid2)
```

## <a name="parameters"></a><span data-ttu-id="00e3e-110">参数</span><span class="sxs-lookup"><span data-stu-id="00e3e-110">Parameters</span></span>

 <span data-ttu-id="00e3e-111">_lpuid1_</span><span class="sxs-lookup"><span data-stu-id="00e3e-111">_lpuid1_</span></span>
  
> <span data-ttu-id="00e3e-112">指向要测试的第一 **个 MAPIUID** 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="00e3e-112">Pointer to the first **MAPIUID** structure to be tested.</span></span> 
    
 <span data-ttu-id="00e3e-113">_lpuid2_</span><span class="sxs-lookup"><span data-stu-id="00e3e-113">_lpuid2_</span></span>
  
> <span data-ttu-id="00e3e-114">指向要测试的第二 **个 MAPIUID** 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="00e3e-114">Pointer to the second **MAPIUID** structure to be tested.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="00e3e-115">备注</span><span class="sxs-lookup"><span data-stu-id="00e3e-115">Remarks</span></span>

<span data-ttu-id="00e3e-116">如果两个 MAPIUID 结构包含相同的标识符， **则 IsEqualMAPIUID** 宏将返回 TRUE;如果两个 **MAPIUID** 结构不包含标识符，则返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="00e3e-116">The **IsEqualMAPIUID** macro returns TRUE if the two **MAPIUID** structures contain the same identifier and FALSE if they do not.</span></span> 
  
<span data-ttu-id="00e3e-117">**IsEqualMAPIUID** 宏要求包含头文件 Memory.h。</span><span class="sxs-lookup"><span data-stu-id="00e3e-117">The **IsEqualMAPIUID** macro requires that the header file Memory.h be included.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="00e3e-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00e3e-118">See also</span></span>



[<span data-ttu-id="00e3e-119">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="00e3e-119">MAPIUID</span></span>](mapiuid.md)


[<span data-ttu-id="00e3e-120">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="00e3e-120">Macros Related to Structures</span></span>](macros-related-to-structures.md)

