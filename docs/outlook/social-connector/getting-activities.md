---
title: 获取活动
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8cb8f916-f061-4c4c-ad1b-40d44af3345a
description: OSC 调用 ISocialProvider：：GetCapabilities 方法以确定适用于社交网络的 OSC 提供程序的功能。
ms.openlocfilehash: 9d504fb64368a6910feaa38f0ef19ed631b4d4e3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420575"
---
# <a name="getting-activities"></a><span data-ttu-id="d6aac-103">获取活动</span><span class="sxs-lookup"><span data-stu-id="d6aac-103">Getting activities</span></span>

<span data-ttu-id="d6aac-104">OSC 调用 [ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md) 方法以确定适用于社交网络的 OSC 提供程序的功能。</span><span class="sxs-lookup"><span data-stu-id="d6aac-104">The OSC calls the [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method to determine the capabilities of the OSC provider for a social network.</span></span> <span data-ttu-id="d6aac-105">如果返回的功能 **XML** 中的 **getActivities** 和 **dynamicActivitiesLookupEx** 元素指示 OSC 提供程序支持按需获取活动以及将活动存储在内存中，则 OSC 可以执行以下调用序列。</span><span class="sxs-lookup"><span data-stu-id="d6aac-105">If the **getActivities** and **dynamicActivitiesLookupEx** elements in the returned **capabilities** XML indicate that the OSC provider supports getting activities on demand and storing activities in memory, the OSC can make the following calling sequence.</span></span> <span data-ttu-id="d6aac-106">OSC 还记下功能 XML 中的 **hashFunction** 元素中指定的 **哈希函数** 。</span><span class="sxs-lookup"><span data-stu-id="d6aac-106">The OSC also notes the hash function specified in the **hashFunction** element in the **capabilities** XML.</span></span> <span data-ttu-id="d6aac-107">OSC 按以下顺序调用方法， (社交网络上的好友和非好友的 [ISocialPerson](isocialpersoniunknown.md)) 支持的活动和信息：</span><span class="sxs-lookup"><span data-stu-id="d6aac-107">The OSC calls methods in the following sequence to get activities and information (as supported by the [ISocialPerson](isocialpersoniunknown.md) interface) for friends and non-friends on the social network:</span></span> 
  
1. <span data-ttu-id="d6aac-108">[ISocialSession：：GetLoggedOnUser](isocialsession-getloggedonuser.md) — 在身份验证过程结束时，OSC 调用 **GetLoggedOnUser** 以获取要进行身份验证的用户的 [ISocialProfile](isocialprofileisocialperson.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="d6aac-108">[ISocialSession::GetLoggedOnUser](isocialsession-getloggedonuser.md) —At the end of the authentication process, the OSC calls **GetLoggedOnUser** to obtain an [ISocialProfile](isocialprofileisocialperson.md) interface for the user being authenticated.</span></span> <span data-ttu-id="d6aac-109">有关身份验证详细信息，请参阅[基本身份验证](basic-authentication.md)[和基于表单的身份验证](forms-based-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="d6aac-109">For more information on authentication, see [Basic Authentication](basic-authentication.md) and [Forms-Based Authentication](forms-based-authentication.md).</span></span>
    
2. <span data-ttu-id="d6aac-110">[ISocialSession2：：GetActivitiesEx](isocialsession2-getactivitiesex.md) - 对于在 Outlook 人员窗格中显示的人员，OSC 获取其 SMTP 地址并哈希，调用 **ISocialSession2：：GetActivitiesEx，** 将 (存储在内存中) 这些人员返回的活动数据。</span><span class="sxs-lookup"><span data-stu-id="d6aac-110">[ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md) —For the persons displayed in the Outlook People Pane, the OSC obtains and hashes their SMTP addresses, calls **ISocialSession2::GetActivitiesEx**, and stores (in memory) the activities data returned for these persons.</span></span> <span data-ttu-id="d6aac-111">OSC 获取输出参数  _activities_，这是一个字符串，其中包含登录用户好友的活动集合。</span><span class="sxs-lookup"><span data-stu-id="d6aac-111">The OSC gets in an output parameter,  _activities_, which is a string that contains a collection of activities for friends of the logged-on user.</span></span> <span data-ttu-id="d6aac-112">此字符串符合 **activityFeed** 元素的架构定义。</span><span class="sxs-lookup"><span data-stu-id="d6aac-112">This string conforms to the schema definition for the **activityFeed** element.</span></span> 
    
3. <span data-ttu-id="d6aac-113">[ISocialSession：：GetPerson](isocialsession-getperson.md) - 对于 **GetActivitiesEx** 返回的 **activityFeed** XML 中的每个 **activityDetails** 元素，都有一个 **ownerID** 元素，用于指示拥有该活动的人。</span><span class="sxs-lookup"><span data-stu-id="d6aac-113">[ISocialSession::GetPerson](isocialsession-getperson.md) —For each **activityDetails** element in the **activityFeed** XML returned by **GetActivitiesEx**, there is an **ownerID** element that indicates the person who owns that activity.</span></span> <span data-ttu-id="d6aac-114">OSC 使用该 **ownerID** 值调用 **GetPerson，** 获取此人的 **ISocialPerson** 接口。</span><span class="sxs-lookup"><span data-stu-id="d6aac-114">The OSC uses that **ownerID** value to call **GetPerson** to get an **ISocialPerson** interface for that person.</span></span> 
    
4. <span data-ttu-id="d6aac-115">[ISocialPerson：：GetDetails](isocialperson-getdetails.md) —根据从步骤 3 获取的 **ISocialPerson** 对象，OSC 调用 **GetDetails** 以获取此人的详细信息，如名字和姓氏。</span><span class="sxs-lookup"><span data-stu-id="d6aac-115">[ISocialPerson::GetDetails](isocialperson-getdetails.md) —Based on the **ISocialPerson** object obtained from step 3, the OSC calls **GetDetails** to get details for that person, such as the first name and last name.</span></span> <span data-ttu-id="d6aac-116">OSC 可以针对步骤 2 中 **GetActivitiesEx** 返回的 **activityFeed** XML 中的 **activityDetails** 元素中指定的每个活动执行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="d6aac-116">The OSC can do the same for each activity specified in an **activityDetails** element in the **activityFeed** XML returned by **GetActivitiesEx** in step 2.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="d6aac-117">OSC 以默认间隔刷新活动缓存。</span><span class="sxs-lookup"><span data-stu-id="d6aac-117">The OSC refreshes the activities cache at a default interval.</span></span> <span data-ttu-id="d6aac-118">有关刷新活动缓存的信息，请参阅 [同步好友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="d6aac-118">For more information about refreshing the activities cache, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d6aac-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6aac-119">See also</span></span>

- [<span data-ttu-id="d6aac-120">功能的 XML</span><span class="sxs-lookup"><span data-stu-id="d6aac-120">XML for Capabilities</span></span>](xml-for-capabilities.md)
- [<span data-ttu-id="d6aac-121">OSC 典型调用序列</span><span class="sxs-lookup"><span data-stu-id="d6aac-121">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)

