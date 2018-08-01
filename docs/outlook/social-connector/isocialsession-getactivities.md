---
title: ISocialSessionGetActivities
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6546be99-aee4-41a6-8297-ace378776503
description: OSC 1.1 中已弃用此方法。
ms.openlocfilehash: dc5fe25e4c4f83717309d407963d0046aa6063ec
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779230"
---
# <a name="isocialsessiongetactivities"></a><span data-ttu-id="bd3eb-103">ISocialSession::GetActivities</span><span class="sxs-lookup"><span data-stu-id="bd3eb-103">ISocialSession::GetActivities</span></span>

<span data-ttu-id="bd3eb-104">OSC 1.1 中已弃用此方法。</span><span class="sxs-lookup"><span data-stu-id="bd3eb-104">This method has been deprecated in OSC 1.1.</span></span>
  
```cpp
HRESULT GetActivities([in] SAFEARRAY(BSTR) emailAddresses, [in] DATE startTime, [out, retval] BSTR *activities);
```

## <a name="remarks"></a><span data-ttu-id="bd3eb-105">说明</span><span class="sxs-lookup"><span data-stu-id="bd3eb-105">Remarks</span></span>

<span data-ttu-id="bd3eb-106">OSC 1.1 中启动 OSC 不再调用**GetActivities**。</span><span class="sxs-lookup"><span data-stu-id="bd3eb-106">Starting in OSC 1.1, the OSC no longer calls **GetActivities**.</span></span> <span data-ttu-id="bd3eb-107">OSC 忽略**dynamicActivitiesLookup**的值。</span><span class="sxs-lookup"><span data-stu-id="bd3eb-107">The OSC ignores the value of **dynamicActivitiesLookup**.</span></span> <span data-ttu-id="bd3eb-108">若要支持动态活动查找，实现[ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md)方法。</span><span class="sxs-lookup"><span data-stu-id="bd3eb-108">To support dynamic activities lookup, implement the [ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md) method.</span></span> <span data-ttu-id="bd3eb-109">设置为**false**，和**getActivities**和为**true**，这将会进行提示 OSC 改为呼叫**ISocialSession2::GetActivitiesEx** **dynamicActivitiesLookupEx** **cacheActivities** 。</span><span class="sxs-lookup"><span data-stu-id="bd3eb-109">Set **cacheActivities** as **false**, and **getActivities** and **dynamicActivitiesLookupEx** as **true**, which will prompt the OSC to call **ISocialSession2::GetActivitiesEx** instead.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bd3eb-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd3eb-110">See also</span></span>

- [<span data-ttu-id="bd3eb-111">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bd3eb-111">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

