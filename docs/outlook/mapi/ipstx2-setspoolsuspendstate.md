---
title: IPSTX2SetSpoolSuspendState
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTX2.SetSpoolSuspendState
api_type:
- COM
ms.assetid: 396db029-1d4a-203d-2256-3353d03c6767
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b6a36c1e0c3854342b627b6fddd6eb5459211f62
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590426"
---
# <a name="ipstx2setspoolsuspendstate"></a><span data-ttu-id="2b4f4-103">IPSTX2::SetSpoolSuspendState</span><span class="sxs-lookup"><span data-stu-id="2b4f4-103">IPSTX2::SetSpoolSuspendState</span></span>

  
  
<span data-ttu-id="2b4f4-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2b4f4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2b4f4-105">在后台处理程序上设置的挂起的状态。</span><span class="sxs-lookup"><span data-stu-id="2b4f4-105">Sets the suspended state on the spooler.</span></span>
  
```cpp
void SetSpoolSuspendState( 
    ULONG ulState 
);
```

## <a name="parameters"></a><span data-ttu-id="2b4f4-106">参数</span><span class="sxs-lookup"><span data-stu-id="2b4f4-106">Parameters</span></span>

 <span data-ttu-id="2b4f4-107">_ulState_</span><span class="sxs-lookup"><span data-stu-id="2b4f4-107">_ulState_</span></span>
  
> <span data-ttu-id="2b4f4-108">[in]要设置为后台处理程序的状态。</span><span class="sxs-lookup"><span data-stu-id="2b4f4-108">[in] The state to set the spooler to.</span></span> <span data-ttu-id="2b4f4-109">它必须是下列值之一：</span><span class="sxs-lookup"><span data-stu-id="2b4f4-109">It must be one of the following values:</span></span>
    
 <span data-ttu-id="2b4f4-110">**SS_ACTIVE**</span><span class="sxs-lookup"><span data-stu-id="2b4f4-110">**SS_ACTIVE**</span></span>
  
> 
    
 <span data-ttu-id="2b4f4-111">**SS_SUSPENDED**</span><span class="sxs-lookup"><span data-stu-id="2b4f4-111">**SS_SUSPENDED**</span></span>
  
> 
    
## <a name="see-also"></a><span data-ttu-id="2b4f4-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b4f4-112">See also</span></span>



[<span data-ttu-id="2b4f4-113">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="2b4f4-113">MAPI Constants</span></span>](mapi-constants.md)

