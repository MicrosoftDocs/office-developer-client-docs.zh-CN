---
title: 活动的 XML
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: acc4a555-a3bf-4a79-86dc-aba6477733b8
description: 本主题包含显示 Outlook Social Connector (OSC) 提供程序扩展性 API 调用 OSC 提供程序实现和 OSC 使获取活动信息的示例方案。 符合 OSC 提供程序的 XML 架构的 XML 字符串中表示的信息。
ms.openlocfilehash: 44f74d9e72eec3ff6da7f9967315fc9d75191584
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779344"
---
# <a name="xml-for-activities"></a><span data-ttu-id="65249-104">活动的 XML</span><span class="sxs-lookup"><span data-stu-id="65249-104">XML for activities</span></span>

<span data-ttu-id="65249-105">本主题包含显示 Outlook Social Connector (OSC) 提供程序扩展性 API 调用 OSC 提供程序实现和 OSC 使获取活动信息的示例方案。</span><span class="sxs-lookup"><span data-stu-id="65249-105">This topic contains an example scenario that shows the Outlook Social Connector (OSC) provider extensibility API calls that an OSC provider implements and the OSC makes to obtain activities information.</span></span> <span data-ttu-id="65249-106">符合 OSC 提供程序的 XML 架构的 XML 字符串中表示的信息。</span><span class="sxs-lookup"><span data-stu-id="65249-106">Information is expressed in XML strings that conform to the OSC provider XML schema.</span></span>
  
<span data-ttu-id="65249-107">OSC 提供程序 XML 架构允许 OSC 提供程序定义活动。</span><span class="sxs-lookup"><span data-stu-id="65249-107">The OSC provider XML schema allows an OSC provider to define activities.</span></span> <span data-ttu-id="65249-108">活动信息可以包含其中活动源项目产生，社交网络的每个活动源项目详细信息 （如所有者，键入，和活动的发布日期），并显示活动的模板。</span><span class="sxs-lookup"><span data-stu-id="65249-108">Activity information can include the social network where the activity feed items originated, details of each activity feed item (such as owner, type, and publish date of the activity), and the template to display the activity.</span></span> <span data-ttu-id="65249-109">若要支持人员窗格或联系人卡片上显示活动，社交网络的 OSC 提供程序必须实现并返回正确的活动 XML。</span><span class="sxs-lookup"><span data-stu-id="65249-109">To support showing activities on the People Pane or Contact Card, a social network's OSC provider must implement and return the correct activities XML.</span></span> <span data-ttu-id="65249-110">示例活动的源 XML，请参阅[活动源 XML 示例](activity-feed-xml-example.md)。</span><span class="sxs-lookup"><span data-stu-id="65249-110">For an example of activity feed XML, see [Activity Feed XML Example](activity-feed-xml-example.md).</span></span> <span data-ttu-id="65249-111">有关同步朋友的活动的详细信息，请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="65249-111">For more information about synchronizing friends' activities, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span> <span data-ttu-id="65249-112">有关完整定义 OSC 提供程序 XML 架构，其中包括哪些元素必需或可选的请参阅[Outlook Social Connector 提供程序 XML 架构](outlook-social-connector-provider-xml-schema.md)。</span><span class="sxs-lookup"><span data-stu-id="65249-112">For a complete definition of the OSC provider XML schema, including which elements are required or optional, see [Outlook Social Connector Provider XML Schema](outlook-social-connector-provider-xml-schema.md).</span></span> 
  
<span data-ttu-id="65249-113">在以下方案中，OSC 动态活动同步人员窗格中选择联系人，并获取有关该联系人的详细信息：</span><span class="sxs-lookup"><span data-stu-id="65249-113">In the following scenario, the OSC dynamically synchronizes activities for a person selected in the People Pane, and gets details about that person:</span></span>
  
1. <span data-ttu-id="65249-114">OSC 提供程序支持的活动的按需同步指示的可以 OSC，通过使用**getActivities**和**dynamicActivitiesLookupEx**元素。</span><span class="sxs-lookup"><span data-stu-id="65249-114">An OSC provider that supports on-demand synchronization of activities indicates that to the OSC by using the **getActivities** and **dynamicActivitiesLookupEx** elements.</span></span> <span data-ttu-id="65249-115">OSC 提供程序还设置**hashFunction**元素。</span><span class="sxs-lookup"><span data-stu-id="65249-115">The OSC provider also sets the **hashFunction** element.</span></span> <span data-ttu-id="65249-116">所有三个元素均**功能**的子元素。</span><span class="sxs-lookup"><span data-stu-id="65249-116">All three elements are child elements of **capabilities**.</span></span> 
    
2. <span data-ttu-id="65249-117">OSC 提供程序实现的**ISocialProvider::GetCapabilities**和[ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md)方法。</span><span class="sxs-lookup"><span data-stu-id="65249-117">The OSC provider implements the **ISocialProvider::GetCapabilities** and [ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md) methods.</span></span> 
    
3. <span data-ttu-id="65249-118">OSC 呼叫**ISocialProvider::GetCapabilities**检查**getActivities**和**dynamicActivitiesLookupEx**的值以验证 OSC 提供程序支持活动的按需的同步。</span><span class="sxs-lookup"><span data-stu-id="65249-118">The OSC calls **ISocialProvider::GetCapabilities** to check the value of **getActivities** and **dynamicActivitiesLookupEx** to verify that the OSC provider supports on-demand synchronization of activities.</span></span> <span data-ttu-id="65249-119">OSC 还备注 OSC 提供程序支持**hashFunction**元素的值。</span><span class="sxs-lookup"><span data-stu-id="65249-119">The OSC also notes the value of the **hashFunction** element supported by the OSC provider.</span></span> 
    
4. <span data-ttu-id="65249-120">OSC 刷新，使用户可以查看选定人员的最新活动人员窗格或联系人卡片。</span><span class="sxs-lookup"><span data-stu-id="65249-120">The OSC refreshes the People Pane or Contact Card to let the user see the latest activities of the selected person.</span></span> <span data-ttu-id="65249-121">OSC 使用**hashFunction**元素中指定的哈希函数形成一个 XML 字符串，符合**hashedAddresses**元素的 XML 架构定义加密此人的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="65249-121">The OSC encrypts the person's SMTP address by using the hash function specified in the **hashFunction** element, forming an XML string that conforms to the XML schema definition for the **hashedAddresses** element.</span></span> 
    
5. <span data-ttu-id="65249-122">OSC 调用**ISocialSession2::GetActivitiesEx**，提供该 XML 字符串的哈希地址作为_hashedAddresses_参数，以获取_活动_参数中的用户的当前活动的集合。</span><span class="sxs-lookup"><span data-stu-id="65249-122">The OSC calls **ISocialSession2::GetActivitiesEx**, providing this XML string of the hashed address as the  _hashedAddresses_ parameter, to get a current collection of activities for that person in the  _activities_ parameter.</span></span> <span data-ttu-id="65249-123">_活动_参数字符串符合**activityFeed**元素的 XML 架构定义。</span><span class="sxs-lookup"><span data-stu-id="65249-123">The  _activities_ parameter string complies with the XML schema definition of the **activityFeed** element.</span></span> 
    
6. <span data-ttu-id="65249-124">根据 XML 架构定义**activityFeed**，OSC 进一步分析要找出类型、 发布日期和有关每个活动的其他信息以及如何显示活动的_活动_字符串。</span><span class="sxs-lookup"><span data-stu-id="65249-124">Based on the XML schema definition for **activityFeed**, the OSC further parses the  _activities_ string to find out the type, publish date, and other information about each activity, and how to display the activity.</span></span> 
    
7. <span data-ttu-id="65249-125">要获取有关选定人员的详细信息，请 OSC 调用[ISocialSession2::GetPeopleDetails](isocialsession2-getpeopledetails.md)，提供的同一个 XML 字符串的哈希地址作为_personsAddresses_参数的参数。</span><span class="sxs-lookup"><span data-stu-id="65249-125">To get details about the selected person, the OSC calls [ISocialSession2::GetPeopleDetails](isocialsession2-getpeopledetails.md), providing the same XML string of hashed addresses as the argument for the  _personsAddresses_ parameter.</span></span> <span data-ttu-id="65249-126">_PersonsCollection_参数中返回有关此人的详细信息。</span><span class="sxs-lookup"><span data-stu-id="65249-126">The details about the person are returned in the  _personsCollection_ parameter.</span></span> <span data-ttu-id="65249-127">**FirstName**、 **lastName**和**emailAddress**，可以包括以下详细信息。</span><span class="sxs-lookup"><span data-stu-id="65249-127">These details can include **firstName**, **lastName**, and **emailAddress**.</span></span> <span data-ttu-id="65249-128">_PersonsCollection_参数符合**person**元素的 XML 架构定义。</span><span class="sxs-lookup"><span data-stu-id="65249-128">The  _personsCollection_ parameter conforms to the XML schema definition for the **person** element.</span></span> 
    
<span data-ttu-id="65249-129">您可以找到有关本节的以下主题中的活动指定 XML 的详细信息：</span><span class="sxs-lookup"><span data-stu-id="65249-129">You can find more information about specifying XML for activities in the following topics of this section:</span></span>
  
- [<span data-ttu-id="65249-130">概述 XML 的活动订阅源</span><span class="sxs-lookup"><span data-stu-id="65249-130">Overview of XML for an Activity Feed Item</span></span>](overview-of-xml-for-an-activity-feed-item.md)
    
- [<span data-ttu-id="65249-131">activityDetails 元素</span><span class="sxs-lookup"><span data-stu-id="65249-131">activityDetails Element</span></span>](activitydetails-element.md)
    
- [<span data-ttu-id="65249-132">activityTemplateContainer 元素</span><span class="sxs-lookup"><span data-stu-id="65249-132">activityTemplateContainer Element</span></span>](activitytemplatecontainer-element.md)
    
- [<span data-ttu-id="65249-133">模板变量</span><span class="sxs-lookup"><span data-stu-id="65249-133">Template Variables</span></span>](template-variables.md)
    
- [<span data-ttu-id="65249-134">正确显示活动的指南</span><span class="sxs-lookup"><span data-stu-id="65249-134">Guidelines for Properly Displaying Activities</span></span>](guidelines-for-properly-displaying-activities.md)
    
## <a name="see-also"></a><span data-ttu-id="65249-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65249-135">See also</span></span>

- [<span data-ttu-id="65249-136">活动源的 XML 示例</span><span class="sxs-lookup"><span data-stu-id="65249-136">Activity Feed XML Example</span></span>](activity-feed-xml-example.md)  
- [<span data-ttu-id="65249-137">同步朋友和活动</span><span class="sxs-lookup"><span data-stu-id="65249-137">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md) 
- [<span data-ttu-id="65249-138">功能 XML</span><span class="sxs-lookup"><span data-stu-id="65249-138">XML for Capabilities</span></span>](xml-for-capabilities.md)  
- [<span data-ttu-id="65249-139">朋友 XML</span><span class="sxs-lookup"><span data-stu-id="65249-139">XML for Friends</span></span>](xml-for-friends.md)
- [<span data-ttu-id="65249-140">开发 OSC XML 架构的提供程序</span><span class="sxs-lookup"><span data-stu-id="65249-140">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)

