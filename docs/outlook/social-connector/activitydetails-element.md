---
title: activityDetails 元素
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c103d48d-53ca-4b19-b16f-2862379587ef
description: activityDetails 元素存储单个活动源项的原始数据。 每个活动源项都必须有自己的 activityDetails 元素。 activityDetails 元素中的数据通过使用 name 元素在活动模板中引用。
ms.openlocfilehash: fd9c2136e8e2b687fa281ecda71039809848f63c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434870"
---
# <a name="activitydetails-element"></a><span data-ttu-id="fb7d3-105">activityDetails 元素</span><span class="sxs-lookup"><span data-stu-id="fb7d3-105">activityDetails Element</span></span>

<span data-ttu-id="fb7d3-106">**activityDetails** 元素存储单个活动源项的原始数据。</span><span class="sxs-lookup"><span data-stu-id="fb7d3-106">The **activityDetails** element stores the raw data for a single activity feed item.</span></span> <span data-ttu-id="fb7d3-107">每个活动源项都必须有自己的 **activityDetails** 元素。</span><span class="sxs-lookup"><span data-stu-id="fb7d3-107">Each activity feed item must have its own **activityDetails** element.</span></span> <span data-ttu-id="fb7d3-108">**activityDetails** 元素中的数据通过使用 name 元素在活动 **模板中** 引用。</span><span class="sxs-lookup"><span data-stu-id="fb7d3-108">Data in the **activityDetails** element is referenced in activity templates by using **name** elements.</span></span> <span data-ttu-id="fb7d3-109">**activityDetails 元素** 中每段数据都必须有 **一个 name** 元素。</span><span class="sxs-lookup"><span data-stu-id="fb7d3-109">Every piece of data in the **activityDetails** element must have a **name** element.</span></span> 
  
<span data-ttu-id="fb7d3-110">下表介绍了 **activityDetails 元素** 所需的六个元素。</span><span class="sxs-lookup"><span data-stu-id="fb7d3-110">The following table describes the six elements that the **activityDetails** element requires.</span></span> 
  
|<span data-ttu-id="fb7d3-111">**元素**</span><span class="sxs-lookup"><span data-stu-id="fb7d3-111">**Element**</span></span>|<span data-ttu-id="fb7d3-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="fb7d3-112">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fb7d3-113">**ownerID**</span><span class="sxs-lookup"><span data-stu-id="fb7d3-113">**ownerID**</span></span> <br/> |<span data-ttu-id="fb7d3-114">社交网络上生成此活动源项的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="fb7d3-114">The ID of the user on the social network who generated this activity feed item.</span></span>  <br/> |
|<span data-ttu-id="fb7d3-115">**objectID**</span><span class="sxs-lookup"><span data-stu-id="fb7d3-115">**objectID**</span></span> <br/> |<span data-ttu-id="fb7d3-116">活动源项的唯一字符串，用于检测重复的源项。</span><span class="sxs-lookup"><span data-stu-id="fb7d3-116">A unique string for the activity feed item to detect duplicate feed items.</span></span>  <br/> |
|<span data-ttu-id="fb7d3-117">**applicationId**</span><span class="sxs-lookup"><span data-stu-id="fb7d3-117">**applicationId**</span></span> <br/> |<span data-ttu-id="fb7d3-118">用于将活动源项与活动源项及其模板相匹配的两个唯一的标识之一。</span><span class="sxs-lookup"><span data-stu-id="fb7d3-118">One of two unique IDs that are used to match the activity feed item with its template.</span></span> <span data-ttu-id="fb7d3-119">如果你有多个应用程序或其他分组，这可用作第一层模板管理器。</span><span class="sxs-lookup"><span data-stu-id="fb7d3-119">If you have multiple applications or other groupings, this can be used as a first-tier template organizer.</span></span>  <br/> |
|<span data-ttu-id="fb7d3-120">**templateId**</span><span class="sxs-lookup"><span data-stu-id="fb7d3-120">**templateId**</span></span> <br/> |<span data-ttu-id="fb7d3-121">用于将活动源项与活动源项及其模板相匹配的第二个唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="fb7d3-121">The second unique ID that is used to match the activity feed item with its template.</span></span> <span data-ttu-id="fb7d3-122">这可用作第二层模板管理器。</span><span class="sxs-lookup"><span data-stu-id="fb7d3-122">This can be used as a second-tier template organizer.</span></span>  <br/> |
|<span data-ttu-id="fb7d3-123">**publishDate**</span><span class="sxs-lookup"><span data-stu-id="fb7d3-123">**publishDate**</span></span> <br/> |<span data-ttu-id="fb7d3-124">活动源项目的发布日期和时间。</span><span class="sxs-lookup"><span data-stu-id="fb7d3-124">The date and time that the activity feed item was published.</span></span>  <br/> |
|<span data-ttu-id="fb7d3-125">**templateVariables**</span><span class="sxs-lookup"><span data-stu-id="fb7d3-125">**templateVariables**</span></span> <br/> |<span data-ttu-id="fb7d3-126">在活动源项模板的令牌中使用的数据。</span><span class="sxs-lookup"><span data-stu-id="fb7d3-126">The data to be used in the tokens for the activity feed item template.</span></span>  <br/> |
   
<span data-ttu-id="fb7d3-127">有关活动源 XML 的示例，请参阅 [活动源 XML 示例](activity-feed-xml-example.md)</span><span class="sxs-lookup"><span data-stu-id="fb7d3-127">For an example of activity feed XML, see [Activity Feed XML Example](activity-feed-xml-example.md)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fb7d3-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb7d3-128">See also</span></span>

- [<span data-ttu-id="fb7d3-129">活动源项的 XML 概述</span><span class="sxs-lookup"><span data-stu-id="fb7d3-129">Overview of XML for an Activity Feed Item</span></span>](overview-of-xml-for-an-activity-feed-item.md)  
- [<span data-ttu-id="fb7d3-130">activityTemplateContainer 元素</span><span class="sxs-lookup"><span data-stu-id="fb7d3-130">activityTemplateContainer Element</span></span>](activitytemplatecontainer-element.md)  
- [<span data-ttu-id="fb7d3-131">模板变量</span><span class="sxs-lookup"><span data-stu-id="fb7d3-131">Template Variables</span></span>](template-variables.md) 
- [<span data-ttu-id="fb7d3-132">正确显示活动指南</span><span class="sxs-lookup"><span data-stu-id="fb7d3-132">Guidelines for Properly Displaying Activities</span></span>](guidelines-for-properly-displaying-activities.md)  
- [<span data-ttu-id="fb7d3-133">活动的 XML</span><span class="sxs-lookup"><span data-stu-id="fb7d3-133">XML for Activities</span></span>](xml-for-activities.md)  
- [<span data-ttu-id="fb7d3-134">OutlookSocial Connector Provider XML 架构</span><span class="sxs-lookup"><span data-stu-id="fb7d3-134">Outlook Social Connector Provider XML Schema</span></span>](outlook-social-connector-provider-xml-schema.md)
- [<span data-ttu-id="fb7d3-135">使用 OSC XML 架构开发提供程序</span><span class="sxs-lookup"><span data-stu-id="fb7d3-135">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)

