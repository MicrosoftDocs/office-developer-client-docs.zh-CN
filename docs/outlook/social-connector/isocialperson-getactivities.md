---
title: ISocialPersonGetActivities
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: cf727140-f6e7-4718-bd74-1f8feeccf70c
description: 此方法在 Outlook Social Connector 2013 中已被弃用。
ms.openlocfilehash: abad4fc2a3e3aaea8a7097ac7e6f56b0aadae299
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437740"
---
# <a name="isocialpersongetactivities"></a><span data-ttu-id="284c2-103">ISocialPerson::GetActivities</span><span class="sxs-lookup"><span data-stu-id="284c2-103">ISocialPerson::GetActivities</span></span>

<span data-ttu-id="284c2-104">此方法在 Outlook Social Connector 2013 中已被弃用。</span><span class="sxs-lookup"><span data-stu-id="284c2-104">This method has been deprecated in Outlook Social Connector 2013.</span></span>
  
```cpp
HRESULT _stdcall GetActivities([in] DATE startTime, [out, retval] BSTR* activities);
```

## <a name="remarks"></a><span data-ttu-id="284c2-105">说明</span><span class="sxs-lookup"><span data-stu-id="284c2-105">Remarks</span></span>

<span data-ttu-id="284c2-106">从 Outlook Social Connector 2013 开始, .osc 仅支持对活动进行按需同步, 而不支持对活动进行缓存或混合同步。</span><span class="sxs-lookup"><span data-stu-id="284c2-106">Starting in Outlook Social Connector 2013, the OSC supports only on-demand synchronization of activities and not cached or hybrid synchronization of activities.</span></span> <span data-ttu-id="284c2-107">.osc 忽略功能 XML 中的**cacheActivities**设置, 不会调用此方法。</span><span class="sxs-lookup"><span data-stu-id="284c2-107">The OSC ignores the **cacheActivities** setting in the capabilities XML and does not call this method.</span></span> <span data-ttu-id="284c2-108">若要支持动态活动查找, 请实现[ISocialSession2:: GetActivitiesEx](isocialsession2-getactivitiesex.md)方法。</span><span class="sxs-lookup"><span data-stu-id="284c2-108">To support dynamic activities lookup, implement the [ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md) method.</span></span> <span data-ttu-id="284c2-109">将**cacheActivities**设置为**false**、 **getActivities**和**dynamicActivitiesLookupEx**为**true**, 这将提示 .osc 调用**ISocialSession2:: GetActivitiesEx** 。</span><span class="sxs-lookup"><span data-stu-id="284c2-109">Set **cacheActivities** as **false**, **getActivities** and **dynamicActivitiesLookupEx** as **true**, which will prompt the OSC to call **ISocialSession2::GetActivitiesEx** instead.</span></span> 
  
<span data-ttu-id="284c2-110">有关 .osc 如何获取好友活动的详细信息, 请参阅[同步好友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="284c2-110">For more information about how the OSC gets friends' activities, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="284c2-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="284c2-111">See also</span></span>

- [<span data-ttu-id="284c2-112">ISocialPerson : IUnknown</span><span class="sxs-lookup"><span data-stu-id="284c2-112">ISocialPerson : IUnknown</span></span>](isocialpersoniunknown.md)

