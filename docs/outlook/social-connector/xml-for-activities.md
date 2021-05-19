---
title: 活动的 XML
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: acc4a555-a3bf-4a79-86dc-aba6477733b8
description: 本主题包含一个示例方案，其中显示了 OSC 提供程序实现和 OSC 为获取活动信息而调用的 Outlook Social Connector (OSC) 提供程序扩展性 API。 信息以符合 OSC 提供程序 XML 架构的 XML 字符串表示。
ms.openlocfilehash: a4f1c6ce1f33b59811f6a6fecb737cd1f737946b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409627"
---
# <a name="xml-for-activities"></a><span data-ttu-id="8a1d5-104">活动的 XML</span><span class="sxs-lookup"><span data-stu-id="8a1d5-104">XML for activities</span></span>

<span data-ttu-id="8a1d5-105">本主题包含一个示例方案，其中显示了 OSC 提供程序实现和 OSC 为获取活动信息而调用的 Outlook Social Connector (OSC) 提供程序扩展性 API。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-105">This topic contains an example scenario that shows the Outlook Social Connector (OSC) provider extensibility API calls that an OSC provider implements and the OSC makes to obtain activities information.</span></span> <span data-ttu-id="8a1d5-106">信息以符合 OSC 提供程序 XML 架构的 XML 字符串表示。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-106">Information is expressed in XML strings that conform to the OSC provider XML schema.</span></span>
  
<span data-ttu-id="8a1d5-107">OSC 提供程序 XML 架构允许 OSC 提供程序定义活动。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-107">The OSC provider XML schema allows an OSC provider to define activities.</span></span> <span data-ttu-id="8a1d5-108">活动信息可能包括源自活动源项目的社交网络、每个活动源项目的详细信息 (如活动) 的所有者、类型和发布日期，以及用于显示活动的模板。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-108">Activity information can include the social network where the activity feed items originated, details of each activity feed item (such as owner, type, and publish date of the activity), and the template to display the activity.</span></span> <span data-ttu-id="8a1d5-109">为了支持在人员窗格或联系人卡片上显示活动，社交网络的 OSC 提供程序必须实现并返回正确的活动 XML。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-109">To support showing activities on the People Pane or Contact Card, a social network's OSC provider must implement and return the correct activities XML.</span></span> <span data-ttu-id="8a1d5-110">有关活动源 XML 的示例，请参阅 [活动源 XML 示例](activity-feed-xml-example.md)。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-110">For an example of activity feed XML, see [Activity Feed XML Example](activity-feed-xml-example.md).</span></span> <span data-ttu-id="8a1d5-111">有关同步好友活动的信息，请参阅 [同步好友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-111">For more information about synchronizing friends' activities, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span> <span data-ttu-id="8a1d5-112">有关 OSC 提供程序 XML 架构的完整定义，包括哪些元素是必需的或可选的，请参阅Outlook[连接器提供程序 XML 架构。](outlook-social-connector-provider-xml-schema.md)</span><span class="sxs-lookup"><span data-stu-id="8a1d5-112">For a complete definition of the OSC provider XML schema, including which elements are required or optional, see [Outlook Social Connector Provider XML Schema](outlook-social-connector-provider-xml-schema.md).</span></span> 
  
<span data-ttu-id="8a1d5-113">在下列方案中，OSC 动态同步在人员窗格中选择的人的活动，并获取此人的详细信息：</span><span class="sxs-lookup"><span data-stu-id="8a1d5-113">In the following scenario, the OSC dynamically synchronizes activities for a person selected in the People Pane, and gets details about that person:</span></span>
  
1. <span data-ttu-id="8a1d5-114">支持按需同步活动的 OSC 提供程序使用 **getActivities** 和 **dynamicActivitiesLookupEx** 元素将指示到 OSC。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-114">An OSC provider that supports on-demand synchronization of activities indicates that to the OSC by using the **getActivities** and **dynamicActivitiesLookupEx** elements.</span></span> <span data-ttu-id="8a1d5-115">OSC 提供程序还会设置 **hashFunction** 元素。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-115">The OSC provider also sets the **hashFunction** element.</span></span> <span data-ttu-id="8a1d5-116">所有三个元素都是功能的 **子元素**。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-116">All three elements are child elements of **capabilities**.</span></span> 
    
2. <span data-ttu-id="8a1d5-117">OSC 提供程序实现 **ISocialProvider：：GetCapabilities** 和 [ISocialSession2：：GetActivitiesEx](isocialsession2-getactivitiesex.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-117">The OSC provider implements the **ISocialProvider::GetCapabilities** and [ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md) methods.</span></span> 
    
3. <span data-ttu-id="8a1d5-118">OSC 调用 **ISocialProvider：：GetCapabilities** 以检查 **getActivities** 和 **dynamicActivitiesLookupEx** 的值，以验证 OSC 提供程序是否支持按需同步活动。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-118">The OSC calls **ISocialProvider::GetCapabilities** to check the value of **getActivities** and **dynamicActivitiesLookupEx** to verify that the OSC provider supports on-demand synchronization of activities.</span></span> <span data-ttu-id="8a1d5-119">OSC 还记下 OSC 提供程序支持的 **hashFunction** 元素的值。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-119">The OSC also notes the value of the **hashFunction** element supported by the OSC provider.</span></span> 
    
4. <span data-ttu-id="8a1d5-120">OSC 刷新人员窗格或联系人卡片，让用户看到所选人员的最新活动。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-120">The OSC refreshes the People Pane or Contact Card to let the user see the latest activities of the selected person.</span></span> <span data-ttu-id="8a1d5-121">OSC 使用 **hashFunction** 元素中指定的哈希函数对个人的 SMTP 地址进行加密，形成一个符合 **hashedAddresses** 元素的 XML 架构定义的 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-121">The OSC encrypts the person's SMTP address by using the hash function specified in the **hashFunction** element, forming an XML string that conforms to the XML schema definition for the **hashedAddresses** element.</span></span> 
    
5. <span data-ttu-id="8a1d5-122">OSC 调用 **ISocialSession2：：GetActivitiesEx，** 将哈希地址的此 XML 字符串作为  _hashedAddresses_ 参数提供，以在  _activities_ 参数中获取此人的当前活动集合。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-122">The OSC calls **ISocialSession2::GetActivitiesEx**, providing this XML string of the hashed address as the  _hashedAddresses_ parameter, to get a current collection of activities for that person in the  _activities_ parameter.</span></span> <span data-ttu-id="8a1d5-123">_activities_ 参数字符串符合 **activityFeed** 元素的 XML 架构定义。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-123">The  _activities_ parameter string complies with the XML schema definition of the **activityFeed** element.</span></span> 
    
6. <span data-ttu-id="8a1d5-124">基于 **activityFeed** 的 XML 架构定义，OSC 进一步分析活动字符串，以查找有关每个活动的类型、发布日期和其他信息，以及如何显示活动。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-124">Based on the XML schema definition for **activityFeed**, the OSC further parses the  _activities_ string to find out the type, publish date, and other information about each activity, and how to display the activity.</span></span> 
    
7. <span data-ttu-id="8a1d5-125">为了获取选定人员的详细信息，OSC 调用 [ISocialSession2：：GetPeopleDetails，](isocialsession2-getpeopledetails.md)提供与  _personAddresses_ 参数参数相同的哈希地址 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-125">To get details about the selected person, the OSC calls [ISocialSession2::GetPeopleDetails](isocialsession2-getpeopledetails.md), providing the same XML string of hashed addresses as the argument for the  _personsAddresses_ parameter.</span></span> <span data-ttu-id="8a1d5-126">有关人员的详细信息在  _personCollection 参数_ 中返回。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-126">The details about the person are returned in the  _personsCollection_ parameter.</span></span> <span data-ttu-id="8a1d5-127">这些详细信息可能包括 **firstName** **、lastName** 和 **emailAddress**。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-127">These details can include **firstName**, **lastName**, and **emailAddress**.</span></span> <span data-ttu-id="8a1d5-128">_personCollection_ 参数符合 **person** 元素的 XML 架构定义。</span><span class="sxs-lookup"><span data-stu-id="8a1d5-128">The  _personsCollection_ parameter conforms to the XML schema definition for the **person** element.</span></span> 
    
<span data-ttu-id="8a1d5-129">有关为活动指定 XML 的信息，请参阅本节的以下主题：</span><span class="sxs-lookup"><span data-stu-id="8a1d5-129">You can find more information about specifying XML for activities in the following topics of this section:</span></span>
  
- [<span data-ttu-id="8a1d5-130">活动源项的 XML 概述</span><span class="sxs-lookup"><span data-stu-id="8a1d5-130">Overview of XML for an Activity Feed Item</span></span>](overview-of-xml-for-an-activity-feed-item.md)
    
- [<span data-ttu-id="8a1d5-131">activityDetails 元素</span><span class="sxs-lookup"><span data-stu-id="8a1d5-131">activityDetails Element</span></span>](activitydetails-element.md)
    
- [<span data-ttu-id="8a1d5-132">activityTemplateContainer 元素</span><span class="sxs-lookup"><span data-stu-id="8a1d5-132">activityTemplateContainer Element</span></span>](activitytemplatecontainer-element.md)
    
- [<span data-ttu-id="8a1d5-133">模板变量</span><span class="sxs-lookup"><span data-stu-id="8a1d5-133">Template Variables</span></span>](template-variables.md)
    
- [<span data-ttu-id="8a1d5-134">正确显示活动指南</span><span class="sxs-lookup"><span data-stu-id="8a1d5-134">Guidelines for Properly Displaying Activities</span></span>](guidelines-for-properly-displaying-activities.md)
    
## <a name="see-also"></a><span data-ttu-id="8a1d5-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a1d5-135">See also</span></span>

- [<span data-ttu-id="8a1d5-136">活动源 XML 示例</span><span class="sxs-lookup"><span data-stu-id="8a1d5-136">Activity Feed XML Example</span></span>](activity-feed-xml-example.md)  
- [<span data-ttu-id="8a1d5-137">同步好友和活动</span><span class="sxs-lookup"><span data-stu-id="8a1d5-137">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md) 
- [<span data-ttu-id="8a1d5-138">功能的 XML</span><span class="sxs-lookup"><span data-stu-id="8a1d5-138">XML for Capabilities</span></span>](xml-for-capabilities.md)  
- [<span data-ttu-id="8a1d5-139">好友 XML</span><span class="sxs-lookup"><span data-stu-id="8a1d5-139">XML for Friends</span></span>](xml-for-friends.md)
- [<span data-ttu-id="8a1d5-140">使用 OSC XML 架构开发提供程序</span><span class="sxs-lookup"><span data-stu-id="8a1d5-140">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)

