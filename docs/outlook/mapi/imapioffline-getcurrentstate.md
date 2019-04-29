---
title: IMAPIOfflineGetCurrentState
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOffline.GetCurrentState
api_type:
- COM
ms.assetid: f3769e83-d678-1087-fc0f-b4f156386333
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f5170ceb443dcde075440bf84d29000afe4680c7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419868"
---
# <a name="imapiofflinegetcurrentstate"></a><span data-ttu-id="d7ff9-103">IMAPIOffline::GetCurrentState</span><span class="sxs-lookup"><span data-stu-id="d7ff9-103">IMAPIOffline::GetCurrentState</span></span>

  
  
<span data-ttu-id="d7ff9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d7ff9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d7ff9-105">获取脱机对象的当前联机或脱机状态。</span><span class="sxs-lookup"><span data-stu-id="d7ff9-105">Gets the current online or offline state of an offline object.</span></span>
  
```cpp
HRESULT GetCurrentState( 
    ULONG* pulState 
);
```

## <a name="parameters"></a><span data-ttu-id="d7ff9-106">参数</span><span class="sxs-lookup"><span data-stu-id="d7ff9-106">Parameters</span></span>

 <span data-ttu-id="d7ff9-107">_pulState_</span><span class="sxs-lookup"><span data-stu-id="d7ff9-107">_pulState_</span></span>
  
> <span data-ttu-id="d7ff9-108">排除脱机对象的当前联机或脱机状态。</span><span class="sxs-lookup"><span data-stu-id="d7ff9-108">[out] The current online or offline state of an offline object.</span></span> <span data-ttu-id="d7ff9-109">它必须是以下两个值之一:</span><span class="sxs-lookup"><span data-stu-id="d7ff9-109">It must be one of these two values:</span></span>
    
<span data-ttu-id="d7ff9-110">MAPIOFFLINE_STATE_ONLINE</span><span class="sxs-lookup"><span data-stu-id="d7ff9-110">MAPIOFFLINE_STATE_ONLINE</span></span>
  
> 
    
<span data-ttu-id="d7ff9-111">MAPIOFFLINE_STATE_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="d7ff9-111">MAPIOFFLINE_STATE_OFFLINE</span></span>
  
> 
    
## <a name="see-also"></a><span data-ttu-id="d7ff9-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7ff9-112">See also</span></span>



[<span data-ttu-id="d7ff9-113">IMAPIOffline::GetCapabilities</span><span class="sxs-lookup"><span data-stu-id="d7ff9-113">IMAPIOffline::GetCapabilities</span></span>](imapioffline-getcapabilities.md)
  
[<span data-ttu-id="d7ff9-114">IMAPIOffline::SetCurrentState</span><span class="sxs-lookup"><span data-stu-id="d7ff9-114">IMAPIOffline::SetCurrentState</span></span>](imapioffline-setcurrentstate.md)


[<span data-ttu-id="d7ff9-115">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="d7ff9-115">MAPI Constants</span></span>](mapi-constants.md)

