---
title: IMAPIGetSessionGetMAPISession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIGetSession.GetMAPISession
api_type:
- COM
ms.assetid: 581db5d9-35f7-43ad-aef3-a5d5da310150
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8090d9b1a1f7fb571532cf32d7a2412261aee1fc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775442"
---
# <a name="imapigetsessiongetmapisession"></a><span data-ttu-id="c9a9a-103">IMAPIGetSession::GetMAPISession</span><span class="sxs-lookup"><span data-stu-id="c9a9a-103">IMAPIGetSession::GetMAPISession</span></span>

  
  
<span data-ttu-id="c9a9a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c9a9a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c9a9a-105">返回到与 MAPI 支持对象关联的 MAPI 会话的指针。</span><span class="sxs-lookup"><span data-stu-id="c9a9a-105">Returns a pointer to the MAPI session associated with the MAPI support object.</span></span>
  
```cpp
HRESULT GetMAPISession(
  LPUNKNOWN *  lppSession
);
```

## <a name="parameters"></a><span data-ttu-id="c9a9a-106">参数</span><span class="sxs-lookup"><span data-stu-id="c9a9a-106">Parameters</span></span>

 <span data-ttu-id="c9a9a-107">_lppSession_</span><span class="sxs-lookup"><span data-stu-id="c9a9a-107">_lppSession_</span></span>
  
> <span data-ttu-id="c9a9a-108">[输出]一个指向当前的 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="c9a9a-108">[out] A pointer to the current MAPI session.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c9a9a-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9a9a-109">See also</span></span>



[<span data-ttu-id="c9a9a-110">IMAPIGetSession: IUnknown</span><span class="sxs-lookup"><span data-stu-id="c9a9a-110">IMAPIGetSession : IUnknown</span></span>](imapigetsessioniunknown.md)


[<span data-ttu-id="c9a9a-111">支持对象概述</span><span class="sxs-lookup"><span data-stu-id="c9a9a-111">Support Object Overview</span></span>](support-object-overview.md)

