---
title: 模板变量
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6f8f6af2-c7fa-4135-9532-7af5fc643b0d
description: 由 templateVariable (表示的模板变量) 指定活动模板中活动源项的数据。
ms.openlocfilehash: 9b37665488f0f1e2bd205fb7d4a5d2201697d7c8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404370"
---
# <a name="template-variables"></a><span data-ttu-id="2a765-103">模板变量</span><span class="sxs-lookup"><span data-stu-id="2a765-103">Template variables</span></span>

<span data-ttu-id="2a765-104">由 **templateVariable** (表示的模板变量) 指定活动模板中的活动源项的数据。</span><span class="sxs-lookup"><span data-stu-id="2a765-104">Instances of template variables (represented by a **templateVariable** element) specify the data of an activity feed item in an activity template.</span></span> 
  
<span data-ttu-id="2a765-105">有关活动源 XML 的示例，请参阅 [活动源 XML 示例](activity-feed-xml-example.md)。</span><span class="sxs-lookup"><span data-stu-id="2a765-105">For an example of activity feed XML, see [Activity Feed XML Example](activity-feed-xml-example.md).</span></span>

<span data-ttu-id="2a765-106">下表显示了受支持的模板变量的类型，每种变量都由相应的 XML 枚举值表示。</span><span class="sxs-lookup"><span data-stu-id="2a765-106">The following table shows the types of supported template variables, each represented by the corresponding XML enumeration value.</span></span>
  
|<span data-ttu-id="2a765-107">**模板变量的类型**</span><span class="sxs-lookup"><span data-stu-id="2a765-107">**Type of template variable**</span></span>|<span data-ttu-id="2a765-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="2a765-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2a765-109">**entityVariable**</span><span class="sxs-lookup"><span data-stu-id="2a765-109">**entityVariable**</span></span> <br/> |<span data-ttu-id="2a765-110">人员、组或事物。</span><span class="sxs-lookup"><span data-stu-id="2a765-110">A person, group, or thing.</span></span>  <br/> |
|<span data-ttu-id="2a765-111">**linkVariable**</span><span class="sxs-lookup"><span data-stu-id="2a765-111">**linkVariable**</span></span> <br/> |<span data-ttu-id="2a765-112">链接。</span><span class="sxs-lookup"><span data-stu-id="2a765-112">A link.</span></span>  <br/> |
|<span data-ttu-id="2a765-113">**listVariable**</span><span class="sxs-lookup"><span data-stu-id="2a765-113">**listVariable**</span></span> <br/> |<span data-ttu-id="2a765-114">一组对象。</span><span class="sxs-lookup"><span data-stu-id="2a765-114">A group of objects.</span></span>  <br/> |
|<span data-ttu-id="2a765-115">**pictureVariable**</span><span class="sxs-lookup"><span data-stu-id="2a765-115">**pictureVariable**</span></span> <br/> |<span data-ttu-id="2a765-116">图片。</span><span class="sxs-lookup"><span data-stu-id="2a765-116">A picture.</span></span>  <br/> |
|<span data-ttu-id="2a765-117">**publisherVariable**</span><span class="sxs-lookup"><span data-stu-id="2a765-117">**publisherVariable**</span></span> <br/> |<span data-ttu-id="2a765-118">活动源项的发布者。</span><span class="sxs-lookup"><span data-stu-id="2a765-118">The publisher of the activity feed item.</span></span>  <br/> |
|<span data-ttu-id="2a765-119">**textVariable**</span><span class="sxs-lookup"><span data-stu-id="2a765-119">**textVariable**</span></span> <br/> |<span data-ttu-id="2a765-120">一个文本块。</span><span class="sxs-lookup"><span data-stu-id="2a765-120">A block of text.</span></span>  <br/> |
   
<span data-ttu-id="2a765-121">每种类型的模板变量都有必需元素来指定有关该变量的数据。</span><span class="sxs-lookup"><span data-stu-id="2a765-121">Each type of template variable has required elements to specify the data about that variable.</span></span> <span data-ttu-id="2a765-122">模板变量的指定方式如下：</span><span class="sxs-lookup"><span data-stu-id="2a765-122">Template variables are specified as follows:</span></span>
  
`<templateVariable type="variable type">`
  
## <a name="list-template-variable"></a><span data-ttu-id="2a765-123">列表模板变量</span><span class="sxs-lookup"><span data-stu-id="2a765-123">List template variable</span></span>

<span data-ttu-id="2a765-124">可以指定包含在列表内且由 **listVariable** 和 **listItems** (分隔的模板变量) 如下所示：</span><span class="sxs-lookup"><span data-stu-id="2a765-124">You can specify template variables that are contained within a list (delimited by the **listVariable** and **listItems** elements) as follows:</span></span> 
  
`<simpleTemplateVariable type="variable type of text, link, or picture">`
  
<span data-ttu-id="2a765-125">**listVariable** 类型的模板变量是对象的容器。</span><span class="sxs-lookup"><span data-stu-id="2a765-125">A template variable of the **listVariable** type is a container for objects.</span></span> <span data-ttu-id="2a765-126">它可以包含链接Variable 或 **textVariable** 类型的 (或 **pictureVariable** 类型的) 或图片 (逗号分隔) 。</span><span class="sxs-lookup"><span data-stu-id="2a765-126">It can contain comma-delimited items (of the **linkVariable** or **textVariable** type) or pictures (of the **pictureVariable** type).</span></span> <span data-ttu-id="2a765-127">列表可以包含最多五个链接项、五个文本项或五个图片。</span><span class="sxs-lookup"><span data-stu-id="2a765-127">Lists can contain up to five link items, five text items, or five pictures.</span></span> 
  
<span data-ttu-id="2a765-128">OUTLOOK Social Connector (OSC) Windows 系统区域设置本地化链接或文本列表项。</span><span class="sxs-lookup"><span data-stu-id="2a765-128">The Outlook Social Connector (OSC) localizes link or text list items according to the Windows system locale.</span></span>
  
<span data-ttu-id="2a765-129">若要在活动源项中正确分析和显示图片，必须在列表中包括图片。</span><span class="sxs-lookup"><span data-stu-id="2a765-129">To correctly parse and display pictures in an activity feed item, you must include pictures in a list.</span></span> <span data-ttu-id="2a765-130">所有图片的大小都调整为 52 像素高。</span><span class="sxs-lookup"><span data-stu-id="2a765-130">All pictures are resized to be 52 pixels high.</span></span> <span data-ttu-id="2a765-131">不调整图片的宽度。</span><span class="sxs-lookup"><span data-stu-id="2a765-131">The width of the picture is not resized.</span></span>
  
## <a name="template-variable-elements"></a><span data-ttu-id="2a765-132">模板变量元素</span><span class="sxs-lookup"><span data-stu-id="2a765-132">Template variable elements</span></span>

<span data-ttu-id="2a765-133">本节介绍每种模板变量类型支持的必需元素和可选元素。</span><span class="sxs-lookup"><span data-stu-id="2a765-133">This section covers the required and optional elements supported for each type of template variable.</span></span>
  
### <a name="entityvariable"></a><span data-ttu-id="2a765-134">entityVariable</span><span class="sxs-lookup"><span data-stu-id="2a765-134">entityVariable</span></span>

|<span data-ttu-id="2a765-135">**元素**</span><span class="sxs-lookup"><span data-stu-id="2a765-135">**Element**</span></span>|<span data-ttu-id="2a765-136">**说明**</span><span class="sxs-lookup"><span data-stu-id="2a765-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2a765-137">**name**</span><span class="sxs-lookup"><span data-stu-id="2a765-137">**name**</span></span> <br/> |<span data-ttu-id="2a765-138">变量的名称。</span><span class="sxs-lookup"><span data-stu-id="2a765-138">The name of the variable.</span></span> <span data-ttu-id="2a765-139">必填。</span><span class="sxs-lookup"><span data-stu-id="2a765-139">Required.</span></span>  <br/> |
|<span data-ttu-id="2a765-140">**id**</span><span class="sxs-lookup"><span data-stu-id="2a765-140">**id**</span></span> <br/> |<span data-ttu-id="2a765-141">用户的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2a765-141">The unique ID of the user.</span></span> <span data-ttu-id="2a765-142">必填。</span><span class="sxs-lookup"><span data-stu-id="2a765-142">Required.</span></span>  <br/> |
|<span data-ttu-id="2a765-143">**nameHint**</span><span class="sxs-lookup"><span data-stu-id="2a765-143">**nameHint**</span></span> <br/> |<span data-ttu-id="2a765-144">要显示在源项中的名称。</span><span class="sxs-lookup"><span data-stu-id="2a765-144">The name to be displayed in the feed item.</span></span> <span data-ttu-id="2a765-145">可选。</span><span class="sxs-lookup"><span data-stu-id="2a765-145">Optional.</span></span>  <br/> |
|<span data-ttu-id="2a765-146">**profileUrl**</span><span class="sxs-lookup"><span data-stu-id="2a765-146">**profileUrl**</span></span> <br/> |<span data-ttu-id="2a765-147">人员个人资料的 URL，如果人员姓名存在，则用作源项中人员姓名的超链接。</span><span class="sxs-lookup"><span data-stu-id="2a765-147">The URL of the person's profile that will be used as the hyperlink for the person's name in the feed item, if the person's name is present.</span></span> <span data-ttu-id="2a765-148">可选。</span><span class="sxs-lookup"><span data-stu-id="2a765-148">Optional.</span></span>  <br/> |
|<span data-ttu-id="2a765-149">**emailAddress**</span><span class="sxs-lookup"><span data-stu-id="2a765-149">**emailAddress**</span></span> <br/> |<span data-ttu-id="2a765-150">用于在 Outlook 中更新此人的联系信息的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2a765-150">The email address that is used to update this person's contact information in Outlook.</span></span> <span data-ttu-id="2a765-151">可选。</span><span class="sxs-lookup"><span data-stu-id="2a765-151">Optional.</span></span>  <br/> |
   
### <a name="linkvariable"></a><span data-ttu-id="2a765-152">linkVariable</span><span class="sxs-lookup"><span data-stu-id="2a765-152">linkVariable</span></span>

|<span data-ttu-id="2a765-153">**元素**</span><span class="sxs-lookup"><span data-stu-id="2a765-153">**Element**</span></span>|<span data-ttu-id="2a765-154">**说明**</span><span class="sxs-lookup"><span data-stu-id="2a765-154">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2a765-155">**name**</span><span class="sxs-lookup"><span data-stu-id="2a765-155">**name**</span></span> <br/> |<span data-ttu-id="2a765-156">变量的名称。</span><span class="sxs-lookup"><span data-stu-id="2a765-156">The name of the variable.</span></span> <span data-ttu-id="2a765-157">必填。</span><span class="sxs-lookup"><span data-stu-id="2a765-157">Required.</span></span>  <br/> |
|<span data-ttu-id="2a765-158">**value**</span><span class="sxs-lookup"><span data-stu-id="2a765-158">**value**</span></span> <br/> |<span data-ttu-id="2a765-159">此链接的 URL。</span><span class="sxs-lookup"><span data-stu-id="2a765-159">The URL for this link.</span></span> <span data-ttu-id="2a765-160">必填。</span><span class="sxs-lookup"><span data-stu-id="2a765-160">Required.</span></span>  <br/> |
|<span data-ttu-id="2a765-161">**text**</span><span class="sxs-lookup"><span data-stu-id="2a765-161">**text**</span></span> <br/> |<span data-ttu-id="2a765-162">要显示的链接文本，而不是 URL 本身。</span><span class="sxs-lookup"><span data-stu-id="2a765-162">The link text to display instead of the URL itself.</span></span> <span data-ttu-id="2a765-163">可选。</span><span class="sxs-lookup"><span data-stu-id="2a765-163">Optional.</span></span>  <br/> |
   
### <a name="listvariable"></a><span data-ttu-id="2a765-164">listVariable</span><span class="sxs-lookup"><span data-stu-id="2a765-164">listVariable</span></span>

|<span data-ttu-id="2a765-165">**元素**</span><span class="sxs-lookup"><span data-stu-id="2a765-165">**Element**</span></span>|<span data-ttu-id="2a765-166">**说明**</span><span class="sxs-lookup"><span data-stu-id="2a765-166">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2a765-167">**name**</span><span class="sxs-lookup"><span data-stu-id="2a765-167">**name**</span></span> <br/> |<span data-ttu-id="2a765-168">变量的名称。</span><span class="sxs-lookup"><span data-stu-id="2a765-168">The name of the variable.</span></span> <span data-ttu-id="2a765-169">必填。</span><span class="sxs-lookup"><span data-stu-id="2a765-169">Required.</span></span>  <br/> |
|<span data-ttu-id="2a765-170">**listItems**</span><span class="sxs-lookup"><span data-stu-id="2a765-170">**listItems**</span></span> <br/> |<span data-ttu-id="2a765-171">列表中项的容器。</span><span class="sxs-lookup"><span data-stu-id="2a765-171">A container for items in the list.</span></span> <span data-ttu-id="2a765-172">必填。</span><span class="sxs-lookup"><span data-stu-id="2a765-172">Required.</span></span>  <br/> |
   
### <a name="picturevariable"></a><span data-ttu-id="2a765-173">pictureVariable</span><span class="sxs-lookup"><span data-stu-id="2a765-173">pictureVariable</span></span>

|<span data-ttu-id="2a765-174">**元素**</span><span class="sxs-lookup"><span data-stu-id="2a765-174">**Element**</span></span>|<span data-ttu-id="2a765-175">**说明**</span><span class="sxs-lookup"><span data-stu-id="2a765-175">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2a765-176">**name**</span><span class="sxs-lookup"><span data-stu-id="2a765-176">**name**</span></span> <br/> |<span data-ttu-id="2a765-177">变量的名称。</span><span class="sxs-lookup"><span data-stu-id="2a765-177">The name of the variable.</span></span> <span data-ttu-id="2a765-178">必填。</span><span class="sxs-lookup"><span data-stu-id="2a765-178">Required.</span></span>  <br/> |
|<span data-ttu-id="2a765-179">**value**</span><span class="sxs-lookup"><span data-stu-id="2a765-179">**value**</span></span> <br/> |<span data-ttu-id="2a765-180">图片的 URL。</span><span class="sxs-lookup"><span data-stu-id="2a765-180">The URL for the picture.</span></span> <span data-ttu-id="2a765-181">必填。</span><span class="sxs-lookup"><span data-stu-id="2a765-181">Required.</span></span>  <br/> |
|<span data-ttu-id="2a765-182">**altText**</span><span class="sxs-lookup"><span data-stu-id="2a765-182">**altText**</span></span> <br/> |<span data-ttu-id="2a765-183">为辅助功能和用户将鼠标指针移动到图片上时显示的备用文本。</span><span class="sxs-lookup"><span data-stu-id="2a765-183">The alternate text to display for accessibility and when the user moves the mouse pointer over the picture.</span></span> <span data-ttu-id="2a765-184">可选。</span><span class="sxs-lookup"><span data-stu-id="2a765-184">Optional.</span></span>  <br/> |
|<span data-ttu-id="2a765-185">**href**</span><span class="sxs-lookup"><span data-stu-id="2a765-185">**href**</span></span> <br/> |<span data-ttu-id="2a765-186">当用户单击图片时使用的超链接（如果所需目标不是 value 元素指定的 **图片 URL）。**</span><span class="sxs-lookup"><span data-stu-id="2a765-186">The hyperlink to use when the user clicks the picture, if the desired target is not the picture URL specified by the **value** element.</span></span> <span data-ttu-id="2a765-187">可选。</span><span class="sxs-lookup"><span data-stu-id="2a765-187">Optional.</span></span>  <br/> |
   
### <a name="publishervariable"></a><span data-ttu-id="2a765-188">publisherVariable</span><span class="sxs-lookup"><span data-stu-id="2a765-188">publisherVariable</span></span>

|<span data-ttu-id="2a765-189">**元素**</span><span class="sxs-lookup"><span data-stu-id="2a765-189">**Element**</span></span>|<span data-ttu-id="2a765-190">**说明**</span><span class="sxs-lookup"><span data-stu-id="2a765-190">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2a765-191">**name**</span><span class="sxs-lookup"><span data-stu-id="2a765-191">**name**</span></span> <br/> |<span data-ttu-id="2a765-192">变量的名称。</span><span class="sxs-lookup"><span data-stu-id="2a765-192">The name of the variable.</span></span> <span data-ttu-id="2a765-193">必填。</span><span class="sxs-lookup"><span data-stu-id="2a765-193">Required.</span></span>  <br/> |
|<span data-ttu-id="2a765-194">**id**</span><span class="sxs-lookup"><span data-stu-id="2a765-194">**id**</span></span> <br/> |<span data-ttu-id="2a765-195">用户的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2a765-195">The unique ID of the user.</span></span> <span data-ttu-id="2a765-196">必填。</span><span class="sxs-lookup"><span data-stu-id="2a765-196">Required.</span></span>  <br/> |
|<span data-ttu-id="2a765-197">**nameHint**</span><span class="sxs-lookup"><span data-stu-id="2a765-197">**nameHint**</span></span> <br/> |<span data-ttu-id="2a765-198">要显示在源项中的名称。</span><span class="sxs-lookup"><span data-stu-id="2a765-198">The name to be displayed in the feed item.</span></span> <span data-ttu-id="2a765-199">可选。</span><span class="sxs-lookup"><span data-stu-id="2a765-199">Optional.</span></span>  <br/> |
|<span data-ttu-id="2a765-200">**profileUrl**</span><span class="sxs-lookup"><span data-stu-id="2a765-200">**profileUrl**</span></span> <br/> |<span data-ttu-id="2a765-201">人员个人资料的 URL，如果人员姓名存在，则用作源项中人员姓名的超链接。</span><span class="sxs-lookup"><span data-stu-id="2a765-201">The URL of the person's profile that will be used as the hyperlink for the person's name in the feed item, if the person's name is present.</span></span> <span data-ttu-id="2a765-202">可选。</span><span class="sxs-lookup"><span data-stu-id="2a765-202">Optional.</span></span>  <br/> |
|<span data-ttu-id="2a765-203">**emailAddress**</span><span class="sxs-lookup"><span data-stu-id="2a765-203">**emailAddress**</span></span> <br/> |<span data-ttu-id="2a765-204">用于在 Outlook 中更新此人的联系信息的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2a765-204">The email address that is used to update this person's contact information in Outlook.</span></span> <span data-ttu-id="2a765-205">可选。</span><span class="sxs-lookup"><span data-stu-id="2a765-205">Optional.</span></span>  <br/> |
   
### <a name="textvariable"></a><span data-ttu-id="2a765-206">textVariable</span><span class="sxs-lookup"><span data-stu-id="2a765-206">textVariable</span></span>

|<span data-ttu-id="2a765-207">**元素**</span><span class="sxs-lookup"><span data-stu-id="2a765-207">**Element**</span></span>|<span data-ttu-id="2a765-208">**说明**</span><span class="sxs-lookup"><span data-stu-id="2a765-208">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2a765-209">**name**</span><span class="sxs-lookup"><span data-stu-id="2a765-209">**name**</span></span> <br/> |<span data-ttu-id="2a765-210">变量的名称。</span><span class="sxs-lookup"><span data-stu-id="2a765-210">The name of the variable.</span></span> <span data-ttu-id="2a765-211">必填。</span><span class="sxs-lookup"><span data-stu-id="2a765-211">Required.</span></span>  <br/> |
|<span data-ttu-id="2a765-212">**value**</span><span class="sxs-lookup"><span data-stu-id="2a765-212">**value**</span></span> <br/> |<span data-ttu-id="2a765-213">要显示的文本。</span><span class="sxs-lookup"><span data-stu-id="2a765-213">The text to display.</span></span> <span data-ttu-id="2a765-214">可选。</span><span class="sxs-lookup"><span data-stu-id="2a765-214">Optional.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="2a765-215">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a765-215">See also</span></span>

- [<span data-ttu-id="2a765-216">活动源项的 XML 概述</span><span class="sxs-lookup"><span data-stu-id="2a765-216">Overview of XML for an Activity Feed Item</span></span>](overview-of-xml-for-an-activity-feed-item.md)  
- [<span data-ttu-id="2a765-217">activityDetails 元素</span><span class="sxs-lookup"><span data-stu-id="2a765-217">activityDetails Element</span></span>](activitydetails-element.md)  
- [<span data-ttu-id="2a765-218">activityTemplateContainer 元素</span><span class="sxs-lookup"><span data-stu-id="2a765-218">activityTemplateContainer Element</span></span>](activitytemplatecontainer-element.md)  
- [<span data-ttu-id="2a765-219">正确显示活动指南</span><span class="sxs-lookup"><span data-stu-id="2a765-219">Guidelines for Properly Displaying Activities</span></span>](guidelines-for-properly-displaying-activities.md)  
- [<span data-ttu-id="2a765-220">活动的 XML</span><span class="sxs-lookup"><span data-stu-id="2a765-220">XML for Activities</span></span>](xml-for-activities.md)  
- [<span data-ttu-id="2a765-221">Outlook Social Connector 提供程序 XML 架构</span><span class="sxs-lookup"><span data-stu-id="2a765-221">Outlook Social Connector Provider XML Schema</span></span>](outlook-social-connector-provider-xml-schema.md)
- [<span data-ttu-id="2a765-222">使用 OSC XML 架构开发提供程序</span><span class="sxs-lookup"><span data-stu-id="2a765-222">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)

