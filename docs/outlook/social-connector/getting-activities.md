---
title: 获取活动
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8cb8f916-f061-4c4c-ad1b-40d44af3345a
description: '.osc 调用 ISocialProvider:: GetCapabilities 方法来确定用于社交网络的 .osc 提供程序的功能。'
ms.openlocfilehash: 9d504fb64368a6910feaa38f0ef19ed631b4d4e3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420575"
---
# <a name="getting-activities"></a><span data-ttu-id="95568-103">获取活动</span><span class="sxs-lookup"><span data-stu-id="95568-103">Getting activities</span></span>

<span data-ttu-id="95568-104">.osc 调用[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)方法来确定用于社交网络的 .osc 提供程序的功能。</span><span class="sxs-lookup"><span data-stu-id="95568-104">The OSC calls the [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method to determine the capabilities of the OSC provider for a social network.</span></span> <span data-ttu-id="95568-105">如果返回的**功能**XML 中的**getActivities**和**dynamicActivitiesLookupEx**元素指示 .osc 提供程序支持按需获取活动并将活动存储在内存中, 则该 .osc 可以进行以下调用顺序。</span><span class="sxs-lookup"><span data-stu-id="95568-105">If the **getActivities** and **dynamicActivitiesLookupEx** elements in the returned **capabilities** XML indicate that the OSC provider supports getting activities on demand and storing activities in memory, the OSC can make the following calling sequence.</span></span> <span data-ttu-id="95568-106">该 .osc 还记录了**功能**XML 的**hashFunction**元素中指定的哈希函数。</span><span class="sxs-lookup"><span data-stu-id="95568-106">The OSC also notes the hash function specified in the **hashFunction** element in the **capabilities** XML.</span></span> <span data-ttu-id="95568-107">.osc 调用以下序列中的方法, 以获取好友和社交网络中的非好友的活动和信息 (由[ISocialPerson](isocialpersoniunknown.md)接口支持):</span><span class="sxs-lookup"><span data-stu-id="95568-107">The OSC calls methods in the following sequence to get activities and information (as supported by the [ISocialPerson](isocialpersoniunknown.md) interface) for friends and non-friends on the social network:</span></span> 
  
1. <span data-ttu-id="95568-108">[ISocialSession:: GetLoggedOnUser](isocialsession-getloggedonuser.md) -在身份验证过程结束时, .osc 调用**GetLoggedOnUser**获取正在进行身份验证的用户的[ISocialProfile](isocialprofileisocialperson.md)接口。</span><span class="sxs-lookup"><span data-stu-id="95568-108">[ISocialSession::GetLoggedOnUser](isocialsession-getloggedonuser.md) —At the end of the authentication process, the OSC calls **GetLoggedOnUser** to obtain an [ISocialProfile](isocialprofileisocialperson.md) interface for the user being authenticated.</span></span> <span data-ttu-id="95568-109">有关身份验证的详细信息, 请参阅[基本身份验证](basic-authentication.md)和[基于表单的身份验证](forms-based-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="95568-109">For more information on authentication, see [Basic Authentication](basic-authentication.md) and [Forms-Based Authentication](forms-based-authentication.md).</span></span>
    
2. <span data-ttu-id="95568-110">[ISocialSession2:: GetActivitiesEx](isocialsession2-getactivitiesex.md) -对于显示在 "Outlook 人员" 窗格中的人员, .osc 获取并散列其 SMTP 地址, 调用**ISocialSession2:: GetActivitiesEx**, 并在内存中存储为其返回的活动数据这些人员。</span><span class="sxs-lookup"><span data-stu-id="95568-110">[ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md) —For the persons displayed in the Outlook People Pane, the OSC obtains and hashes their SMTP addresses, calls **ISocialSession2::GetActivitiesEx**, and stores (in memory) the activities data returned for these persons.</span></span> <span data-ttu-id="95568-111">.osc 获取一个输出参数 ( _activity_), 它是一个字符串, 其中包含登录用户的好友活动的集合。</span><span class="sxs-lookup"><span data-stu-id="95568-111">The OSC gets in an output parameter,  _activities_, which is a string that contains a collection of activities for friends of the logged-on user.</span></span> <span data-ttu-id="95568-112">此字符串符合**microsoft.office.server.activityfeed**元素的架构定义。</span><span class="sxs-lookup"><span data-stu-id="95568-112">This string conforms to the schema definition for the **activityFeed** element.</span></span> 
    
3. <span data-ttu-id="95568-113">[ISocialSession:: GetPerson](isocialsession-getperson.md) -对于**GetActivitiesEx**返回的**microsoft.office.server.activityfeed** XML 中的每个**activityDetails**元素, 都有一个**ownerID**元素, 该元素指示拥有该活动的人员。</span><span class="sxs-lookup"><span data-stu-id="95568-113">[ISocialSession::GetPerson](isocialsession-getperson.md) —For each **activityDetails** element in the **activityFeed** XML returned by **GetActivitiesEx**, there is an **ownerID** element that indicates the person who owns that activity.</span></span> <span data-ttu-id="95568-114">.osc 使用该**ownerID**值来调用**GetPerson** , 以获取该人员的**ISocialPerson**接口。</span><span class="sxs-lookup"><span data-stu-id="95568-114">The OSC uses that **ownerID** value to call **GetPerson** to get an **ISocialPerson** interface for that person.</span></span> 
    
4. <span data-ttu-id="95568-115">[ISocialPerson:: GetDetails](isocialperson-getdetails.md) -基于从步骤3获取的**ISocialPerson**对象, .osc 调用**GetDetails**以获取该人员的详细信息, 例如名字和姓氏。</span><span class="sxs-lookup"><span data-stu-id="95568-115">[ISocialPerson::GetDetails](isocialperson-getdetails.md) —Based on the **ISocialPerson** object obtained from step 3, the OSC calls **GetDetails** to get details for that person, such as the first name and last name.</span></span> <span data-ttu-id="95568-116">对于在步骤2中**GetActivitiesEx**返回的**microsoft.office.server.activityfeed** XML 中的**activityDetails**元素中指定的每个活动, .osc 可执行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="95568-116">The OSC can do the same for each activity specified in an **activityDetails** element in the **activityFeed** XML returned by **GetActivitiesEx** in step 2.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="95568-117">.osc 将按默认间隔刷新活动缓存。</span><span class="sxs-lookup"><span data-stu-id="95568-117">The OSC refreshes the activities cache at a default interval.</span></span> <span data-ttu-id="95568-118">有关刷新活动缓存的详细信息, 请参阅[同步好友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="95568-118">For more information about refreshing the activities cache, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="95568-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95568-119">See also</span></span>

- [<span data-ttu-id="95568-120">XML 的功能</span><span class="sxs-lookup"><span data-stu-id="95568-120">XML for Capabilities</span></span>](xml-for-capabilities.md)
- [<span data-ttu-id="95568-121">.osc 典型调用序列</span><span class="sxs-lookup"><span data-stu-id="95568-121">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)

