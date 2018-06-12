---
title: 概述 XML 的活动订阅源
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 366550fa-e787-4ca0-bfe1-a7890dfc27c6
description: 活动源包括社交网络上发生的一个或多个活动。 每个活动源由 activityFeed 元素，并具有以下三个信息特征：
ms.openlocfilehash: 318875aeb6312a3710654d129f3f48139ff7ef12
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779341"
---
# <a name="overview-of-xml-for-an-activity-feed-item"></a><span data-ttu-id="82053-104">概述 XML 的活动订阅源</span><span class="sxs-lookup"><span data-stu-id="82053-104">Overview of XML for an activity feed item</span></span>

<span data-ttu-id="82053-105">活动源包括社交网络上发生的一个或多个活动。</span><span class="sxs-lookup"><span data-stu-id="82053-105">An activity feed consists of one or more activities occurring on a social network.</span></span> <span data-ttu-id="82053-106">每个活动源由**activityFeed**元素，并具有以下三个信息特征：</span><span class="sxs-lookup"><span data-stu-id="82053-106">Each activity feed is represented by an **activityFeed** element, and is characterized by these three pieces of information:</span></span> 
  
- <span data-ttu-id="82053-107">**网络**— 活动产生的社交网络的名称。</span><span class="sxs-lookup"><span data-stu-id="82053-107">**network**—Name of the social network from which the activities originated.</span></span>
    
- <span data-ttu-id="82053-108">**活动**-活动上登录的用户的帐户的社交网络上发生的情况的容器。</span><span class="sxs-lookup"><span data-stu-id="82053-108">**activities**—Container for activities happening on the logged on user's account on that social network.</span></span>
    
- <span data-ttu-id="82053-109">**模板**— 用于显示相应的活动项目中**活动**的模板的容器。</span><span class="sxs-lookup"><span data-stu-id="82053-109">**templates**—Container for templates that are used to display the corresponding activity item in **activities**.</span></span>
    
<span data-ttu-id="82053-110">若要创建活动源项目，必须符合 Outlook Social Connector (OSC) 提供程序扩展性 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="82053-110">To create an activity feed item, you must conform to the Outlook Social Connector (OSC) provider extensibility XML schema.</span></span> <span data-ttu-id="82053-111">图 1 显示活动的源 XML 结构。</span><span class="sxs-lookup"><span data-stu-id="82053-111">Figure 1 shows the activity feed XML structure.</span></span>
  
<span data-ttu-id="82053-112">**图 1。活动源 XML 结构**</span><span class="sxs-lookup"><span data-stu-id="82053-112">**Figure 1. Activity feed XML structure**</span></span>

![活动 XML 结构](media/odc_ol14_ta_OSC_Fig06.gif)
  
<span data-ttu-id="82053-114">每个活动订阅源，此架构的两个最重要部分是**activityDetails**和**activityTemplateContainer**要素：</span><span class="sxs-lookup"><span data-stu-id="82053-114">For each activity feed item, the two most important parts of this schema are the **activityDetails** and **activityTemplateContainer** elements:</span></span> 
  
- <span data-ttu-id="82053-115">**ActivityDetails**元素存储每个活动源项目，如活动所有者的名称或图片上载的 URL 的特定信息。</span><span class="sxs-lookup"><span data-stu-id="82053-115">The **activityDetails** element stores specific information for each activity feed item, such as the activity owner's name or the URL for the pictures uploaded.</span></span> 
    
- <span data-ttu-id="82053-116">为每个活动的布局源项目或**activityTemplateContainer**元素存储格式。</span><span class="sxs-lookup"><span data-stu-id="82053-116">The **activityTemplateContainer** element stores the format or layout for each activity feed item.</span></span> <span data-ttu-id="82053-117">它包含模板，由单个**activityTemplate**元素，表示可重用的多个源的项目。</span><span class="sxs-lookup"><span data-stu-id="82053-117">It consists of templates, represented by individual **activityTemplate** elements, that can be reused for multiple feed items.</span></span> 
    
<span data-ttu-id="82053-118">为单个活动订阅源， **activityTemplate**元素指定信息的以下四个部分：</span><span class="sxs-lookup"><span data-stu-id="82053-118">For an individual activity feed item, the **activityTemplate** element specifies the following four pieces of information:</span></span> 
  
- <span data-ttu-id="82053-119">**图标**— 指定图标的 URL，以显示活动订阅源。</span><span class="sxs-lookup"><span data-stu-id="82053-119">**icon**—Specifies the URL for the icon to display the activity feed item.</span></span>
    
- <span data-ttu-id="82053-120">**标题**— 介绍的活动订阅源。</span><span class="sxs-lookup"><span data-stu-id="82053-120">**title**—Describes the activity feed item.</span></span>
    
- <span data-ttu-id="82053-121">**类型**— 指定活动，如状态、 照片或文档更新的类型。</span><span class="sxs-lookup"><span data-stu-id="82053-121">**type**—Specifies the type of activity, such as a status, photo, or document update.</span></span>
    
- <span data-ttu-id="82053-122">**数据**— 指定显示与活动订阅源的任何额外信息。</span><span class="sxs-lookup"><span data-stu-id="82053-122">**data**—Specifies any extra information displayed with activity feed item.</span></span>
    
> [!TIP]
> <span data-ttu-id="82053-123">活动源中显示的图标始终是**ISocialProvider::SocialNetworkIcon**属性返回的提供程序图标相同。</span><span class="sxs-lookup"><span data-stu-id="82053-123">The icon displayed in the activity feed is always the same as the provider icon returned by the **ISocialProvider::SocialNetworkIcon** property.</span></span> 
  
<span data-ttu-id="82053-124">请参阅以下主题有关**activityDetails**元素、 **activityTemplateContainer**元素、 模板令牌和模板变量的详细信息：</span><span class="sxs-lookup"><span data-stu-id="82053-124">See the following topics for more information about the **activityDetails** element, the **activityTemplateContainer** element, template tokens, and template variables:</span></span> 
  
- [<span data-ttu-id="82053-125">activityDetails 元素</span><span class="sxs-lookup"><span data-stu-id="82053-125">activityDetails Element</span></span>](activitydetails-element.md)
    
- [<span data-ttu-id="82053-126">activityTemplateContainer 元素</span><span class="sxs-lookup"><span data-stu-id="82053-126">activityTemplateContainer Element</span></span>](activitytemplatecontainer-element.md)
    
- [<span data-ttu-id="82053-127">模板变量</span><span class="sxs-lookup"><span data-stu-id="82053-127">Template Variables</span></span>](template-variables.md)
    
- [<span data-ttu-id="82053-128">正确显示活动的指南</span><span class="sxs-lookup"><span data-stu-id="82053-128">Guidelines for Properly Displaying Activities</span></span>](guidelines-for-properly-displaying-activities.md)
    
<span data-ttu-id="82053-129">示例活动的源 XML，请参阅[活动源 XML 示例](activity-feed-xml-example.md)。</span><span class="sxs-lookup"><span data-stu-id="82053-129">For an example of activity feed XML, see [Activity Feed XML Example](activity-feed-xml-example.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="82053-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82053-130">See also</span></span>

- [<span data-ttu-id="82053-131">活动的 XML</span><span class="sxs-lookup"><span data-stu-id="82053-131">XML for Activities</span></span>](xml-for-activities.md) 
- [<span data-ttu-id="82053-132">Outlook Social Connector 提供程序的 XML 架构</span><span class="sxs-lookup"><span data-stu-id="82053-132">Outlook Social Connector Provider XML Schema</span></span>](outlook-social-connector-provider-xml-schema.md)
- [<span data-ttu-id="82053-133">开发 OSC XML 架构的提供程序</span><span class="sxs-lookup"><span data-stu-id="82053-133">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)

