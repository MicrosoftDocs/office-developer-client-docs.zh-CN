---
title: 获取活动
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8cb8f916-f061-4c4c-ad1b-40d44af3345a
description: OSC 调用 ISocialProvider::GetCapabilities 方法来确定社交网络 OSC 提供程序的功能。
ms.openlocfilehash: 82bb5322118fa3ebd7610f56b8f34ae95b59a40f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779201"
---
# <a name="getting-activities"></a><span data-ttu-id="1269a-103">获取活动</span><span class="sxs-lookup"><span data-stu-id="1269a-103">Getting activities</span></span>

<span data-ttu-id="1269a-104">OSC 调用[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)方法来确定社交网络 OSC 提供程序的功能。</span><span class="sxs-lookup"><span data-stu-id="1269a-104">The OSC calls the [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method to determine the capabilities of the OSC provider for a social network.</span></span> <span data-ttu-id="1269a-105">如果返回**功能**XML 中的**getActivities**和**dynamicActivitiesLookupEx**元素指示 OSC 提供程序需求和存储在内存中的活动支持入门活动、 OSC 可以进行下列调用序列。</span><span class="sxs-lookup"><span data-stu-id="1269a-105">If the **getActivities** and **dynamicActivitiesLookupEx** elements in the returned **capabilities** XML indicate that the OSC provider supports getting activities on demand and storing activities in memory, the OSC can make the following calling sequence.</span></span> <span data-ttu-id="1269a-106">OSC 还备注**hashFunction**元素中指定的**功能**XML 中的哈希函数。</span><span class="sxs-lookup"><span data-stu-id="1269a-106">The OSC also notes the hash function specified in the **hashFunction** element in the **capabilities** XML.</span></span> <span data-ttu-id="1269a-107">OSC 调用方法以获取活动和信息 （如[ISocialPerson](isocialpersoniunknown.md)接口支持） 朋友和社交网络上的非朋友按以下顺序：</span><span class="sxs-lookup"><span data-stu-id="1269a-107">The OSC calls methods in the following sequence to get activities and information (as supported by the [ISocialPerson](isocialpersoniunknown.md) interface) for friends and non-friends on the social network:</span></span> 
  
1. <span data-ttu-id="1269a-108">[ISocialSession::GetLoggedOnUser](isocialsession-getloggedonuser.md) — 在身份验证过程的末尾，OSC 调用**GetLoggedOnUser**获取[ISocialProfile](isocialprofileisocialperson.md)接口未经过身份验证的用户。</span><span class="sxs-lookup"><span data-stu-id="1269a-108">[ISocialSession::GetLoggedOnUser](isocialsession-getloggedonuser.md) —At the end of the authentication process, the OSC calls **GetLoggedOnUser** to obtain an [ISocialProfile](isocialprofileisocialperson.md) interface for the user being authenticated.</span></span> <span data-ttu-id="1269a-109">身份验证的详细信息，请参阅[基本身份验证](basic-authentication.md)和[基于表单的身份验证](forms-based-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="1269a-109">For more information on authentication, see [Basic Authentication](basic-authentication.md) and [Forms-Based Authentication](forms-based-authentication.md).</span></span>
    
2. <span data-ttu-id="1269a-110">[ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md) — 为 Outlook 人员窗格中显示的人员，OSC 获取和返回哈希其 SMTP 地址，调用**ISocialSession2::GetActivitiesEx**，并将活动数据存储 （内存中）这些人员。</span><span class="sxs-lookup"><span data-stu-id="1269a-110">[ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md) —For the persons displayed in the Outlook People Pane, the OSC obtains and hashes their SMTP addresses, calls **ISocialSession2::GetActivitiesEx**, and stores (in memory) the activities data returned for these persons.</span></span> <span data-ttu-id="1269a-111">OSC 获取中输出参数，_活动_，它是一个字符串，包含朋友登录用户的活动的集合。</span><span class="sxs-lookup"><span data-stu-id="1269a-111">The OSC gets in an output parameter,  _activities_, which is a string that contains a collection of activities for friends of the logged-on user.</span></span> <span data-ttu-id="1269a-112">此字符串符合**activityFeed**元素的架构定义。</span><span class="sxs-lookup"><span data-stu-id="1269a-112">This string conforms to the schema definition for the **activityFeed** element.</span></span> 
    
3. <span data-ttu-id="1269a-113">[ISocialSession::GetPerson](isocialsession-getperson.md) — **activityFeed** **GetActivitiesEx**返回 XML 中的每个**activityDetails**元素，没有**ownerID**元素指示拥有该活动的人员。</span><span class="sxs-lookup"><span data-stu-id="1269a-113">[ISocialSession::GetPerson](isocialsession-getperson.md) —For each **activityDetails** element in the **activityFeed** XML returned by **GetActivitiesEx**, there is an **ownerID** element that indicates the person who owns that activity.</span></span> <span data-ttu-id="1269a-114">OSC 使用该值**ownerID**来调用**GetPerson**以获取该用户**ISocialPerson**接口。</span><span class="sxs-lookup"><span data-stu-id="1269a-114">The OSC uses that **ownerID** value to call **GetPerson** to get an **ISocialPerson** interface for that person.</span></span> 
    
4. <span data-ttu-id="1269a-115">[ISocialPerson::GetDetails](isocialperson-getdetails.md) — 基于**ISocialPerson**对象获取从步骤 3，OSC 调用**GetDetails**以获取该用户，例如名字和姓氏详细信息。</span><span class="sxs-lookup"><span data-stu-id="1269a-115">[ISocialPerson::GetDetails](isocialperson-getdetails.md) —Based on the **ISocialPerson** object obtained from step 3, the OSC calls **GetDetails** to get details for that person, such as the first name and last name.</span></span> <span data-ttu-id="1269a-116">OSC 可执行相同的**activityDetails**元素**activityFeed** **GetActivitiesEx**在步骤 2 中返回的 XML 中指定每个活动。</span><span class="sxs-lookup"><span data-stu-id="1269a-116">The OSC can do the same for each activity specified in an **activityDetails** element in the **activityFeed** XML returned by **GetActivitiesEx** in step 2.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="1269a-117">OSC 刷新按默认的时间间隔的活动缓存。</span><span class="sxs-lookup"><span data-stu-id="1269a-117">The OSC refreshes the activities cache at a default interval.</span></span> <span data-ttu-id="1269a-118">有关刷新活动缓存的详细信息，请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="1269a-118">For more information about refreshing the activities cache, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1269a-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1269a-119">See also</span></span>

- [<span data-ttu-id="1269a-120">功能 XML</span><span class="sxs-lookup"><span data-stu-id="1269a-120">XML for Capabilities</span></span>](xml-for-capabilities.md)
- [<span data-ttu-id="1269a-121">OSC 典型调用序列 （英文)</span><span class="sxs-lookup"><span data-stu-id="1269a-121">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)

