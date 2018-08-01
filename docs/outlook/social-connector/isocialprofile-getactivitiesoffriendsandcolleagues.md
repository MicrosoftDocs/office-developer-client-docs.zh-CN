---
title: ISocialProfileGetActivitiesOfFriendsAndColleagues
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 4aaf7417-0a03-42a4-a282-599327ec5381
description: Outlook Social Connector 2013 中已弃用此方法。
ms.openlocfilehash: 54b5cd6d681aa1e8008eade024ef57783bf18ead
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779247"
---
# <a name="isocialprofilegetactivitiesoffriendsandcolleagues"></a><span data-ttu-id="04ad3-103">ISocialProfile::GetActivitiesOfFriendsAndColleagues</span><span class="sxs-lookup"><span data-stu-id="04ad3-103">ISocialProfile::GetActivitiesOfFriendsAndColleagues</span></span>

<span data-ttu-id="04ad3-104">Outlook Social Connector 2013 中已弃用此方法。</span><span class="sxs-lookup"><span data-stu-id="04ad3-104">This method has been deprecated in Outlook Social Connector 2013.</span></span>
  
```cpp
HRESULT _stdcall GetActivitiesOfFriendsAndColleagues([in] DATE startTime, [out, retval] BSTR* activitiesCollection);
```

## <a name="remarks"></a><span data-ttu-id="04ad3-105">说明</span><span class="sxs-lookup"><span data-stu-id="04ad3-105">Remarks</span></span>

<span data-ttu-id="04ad3-106">Outlook Social Connector 2013、 OSC 支持仅按需活动同步和不在缓存或活动同步混合中启动。</span><span class="sxs-lookup"><span data-stu-id="04ad3-106">Starting in Outlook Social Connector 2013, the OSC supports only on-demand synchronization of activities and not cached or hybrid synchronization of activities.</span></span> <span data-ttu-id="04ad3-107">OSC 忽略的功能 XML 中的**cacheActivities**设置，无法再调用此方法。</span><span class="sxs-lookup"><span data-stu-id="04ad3-107">The OSC ignores the **cacheActivities** setting in the capabilities XML and no longer calls this method.</span></span> <span data-ttu-id="04ad3-108">若要支持动态活动查找，实现[ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md)方法。</span><span class="sxs-lookup"><span data-stu-id="04ad3-108">To support dynamic activities lookup, implement the [ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md) method.</span></span> <span data-ttu-id="04ad3-109">将**getActivities**和**dynamicActivitiesLookupEx**设置为**true**，这将提示呼叫**ISocialSession2::GetActivitiesEx**改为 OSC。</span><span class="sxs-lookup"><span data-stu-id="04ad3-109">Set **getActivities** and **dynamicActivitiesLookupEx** as **true**, which will prompt the OSC to call **ISocialSession2::GetActivitiesEx** instead.</span></span> 
  
<span data-ttu-id="04ad3-110">有关如何 OSC 获取朋友的活动的详细信息，请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="04ad3-110">For more information about how the OSC gets friends' activities, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="04ad3-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04ad3-111">See also</span></span>

- [<span data-ttu-id="04ad3-112">ISocialProfile : ISocialPerson</span><span class="sxs-lookup"><span data-stu-id="04ad3-112">ISocialProfile : ISocialPerson</span></span>](isocialprofileisocialperson.md)

