---
title: ISocialSessionGetActivities
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6546be99-aee4-41a6-8297-ace378776503
description: 在 .osc 1.1 中已弃用此方法。
ms.openlocfilehash: 29a7cdc9895dcfa2bd926d95dbd2089b7a5dc778
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439294"
---
# <a name="isocialsessiongetactivities"></a><span data-ttu-id="f3e38-103">ISocialSession::GetActivities</span><span class="sxs-lookup"><span data-stu-id="f3e38-103">ISocialSession::GetActivities</span></span>

<span data-ttu-id="f3e38-104">在 .osc 1.1 中已弃用此方法。</span><span class="sxs-lookup"><span data-stu-id="f3e38-104">This method has been deprecated in OSC 1.1.</span></span>
  
```cpp
HRESULT GetActivities([in] SAFEARRAY(BSTR) emailAddresses, [in] DATE startTime, [out, retval] BSTR *activities);
```

## <a name="remarks"></a><span data-ttu-id="f3e38-105">说明</span><span class="sxs-lookup"><span data-stu-id="f3e38-105">Remarks</span></span>

<span data-ttu-id="f3e38-106">从 .osc 1.1 开始, .osc 将不再调用**GetActivities**。</span><span class="sxs-lookup"><span data-stu-id="f3e38-106">Starting in OSC 1.1, the OSC no longer calls **GetActivities**.</span></span> <span data-ttu-id="f3e38-107">.osc 忽略**dynamicActivitiesLookup**的值。</span><span class="sxs-lookup"><span data-stu-id="f3e38-107">The OSC ignores the value of **dynamicActivitiesLookup**.</span></span> <span data-ttu-id="f3e38-108">若要支持动态活动查找, 请实现[ISocialSession2:: GetActivitiesEx](isocialsession2-getactivitiesex.md)方法。</span><span class="sxs-lookup"><span data-stu-id="f3e38-108">To support dynamic activities lookup, implement the [ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md) method.</span></span> <span data-ttu-id="f3e38-109">将**cacheActivities**设置为**false**, 并将**getActivities**和**dynamicActivitiesLookupEx**设置为**true**, 这将提示 .osc 调用**ISocialSession2:: GetActivitiesEx**而不是。</span><span class="sxs-lookup"><span data-stu-id="f3e38-109">Set **cacheActivities** as **false**, and **getActivities** and **dynamicActivitiesLookupEx** as **true**, which will prompt the OSC to call **ISocialSession2::GetActivitiesEx** instead.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f3e38-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3e38-110">See also</span></span>

- [<span data-ttu-id="f3e38-111">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f3e38-111">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

