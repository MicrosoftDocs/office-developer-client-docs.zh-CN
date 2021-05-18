---
title: ISocialSession2GetActivitiesEx
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: bfe30c22-017b-42e0-93be-c85d674c07e3
description: 获取一个字符串，代表 hashedAddresses 参数指定的每个用户的活动集合。
ms.openlocfilehash: be29d0226eb137b1ad8ed025acfe3f4958efa85f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404335"
---
# <a name="isocialsession2getactivitiesex"></a><span data-ttu-id="12a4b-103">ISocialSession2::GetActivitiesEx</span><span class="sxs-lookup"><span data-stu-id="12a4b-103">ISocialSession2::GetActivitiesEx</span></span>

<span data-ttu-id="12a4b-104">获取一个字符串，代表  _hashedAddresses_ 参数指定的每个用户的活动集合。</span><span class="sxs-lookup"><span data-stu-id="12a4b-104">Gets a string that represents a collection of activities of each of the users specified by the  _hashedAddresses_ parameter.</span></span> 
  
```cpp
HRESULT _stdcall GetActivitiesEx([in] SAFEARRAY(BSTR) hashedAddresses, [in] DATE startTime, [out, retval] BSTR *activities);
```

## <a name="parameters"></a><span data-ttu-id="12a4b-105">参数</span><span class="sxs-lookup"><span data-stu-id="12a4b-105">Parameters</span></span>

<span data-ttu-id="12a4b-106">_hashedAddresses_</span><span class="sxs-lookup"><span data-stu-id="12a4b-106">_hashedAddresses_</span></span>
  
> <span data-ttu-id="12a4b-107">[in]为一组用户指定哈希 SMTP 地址数组的结构。</span><span class="sxs-lookup"><span data-stu-id="12a4b-107">[in] A structure that specifies an array of hashed SMTP addresses for a set of users.</span></span>
    
<span data-ttu-id="12a4b-108">_startTime_</span><span class="sxs-lookup"><span data-stu-id="12a4b-108">_startTime_</span></span>
  
> <span data-ttu-id="12a4b-109">[in]返回所创建活动的时间。</span><span class="sxs-lookup"><span data-stu-id="12a4b-109">[in] The time after which activities that are created would be returned.</span></span>
    
<span data-ttu-id="12a4b-110">_activities_</span><span class="sxs-lookup"><span data-stu-id="12a4b-110">_activities_</span></span>
  
> <span data-ttu-id="12a4b-111">[out]一个 XML 字符串，表示自 startTime 以来社交网络上的  _hashedAddresses_ 指定的用户  _的活动集_。</span><span class="sxs-lookup"><span data-stu-id="12a4b-111">[out] An XML string that represents the set of activities of the users specified by  _hashedAddresses_ on the social network since  _startTime_.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="12a4b-112">备注</span><span class="sxs-lookup"><span data-stu-id="12a4b-112">Remarks</span></span>

<span data-ttu-id="12a4b-113">如果 OSC 提供程序支持按需同步活动，OSC 将调用 **GetActivitiesEx。**</span><span class="sxs-lookup"><span data-stu-id="12a4b-113">The OSC calls **GetActivitiesEx** if the OSC provider supports on-demand synchronization of activities.</span></span> <span data-ttu-id="12a4b-114">OSC 将返回的信息存储在  _内存中的活动_ 。</span><span class="sxs-lookup"><span data-stu-id="12a4b-114">The OSC stores the information returned in  _activities_ in memory.</span></span> <span data-ttu-id="12a4b-115">有关 OSC 如何在内存中使用和更新此信息的信息，请参阅 [同步好友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="12a4b-115">For more information about how the OSC uses and updates this information in memory, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span>
  
<span data-ttu-id="12a4b-116">从 Outlook Social Connector 2013 开始，OSC 仅支持按需同步活动，并仅调用 **GetActivitiesEx** 获取活动。</span><span class="sxs-lookup"><span data-stu-id="12a4b-116">Starting in Outlook Social Connector 2013, the OSC supports only on-demand synchronization of activities and calls only **GetActivitiesEx** to get activities.</span></span> <span data-ttu-id="12a4b-117">若要支持按需活动查找，将 **cacheActivities** 设置为 **false，** 将 **getActivities** 和 **dynamicActivitiesLookupEx** 设置为 **true，OSC** 将调用 **GetActivitiesEx**。</span><span class="sxs-lookup"><span data-stu-id="12a4b-117">To support on-demand activities lookup, set **cacheActivities** as **false**, and **getActivities** and **dynamicActivitiesLookupEx** as **true**, and the OSC will call **GetActivitiesEx**.</span></span>
  
<span data-ttu-id="12a4b-118">返回的 XML 字符串必须符合 **activityFeed** 的架构定义，如 OSC 提供程序扩展性架构中的定义。</span><span class="sxs-lookup"><span data-stu-id="12a4b-118">The returned XML string must comply with the schema definition for **activityFeed**, as defined in the schema for OSC provider extensibility.</span></span>
  
<span data-ttu-id="12a4b-119">_hashedAddresses_ sring 表示显示在人员窗格中的每个用户的一组哈希地址。</span><span class="sxs-lookup"><span data-stu-id="12a4b-119">The  _hashedAddresses_ sring represents a set of hashed addresses for each user displayed in the People Pane.</span></span> <span data-ttu-id="12a4b-120">哈希 SMTP 地址使用提供程序的功能 XML 中 **hashFunction** 元素指定的哈希函数 **进行** 加密。</span><span class="sxs-lookup"><span data-stu-id="12a4b-120">The hashed SMTP addresses are encrypted by using the hashing function specified by the **hashFunction** element in the provider's **capabilities** XML.</span></span> <span data-ttu-id="12a4b-121">用户无需是 [ISocialSession：：LoggedOnUserName](isocialsession-loggedonusername.md) 属性所代表的已登录用户的好友。</span><span class="sxs-lookup"><span data-stu-id="12a4b-121">The user does not have to be a friend of the logged-on user represented by the [ISocialSession::LoggedOnUserName](isocialsession-loggedonusername.md) property.</span></span> 
  
<span data-ttu-id="12a4b-122">_startTime_ 参数是协调世界时与 UTC 时间 (Date) 。</span><span class="sxs-lookup"><span data-stu-id="12a4b-122">The  _startTime_ parameter is a **Date** value in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="12a4b-123">本地时间值必须转换为 UTC **日期** 值。</span><span class="sxs-lookup"><span data-stu-id="12a4b-123">Local time values must be converted to UTC **Date** values.</span></span> 
  
<span data-ttu-id="12a4b-124">**GetActivitiesEx** 方法返回的活动必须具有大于 _startTime_ 且小于或等于 Now 的创建时间 **值**。</span><span class="sxs-lookup"><span data-stu-id="12a4b-124">Activities that the **GetActivitiesEx** method returns must have a creation time value that is greater than  _startTime_ and less than or equal to **Now**.</span></span> <span data-ttu-id="12a4b-125">如果在 **startTime** 和 **Now** 之间未发生更改，则提供程序必须返回OSC_E_NO_CHANGES错误。</span><span class="sxs-lookup"><span data-stu-id="12a4b-125">If no changes have occurred between **startTime** and **Now**, the provider must return an OSC_E_NO_CHANGES error.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="12a4b-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12a4b-126">See also</span></span>

- [<span data-ttu-id="12a4b-127">ISocialSession2 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="12a4b-127">ISocialSession2 : IUnknown</span></span>](isocialsession2iunknown.md)
- [<span data-ttu-id="12a4b-128">同步好友和活动</span><span class="sxs-lookup"><span data-stu-id="12a4b-128">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md)

