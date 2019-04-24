---
title: activityTemplateContainer 元素
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 74662f25-5e18-4d0b-999c-a144427ad9e3
description: activityTemplateContainer 元素是一个模板, 允许您设置活动源项目的格式, 并重复使用指定布局的 XML。
ms.openlocfilehash: c2540b1d871e440e8f8f343a1788194c32d7dcc2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281118"
---
# <a name="activitytemplatecontainer-element"></a><span data-ttu-id="742f4-103">activityTemplateContainer 元素</span><span class="sxs-lookup"><span data-stu-id="742f4-103">activityTemplateContainer Element</span></span>

<span data-ttu-id="742f4-104">**activityTemplateContainer**元素是一个模板, 允许您设置活动源项目的格式, 并重复使用指定布局的 XML。</span><span class="sxs-lookup"><span data-stu-id="742f4-104">An **activityTemplateContainer** element is a template that allows you to format your activity feed items and reuse XML that specifies a layout.</span></span> <span data-ttu-id="742f4-105">使用 id (**applicationID**和**templateID**) 将源项目 (**activityDetails**) 与模板 (**activityTemplateContainer**) 相匹配。</span><span class="sxs-lookup"><span data-stu-id="742f4-105">Use IDs (**applicationID** and **templateID**) to match a feed item (**activityDetails**) to a template (**activityTemplateContainer**).</span></span> <span data-ttu-id="742f4-106">将布局数据存储为**activityTemplate**元素的一部分。</span><span class="sxs-lookup"><span data-stu-id="742f4-106">Store the layout data as part of the **activityTemplate** element.</span></span> <span data-ttu-id="742f4-107">若要引用从单个活动源项中提取的数据, 请使用模板变量作为信息 (如人员、链接和文本) 的占位符。</span><span class="sxs-lookup"><span data-stu-id="742f4-107">To reference data that is pulled from the individual activity feed item, use template variables as placeholders for information such as people, links, and text.</span></span> 
  
<span data-ttu-id="742f4-108">下表描述了**activityTemplateContainer**元素所需的三个元素。</span><span class="sxs-lookup"><span data-stu-id="742f4-108">The following table describes the three elements that the **activityTemplateContainer** element requires.</span></span> 
  
|<span data-ttu-id="742f4-109">**元素**</span><span class="sxs-lookup"><span data-stu-id="742f4-109">**Element**</span></span>|<span data-ttu-id="742f4-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="742f4-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="742f4-111">**applicationID**</span><span class="sxs-lookup"><span data-stu-id="742f4-111">**applicationID**</span></span> <br/> |<span data-ttu-id="742f4-112">用于将订阅源项与模板相匹配的两个唯一 id 之一。</span><span class="sxs-lookup"><span data-stu-id="742f4-112">One of two unique IDs that are used to match the feed item with its template.</span></span> <span data-ttu-id="742f4-113">如果您有多个应用程序或其他分组, 则可用作第一层模板组织者。</span><span class="sxs-lookup"><span data-stu-id="742f4-113">If you have multiple applications or other groupings, this can be used as a first-tier template organizer.</span></span>  <br/> |
|<span data-ttu-id="742f4-114">**templateID**</span><span class="sxs-lookup"><span data-stu-id="742f4-114">**templateID**</span></span> <br/> |<span data-ttu-id="742f4-115">用于将订阅源项与模板相匹配的第二个唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="742f4-115">The second unique ID that is used to match the feed item with its template.</span></span> <span data-ttu-id="742f4-116">这可用作第二层模板组织者。</span><span class="sxs-lookup"><span data-stu-id="742f4-116">This can be used as a second-tier template organizer.</span></span>  <br/> |
|<span data-ttu-id="742f4-117">**activityTemplate**</span><span class="sxs-lookup"><span data-stu-id="742f4-117">**activityTemplate**</span></span> <br/> |<span data-ttu-id="742f4-118">模板的布局 (**图标**、**标题**和**数据**元素) 以及活动的类型 (**type**元素)。</span><span class="sxs-lookup"><span data-stu-id="742f4-118">The layout of the template (**icon**, **title**, and **data** elements), and the type of activity (**type** element).</span></span>  <br/> |
   
<span data-ttu-id="742f4-119">下表描述了**activityTemplate**的子元素, 这些子元素描述了模板的布局和类型。</span><span class="sxs-lookup"><span data-stu-id="742f4-119">The following table describes the child elements of **activityTemplate**, which describe the layout and the type of a template.</span></span>
  
|<span data-ttu-id="742f4-120">**元素**</span><span class="sxs-lookup"><span data-stu-id="742f4-120">**Element**</span></span>|<span data-ttu-id="742f4-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="742f4-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="742f4-122">**icon**</span><span class="sxs-lookup"><span data-stu-id="742f4-122">**icon**</span></span> <br/> |<span data-ttu-id="742f4-123">链接令牌, 它引用该源项目的图标的 URL。</span><span class="sxs-lookup"><span data-stu-id="742f4-123">A link token, which references the URL for the icon for that feed item.</span></span>  <br/> |
|<span data-ttu-id="742f4-124">**title**</span><span class="sxs-lookup"><span data-stu-id="742f4-124">**title**</span></span> <br/> |<span data-ttu-id="742f4-125">订阅源项所需的信息。</span><span class="sxs-lookup"><span data-stu-id="742f4-125">The required information for the feed item.</span></span>  <br/> |
|<span data-ttu-id="742f4-126">**type**</span><span class="sxs-lookup"><span data-stu-id="742f4-126">**type**</span></span> <br/> |<span data-ttu-id="742f4-127">活动的类型, 例如状态、照片或文档的更新。</span><span class="sxs-lookup"><span data-stu-id="742f4-127">The type of activity, such as an update of status, photo, or document.</span></span>  <br/> |
|<span data-ttu-id="742f4-128">**data**</span><span class="sxs-lookup"><span data-stu-id="742f4-128">**data**</span></span> <br/> |<span data-ttu-id="742f4-129">订阅源项的任何附加信息, 如图片、文本或链接。</span><span class="sxs-lookup"><span data-stu-id="742f4-129">Any additional information for the feed item, such as pictures, text, or links.</span></span>  <br/> |
   
<span data-ttu-id="742f4-130">有关活动源 xml 的示例, 请参阅[活动源 xml 示例](activity-feed-xml-example.md)</span><span class="sxs-lookup"><span data-stu-id="742f4-130">For an example of activity feed XML, see [Activity Feed XML Example](activity-feed-xml-example.md)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="742f4-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="742f4-131">See also</span></span>

- [<span data-ttu-id="742f4-132">活动源项目的 XML 概述</span><span class="sxs-lookup"><span data-stu-id="742f4-132">Overview of XML for an Activity Feed Item</span></span>](overview-of-xml-for-an-activity-feed-item.md)  
- [<span data-ttu-id="742f4-133">activityDetails 元素</span><span class="sxs-lookup"><span data-stu-id="742f4-133">activityDetails Element</span></span>](activitydetails-element.md)  
- [<span data-ttu-id="742f4-134">模板变量</span><span class="sxs-lookup"><span data-stu-id="742f4-134">Template Variables</span></span>](template-variables.md)  
- [<span data-ttu-id="742f4-135">正确显示活动的准则</span><span class="sxs-lookup"><span data-stu-id="742f4-135">Guidelines for Properly Displaying Activities</span></span>](guidelines-for-properly-displaying-activities.md)  
- [<span data-ttu-id="742f4-136">适用于活动的 XML</span><span class="sxs-lookup"><span data-stu-id="742f4-136">XML for Activities</span></span>](xml-for-activities.md)  
- [<span data-ttu-id="742f4-137">Outlook Social Connector 提供程序 XML 架构</span><span class="sxs-lookup"><span data-stu-id="742f4-137">Outlook Social Connector Provider XML Schema</span></span>](outlook-social-connector-provider-xml-schema.md)
- [<span data-ttu-id="742f4-138">使用 .osc XML 架构开发提供程序</span><span class="sxs-lookup"><span data-stu-id="742f4-138">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)

