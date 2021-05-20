---
title: ISocialPersonGetActivities
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: cf727140-f6e7-4718-bd74-1f8feeccf70c
description: Social Connector 2013 中Outlook弃用此方法。
ms.openlocfilehash: abad4fc2a3e3aaea8a7097ac7e6f56b0aadae299
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437740"
---
# <a name="isocialpersongetactivities"></a><span data-ttu-id="c520a-103">ISocialPerson::GetActivities</span><span class="sxs-lookup"><span data-stu-id="c520a-103">ISocialPerson::GetActivities</span></span>

<span data-ttu-id="c520a-104">Social Connector 2013 中Outlook弃用此方法。</span><span class="sxs-lookup"><span data-stu-id="c520a-104">This method has been deprecated in Outlook Social Connector 2013.</span></span>
  
```cpp
HRESULT _stdcall GetActivities([in] DATE startTime, [out, retval] BSTR* activities);
```

## <a name="remarks"></a><span data-ttu-id="c520a-105">备注</span><span class="sxs-lookup"><span data-stu-id="c520a-105">Remarks</span></span>

<span data-ttu-id="c520a-106">从 Outlook Social Connector 2013 开始，OSC 仅支持按需同步活动，而不允许缓存或混合同步活动。</span><span class="sxs-lookup"><span data-stu-id="c520a-106">Starting in Outlook Social Connector 2013, the OSC supports only on-demand synchronization of activities and not cached or hybrid synchronization of activities.</span></span> <span data-ttu-id="c520a-107">OSC 将忽略功能 XML **中的 cacheActivities** 设置，并且不调用此方法。</span><span class="sxs-lookup"><span data-stu-id="c520a-107">The OSC ignores the **cacheActivities** setting in the capabilities XML and does not call this method.</span></span> <span data-ttu-id="c520a-108">若要支持动态活动查找，请实现 [ISocialSession2：：GetActivitiesEx](isocialsession2-getactivitiesex.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="c520a-108">To support dynamic activities lookup, implement the [ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md) method.</span></span> <span data-ttu-id="c520a-109">将 **cacheActivities** 设置为 **false，** 将 **getActivities 和 dynamicActivitiesLookupEx** 设置为 **true**，这将提示 OSC 改为调用 **ISocialSession2：：GetActivitiesEx。**</span><span class="sxs-lookup"><span data-stu-id="c520a-109">Set **cacheActivities** as **false**, **getActivities** and **dynamicActivitiesLookupEx** as **true**, which will prompt the OSC to call **ISocialSession2::GetActivitiesEx** instead.</span></span> 
  
<span data-ttu-id="c520a-110">有关 OSC 如何获取好友活动的信息，请参阅同步好友 [和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="c520a-110">For more information about how the OSC gets friends' activities, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c520a-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c520a-111">See also</span></span>

- [<span data-ttu-id="c520a-112">ISocialPerson : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c520a-112">ISocialPerson : IUnknown</span></span>](isocialpersoniunknown.md)

