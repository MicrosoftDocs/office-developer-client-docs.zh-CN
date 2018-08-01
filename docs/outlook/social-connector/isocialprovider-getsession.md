---
title: ISocialProviderGetSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 371b48c5-6d77-4d2d-890c-bb234c7eaabc
description: 获取 ISocialSession 接口。
ms.openlocfilehash: 59e6f61e1954f64d875c6336b211dcb530100252
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779237"
---
# <a name="isocialprovidergetsession"></a><span data-ttu-id="7b8ac-103">ISocialProvider::GetSession</span><span class="sxs-lookup"><span data-stu-id="7b8ac-103">ISocialProvider::GetSession</span></span>

<span data-ttu-id="7b8ac-104">获取[ISocialSession](isocialsessioniunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="7b8ac-104">Gets an [ISocialSession](isocialsessioniunknown.md) interface.</span></span> 
  
```cpp
HRESULT _stdcall GetSession([out, retval] ISocialSession** session);
```

## <a name="parameters"></a><span data-ttu-id="7b8ac-105">参数</span><span class="sxs-lookup"><span data-stu-id="7b8ac-105">Parameters</span></span>

<span data-ttu-id="7b8ac-106">_Session_</span><span class="sxs-lookup"><span data-stu-id="7b8ac-106">_session_</span></span>
  
> <span data-ttu-id="7b8ac-107">[out] **ISocialSession** 界面。</span><span class="sxs-lookup"><span data-stu-id="7b8ac-107">[out] An **ISocialSession** interface.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="7b8ac-108">说明</span><span class="sxs-lookup"><span data-stu-id="7b8ac-108">Remarks</span></span>

<span data-ttu-id="7b8ac-109">Outlook Social Connector (OSC) 使用**ISocialSession**接口登录到社交网络。</span><span class="sxs-lookup"><span data-stu-id="7b8ac-109">The Outlook Social Connector (OSC) uses the **ISocialSession** interface to log on to the social network.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7b8ac-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b8ac-110">See also</span></span>

- [<span data-ttu-id="7b8ac-111">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7b8ac-111">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

