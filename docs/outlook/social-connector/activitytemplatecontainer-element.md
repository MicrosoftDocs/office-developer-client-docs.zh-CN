---
title: activityTemplateContainer 元素
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 74662f25-5e18-4d0b-999c-a144427ad9e3
description: ActivityTemplateContainer 元素是允许您格式活动源项目并重用指定布局 XML 模板。
ms.openlocfilehash: e744bb1bdb828003cdda7086468533b32b4bf20f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779205"
---
# <a name="activitytemplatecontainer-element"></a><span data-ttu-id="e02dc-103">activityTemplateContainer 元素</span><span class="sxs-lookup"><span data-stu-id="e02dc-103">activityTemplateContainer Element</span></span>

<span data-ttu-id="e02dc-104">**ActivityTemplateContainer**元素是允许您格式活动源项目并重用指定布局 XML 模板。</span><span class="sxs-lookup"><span data-stu-id="e02dc-104">An **activityTemplateContainer** element is a template that allows you to format your activity feed items and reuse XML that specifies a layout.</span></span> <span data-ttu-id="e02dc-105">使用 Id （**applicationID**和**templateID**），以匹配模板 (**activityTemplateContainer**) 的源的项 (**activityDetails**)。</span><span class="sxs-lookup"><span data-stu-id="e02dc-105">Use IDs (**applicationID** and **templateID**) to match a feed item (**activityDetails**) to a template (**activityTemplateContainer**).</span></span> <span data-ttu-id="e02dc-106">存储布局数据作为**activityTemplate**元素的一部分。</span><span class="sxs-lookup"><span data-stu-id="e02dc-106">Store the layout data as part of the **activityTemplate** element.</span></span> <span data-ttu-id="e02dc-107">若要引用取自单独的活动订阅源的数据，用作模板变量占位符的信息，如人员、 链接和文本。</span><span class="sxs-lookup"><span data-stu-id="e02dc-107">To reference data that is pulled from the individual activity feed item, use template variables as placeholders for information such as people, links, and text.</span></span> 
  
<span data-ttu-id="e02dc-108">下表介绍**activityTemplateContainer**元素需要的三个元素。</span><span class="sxs-lookup"><span data-stu-id="e02dc-108">The following table describes the three elements that the **activityTemplateContainer** element requires.</span></span> 
  
|<span data-ttu-id="e02dc-109">**元素**</span><span class="sxs-lookup"><span data-stu-id="e02dc-109">**Element**</span></span>|<span data-ttu-id="e02dc-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="e02dc-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e02dc-111">**applicationID**</span><span class="sxs-lookup"><span data-stu-id="e02dc-111">**applicationID**</span></span> <br/> |<span data-ttu-id="e02dc-112">一个用于匹配具有其模板的源的项的两个唯一 Id。</span><span class="sxs-lookup"><span data-stu-id="e02dc-112">One of two unique IDs that are used to match the feed item with its template.</span></span> <span data-ttu-id="e02dc-113">如果您有多个应用程序或其他分组，这可作为第一层模板组织者。</span><span class="sxs-lookup"><span data-stu-id="e02dc-113">If you have multiple applications or other groupings, this can be used as a first-tier template organizer.</span></span>  <br/> |
|<span data-ttu-id="e02dc-114">**templateID**</span><span class="sxs-lookup"><span data-stu-id="e02dc-114">**templateID**</span></span> <br/> |<span data-ttu-id="e02dc-115">用于匹配具有其模板的源的项第二个唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="e02dc-115">The second unique ID that is used to match the feed item with its template.</span></span> <span data-ttu-id="e02dc-116">这可以用作第二层模板管理器。</span><span class="sxs-lookup"><span data-stu-id="e02dc-116">This can be used as a second-tier template organizer.</span></span>  <br/> |
|<span data-ttu-id="e02dc-117">**activityTemplate**</span><span class="sxs-lookup"><span data-stu-id="e02dc-117">**activityTemplate**</span></span> <br/> |<span data-ttu-id="e02dc-118">模板 （**图标**、**标题**和**数据**元素），以及活动 （**type**元素） 的类型的布局。</span><span class="sxs-lookup"><span data-stu-id="e02dc-118">The layout of the template (**icon**, **title**, and **data** elements), and the type of activity (**type** element).</span></span>  <br/> |
   
<span data-ttu-id="e02dc-119">下表介绍**activityTemplate**，其中描述了布局和模板的类型的子元素。</span><span class="sxs-lookup"><span data-stu-id="e02dc-119">The following table describes the child elements of **activityTemplate**, which describe the layout and the type of a template.</span></span>
  
|<span data-ttu-id="e02dc-120">**元素**</span><span class="sxs-lookup"><span data-stu-id="e02dc-120">**Element**</span></span>|<span data-ttu-id="e02dc-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="e02dc-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e02dc-122">**icon**</span><span class="sxs-lookup"><span data-stu-id="e02dc-122">**icon**</span></span> <br/> |<span data-ttu-id="e02dc-123">链接令牌，引用该订阅源的项目的图标的 URL。</span><span class="sxs-lookup"><span data-stu-id="e02dc-123">A link token, which references the URL for the icon for that feed item.</span></span>  <br/> |
|<span data-ttu-id="e02dc-124">**title**</span><span class="sxs-lookup"><span data-stu-id="e02dc-124">**title**</span></span> <br/> |<span data-ttu-id="e02dc-125">订阅源所需的信息。</span><span class="sxs-lookup"><span data-stu-id="e02dc-125">The required information for the feed item.</span></span>  <br/> |
|<span data-ttu-id="e02dc-126">**type**</span><span class="sxs-lookup"><span data-stu-id="e02dc-126">**type**</span></span> <br/> |<span data-ttu-id="e02dc-127">活动，如状态、 照片或文档的更新的类型。</span><span class="sxs-lookup"><span data-stu-id="e02dc-127">The type of activity, such as an update of status, photo, or document.</span></span>  <br/> |
|<span data-ttu-id="e02dc-128">**data**</span><span class="sxs-lookup"><span data-stu-id="e02dc-128">**data**</span></span> <br/> |<span data-ttu-id="e02dc-129">对于订阅源的项，如图片、 文本或链接的任何其他信息。</span><span class="sxs-lookup"><span data-stu-id="e02dc-129">Any additional information for the feed item, such as pictures, text, or links.</span></span>  <br/> |
   
<span data-ttu-id="e02dc-130">有关示例活动的源 XML，请参阅[活动源 XML 示例](activity-feed-xml-example.md)</span><span class="sxs-lookup"><span data-stu-id="e02dc-130">For an example of activity feed XML, see [Activity Feed XML Example](activity-feed-xml-example.md)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e02dc-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e02dc-131">See also</span></span>

- [<span data-ttu-id="e02dc-132">概述 XML 的活动订阅源</span><span class="sxs-lookup"><span data-stu-id="e02dc-132">Overview of XML for an Activity Feed Item</span></span>](overview-of-xml-for-an-activity-feed-item.md)  
- [<span data-ttu-id="e02dc-133">activityDetails 元素</span><span class="sxs-lookup"><span data-stu-id="e02dc-133">activityDetails Element</span></span>](activitydetails-element.md)  
- [<span data-ttu-id="e02dc-134">模板变量</span><span class="sxs-lookup"><span data-stu-id="e02dc-134">Template Variables</span></span>](template-variables.md)  
- [<span data-ttu-id="e02dc-135">正确显示活动的指南</span><span class="sxs-lookup"><span data-stu-id="e02dc-135">Guidelines for Properly Displaying Activities</span></span>](guidelines-for-properly-displaying-activities.md)  
- [<span data-ttu-id="e02dc-136">活动的 XML</span><span class="sxs-lookup"><span data-stu-id="e02dc-136">XML for Activities</span></span>](xml-for-activities.md)  
- [<span data-ttu-id="e02dc-137">Outlook Social Connector 提供程序的 XML 架构</span><span class="sxs-lookup"><span data-stu-id="e02dc-137">Outlook Social Connector Provider XML Schema</span></span>](outlook-social-connector-provider-xml-schema.md)
- [<span data-ttu-id="e02dc-138">开发 OSC XML 架构的提供程序</span><span class="sxs-lookup"><span data-stu-id="e02dc-138">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)

