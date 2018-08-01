---
title: ISocialSession2GetActivitiesEx
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: bfe30c22-017b-42e0-93be-c85d674c07e3
description: 获取一个字符串，表示活动的每个 hashedAddresses 参数指定用户的集合。
ms.openlocfilehash: 7c24494d924b63f5e137f8e9928257967469f19c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779244"
---
# <a name="isocialsession2getactivitiesex"></a><span data-ttu-id="93106-103">ISocialSession2::GetActivitiesEx</span><span class="sxs-lookup"><span data-stu-id="93106-103">ISocialSession2::GetActivitiesEx</span></span>

<span data-ttu-id="93106-104">获取一个字符串，表示活动的每个_hashedAddresses_参数指定用户的集合。</span><span class="sxs-lookup"><span data-stu-id="93106-104">Gets a string that represents a collection of activities of each of the users specified by the  _hashedAddresses_ parameter.</span></span> 
  
```cpp
HRESULT _stdcall GetActivitiesEx([in] SAFEARRAY(BSTR) hashedAddresses, [in] DATE startTime, [out, retval] BSTR *activities);
```

## <a name="parameters"></a><span data-ttu-id="93106-105">参数</span><span class="sxs-lookup"><span data-stu-id="93106-105">Parameters</span></span>

<span data-ttu-id="93106-106">_hashedAddresses_</span><span class="sxs-lookup"><span data-stu-id="93106-106">_hashedAddresses_</span></span>
  
> <span data-ttu-id="93106-107">[in]结构，它指定一个数组哈希 SMTP 地址的一组用户。</span><span class="sxs-lookup"><span data-stu-id="93106-107">[in] A structure that specifies an array of hashed SMTP addresses for a set of users.</span></span>
    
<span data-ttu-id="93106-108">_startTime_</span><span class="sxs-lookup"><span data-stu-id="93106-108">_startTime_</span></span>
  
> <span data-ttu-id="93106-109">[in]之后将返回活动创建的时间。</span><span class="sxs-lookup"><span data-stu-id="93106-109">[in] The time after which activities that are created would be returned.</span></span>
    
<span data-ttu-id="93106-110">_活动_</span><span class="sxs-lookup"><span data-stu-id="93106-110">_activities_</span></span>
  
> <span data-ttu-id="93106-111">[输出]代表一组指定_startTime_以来_hashedAddresses_社交网络上的用户的活动的 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="93106-111">[out] An XML string that represents the set of activities of the users specified by  _hashedAddresses_ on the social network since  _startTime_.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="93106-112">说明</span><span class="sxs-lookup"><span data-stu-id="93106-112">Remarks</span></span>

<span data-ttu-id="93106-113">OSC 调用**GetActivitiesEx**如果 OSC 提供程序支持的活动的按需同步。</span><span class="sxs-lookup"><span data-stu-id="93106-113">The OSC calls **GetActivitiesEx** if the OSC provider supports on-demand synchronization of activities.</span></span> <span data-ttu-id="93106-114">OSC 存储在内存中的_活动_中返回的信息。</span><span class="sxs-lookup"><span data-stu-id="93106-114">The OSC stores the information returned in  _activities_ in memory.</span></span> <span data-ttu-id="93106-115">有关如何 OSC 使用和更新内存中的此信息的详细信息，请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="93106-115">For more information about how the OSC uses and updates this information in memory, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span>
  
<span data-ttu-id="93106-116">Outlook Social Connector 2013 中启动 OSC 支持仅按需活动同步，并调用仅**GetActivitiesEx**获取活动。</span><span class="sxs-lookup"><span data-stu-id="93106-116">Starting in Outlook Social Connector 2013, the OSC supports only on-demand synchronization of activities and calls only **GetActivitiesEx** to get activities.</span></span> <span data-ttu-id="93106-117">若要支持按需活动查找，将**cacheActivities**设置为**false**，和**getActivities**和为**true**， **dynamicActivitiesLookupEx**和 OSC 将调用**GetActivitiesEx**。</span><span class="sxs-lookup"><span data-stu-id="93106-117">To support on-demand activities lookup, set **cacheActivities** as **false**, and **getActivities** and **dynamicActivitiesLookupEx** as **true**, and the OSC will call **GetActivitiesEx**.</span></span>
  
<span data-ttu-id="93106-118">OSC 提供程序扩展性的架构中定义，则返回的 XML 字符串必须符合**activityFeed**，架构定义。</span><span class="sxs-lookup"><span data-stu-id="93106-118">The returned XML string must comply with the schema definition for **activityFeed**, as defined in the schema for OSC provider extensibility.</span></span>
  
<span data-ttu-id="93106-119">_HashedAddresses_字符串实例表示一组的人员窗格中显示每个用户的哈希地址。</span><span class="sxs-lookup"><span data-stu-id="93106-119">The  _hashedAddresses_ sring represents a set of hashed addresses for each user displayed in the People Pane.</span></span> <span data-ttu-id="93106-120">使用提供程序的**功能**XML 中指定**hashFunction**元素的哈希函数进行加密的哈希的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="93106-120">The hashed SMTP addresses are encrypted by using the hashing function specified by the **hashFunction** element in the provider's **capabilities** XML.</span></span> <span data-ttu-id="93106-121">用户不必是由[ISocialSession::LoggedOnUserName](isocialsession-loggedonusername.md)属性表示的登录用户的好帮手。</span><span class="sxs-lookup"><span data-stu-id="93106-121">The user does not have to be a friend of the logged-on user represented by the [ISocialSession::LoggedOnUserName](isocialsession-loggedonusername.md) property.</span></span> 
  
<span data-ttu-id="93106-122">_StartTime_参数都是**日期**值以协调世界时 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="93106-122">The  _startTime_ parameter is a **Date** value in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="93106-123">必须是本地时间值转换为 UTC**日期**值。</span><span class="sxs-lookup"><span data-stu-id="93106-123">Local time values must be converted to UTC **Date** values.</span></span> 
  
<span data-ttu-id="93106-124">活动**GetActivitiesEx**方法返回的值必须为创建时间大于_startTime_且小于或等于**现在**。</span><span class="sxs-lookup"><span data-stu-id="93106-124">Activities that the **GetActivitiesEx** method returns must have a creation time value that is greater than  _startTime_ and less than or equal to **Now**.</span></span> <span data-ttu-id="93106-125">如果之间**开始时间**和**立即**不发生了任何更改，提供程序必须返回 OSC_E_NO_CHANGES 错误。</span><span class="sxs-lookup"><span data-stu-id="93106-125">If no changes have occurred between **startTime** and **Now**, the provider must return an OSC_E_NO_CHANGES error.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="93106-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93106-126">See also</span></span>

- [<span data-ttu-id="93106-127">ISocialSession2 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="93106-127">ISocialSession2 : IUnknown</span></span>](isocialsession2iunknown.md)
- [<span data-ttu-id="93106-128">同步朋友和活动</span><span class="sxs-lookup"><span data-stu-id="93106-128">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md)

