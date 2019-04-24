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
ms.openlocfilehash: afa13bddd5cbbc53081f6ae7ddcc1671d1c40303
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285770"
---
# <a name="isocialprovidergetsession"></a><span data-ttu-id="8a667-103">ISocialProvider::GetSession</span><span class="sxs-lookup"><span data-stu-id="8a667-103">ISocialProvider::GetSession</span></span>

<span data-ttu-id="8a667-104">获取[ISocialSession](isocialsessioniunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="8a667-104">Gets an [ISocialSession](isocialsessioniunknown.md) interface.</span></span> 
  
```cpp
HRESULT _stdcall GetSession([out, retval] ISocialSession** session);
```

## <a name="parameters"></a><span data-ttu-id="8a667-105">参数</span><span class="sxs-lookup"><span data-stu-id="8a667-105">Parameters</span></span>

<span data-ttu-id="8a667-106">_Session_</span><span class="sxs-lookup"><span data-stu-id="8a667-106">_session_</span></span>
  
> <span data-ttu-id="8a667-107">[out] **ISocialSession** 界面。</span><span class="sxs-lookup"><span data-stu-id="8a667-107">[out] An **ISocialSession** interface.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="8a667-108">说明</span><span class="sxs-lookup"><span data-stu-id="8a667-108">Remarks</span></span>

<span data-ttu-id="8a667-109">Outlook Social Connector (.osc) 使用**ISocialSession**接口登录到社交网络。</span><span class="sxs-lookup"><span data-stu-id="8a667-109">The Outlook Social Connector (OSC) uses the **ISocialSession** interface to log on to the social network.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8a667-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a667-110">See also</span></span>

- [<span data-ttu-id="8a667-111">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="8a667-111">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

