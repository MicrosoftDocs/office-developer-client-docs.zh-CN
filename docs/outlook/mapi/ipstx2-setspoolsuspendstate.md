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
ms.openlocfilehash: 30ec82788e46ca07c6529ce74872e0a0c7c012a1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776050"
---
# <a name="ipstx2setspoolsuspendstate"></a><span data-ttu-id="83ed9-103">IPSTX2::SetSpoolSuspendState</span><span class="sxs-lookup"><span data-stu-id="83ed9-103">IPSTX2::SetSpoolSuspendState</span></span>

  
  
<span data-ttu-id="83ed9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="83ed9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="83ed9-105">在后台处理程序上设置的挂起的状态。</span><span class="sxs-lookup"><span data-stu-id="83ed9-105">Sets the suspended state on the spooler.</span></span>
  
```cpp
void SetSpoolSuspendState( 
    ULONG ulState 
);
```

## <a name="parameters"></a><span data-ttu-id="83ed9-106">参数</span><span class="sxs-lookup"><span data-stu-id="83ed9-106">Parameters</span></span>

 <span data-ttu-id="83ed9-107">_ulState_</span><span class="sxs-lookup"><span data-stu-id="83ed9-107">_ulState_</span></span>
  
> <span data-ttu-id="83ed9-108">[in]要设置为后台处理程序的状态。</span><span class="sxs-lookup"><span data-stu-id="83ed9-108">[in] The state to set the spooler to.</span></span> <span data-ttu-id="83ed9-109">它必须是下列值之一：</span><span class="sxs-lookup"><span data-stu-id="83ed9-109">It must be one of the following values:</span></span>
    
 <span data-ttu-id="83ed9-110">**SS_ACTIVE**</span><span class="sxs-lookup"><span data-stu-id="83ed9-110">**SS_ACTIVE**</span></span>
  
> 
    
 <span data-ttu-id="83ed9-111">**SS_SUSPENDED**</span><span class="sxs-lookup"><span data-stu-id="83ed9-111">**SS_SUSPENDED**</span></span>
  
> 
    
## <a name="see-also"></a><span data-ttu-id="83ed9-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83ed9-112">See also</span></span>



[<span data-ttu-id="83ed9-113">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="83ed9-113">MAPI Constants</span></span>](mapi-constants.md)

