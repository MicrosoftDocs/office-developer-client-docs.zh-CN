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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e988114e8e71ad1f80d20ab0d5a30c37425f5952
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315055"
---
# <a name="ipstx2setspoolsuspendstate"></a><span data-ttu-id="7af1e-103">IPSTX2::SetSpoolSuspendState</span><span class="sxs-lookup"><span data-stu-id="7af1e-103">IPSTX2::SetSpoolSuspendState</span></span>

  
  
<span data-ttu-id="7af1e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7af1e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7af1e-105">设置后台处理程序的挂起状态。</span><span class="sxs-lookup"><span data-stu-id="7af1e-105">Sets the suspended state on the spooler.</span></span>
  
```cpp
void SetSpoolSuspendState( 
    ULONG ulState 
);
```

## <a name="parameters"></a><span data-ttu-id="7af1e-106">参数</span><span class="sxs-lookup"><span data-stu-id="7af1e-106">Parameters</span></span>

 <span data-ttu-id="7af1e-107">_ulState_</span><span class="sxs-lookup"><span data-stu-id="7af1e-107">_ulState_</span></span>
  
> <span data-ttu-id="7af1e-108">实时要将后台打印程序设置为的状态。</span><span class="sxs-lookup"><span data-stu-id="7af1e-108">[in] The state to set the spooler to.</span></span> <span data-ttu-id="7af1e-109">它必须是下列值之一:</span><span class="sxs-lookup"><span data-stu-id="7af1e-109">It must be one of the following values:</span></span>
    
 <span data-ttu-id="7af1e-110">**SS_ACTIVE**</span><span class="sxs-lookup"><span data-stu-id="7af1e-110">**SS_ACTIVE**</span></span>
  
> 
    
 <span data-ttu-id="7af1e-111">**SS_SUSPENDED**</span><span class="sxs-lookup"><span data-stu-id="7af1e-111">**SS_SUSPENDED**</span></span>
  
> 
    
## <a name="see-also"></a><span data-ttu-id="7af1e-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7af1e-112">See also</span></span>



[<span data-ttu-id="7af1e-113">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="7af1e-113">MAPI Constants</span></span>](mapi-constants.md)

