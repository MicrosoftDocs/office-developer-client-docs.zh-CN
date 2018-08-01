---
title: activityDetails 元素
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c103d48d-53ca-4b19-b16f-2862379587ef
description: ActivityDetails 元素存储单个活动源项目的原始数据。 每个活动源项必须具有自己 activityDetails 元素。 使用名称元素中活动模板引用了 activityDetails 元素中的数据。
ms.openlocfilehash: c326017a038dff138d690b020a98972a08212690
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779202"
---
# <a name="activitydetails-element"></a><span data-ttu-id="cc2b0-105">activityDetails 元素</span><span class="sxs-lookup"><span data-stu-id="cc2b0-105">activityDetails Element</span></span>

<span data-ttu-id="cc2b0-106">**ActivityDetails**元素存储单个活动源项目的原始数据。</span><span class="sxs-lookup"><span data-stu-id="cc2b0-106">The **activityDetails** element stores the raw data for a single activity feed item.</span></span> <span data-ttu-id="cc2b0-107">每个活动源项必须具有自己**activityDetails**元素。</span><span class="sxs-lookup"><span data-stu-id="cc2b0-107">Each activity feed item must have its own **activityDetails** element.</span></span> <span data-ttu-id="cc2b0-108">使用**名称**元素中活动模板引用了**activityDetails**元素中的数据。</span><span class="sxs-lookup"><span data-stu-id="cc2b0-108">Data in the **activityDetails** element is referenced in activity templates by using **name** elements.</span></span> <span data-ttu-id="cc2b0-109">每条**activityDetails**元素中的数据必须具有**name**元素。</span><span class="sxs-lookup"><span data-stu-id="cc2b0-109">Every piece of data in the **activityDetails** element must have a **name** element.</span></span> 
  
<span data-ttu-id="cc2b0-110">下表介绍**activityDetails**元素需要的六个元素。</span><span class="sxs-lookup"><span data-stu-id="cc2b0-110">The following table describes the six elements that the **activityDetails** element requires.</span></span> 
  
|<span data-ttu-id="cc2b0-111">**元素**</span><span class="sxs-lookup"><span data-stu-id="cc2b0-111">**Element**</span></span>|<span data-ttu-id="cc2b0-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="cc2b0-112">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc2b0-113">**ownerID**</span><span class="sxs-lookup"><span data-stu-id="cc2b0-113">**ownerID**</span></span> <br/> |<span data-ttu-id="cc2b0-114">社交网络产生此活动用户的 ID 的订阅源。</span><span class="sxs-lookup"><span data-stu-id="cc2b0-114">The ID of the user on the social network who generated this activity feed item.</span></span>  <br/> |
|<span data-ttu-id="cc2b0-115">**objectID**</span><span class="sxs-lookup"><span data-stu-id="cc2b0-115">**objectID**</span></span> <br/> |<span data-ttu-id="cc2b0-116">活动的唯一字符串源来检测重复源项目的项目。</span><span class="sxs-lookup"><span data-stu-id="cc2b0-116">A unique string for the activity feed item to detect duplicate feed items.</span></span>  <br/> |
|<span data-ttu-id="cc2b0-117">**applicationId**</span><span class="sxs-lookup"><span data-stu-id="cc2b0-117">**applicationId**</span></span> <br/> |<span data-ttu-id="cc2b0-118">一个用于匹配活动的两个唯一 Id 源具有其模板的项目。</span><span class="sxs-lookup"><span data-stu-id="cc2b0-118">One of two unique IDs that are used to match the activity feed item with its template.</span></span> <span data-ttu-id="cc2b0-119">如果您有多个应用程序或其他分组，这可作为第一层模板组织者。</span><span class="sxs-lookup"><span data-stu-id="cc2b0-119">If you have multiple applications or other groupings, this can be used as a first-tier template organizer.</span></span>  <br/> |
|<span data-ttu-id="cc2b0-120">**templateId**</span><span class="sxs-lookup"><span data-stu-id="cc2b0-120">**templateId**</span></span> <br/> |<span data-ttu-id="cc2b0-121">用于匹配活动的第二个唯一 ID 源具有其模板的项目。</span><span class="sxs-lookup"><span data-stu-id="cc2b0-121">The second unique ID that is used to match the activity feed item with its template.</span></span> <span data-ttu-id="cc2b0-122">这可以用作第二层模板管理器。</span><span class="sxs-lookup"><span data-stu-id="cc2b0-122">This can be used as a second-tier template organizer.</span></span>  <br/> |
|<span data-ttu-id="cc2b0-123">**publishDate**</span><span class="sxs-lookup"><span data-stu-id="cc2b0-123">**publishDate**</span></span> <br/> |<span data-ttu-id="cc2b0-124">已发布的日期和时间的活动订阅源。</span><span class="sxs-lookup"><span data-stu-id="cc2b0-124">The date and time that the activity feed item was published.</span></span>  <br/> |
|<span data-ttu-id="cc2b0-125">**templateVariables**</span><span class="sxs-lookup"><span data-stu-id="cc2b0-125">**templateVariables**</span></span> <br/> |<span data-ttu-id="cc2b0-126">要用于活动的令牌中的数据源项目模板。</span><span class="sxs-lookup"><span data-stu-id="cc2b0-126">The data to be used in the tokens for the activity feed item template.</span></span>  <br/> |
   
<span data-ttu-id="cc2b0-127">有关示例活动的源 XML，请参阅[活动源 XML 示例](activity-feed-xml-example.md)</span><span class="sxs-lookup"><span data-stu-id="cc2b0-127">For an example of activity feed XML, see [Activity Feed XML Example](activity-feed-xml-example.md)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cc2b0-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc2b0-128">See also</span></span>

- [<span data-ttu-id="cc2b0-129">概述 XML 的活动订阅源</span><span class="sxs-lookup"><span data-stu-id="cc2b0-129">Overview of XML for an Activity Feed Item</span></span>](overview-of-xml-for-an-activity-feed-item.md)  
- [<span data-ttu-id="cc2b0-130">activityTemplateContainer 元素</span><span class="sxs-lookup"><span data-stu-id="cc2b0-130">activityTemplateContainer Element</span></span>](activitytemplatecontainer-element.md)  
- [<span data-ttu-id="cc2b0-131">模板变量</span><span class="sxs-lookup"><span data-stu-id="cc2b0-131">Template Variables</span></span>](template-variables.md) 
- [<span data-ttu-id="cc2b0-132">正确显示活动的指南</span><span class="sxs-lookup"><span data-stu-id="cc2b0-132">Guidelines for Properly Displaying Activities</span></span>](guidelines-for-properly-displaying-activities.md)  
- [<span data-ttu-id="cc2b0-133">活动的 XML</span><span class="sxs-lookup"><span data-stu-id="cc2b0-133">XML for Activities</span></span>](xml-for-activities.md)  
- [<span data-ttu-id="cc2b0-134">Outlook Social Connector 提供程序的 XML 架构</span><span class="sxs-lookup"><span data-stu-id="cc2b0-134">Outlook Social Connector Provider XML Schema</span></span>](outlook-social-connector-provider-xml-schema.md)
- [<span data-ttu-id="cc2b0-135">开发 OSC XML 架构的提供程序</span><span class="sxs-lookup"><span data-stu-id="cc2b0-135">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)

