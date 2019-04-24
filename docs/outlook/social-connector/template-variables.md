---
title: 模板变量
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6f8f6af2-c7fa-4135-9532-7af5fc643b0d
description: template 变量的实例 (由 templateVariable 元素表示) 指定活动模板中的活动源项的数据。
ms.openlocfilehash: 9b37665488f0f1e2bd205fb7d4a5d2201697d7c8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329174"
---
# <a name="template-variables"></a><span data-ttu-id="ed5b6-103">模板变量</span><span class="sxs-lookup"><span data-stu-id="ed5b6-103">Template variables</span></span>

<span data-ttu-id="ed5b6-104">template 变量的实例 (由**templateVariable**元素表示) 指定活动模板中的活动源项的数据。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-104">Instances of template variables (represented by a **templateVariable** element) specify the data of an activity feed item in an activity template.</span></span> 
  
<span data-ttu-id="ed5b6-105">有关活动源 xml 的示例, 请参阅[活动源 xml 示例](activity-feed-xml-example.md)。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-105">For an example of activity feed XML, see [Activity Feed XML Example](activity-feed-xml-example.md).</span></span>

<span data-ttu-id="ed5b6-106">下表显示了受支持的模板变量的类型, 每个都由相应的 XML 枚举值表示。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-106">The following table shows the types of supported template variables, each represented by the corresponding XML enumeration value.</span></span>
  
|<span data-ttu-id="ed5b6-107">**模板变量的类型**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-107">**Type of template variable**</span></span>|<span data-ttu-id="ed5b6-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ed5b6-109">**entityVariable**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-109">**entityVariable**</span></span> <br/> |<span data-ttu-id="ed5b6-110">个人、组或事物。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-110">A person, group, or thing.</span></span>  <br/> |
|<span data-ttu-id="ed5b6-111">**linkVariable**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-111">**linkVariable**</span></span> <br/> |<span data-ttu-id="ed5b6-112">一个链接。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-112">A link.</span></span>  <br/> |
|<span data-ttu-id="ed5b6-113">**listVariable**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-113">**listVariable**</span></span> <br/> |<span data-ttu-id="ed5b6-114">一组对象。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-114">A group of objects.</span></span>  <br/> |
|<span data-ttu-id="ed5b6-115">**pictureVariable**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-115">**pictureVariable**</span></span> <br/> |<span data-ttu-id="ed5b6-116">图片。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-116">A picture.</span></span>  <br/> |
|<span data-ttu-id="ed5b6-117">**publisherVariable**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-117">**publisherVariable**</span></span> <br/> |<span data-ttu-id="ed5b6-118">活动源项目的发布者。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-118">The publisher of the activity feed item.</span></span>  <br/> |
|<span data-ttu-id="ed5b6-119">**textVariable**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-119">**textVariable**</span></span> <br/> |<span data-ttu-id="ed5b6-120">文本块。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-120">A block of text.</span></span>  <br/> |
   
<span data-ttu-id="ed5b6-121">每种类型的模板变量都具有指定有关该变量的数据所需的元素。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-121">Each type of template variable has required elements to specify the data about that variable.</span></span> <span data-ttu-id="ed5b6-122">模板变量的指定如下所示:</span><span class="sxs-lookup"><span data-stu-id="ed5b6-122">Template variables are specified as follows:</span></span>
  
`<templateVariable type="variable type">`
  
## <a name="list-template-variable"></a><span data-ttu-id="ed5b6-123">列表模板变量</span><span class="sxs-lookup"><span data-stu-id="ed5b6-123">List template variable</span></span>

<span data-ttu-id="ed5b6-124">您可以指定列表中包含的模板变量 (由**listVariable**和**listItems**元素分隔), 如下所示:</span><span class="sxs-lookup"><span data-stu-id="ed5b6-124">You can specify template variables that are contained within a list (delimited by the **listVariable** and **listItems** elements) as follows:</span></span> 
  
`<simpleTemplateVariable type="variable type of text, link, or picture">`
  
<span data-ttu-id="ed5b6-125">**listVariable**类型的模板变量是对象的容器。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-125">A template variable of the **listVariable** type is a container for objects.</span></span> <span data-ttu-id="ed5b6-126">它可以包含以逗号分隔的项目 ( **linkVariable**或**textVariable**类型) 或图片 (属于**pictureVariable**类型)。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-126">It can contain comma-delimited items (of the **linkVariable** or **textVariable** type) or pictures (of the **pictureVariable** type).</span></span> <span data-ttu-id="ed5b6-127">列表最长可包含五个链接项目、五个文本项目或五个图片。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-127">Lists can contain up to five link items, five text items, or five pictures.</span></span> 
  
<span data-ttu-id="ed5b6-128">Outlook Social Connector (.osc) 根据 Windows 系统区域设置对链接或文本列表项进行本地化。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-128">The Outlook Social Connector (OSC) localizes link or text list items according to the Windows system locale.</span></span>
  
<span data-ttu-id="ed5b6-129">若要在活动源项目中正确分析和显示图片, 必须在列表中包含图片。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-129">To correctly parse and display pictures in an activity feed item, you must include pictures in a list.</span></span> <span data-ttu-id="ed5b6-130">所有图片的大小均调整为52像素高。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-130">All pictures are resized to be 52 pixels high.</span></span> <span data-ttu-id="ed5b6-131">图片的宽度不调整大小。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-131">The width of the picture is not resized.</span></span>
  
## <a name="template-variable-elements"></a><span data-ttu-id="ed5b6-132">模板变量元素</span><span class="sxs-lookup"><span data-stu-id="ed5b6-132">Template variable elements</span></span>

<span data-ttu-id="ed5b6-133">本节介绍每种类型的模板变量支持的必需和可选元素。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-133">This section covers the required and optional elements supported for each type of template variable.</span></span>
  
### <a name="entityvariable"></a><span data-ttu-id="ed5b6-134">entityVariable</span><span class="sxs-lookup"><span data-stu-id="ed5b6-134">entityVariable</span></span>

|<span data-ttu-id="ed5b6-135">**元素**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-135">**Element**</span></span>|<span data-ttu-id="ed5b6-136">**说明**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ed5b6-137">**name**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-137">**name**</span></span> <br/> |<span data-ttu-id="ed5b6-138">变量的名称。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-138">The name of the variable.</span></span> <span data-ttu-id="ed5b6-139">必需。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-139">Required.</span></span>  <br/> |
|<span data-ttu-id="ed5b6-140">**id**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-140">**id**</span></span> <br/> |<span data-ttu-id="ed5b6-141">用户的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-141">The unique ID of the user.</span></span> <span data-ttu-id="ed5b6-142">必需。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-142">Required.</span></span>  <br/> |
|<span data-ttu-id="ed5b6-143">**nameHint**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-143">**nameHint**</span></span> <br/> |<span data-ttu-id="ed5b6-144">要显示在订阅源项中的名称。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-144">The name to be displayed in the feed item.</span></span> <span data-ttu-id="ed5b6-145">可选。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-145">Optional.</span></span>  <br/> |
|<span data-ttu-id="ed5b6-146">**profileUrl**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-146">**profileUrl**</span></span> <br/> |<span data-ttu-id="ed5b6-147">个人个人资料的 URL, 如果此人的姓名存在, 将用作订阅源项目中人员姓名的超链接。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-147">The URL of the person's profile that will be used as the hyperlink for the person's name in the feed item, if the person's name is present.</span></span> <span data-ttu-id="ed5b6-148">可选。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-148">Optional.</span></span>  <br/> |
|<span data-ttu-id="ed5b6-149">**emailAddress**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-149">**emailAddress**</span></span> <br/> |<span data-ttu-id="ed5b6-150">用于在 Outlook 中更新此人的联系人信息的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-150">The email address that is used to update this person's contact information in Outlook.</span></span> <span data-ttu-id="ed5b6-151">可选。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-151">Optional.</span></span>  <br/> |
   
### <a name="linkvariable"></a><span data-ttu-id="ed5b6-152">linkVariable</span><span class="sxs-lookup"><span data-stu-id="ed5b6-152">linkVariable</span></span>

|<span data-ttu-id="ed5b6-153">**元素**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-153">**Element**</span></span>|<span data-ttu-id="ed5b6-154">**说明**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-154">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ed5b6-155">**name**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-155">**name**</span></span> <br/> |<span data-ttu-id="ed5b6-156">变量的名称。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-156">The name of the variable.</span></span> <span data-ttu-id="ed5b6-157">必需。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-157">Required.</span></span>  <br/> |
|<span data-ttu-id="ed5b6-158">**value**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-158">**value**</span></span> <br/> |<span data-ttu-id="ed5b6-159">此链接的 URL。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-159">The URL for this link.</span></span> <span data-ttu-id="ed5b6-160">必需。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-160">Required.</span></span>  <br/> |
|<span data-ttu-id="ed5b6-161">**text**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-161">**text**</span></span> <br/> |<span data-ttu-id="ed5b6-162">显示的链接文本, 而不是 URL 本身。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-162">The link text to display instead of the URL itself.</span></span> <span data-ttu-id="ed5b6-163">可选。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-163">Optional.</span></span>  <br/> |
   
### <a name="listvariable"></a><span data-ttu-id="ed5b6-164">listVariable</span><span class="sxs-lookup"><span data-stu-id="ed5b6-164">listVariable</span></span>

|<span data-ttu-id="ed5b6-165">**元素**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-165">**Element**</span></span>|<span data-ttu-id="ed5b6-166">**说明**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-166">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ed5b6-167">**name**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-167">**name**</span></span> <br/> |<span data-ttu-id="ed5b6-168">变量的名称。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-168">The name of the variable.</span></span> <span data-ttu-id="ed5b6-169">必需。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-169">Required.</span></span>  <br/> |
|<span data-ttu-id="ed5b6-170">**listItems**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-170">**listItems**</span></span> <br/> |<span data-ttu-id="ed5b6-171">列表中的项的容器。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-171">A container for items in the list.</span></span> <span data-ttu-id="ed5b6-172">必需。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-172">Required.</span></span>  <br/> |
   
### <a name="picturevariable"></a><span data-ttu-id="ed5b6-173">pictureVariable</span><span class="sxs-lookup"><span data-stu-id="ed5b6-173">pictureVariable</span></span>

|<span data-ttu-id="ed5b6-174">**元素**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-174">**Element**</span></span>|<span data-ttu-id="ed5b6-175">**说明**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-175">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ed5b6-176">**name**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-176">**name**</span></span> <br/> |<span data-ttu-id="ed5b6-177">变量的名称。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-177">The name of the variable.</span></span> <span data-ttu-id="ed5b6-178">必需。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-178">Required.</span></span>  <br/> |
|<span data-ttu-id="ed5b6-179">**value**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-179">**value**</span></span> <br/> |<span data-ttu-id="ed5b6-180">图片的 URL。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-180">The URL for the picture.</span></span> <span data-ttu-id="ed5b6-181">必需。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-181">Required.</span></span>  <br/> |
|<span data-ttu-id="ed5b6-182">**altText**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-182">**altText**</span></span> <br/> |<span data-ttu-id="ed5b6-183">为辅助功能以及当用户将鼠标指针移动到图片上时要显示的替换文字。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-183">The alternate text to display for accessibility and when the user moves the mouse pointer over the picture.</span></span> <span data-ttu-id="ed5b6-184">可选。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-184">Optional.</span></span>  <br/> |
|<span data-ttu-id="ed5b6-185">**href**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-185">**href**</span></span> <br/> |<span data-ttu-id="ed5b6-186">当用户单击图片时要使用的超链接 (如果所需目标不是**value**元素指定的图片 URL)。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-186">The hyperlink to use when the user clicks the picture, if the desired target is not the picture URL specified by the **value** element.</span></span> <span data-ttu-id="ed5b6-187">可选。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-187">Optional.</span></span>  <br/> |
   
### <a name="publishervariable"></a><span data-ttu-id="ed5b6-188">publisherVariable</span><span class="sxs-lookup"><span data-stu-id="ed5b6-188">publisherVariable</span></span>

|<span data-ttu-id="ed5b6-189">**元素**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-189">**Element**</span></span>|<span data-ttu-id="ed5b6-190">**说明**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-190">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ed5b6-191">**name**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-191">**name**</span></span> <br/> |<span data-ttu-id="ed5b6-192">变量的名称。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-192">The name of the variable.</span></span> <span data-ttu-id="ed5b6-193">必需。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-193">Required.</span></span>  <br/> |
|<span data-ttu-id="ed5b6-194">**id**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-194">**id**</span></span> <br/> |<span data-ttu-id="ed5b6-195">用户的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-195">The unique ID of the user.</span></span> <span data-ttu-id="ed5b6-196">必需。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-196">Required.</span></span>  <br/> |
|<span data-ttu-id="ed5b6-197">**nameHint**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-197">**nameHint**</span></span> <br/> |<span data-ttu-id="ed5b6-198">要显示在订阅源项中的名称。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-198">The name to be displayed in the feed item.</span></span> <span data-ttu-id="ed5b6-199">可选。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-199">Optional.</span></span>  <br/> |
|<span data-ttu-id="ed5b6-200">**profileUrl**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-200">**profileUrl**</span></span> <br/> |<span data-ttu-id="ed5b6-201">个人个人资料的 URL, 如果此人的姓名存在, 将用作订阅源项目中人员姓名的超链接。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-201">The URL of the person's profile that will be used as the hyperlink for the person's name in the feed item, if the person's name is present.</span></span> <span data-ttu-id="ed5b6-202">可选。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-202">Optional.</span></span>  <br/> |
|<span data-ttu-id="ed5b6-203">**emailAddress**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-203">**emailAddress**</span></span> <br/> |<span data-ttu-id="ed5b6-204">用于在 Outlook 中更新此人的联系人信息的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-204">The email address that is used to update this person's contact information in Outlook.</span></span> <span data-ttu-id="ed5b6-205">可选。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-205">Optional.</span></span>  <br/> |
   
### <a name="textvariable"></a><span data-ttu-id="ed5b6-206">textVariable</span><span class="sxs-lookup"><span data-stu-id="ed5b6-206">textVariable</span></span>

|<span data-ttu-id="ed5b6-207">**元素**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-207">**Element**</span></span>|<span data-ttu-id="ed5b6-208">**说明**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-208">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ed5b6-209">**name**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-209">**name**</span></span> <br/> |<span data-ttu-id="ed5b6-210">变量的名称。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-210">The name of the variable.</span></span> <span data-ttu-id="ed5b6-211">必需。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-211">Required.</span></span>  <br/> |
|<span data-ttu-id="ed5b6-212">**value**</span><span class="sxs-lookup"><span data-stu-id="ed5b6-212">**value**</span></span> <br/> |<span data-ttu-id="ed5b6-213">要显示的文本。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-213">The text to display.</span></span> <span data-ttu-id="ed5b6-214">可选。</span><span class="sxs-lookup"><span data-stu-id="ed5b6-214">Optional.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ed5b6-215">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed5b6-215">See also</span></span>

- [<span data-ttu-id="ed5b6-216">活动源项目的 XML 概述</span><span class="sxs-lookup"><span data-stu-id="ed5b6-216">Overview of XML for an Activity Feed Item</span></span>](overview-of-xml-for-an-activity-feed-item.md)  
- [<span data-ttu-id="ed5b6-217">activityDetails 元素</span><span class="sxs-lookup"><span data-stu-id="ed5b6-217">activityDetails Element</span></span>](activitydetails-element.md)  
- [<span data-ttu-id="ed5b6-218">activityTemplateContainer 元素</span><span class="sxs-lookup"><span data-stu-id="ed5b6-218">activityTemplateContainer Element</span></span>](activitytemplatecontainer-element.md)  
- [<span data-ttu-id="ed5b6-219">正确显示活动的准则</span><span class="sxs-lookup"><span data-stu-id="ed5b6-219">Guidelines for Properly Displaying Activities</span></span>](guidelines-for-properly-displaying-activities.md)  
- [<span data-ttu-id="ed5b6-220">适用于活动的 XML</span><span class="sxs-lookup"><span data-stu-id="ed5b6-220">XML for Activities</span></span>](xml-for-activities.md)  
- [<span data-ttu-id="ed5b6-221">Outlook Social Connector 提供程序 XML 架构</span><span class="sxs-lookup"><span data-stu-id="ed5b6-221">Outlook Social Connector Provider XML Schema</span></span>](outlook-social-connector-provider-xml-schema.md)
- [<span data-ttu-id="ed5b6-222">使用 .osc XML 架构开发提供程序</span><span class="sxs-lookup"><span data-stu-id="ed5b6-222">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)

