---
title: 活动源项的 XML 概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 366550fa-e787-4ca0-bfe1-a7890dfc27c6
description: '活动源由社交网络中发生的一个或多个活动组成。 每个活动源均由一个 microsoft.office.server.activityfeed 元素表示, 并由以下三条信息组成:'
ms.openlocfilehash: 971c54cf69a65bebbe4fd04e8608e88b89145bb4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439945"
---
# <a name="overview-of-xml-for-an-activity-feed-item"></a><span data-ttu-id="de85e-104">活动源项的 XML 概述</span><span class="sxs-lookup"><span data-stu-id="de85e-104">Overview of XML for an activity feed item</span></span>

<span data-ttu-id="de85e-105">活动源由社交网络中发生的一个或多个活动组成。</span><span class="sxs-lookup"><span data-stu-id="de85e-105">An activity feed consists of one or more activities occurring on a social network.</span></span> <span data-ttu-id="de85e-106">每个活动源均由一个**microsoft.office.server.activityfeed**元素表示, 并由以下三条信息组成:</span><span class="sxs-lookup"><span data-stu-id="de85e-106">Each activity feed is represented by an **activityFeed** element, and is characterized by these three pieces of information:</span></span> 
  
- <span data-ttu-id="de85e-107">**网络**—活动源自的社交网络的名称。</span><span class="sxs-lookup"><span data-stu-id="de85e-107">**network**—Name of the social network from which the activities originated.</span></span>
    
- <span data-ttu-id="de85e-108">**活动**—在该社交网络上登录用户帐户上发生的活动的容器。</span><span class="sxs-lookup"><span data-stu-id="de85e-108">**activities**—Container for activities happening on the logged on user's account on that social network.</span></span>
    
- <span data-ttu-id="de85e-109">**模板**-用于在**活动**中显示相应活动项的模板的容器。</span><span class="sxs-lookup"><span data-stu-id="de85e-109">**templates**—Container for templates that are used to display the corresponding activity item in **activities**.</span></span>
    
<span data-ttu-id="de85e-110">若要创建活动源项目, 您必须符合 Outlook Social Connector (.osc) 提供程序扩展性 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="de85e-110">To create an activity feed item, you must conform to the Outlook Social Connector (OSC) provider extensibility XML schema.</span></span> <span data-ttu-id="de85e-111">图1显示了活动源 XML 结构。</span><span class="sxs-lookup"><span data-stu-id="de85e-111">Figure 1 shows the activity feed XML structure.</span></span>
  
<span data-ttu-id="de85e-112">**图1。活动源 XML 结构**</span><span class="sxs-lookup"><span data-stu-id="de85e-112">**Figure 1. Activity feed XML structure**</span></span>

![活动 XML 结构](media/odc_ol14_ta_OSC_Fig06.gif)
  
<span data-ttu-id="de85e-114">对于每个活动源项目, 此架构的两个最重要部分是**activityDetails**和**activityTemplateContainer**元素:</span><span class="sxs-lookup"><span data-stu-id="de85e-114">For each activity feed item, the two most important parts of this schema are the **activityDetails** and **activityTemplateContainer** elements:</span></span> 
  
- <span data-ttu-id="de85e-115">**activityDetails**元素存储每个活动源项的特定信息, 例如活动所有者的名称或上载的图片的 URL。</span><span class="sxs-lookup"><span data-stu-id="de85e-115">The **activityDetails** element stores specific information for each activity feed item, such as the activity owner's name or the URL for the pictures uploaded.</span></span> 
    
- <span data-ttu-id="de85e-116">**activityTemplateContainer**元素存储每个活动源项目的格式或布局。</span><span class="sxs-lookup"><span data-stu-id="de85e-116">The **activityTemplateContainer** element stores the format or layout for each activity feed item.</span></span> <span data-ttu-id="de85e-117">它由各个**activityTemplate**元素表示的模板组成, 这些模板可重复用于多个订阅源项。</span><span class="sxs-lookup"><span data-stu-id="de85e-117">It consists of templates, represented by individual **activityTemplate** elements, that can be reused for multiple feed items.</span></span> 
    
<span data-ttu-id="de85e-118">对于单个活动源项, **activityTemplate**元素将指定以下四条信息:</span><span class="sxs-lookup"><span data-stu-id="de85e-118">For an individual activity feed item, the **activityTemplate** element specifies the following four pieces of information:</span></span> 
  
- <span data-ttu-id="de85e-119">**图标**—指定用于显示活动源项目的图标的 URL。</span><span class="sxs-lookup"><span data-stu-id="de85e-119">**icon**—Specifies the URL for the icon to display the activity feed item.</span></span>
    
- <span data-ttu-id="de85e-120">**标题**—描述活动源项目。</span><span class="sxs-lookup"><span data-stu-id="de85e-120">**title**—Describes the activity feed item.</span></span>
    
- <span data-ttu-id="de85e-121">**类型**—指定活动的类型, 如状态、照片或文档更新。</span><span class="sxs-lookup"><span data-stu-id="de85e-121">**type**—Specifies the type of activity, such as a status, photo, or document update.</span></span>
    
- <span data-ttu-id="de85e-122">**data**-指定与活动源项目一起显示的任何额外信息。</span><span class="sxs-lookup"><span data-stu-id="de85e-122">**data**—Specifies any extra information displayed with activity feed item.</span></span>
    
> [!TIP]
> <span data-ttu-id="de85e-123">活动源中显示的图标总是与**ISocialProvider:: SocialNetworkIcon**属性返回的提供程序图标相同。</span><span class="sxs-lookup"><span data-stu-id="de85e-123">The icon displayed in the activity feed is always the same as the provider icon returned by the **ISocialProvider::SocialNetworkIcon** property.</span></span> 
  
<span data-ttu-id="de85e-124">有关**activityDetails**元素、 **activityTemplateContainer**元素、模板标记和模板变量的详细信息, 请参阅以下主题:</span><span class="sxs-lookup"><span data-stu-id="de85e-124">See the following topics for more information about the **activityDetails** element, the **activityTemplateContainer** element, template tokens, and template variables:</span></span> 
  
- [<span data-ttu-id="de85e-125">activityDetails 元素</span><span class="sxs-lookup"><span data-stu-id="de85e-125">activityDetails Element</span></span>](activitydetails-element.md)
    
- [<span data-ttu-id="de85e-126">activityTemplateContainer 元素</span><span class="sxs-lookup"><span data-stu-id="de85e-126">activityTemplateContainer Element</span></span>](activitytemplatecontainer-element.md)
    
- [<span data-ttu-id="de85e-127">模板变量</span><span class="sxs-lookup"><span data-stu-id="de85e-127">Template Variables</span></span>](template-variables.md)
    
- [<span data-ttu-id="de85e-128">正确显示活动的准则</span><span class="sxs-lookup"><span data-stu-id="de85e-128">Guidelines for Properly Displaying Activities</span></span>](guidelines-for-properly-displaying-activities.md)
    
<span data-ttu-id="de85e-129">有关活动源 xml 的示例, 请参阅[活动源 xml 示例](activity-feed-xml-example.md)。</span><span class="sxs-lookup"><span data-stu-id="de85e-129">For an example of activity feed XML, see [Activity Feed XML Example](activity-feed-xml-example.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="de85e-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de85e-130">See also</span></span>

- [<span data-ttu-id="de85e-131">适用于活动的 XML</span><span class="sxs-lookup"><span data-stu-id="de85e-131">XML for Activities</span></span>](xml-for-activities.md) 
- [<span data-ttu-id="de85e-132">Outlook Social Connector 提供程序 XML 架构</span><span class="sxs-lookup"><span data-stu-id="de85e-132">Outlook Social Connector Provider XML Schema</span></span>](outlook-social-connector-provider-xml-schema.md)
- [<span data-ttu-id="de85e-133">使用 .osc XML 架构开发提供程序</span><span class="sxs-lookup"><span data-stu-id="de85e-133">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)

