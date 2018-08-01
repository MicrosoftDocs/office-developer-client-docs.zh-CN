---
title: 模板变量
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6f8f6af2-c7fa-4135-9532-7af5fc643b0d
description: 模板变量 （由 templateVariable 元素） 的实例指定活动源中活动模板的项目的数据。
ms.openlocfilehash: 99f4c2de586447fb0361e528bcd33d62b79e0fb1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779352"
---
# <a name="template-variables"></a><span data-ttu-id="e95c0-103">模板变量</span><span class="sxs-lookup"><span data-stu-id="e95c0-103">Template variables</span></span>

<span data-ttu-id="e95c0-104">模板变量 （由**templateVariable**元素） 的实例指定活动源中活动模板的项目的数据。</span><span class="sxs-lookup"><span data-stu-id="e95c0-104">Instances of template variables (represented by a **templateVariable** element) specify the data of an activity feed item in an activity template.</span></span> 
  
<span data-ttu-id="e95c0-105">示例活动的源 XML，请参阅[活动源 XML 示例](activity-feed-xml-example.md)。</span><span class="sxs-lookup"><span data-stu-id="e95c0-105">For an example of activity feed XML, see [Activity Feed XML Example](activity-feed-xml-example.md).</span></span>

<span data-ttu-id="e95c0-106">下表显示了每个相应的 XML 枚举值由表示支持的模板变量的类型。</span><span class="sxs-lookup"><span data-stu-id="e95c0-106">The following table shows the types of supported template variables, each represented by the corresponding XML enumeration value.</span></span>
  
|<span data-ttu-id="e95c0-107">**模板变量的类型**</span><span class="sxs-lookup"><span data-stu-id="e95c0-107">**Type of template variable**</span></span>|<span data-ttu-id="e95c0-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="e95c0-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e95c0-109">**entityVariable**</span><span class="sxs-lookup"><span data-stu-id="e95c0-109">**entityVariable**</span></span> <br/> |<span data-ttu-id="e95c0-110">人员、 组或事物。</span><span class="sxs-lookup"><span data-stu-id="e95c0-110">A person, group, or thing.</span></span>  <br/> |
|<span data-ttu-id="e95c0-111">**linkVariable**</span><span class="sxs-lookup"><span data-stu-id="e95c0-111">**linkVariable**</span></span> <br/> |<span data-ttu-id="e95c0-112">链接。</span><span class="sxs-lookup"><span data-stu-id="e95c0-112">A link.</span></span>  <br/> |
|<span data-ttu-id="e95c0-113">**listVariable**</span><span class="sxs-lookup"><span data-stu-id="e95c0-113">**listVariable**</span></span> <br/> |<span data-ttu-id="e95c0-114">一组对象。</span><span class="sxs-lookup"><span data-stu-id="e95c0-114">A group of objects.</span></span>  <br/> |
|<span data-ttu-id="e95c0-115">**pictureVariable**</span><span class="sxs-lookup"><span data-stu-id="e95c0-115">**pictureVariable**</span></span> <br/> |<span data-ttu-id="e95c0-116">图片。</span><span class="sxs-lookup"><span data-stu-id="e95c0-116">A picture.</span></span>  <br/> |
|<span data-ttu-id="e95c0-117">**publisherVariable**</span><span class="sxs-lookup"><span data-stu-id="e95c0-117">**publisherVariable**</span></span> <br/> |<span data-ttu-id="e95c0-118">发布者的活动订阅源。</span><span class="sxs-lookup"><span data-stu-id="e95c0-118">The publisher of the activity feed item.</span></span>  <br/> |
|<span data-ttu-id="e95c0-119">**textVariable**</span><span class="sxs-lookup"><span data-stu-id="e95c0-119">**textVariable**</span></span> <br/> |<span data-ttu-id="e95c0-120">文本块。</span><span class="sxs-lookup"><span data-stu-id="e95c0-120">A block of text.</span></span>  <br/> |
   
<span data-ttu-id="e95c0-121">每种类型的模板变量需要元素指定有关该变量的数据。</span><span class="sxs-lookup"><span data-stu-id="e95c0-121">Each type of template variable has required elements to specify the data about that variable.</span></span> <span data-ttu-id="e95c0-122">模板变量，如下所示指定：</span><span class="sxs-lookup"><span data-stu-id="e95c0-122">Template variables are specified as follows:</span></span>
  
`<templateVariable type="variable type">`
  
## <a name="list-template-variable"></a><span data-ttu-id="e95c0-123">列表模板变量</span><span class="sxs-lookup"><span data-stu-id="e95c0-123">List template variable</span></span>

<span data-ttu-id="e95c0-124">您可以指定模板变量包含在列表 （分隔的**listVariable**和**listItems**元素），如下所示：</span><span class="sxs-lookup"><span data-stu-id="e95c0-124">You can specify template variables that are contained within a list (delimited by the **listVariable** and **listItems** elements) as follows:</span></span> 
  
`<simpleTemplateVariable type="variable type of text, link, or picture">`
  
<span data-ttu-id="e95c0-125">**ListVariable**类型的模板变量是对象的容器。</span><span class="sxs-lookup"><span data-stu-id="e95c0-125">A template variable of the **listVariable** type is a container for objects.</span></span> <span data-ttu-id="e95c0-126">它可以包含 （ **linkVariable**或**textVariable**类型） 的逗号分隔的项目或 （ **pictureVariable**类型） 的图片。</span><span class="sxs-lookup"><span data-stu-id="e95c0-126">It can contain comma-delimited items (of the **linkVariable** or **textVariable** type) or pictures (of the **pictureVariable** type).</span></span> <span data-ttu-id="e95c0-127">列表可以包含最多五个链接项目、 五个文本项目或五个图片。</span><span class="sxs-lookup"><span data-stu-id="e95c0-127">Lists can contain up to five link items, five text items, or five pictures.</span></span> 
  
<span data-ttu-id="e95c0-128">Outlook Social Connector (OSC) 本地化链接或文本根据 Windows 系统区域设置的列表项。</span><span class="sxs-lookup"><span data-stu-id="e95c0-128">The Outlook Social Connector (OSC) localizes link or text list items according to the Windows system locale.</span></span>
  
<span data-ttu-id="e95c0-129">要正确分析，并在活动源项目中显示图片，您必须包括列表中的图片。</span><span class="sxs-lookup"><span data-stu-id="e95c0-129">To correctly parse and display pictures in an activity feed item, you must include pictures in a list.</span></span> <span data-ttu-id="e95c0-130">所有图片调整都大小为 52 像素高。</span><span class="sxs-lookup"><span data-stu-id="e95c0-130">All pictures are resized to be 52 pixels high.</span></span> <span data-ttu-id="e95c0-131">图片的宽度不调整大小。</span><span class="sxs-lookup"><span data-stu-id="e95c0-131">The width of the picture is not resized.</span></span>
  
## <a name="template-variable-elements"></a><span data-ttu-id="e95c0-132">模板变量元素</span><span class="sxs-lookup"><span data-stu-id="e95c0-132">Template variable elements</span></span>

<span data-ttu-id="e95c0-133">本节介绍支持的每种类型的模板变量的必需的和可选元素。</span><span class="sxs-lookup"><span data-stu-id="e95c0-133">This section covers the required and optional elements supported for each type of template variable.</span></span>
  
### <a name="entityvariable"></a><span data-ttu-id="e95c0-134">entityVariable</span><span class="sxs-lookup"><span data-stu-id="e95c0-134">entityVariable</span></span>

|<span data-ttu-id="e95c0-135">**元素**</span><span class="sxs-lookup"><span data-stu-id="e95c0-135">**Element**</span></span>|<span data-ttu-id="e95c0-136">**说明**</span><span class="sxs-lookup"><span data-stu-id="e95c0-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e95c0-137">**name**</span><span class="sxs-lookup"><span data-stu-id="e95c0-137">**name**</span></span> <br/> |<span data-ttu-id="e95c0-138">变量的名称。</span><span class="sxs-lookup"><span data-stu-id="e95c0-138">The name of the variable.</span></span> <span data-ttu-id="e95c0-139">必需。</span><span class="sxs-lookup"><span data-stu-id="e95c0-139">Required.</span></span>  <br/> |
|<span data-ttu-id="e95c0-140">**id**</span><span class="sxs-lookup"><span data-stu-id="e95c0-140">**id**</span></span> <br/> |<span data-ttu-id="e95c0-141">用户的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="e95c0-141">The unique ID of the user.</span></span> <span data-ttu-id="e95c0-142">必需。</span><span class="sxs-lookup"><span data-stu-id="e95c0-142">Required.</span></span>  <br/> |
|<span data-ttu-id="e95c0-143">**nameHint**</span><span class="sxs-lookup"><span data-stu-id="e95c0-143">**nameHint**</span></span> <br/> |<span data-ttu-id="e95c0-144">要馈送项目中显示的名称。</span><span class="sxs-lookup"><span data-stu-id="e95c0-144">The name to be displayed in the feed item.</span></span> <span data-ttu-id="e95c0-145">可选。</span><span class="sxs-lookup"><span data-stu-id="e95c0-145">Optional.</span></span>  <br/> |
|<span data-ttu-id="e95c0-146">**profileUrl**</span><span class="sxs-lookup"><span data-stu-id="e95c0-146">**profileUrl**</span></span> <br/> |<span data-ttu-id="e95c0-147">将用于为超链接中的订阅源的项目，此人的姓名如果存在此人的姓名的人的配置文件的 URL。</span><span class="sxs-lookup"><span data-stu-id="e95c0-147">The URL of the person's profile that will be used as the hyperlink for the person's name in the feed item, if the person's name is present.</span></span> <span data-ttu-id="e95c0-148">可选。</span><span class="sxs-lookup"><span data-stu-id="e95c0-148">Optional.</span></span>  <br/> |
|<span data-ttu-id="e95c0-149">**emailAddress**</span><span class="sxs-lookup"><span data-stu-id="e95c0-149">**emailAddress**</span></span> <br/> |<span data-ttu-id="e95c0-150">用于更新此人的联系人信息在 Outlook 中的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e95c0-150">The email address that is used to update this person's contact information in Outlook.</span></span> <span data-ttu-id="e95c0-151">可选。</span><span class="sxs-lookup"><span data-stu-id="e95c0-151">Optional.</span></span>  <br/> |
   
### <a name="linkvariable"></a><span data-ttu-id="e95c0-152">linkVariable</span><span class="sxs-lookup"><span data-stu-id="e95c0-152">linkVariable</span></span>

|<span data-ttu-id="e95c0-153">**元素**</span><span class="sxs-lookup"><span data-stu-id="e95c0-153">**Element**</span></span>|<span data-ttu-id="e95c0-154">**说明**</span><span class="sxs-lookup"><span data-stu-id="e95c0-154">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e95c0-155">**name**</span><span class="sxs-lookup"><span data-stu-id="e95c0-155">**name**</span></span> <br/> |<span data-ttu-id="e95c0-156">变量的名称。</span><span class="sxs-lookup"><span data-stu-id="e95c0-156">The name of the variable.</span></span> <span data-ttu-id="e95c0-157">必需。</span><span class="sxs-lookup"><span data-stu-id="e95c0-157">Required.</span></span>  <br/> |
|<span data-ttu-id="e95c0-158">**value**</span><span class="sxs-lookup"><span data-stu-id="e95c0-158">**value**</span></span> <br/> |<span data-ttu-id="e95c0-159">此链接的 URL。</span><span class="sxs-lookup"><span data-stu-id="e95c0-159">The URL for this link.</span></span> <span data-ttu-id="e95c0-160">必需。</span><span class="sxs-lookup"><span data-stu-id="e95c0-160">Required.</span></span>  <br/> |
|<span data-ttu-id="e95c0-161">**text**</span><span class="sxs-lookup"><span data-stu-id="e95c0-161">**text**</span></span> <br/> |<span data-ttu-id="e95c0-162">要显示而不是该 URL 本身的链接文本。</span><span class="sxs-lookup"><span data-stu-id="e95c0-162">The link text to display instead of the URL itself.</span></span> <span data-ttu-id="e95c0-163">可选。</span><span class="sxs-lookup"><span data-stu-id="e95c0-163">Optional.</span></span>  <br/> |
   
### <a name="listvariable"></a><span data-ttu-id="e95c0-164">listVariable</span><span class="sxs-lookup"><span data-stu-id="e95c0-164">listVariable</span></span>

|<span data-ttu-id="e95c0-165">**元素**</span><span class="sxs-lookup"><span data-stu-id="e95c0-165">**Element**</span></span>|<span data-ttu-id="e95c0-166">**说明**</span><span class="sxs-lookup"><span data-stu-id="e95c0-166">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e95c0-167">**name**</span><span class="sxs-lookup"><span data-stu-id="e95c0-167">**name**</span></span> <br/> |<span data-ttu-id="e95c0-168">变量的名称。</span><span class="sxs-lookup"><span data-stu-id="e95c0-168">The name of the variable.</span></span> <span data-ttu-id="e95c0-169">必需。</span><span class="sxs-lookup"><span data-stu-id="e95c0-169">Required.</span></span>  <br/> |
|<span data-ttu-id="e95c0-170">**列表项目**</span><span class="sxs-lookup"><span data-stu-id="e95c0-170">**listItems**</span></span> <br/> |<span data-ttu-id="e95c0-171">在列表中的项的容器。</span><span class="sxs-lookup"><span data-stu-id="e95c0-171">A container for items in the list.</span></span> <span data-ttu-id="e95c0-172">必需。</span><span class="sxs-lookup"><span data-stu-id="e95c0-172">Required.</span></span>  <br/> |
   
### <a name="picturevariable"></a><span data-ttu-id="e95c0-173">pictureVariable</span><span class="sxs-lookup"><span data-stu-id="e95c0-173">pictureVariable</span></span>

|<span data-ttu-id="e95c0-174">**元素**</span><span class="sxs-lookup"><span data-stu-id="e95c0-174">**Element**</span></span>|<span data-ttu-id="e95c0-175">**说明**</span><span class="sxs-lookup"><span data-stu-id="e95c0-175">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e95c0-176">**name**</span><span class="sxs-lookup"><span data-stu-id="e95c0-176">**name**</span></span> <br/> |<span data-ttu-id="e95c0-177">变量的名称。</span><span class="sxs-lookup"><span data-stu-id="e95c0-177">The name of the variable.</span></span> <span data-ttu-id="e95c0-178">必需。</span><span class="sxs-lookup"><span data-stu-id="e95c0-178">Required.</span></span>  <br/> |
|<span data-ttu-id="e95c0-179">**value**</span><span class="sxs-lookup"><span data-stu-id="e95c0-179">**value**</span></span> <br/> |<span data-ttu-id="e95c0-180">图片 URL。</span><span class="sxs-lookup"><span data-stu-id="e95c0-180">The URL for the picture.</span></span> <span data-ttu-id="e95c0-181">必需。</span><span class="sxs-lookup"><span data-stu-id="e95c0-181">Required.</span></span>  <br/> |
|<span data-ttu-id="e95c0-182">**altText**</span><span class="sxs-lookup"><span data-stu-id="e95c0-182">**altText**</span></span> <br/> |<span data-ttu-id="e95c0-183">备用辅助功能和用户将鼠标指针移到图片上时显示的文本。</span><span class="sxs-lookup"><span data-stu-id="e95c0-183">The alternate text to display for accessibility and when the user moves the mouse pointer over the picture.</span></span> <span data-ttu-id="e95c0-184">可选。</span><span class="sxs-lookup"><span data-stu-id="e95c0-184">Optional.</span></span>  <br/> |
|<span data-ttu-id="e95c0-185">**href**</span><span class="sxs-lookup"><span data-stu-id="e95c0-185">**href**</span></span> <br/> |<span data-ttu-id="e95c0-186">若要使用当用户单击该图片，如果所需的目标不是**值**元素所指定的图片 URL 超链接。</span><span class="sxs-lookup"><span data-stu-id="e95c0-186">The hyperlink to use when the user clicks the picture, if the desired target is not the picture URL specified by the **value** element.</span></span> <span data-ttu-id="e95c0-187">可选。</span><span class="sxs-lookup"><span data-stu-id="e95c0-187">Optional.</span></span>  <br/> |
   
### <a name="publishervariable"></a><span data-ttu-id="e95c0-188">publisherVariable</span><span class="sxs-lookup"><span data-stu-id="e95c0-188">publisherVariable</span></span>

|<span data-ttu-id="e95c0-189">**元素**</span><span class="sxs-lookup"><span data-stu-id="e95c0-189">**Element**</span></span>|<span data-ttu-id="e95c0-190">**说明**</span><span class="sxs-lookup"><span data-stu-id="e95c0-190">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e95c0-191">**name**</span><span class="sxs-lookup"><span data-stu-id="e95c0-191">**name**</span></span> <br/> |<span data-ttu-id="e95c0-192">变量的名称。</span><span class="sxs-lookup"><span data-stu-id="e95c0-192">The name of the variable.</span></span> <span data-ttu-id="e95c0-193">必需。</span><span class="sxs-lookup"><span data-stu-id="e95c0-193">Required.</span></span>  <br/> |
|<span data-ttu-id="e95c0-194">**id**</span><span class="sxs-lookup"><span data-stu-id="e95c0-194">**id**</span></span> <br/> |<span data-ttu-id="e95c0-195">用户的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="e95c0-195">The unique ID of the user.</span></span> <span data-ttu-id="e95c0-196">必需。</span><span class="sxs-lookup"><span data-stu-id="e95c0-196">Required.</span></span>  <br/> |
|<span data-ttu-id="e95c0-197">**nameHint**</span><span class="sxs-lookup"><span data-stu-id="e95c0-197">**nameHint**</span></span> <br/> |<span data-ttu-id="e95c0-198">要馈送项目中显示的名称。</span><span class="sxs-lookup"><span data-stu-id="e95c0-198">The name to be displayed in the feed item.</span></span> <span data-ttu-id="e95c0-199">可选。</span><span class="sxs-lookup"><span data-stu-id="e95c0-199">Optional.</span></span>  <br/> |
|<span data-ttu-id="e95c0-200">**profileUrl**</span><span class="sxs-lookup"><span data-stu-id="e95c0-200">**profileUrl**</span></span> <br/> |<span data-ttu-id="e95c0-201">将用于为超链接中的订阅源的项目，此人的姓名如果存在此人的姓名的人的配置文件的 URL。</span><span class="sxs-lookup"><span data-stu-id="e95c0-201">The URL of the person's profile that will be used as the hyperlink for the person's name in the feed item, if the person's name is present.</span></span> <span data-ttu-id="e95c0-202">可选。</span><span class="sxs-lookup"><span data-stu-id="e95c0-202">Optional.</span></span>  <br/> |
|<span data-ttu-id="e95c0-203">**emailAddress**</span><span class="sxs-lookup"><span data-stu-id="e95c0-203">**emailAddress**</span></span> <br/> |<span data-ttu-id="e95c0-204">用于更新此人的联系人信息在 Outlook 中的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e95c0-204">The email address that is used to update this person's contact information in Outlook.</span></span> <span data-ttu-id="e95c0-205">可选。</span><span class="sxs-lookup"><span data-stu-id="e95c0-205">Optional.</span></span>  <br/> |
   
### <a name="textvariable"></a><span data-ttu-id="e95c0-206">textVariable</span><span class="sxs-lookup"><span data-stu-id="e95c0-206">textVariable</span></span>

|<span data-ttu-id="e95c0-207">**元素**</span><span class="sxs-lookup"><span data-stu-id="e95c0-207">**Element**</span></span>|<span data-ttu-id="e95c0-208">**说明**</span><span class="sxs-lookup"><span data-stu-id="e95c0-208">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e95c0-209">**name**</span><span class="sxs-lookup"><span data-stu-id="e95c0-209">**name**</span></span> <br/> |<span data-ttu-id="e95c0-210">变量的名称。</span><span class="sxs-lookup"><span data-stu-id="e95c0-210">The name of the variable.</span></span> <span data-ttu-id="e95c0-211">必需。</span><span class="sxs-lookup"><span data-stu-id="e95c0-211">Required.</span></span>  <br/> |
|<span data-ttu-id="e95c0-212">**value**</span><span class="sxs-lookup"><span data-stu-id="e95c0-212">**value**</span></span> <br/> |<span data-ttu-id="e95c0-213">要显示的文本。</span><span class="sxs-lookup"><span data-stu-id="e95c0-213">The text to display.</span></span> <span data-ttu-id="e95c0-214">可选。</span><span class="sxs-lookup"><span data-stu-id="e95c0-214">Optional.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e95c0-215">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e95c0-215">See also</span></span>

- [<span data-ttu-id="e95c0-216">概述 XML 的活动订阅源</span><span class="sxs-lookup"><span data-stu-id="e95c0-216">Overview of XML for an Activity Feed Item</span></span>](overview-of-xml-for-an-activity-feed-item.md)  
- [<span data-ttu-id="e95c0-217">activityDetails 元素</span><span class="sxs-lookup"><span data-stu-id="e95c0-217">activityDetails Element</span></span>](activitydetails-element.md)  
- [<span data-ttu-id="e95c0-218">activityTemplateContainer 元素</span><span class="sxs-lookup"><span data-stu-id="e95c0-218">activityTemplateContainer Element</span></span>](activitytemplatecontainer-element.md)  
- [<span data-ttu-id="e95c0-219">正确显示活动的指南</span><span class="sxs-lookup"><span data-stu-id="e95c0-219">Guidelines for Properly Displaying Activities</span></span>](guidelines-for-properly-displaying-activities.md)  
- [<span data-ttu-id="e95c0-220">活动的 XML</span><span class="sxs-lookup"><span data-stu-id="e95c0-220">XML for Activities</span></span>](xml-for-activities.md)  
- [<span data-ttu-id="e95c0-221">Outlook Social Connector 提供程序的 XML 架构</span><span class="sxs-lookup"><span data-stu-id="e95c0-221">Outlook Social Connector Provider XML Schema</span></span>](outlook-social-connector-provider-xml-schema.md)
- [<span data-ttu-id="e95c0-222">开发 OSC XML 架构的提供程序</span><span class="sxs-lookup"><span data-stu-id="e95c0-222">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)

