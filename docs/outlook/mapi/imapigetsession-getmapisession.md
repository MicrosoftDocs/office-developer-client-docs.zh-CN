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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: dbf9f9f73d9e3860b482f81fb942673e6d373267
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439609"
---
# <a name="imapigetsessiongetmapisession"></a><span data-ttu-id="bcc53-103">IMAPIGetSession::GetMAPISession</span><span class="sxs-lookup"><span data-stu-id="bcc53-103">IMAPIGetSession::GetMAPISession</span></span>

  
  
<span data-ttu-id="bcc53-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bcc53-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bcc53-105">返回一个指向与 MAPI 支持对象关联的 MAPI 会话的指针。</span><span class="sxs-lookup"><span data-stu-id="bcc53-105">Returns a pointer to the MAPI session associated with the MAPI support object.</span></span>
  
```cpp
HRESULT GetMAPISession(
  LPUNKNOWN *  lppSession
);
```

## <a name="parameters"></a><span data-ttu-id="bcc53-106">参数</span><span class="sxs-lookup"><span data-stu-id="bcc53-106">Parameters</span></span>

 <span data-ttu-id="bcc53-107">_lppSession_</span><span class="sxs-lookup"><span data-stu-id="bcc53-107">_lppSession_</span></span>
  
> <span data-ttu-id="bcc53-108">[out]指向当前 MAPI 会话的指针。</span><span class="sxs-lookup"><span data-stu-id="bcc53-108">[out] A pointer to the current MAPI session.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bcc53-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bcc53-109">See also</span></span>



[<span data-ttu-id="bcc53-110">IMAPIGetSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bcc53-110">IMAPIGetSession : IUnknown</span></span>](imapigetsessioniunknown.md)


[<span data-ttu-id="bcc53-111">支持对象概述</span><span class="sxs-lookup"><span data-stu-id="bcc53-111">Support Object Overview</span></span>](support-object-overview.md)

