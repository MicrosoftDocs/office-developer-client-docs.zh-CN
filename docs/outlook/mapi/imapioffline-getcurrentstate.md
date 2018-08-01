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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3cf8ad3966c44add3fd85b9f1adf677039bfce15
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775488"
---
# <a name="imapiofflinegetcurrentstate"></a><span data-ttu-id="b3cb5-103">IMAPIOffline::GetCurrentState</span><span class="sxs-lookup"><span data-stu-id="b3cb5-103">IMAPIOffline::GetCurrentState</span></span>

  
  
<span data-ttu-id="b3cb5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b3cb5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b3cb5-105">获取一个脱机对象的当前联机或脱机状态。</span><span class="sxs-lookup"><span data-stu-id="b3cb5-105">Gets the current online or offline state of an offline object.</span></span>
  
```cpp
HRESULT GetCurrentState( 
    ULONG* pulState 
);
```

## <a name="parameters"></a><span data-ttu-id="b3cb5-106">参数</span><span class="sxs-lookup"><span data-stu-id="b3cb5-106">Parameters</span></span>

 <span data-ttu-id="b3cb5-107">_pulState_</span><span class="sxs-lookup"><span data-stu-id="b3cb5-107">_pulState_</span></span>
  
> <span data-ttu-id="b3cb5-108">[输出]脱机对象的当前联机或脱机状态。</span><span class="sxs-lookup"><span data-stu-id="b3cb5-108">[out] The current online or offline state of an offline object.</span></span> <span data-ttu-id="b3cb5-109">它必须是这两个值之一：</span><span class="sxs-lookup"><span data-stu-id="b3cb5-109">It must be one of these two values:</span></span>
    
<span data-ttu-id="b3cb5-110">MAPIOFFLINE_STATE_ONLINE</span><span class="sxs-lookup"><span data-stu-id="b3cb5-110">MAPIOFFLINE_STATE_ONLINE</span></span>
  
> 
    
<span data-ttu-id="b3cb5-111">MAPIOFFLINE_STATE_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="b3cb5-111">MAPIOFFLINE_STATE_OFFLINE</span></span>
  
> 
    
## <a name="see-also"></a><span data-ttu-id="b3cb5-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3cb5-112">See also</span></span>



[<span data-ttu-id="b3cb5-113">IMAPIOffline::GetCapabilities</span><span class="sxs-lookup"><span data-stu-id="b3cb5-113">IMAPIOffline::GetCapabilities</span></span>](imapioffline-getcapabilities.md)
  
[<span data-ttu-id="b3cb5-114">IMAPIOffline::SetCurrentState</span><span class="sxs-lookup"><span data-stu-id="b3cb5-114">IMAPIOffline::SetCurrentState</span></span>](imapioffline-setcurrentstate.md)


[<span data-ttu-id="b3cb5-115">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="b3cb5-115">MAPI Constants</span></span>](mapi-constants.md)

