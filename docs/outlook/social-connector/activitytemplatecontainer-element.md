---
title: activityTemplateContainer 元素
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 74662f25-5e18-4d0b-999c-a144427ad9e3
description: activityTemplateContainer 元素是一个模板，允许你设置活动源项的格式，并重复使用指定布局的 XML。
ms.openlocfilehash: c2540b1d871e440e8f8f343a1788194c32d7dcc2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413715"
---
# <a name="activitytemplatecontainer-element"></a><span data-ttu-id="70361-103">activityTemplateContainer 元素</span><span class="sxs-lookup"><span data-stu-id="70361-103">activityTemplateContainer Element</span></span>

<span data-ttu-id="70361-104">**activityTemplateContainer** 元素是一个模板，允许你设置活动源项的格式，并重复使用指定布局的 XML。</span><span class="sxs-lookup"><span data-stu-id="70361-104">An **activityTemplateContainer** element is a template that allows you to format your activity feed items and reuse XML that specifies a layout.</span></span> <span data-ttu-id="70361-105">使用 id (**applicationID** 和 **templateID**) 将源项目 (**activityDetails**) 与 (**activityTemplateContainer**) 。</span><span class="sxs-lookup"><span data-stu-id="70361-105">Use IDs (**applicationID** and **templateID**) to match a feed item (**activityDetails**) to a template (**activityTemplateContainer**).</span></span> <span data-ttu-id="70361-106">将布局数据存储为 **activityTemplate 元素的一** 部分。</span><span class="sxs-lookup"><span data-stu-id="70361-106">Store the layout data as part of the **activityTemplate** element.</span></span> <span data-ttu-id="70361-107">若要引用数据单个活动源项提取的内容，请使用模板变量作为人员、链接和文本等信息的占位符。</span><span class="sxs-lookup"><span data-stu-id="70361-107">To reference data that is pulled from the individual activity feed item, use template variables as placeholders for information such as people, links, and text.</span></span> 
  
<span data-ttu-id="70361-108">下表介绍了 **activityTemplateContainer** 元素所需的三个元素。</span><span class="sxs-lookup"><span data-stu-id="70361-108">The following table describes the three elements that the **activityTemplateContainer** element requires.</span></span> 
  
|<span data-ttu-id="70361-109">**元素**</span><span class="sxs-lookup"><span data-stu-id="70361-109">**Element**</span></span>|<span data-ttu-id="70361-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="70361-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="70361-111">**applicationID**</span><span class="sxs-lookup"><span data-stu-id="70361-111">**applicationID**</span></span> <br/> |<span data-ttu-id="70361-112">用于将源项与它的模板相匹配的两个唯一的标识之一。</span><span class="sxs-lookup"><span data-stu-id="70361-112">One of two unique IDs that are used to match the feed item with its template.</span></span> <span data-ttu-id="70361-113">如果你有多个应用程序或其他分组，这可用作第一层模板管理器。</span><span class="sxs-lookup"><span data-stu-id="70361-113">If you have multiple applications or other groupings, this can be used as a first-tier template organizer.</span></span>  <br/> |
|<span data-ttu-id="70361-114">**templateID**</span><span class="sxs-lookup"><span data-stu-id="70361-114">**templateID**</span></span> <br/> |<span data-ttu-id="70361-115">用于将源项与它的模板相匹配的第二个唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="70361-115">The second unique ID that is used to match the feed item with its template.</span></span> <span data-ttu-id="70361-116">这可用作第二层模板管理器。</span><span class="sxs-lookup"><span data-stu-id="70361-116">This can be used as a second-tier template organizer.</span></span>  <br/> |
|<span data-ttu-id="70361-117">**activityTemplate**</span><span class="sxs-lookup"><span data-stu-id="70361-117">**activityTemplate**</span></span> <br/> |<span data-ttu-id="70361-118">模板的布局 (**图标**、**标题** 和数据元素) ，以及活动类型 (**元素**) 。</span><span class="sxs-lookup"><span data-stu-id="70361-118">The layout of the template (**icon**, **title**, and **data** elements), and the type of activity (**type** element).</span></span>  <br/> |
   
<span data-ttu-id="70361-119">下表介绍了 **activityTemplate** 的子元素，这些子元素描述了模板的布局和类型。</span><span class="sxs-lookup"><span data-stu-id="70361-119">The following table describes the child elements of **activityTemplate**, which describe the layout and the type of a template.</span></span>
  
|<span data-ttu-id="70361-120">**元素**</span><span class="sxs-lookup"><span data-stu-id="70361-120">**Element**</span></span>|<span data-ttu-id="70361-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="70361-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="70361-122">**icon**</span><span class="sxs-lookup"><span data-stu-id="70361-122">**icon**</span></span> <br/> |<span data-ttu-id="70361-123">链接令牌，引用该源项的图标的 URL。</span><span class="sxs-lookup"><span data-stu-id="70361-123">A link token, which references the URL for the icon for that feed item.</span></span>  <br/> |
|<span data-ttu-id="70361-124">**title**</span><span class="sxs-lookup"><span data-stu-id="70361-124">**title**</span></span> <br/> |<span data-ttu-id="70361-125">源项的必需信息。</span><span class="sxs-lookup"><span data-stu-id="70361-125">The required information for the feed item.</span></span>  <br/> |
|<span data-ttu-id="70361-126">**type**</span><span class="sxs-lookup"><span data-stu-id="70361-126">**type**</span></span> <br/> |<span data-ttu-id="70361-127">活动类型，例如状态、照片或文档的更新。</span><span class="sxs-lookup"><span data-stu-id="70361-127">The type of activity, such as an update of status, photo, or document.</span></span>  <br/> |
|<span data-ttu-id="70361-128">**data**</span><span class="sxs-lookup"><span data-stu-id="70361-128">**data**</span></span> <br/> |<span data-ttu-id="70361-129">源项的其他任何信息，例如图片、文本或链接。</span><span class="sxs-lookup"><span data-stu-id="70361-129">Any additional information for the feed item, such as pictures, text, or links.</span></span>  <br/> |
   
<span data-ttu-id="70361-130">有关活动源 XML 的示例，请参阅 [活动源 XML 示例](activity-feed-xml-example.md)</span><span class="sxs-lookup"><span data-stu-id="70361-130">For an example of activity feed XML, see [Activity Feed XML Example](activity-feed-xml-example.md)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="70361-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70361-131">See also</span></span>

- [<span data-ttu-id="70361-132">活动源项的 XML 概述</span><span class="sxs-lookup"><span data-stu-id="70361-132">Overview of XML for an Activity Feed Item</span></span>](overview-of-xml-for-an-activity-feed-item.md)  
- [<span data-ttu-id="70361-133">activityDetails 元素</span><span class="sxs-lookup"><span data-stu-id="70361-133">activityDetails Element</span></span>](activitydetails-element.md)  
- [<span data-ttu-id="70361-134">模板变量</span><span class="sxs-lookup"><span data-stu-id="70361-134">Template Variables</span></span>](template-variables.md)  
- [<span data-ttu-id="70361-135">正确显示活动指南</span><span class="sxs-lookup"><span data-stu-id="70361-135">Guidelines for Properly Displaying Activities</span></span>](guidelines-for-properly-displaying-activities.md)  
- [<span data-ttu-id="70361-136">活动的 XML</span><span class="sxs-lookup"><span data-stu-id="70361-136">XML for Activities</span></span>](xml-for-activities.md)  
- [<span data-ttu-id="70361-137">OutlookSocial Connector Provider XML 架构</span><span class="sxs-lookup"><span data-stu-id="70361-137">Outlook Social Connector Provider XML Schema</span></span>](outlook-social-connector-provider-xml-schema.md)
- [<span data-ttu-id="70361-138">使用 OSC XML 架构开发提供程序</span><span class="sxs-lookup"><span data-stu-id="70361-138">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)

