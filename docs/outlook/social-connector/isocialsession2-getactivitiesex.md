---
title: ISocialSession2GetActivitiesEx
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: bfe30c22-017b-42e0-93be-c85d674c07e3
description: 获取一个字符串, 表示由 hashedAddresses 参数指定的每个用户的活动的集合。
ms.openlocfilehash: be29d0226eb137b1ad8ed025acfe3f4958efa85f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404335"
---
# <a name="isocialsession2getactivitiesex"></a><span data-ttu-id="d277d-103">ISocialSession2::GetActivitiesEx</span><span class="sxs-lookup"><span data-stu-id="d277d-103">ISocialSession2::GetActivitiesEx</span></span>

<span data-ttu-id="d277d-104">获取一个字符串, 表示由_hashedAddresses_参数指定的每个用户的活动的集合。</span><span class="sxs-lookup"><span data-stu-id="d277d-104">Gets a string that represents a collection of activities of each of the users specified by the  _hashedAddresses_ parameter.</span></span> 
  
```cpp
HRESULT _stdcall GetActivitiesEx([in] SAFEARRAY(BSTR) hashedAddresses, [in] DATE startTime, [out, retval] BSTR *activities);
```

## <a name="parameters"></a><span data-ttu-id="d277d-105">参数</span><span class="sxs-lookup"><span data-stu-id="d277d-105">Parameters</span></span>

<span data-ttu-id="d277d-106">_hashedAddresses_</span><span class="sxs-lookup"><span data-stu-id="d277d-106">_hashedAddresses_</span></span>
  
> <span data-ttu-id="d277d-107">实时指定一组用户的哈希 SMTP 地址数组的结构。</span><span class="sxs-lookup"><span data-stu-id="d277d-107">[in] A structure that specifies an array of hashed SMTP addresses for a set of users.</span></span>
    
<span data-ttu-id="d277d-108">_startTime_</span><span class="sxs-lookup"><span data-stu-id="d277d-108">_startTime_</span></span>
  
> <span data-ttu-id="d277d-109">实时在其后将返回创建的活动的时间。</span><span class="sxs-lookup"><span data-stu-id="d277d-109">[in] The time after which activities that are created would be returned.</span></span>
    
<span data-ttu-id="d277d-110">_activities_</span><span class="sxs-lookup"><span data-stu-id="d277d-110">_activities_</span></span>
  
> <span data-ttu-id="d277d-111">排除一个 XML 字符串, 表示自_startTime_以来由社交网络上的_hashedAddresses_指定的用户的一组活动。</span><span class="sxs-lookup"><span data-stu-id="d277d-111">[out] An XML string that represents the set of activities of the users specified by  _hashedAddresses_ on the social network since  _startTime_.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d277d-112">说明</span><span class="sxs-lookup"><span data-stu-id="d277d-112">Remarks</span></span>

<span data-ttu-id="d277d-113">如果 .osc 提供程序支持按需同步的活动, 则 .osc 会调用**GetActivitiesEx** 。</span><span class="sxs-lookup"><span data-stu-id="d277d-113">The OSC calls **GetActivitiesEx** if the OSC provider supports on-demand synchronization of activities.</span></span> <span data-ttu-id="d277d-114">.osc 将返回的信息存储在内存中的_活动_中。</span><span class="sxs-lookup"><span data-stu-id="d277d-114">The OSC stores the information returned in  _activities_ in memory.</span></span> <span data-ttu-id="d277d-115">有关 .osc 如何在内存中使用和更新此信息的详细信息, 请参阅[同步好友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="d277d-115">For more information about how the OSC uses and updates this information in memory, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span>
  
<span data-ttu-id="d277d-116">从 Outlook Social Connector 2013 开始, .osc 仅支持活动的按需同步, 并且仅调用**GetActivitiesEx**获取活动。</span><span class="sxs-lookup"><span data-stu-id="d277d-116">Starting in Outlook Social Connector 2013, the OSC supports only on-demand synchronization of activities and calls only **GetActivitiesEx** to get activities.</span></span> <span data-ttu-id="d277d-117">若要支持按需活动查找, 请将**cacheActivities**设置为**false**, 将**getActivities**和**dynamicActivitiesLookupEx**设置为**true**, 并且 .osc 将调用**GetActivitiesEx**。</span><span class="sxs-lookup"><span data-stu-id="d277d-117">To support on-demand activities lookup, set **cacheActivities** as **false**, and **getActivities** and **dynamicActivitiesLookupEx** as **true**, and the OSC will call **GetActivitiesEx**.</span></span>
  
<span data-ttu-id="d277d-118">返回的 XML 字符串必须符合**microsoft.office.server.activityfeed**的架构定义, 如在您的 .osc 提供程序扩展性架构中定义的那样。</span><span class="sxs-lookup"><span data-stu-id="d277d-118">The returned XML string must comply with the schema definition for **activityFeed**, as defined in the schema for OSC provider extensibility.</span></span>
  
<span data-ttu-id="d277d-119">_hashedAddresses_ sring 表示在人员窗格中显示的每个用户的一组散列地址。</span><span class="sxs-lookup"><span data-stu-id="d277d-119">The  _hashedAddresses_ sring represents a set of hashed addresses for each user displayed in the People Pane.</span></span> <span data-ttu-id="d277d-120">哈希 SMTP 地址通过使用提供程序的**功能**XML 中的**hashFunction**元素指定的哈希函数进行加密。</span><span class="sxs-lookup"><span data-stu-id="d277d-120">The hashed SMTP addresses are encrypted by using the hashing function specified by the **hashFunction** element in the provider's **capabilities** XML.</span></span> <span data-ttu-id="d277d-121">用户不必是[ISocialSession:: LoggedOnUserName](isocialsession-loggedonusername.md)属性所表示的已登录用户的友元。</span><span class="sxs-lookup"><span data-stu-id="d277d-121">The user does not have to be a friend of the logged-on user represented by the [ISocialSession::LoggedOnUserName](isocialsession-loggedonusername.md) property.</span></span> 
  
<span data-ttu-id="d277d-122">_startTime_参数是以协调通用时间 (UTC) 表示的**日期**值。</span><span class="sxs-lookup"><span data-stu-id="d277d-122">The  _startTime_ parameter is a **Date** value in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="d277d-123">必须将本地时间值转换为 UTC**日期**值。</span><span class="sxs-lookup"><span data-stu-id="d277d-123">Local time values must be converted to UTC **Date** values.</span></span> 
  
<span data-ttu-id="d277d-124">**GetActivitiesEx**方法返回的活动必须具有大于_startTime_且小于或等于**当前**值的创建时间值。</span><span class="sxs-lookup"><span data-stu-id="d277d-124">Activities that the **GetActivitiesEx** method returns must have a creation time value that is greater than  _startTime_ and less than or equal to **Now**.</span></span> <span data-ttu-id="d277d-125">如果在**startTime**和**Now**之间未发生更改, 则提供程序必须返回 OSC_E_NO_CHANGES 错误。</span><span class="sxs-lookup"><span data-stu-id="d277d-125">If no changes have occurred between **startTime** and **Now**, the provider must return an OSC_E_NO_CHANGES error.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d277d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d277d-126">See also</span></span>

- [<span data-ttu-id="d277d-127">ISocialSession2 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d277d-127">ISocialSession2 : IUnknown</span></span>](isocialsession2iunknown.md)
- [<span data-ttu-id="d277d-128">同步好友和活动</span><span class="sxs-lookup"><span data-stu-id="d277d-128">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md)

