---
title: ISocialProfileGetActivitiesOfFriendsAndColleagues
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 4aaf7417-0a03-42a4-a282-599327ec5381
description: Social Connector 2013 中Outlook弃用此方法。
ms.openlocfilehash: c02cf0e8a6d2da3f9fb7704c92e10e0409042393
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406890"
---
# <a name="isocialprofilegetactivitiesoffriendsandcolleagues"></a><span data-ttu-id="f8d90-103">ISocialProfile::GetActivitiesOfFriendsAndColleagues</span><span class="sxs-lookup"><span data-stu-id="f8d90-103">ISocialProfile::GetActivitiesOfFriendsAndColleagues</span></span>

<span data-ttu-id="f8d90-104">Social Connector 2013 中Outlook弃用此方法。</span><span class="sxs-lookup"><span data-stu-id="f8d90-104">This method has been deprecated in Outlook Social Connector 2013.</span></span>
  
```cpp
HRESULT _stdcall GetActivitiesOfFriendsAndColleagues([in] DATE startTime, [out, retval] BSTR* activitiesCollection);
```

## <a name="remarks"></a><span data-ttu-id="f8d90-105">备注</span><span class="sxs-lookup"><span data-stu-id="f8d90-105">Remarks</span></span>

<span data-ttu-id="f8d90-106">从 Outlook Social Connector 2013 开始，OSC 仅支持按需同步活动，而不允许缓存或混合同步活动。</span><span class="sxs-lookup"><span data-stu-id="f8d90-106">Starting in Outlook Social Connector 2013, the OSC supports only on-demand synchronization of activities and not cached or hybrid synchronization of activities.</span></span> <span data-ttu-id="f8d90-107">OSC 将忽略功能 XML **中的 cacheActivities** 设置，并且不再调用此方法。</span><span class="sxs-lookup"><span data-stu-id="f8d90-107">The OSC ignores the **cacheActivities** setting in the capabilities XML and no longer calls this method.</span></span> <span data-ttu-id="f8d90-108">若要支持动态活动查找，请实现 [ISocialSession2：：GetActivitiesEx](isocialsession2-getactivitiesex.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="f8d90-108">To support dynamic activities lookup, implement the [ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md) method.</span></span> <span data-ttu-id="f8d90-109">将 **getActivities** 和 **dynamicActivitiesLookupEx** 设置为 **true**，这将提示 OSC 改为调用 **ISocialSession2：：GetActivitiesEx。**</span><span class="sxs-lookup"><span data-stu-id="f8d90-109">Set **getActivities** and **dynamicActivitiesLookupEx** as **true**, which will prompt the OSC to call **ISocialSession2::GetActivitiesEx** instead.</span></span> 
  
<span data-ttu-id="f8d90-110">有关 OSC 如何获取好友活动的信息，请参阅同步好友 [和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="f8d90-110">For more information about how the OSC gets friends' activities, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f8d90-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8d90-111">See also</span></span>

- [<span data-ttu-id="f8d90-112">ISocialProfile : ISocialPerson</span><span class="sxs-lookup"><span data-stu-id="f8d90-112">ISocialProfile : ISocialPerson</span></span>](isocialprofileisocialperson.md)

