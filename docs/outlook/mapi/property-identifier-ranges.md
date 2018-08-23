---
title: 属性标识符范围
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c01e95bb-be25-490d-880b-60674f890258
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 479e5abda9137ddaedcabb8d914bc038ddf200f3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581102"
---
# <a name="property-identifier-ranges"></a><span data-ttu-id="c6388-103">属性标识符范围</span><span class="sxs-lookup"><span data-stu-id="c6388-103">Property Identifier Ranges</span></span>

  
  
<span data-ttu-id="c6388-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c6388-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c6388-105">下表总结了不同属性标识符，描述每个范围中的属性的所有者的范围。</span><span class="sxs-lookup"><span data-stu-id="c6388-105">The following table summarizes the different ranges for property identifiers, describing the owner for the properties in each range.</span></span>
  
|<span data-ttu-id="c6388-106">**标识符范围**</span><span class="sxs-lookup"><span data-stu-id="c6388-106">**Identifier range**</span></span>|<span data-ttu-id="c6388-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="c6388-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c6388-108">0000</span><span class="sxs-lookup"><span data-stu-id="c6388-108">0000</span></span>  <br/> |<span data-ttu-id="c6388-109">通过 MAPI 供特殊值**PR_NULL**。</span><span class="sxs-lookup"><span data-stu-id="c6388-109">Reserved by MAPI for the special value **PR_NULL**.</span></span>  <br/> |
|<span data-ttu-id="c6388-110">0001-0BFF</span><span class="sxs-lookup"><span data-stu-id="c6388-110">0001 - 0BFF</span></span>  <br/> |<span data-ttu-id="c6388-111">定义的 MAPI 邮件信封属性。</span><span class="sxs-lookup"><span data-stu-id="c6388-111">Message envelope properties defined by MAPI.</span></span>  <br/> |
|<span data-ttu-id="c6388-112">0 C 00-0DFF</span><span class="sxs-lookup"><span data-stu-id="c6388-112">0C00 - 0DFF</span></span>  <br/> |<span data-ttu-id="c6388-113">定义的 MAPI 的收件人属性。</span><span class="sxs-lookup"><span data-stu-id="c6388-113">Recipient properties defined by MAPI.</span></span>  <br/> |
|<span data-ttu-id="c6388-114">0E00-0FFF</span><span class="sxs-lookup"><span data-stu-id="c6388-114">0E00 - 0FFF</span></span>  <br/> |<span data-ttu-id="c6388-115">非可传送消息定义 MAPI 的属性。</span><span class="sxs-lookup"><span data-stu-id="c6388-115">Non-transmittable message properties defined by MAPI.</span></span>  <br/> |
|<span data-ttu-id="c6388-116">1000-2FFF</span><span class="sxs-lookup"><span data-stu-id="c6388-116">1000 - 2FFF</span></span>  <br/> |<span data-ttu-id="c6388-117">定义的 MAPI 邮件内容属性。</span><span class="sxs-lookup"><span data-stu-id="c6388-117">Message content properties defined by MAPI.</span></span>  <br/> |
|<span data-ttu-id="c6388-118">3000-3FFF</span><span class="sxs-lookup"><span data-stu-id="c6388-118">3000 - 3FFF</span></span>  <br/> |<span data-ttu-id="c6388-119">邮件和收件人的 MAPI 定义以外的对象的属性。</span><span class="sxs-lookup"><span data-stu-id="c6388-119">Properties for objects other than messages and recipients defined by MAPI.</span></span>  <br/> |
|<span data-ttu-id="c6388-120">4000-57FF</span><span class="sxs-lookup"><span data-stu-id="c6388-120">4000 - 57FF</span></span>  <br/> |<span data-ttu-id="c6388-121">邮件信封属性由传输提供程序定义。</span><span class="sxs-lookup"><span data-stu-id="c6388-121">Message envelope properties defined by transport providers.</span></span>  <br/> |
|<span data-ttu-id="c6388-122">5800-5FFF</span><span class="sxs-lookup"><span data-stu-id="c6388-122">5800 - 5FFF</span></span>  <br/> |<span data-ttu-id="c6388-123">由传输和通讯簿提供程序定义的收件人属性。</span><span class="sxs-lookup"><span data-stu-id="c6388-123">Recipient properties defined by transport and address book providers.</span></span>  <br/> |
|<span data-ttu-id="c6388-124">6000-65FF</span><span class="sxs-lookup"><span data-stu-id="c6388-124">6000 - 65FF</span></span>  <br/> |<span data-ttu-id="c6388-125">定义由客户端的非可传送邮件属性。</span><span class="sxs-lookup"><span data-stu-id="c6388-125">Non-transmittable message properties defined by clients.</span></span>  <br/> |
|<span data-ttu-id="c6388-126">6600-67FF</span><span class="sxs-lookup"><span data-stu-id="c6388-126">6600 - 67FF</span></span>  <br/> |<span data-ttu-id="c6388-127">定义由服务提供商的非可传送属性。</span><span class="sxs-lookup"><span data-stu-id="c6388-127">Non-transmittable properties defined by a service provider.</span></span> <span data-ttu-id="c6388-128">这些属性可以是用户可见或不可见。</span><span class="sxs-lookup"><span data-stu-id="c6388-128">These properties can be visible or invisible to users.</span></span>  <br/> |
|<span data-ttu-id="c6388-129">6800-7BFF</span><span class="sxs-lookup"><span data-stu-id="c6388-129">6800 - 7BFF</span></span>  <br/> |<span data-ttu-id="c6388-130">自定义邮件类定义这些类的创建者的消息内容属性。</span><span class="sxs-lookup"><span data-stu-id="c6388-130">Message content properties for custom message classes defined by creators of those classes.</span></span>  <br/> |
|<span data-ttu-id="c6388-131">7C 00-7FFF</span><span class="sxs-lookup"><span data-stu-id="c6388-131">7C00 - 7FFF</span></span>  <br/> |<span data-ttu-id="c6388-132">自定义邮件类定义这些类的创建者的非可传送属性。</span><span class="sxs-lookup"><span data-stu-id="c6388-132">Non-transmittable properties for custom message classes defined by creators of those classes.</span></span>  <br/> |
|<span data-ttu-id="c6388-133">8000-FFFE</span><span class="sxs-lookup"><span data-stu-id="c6388-133">8000 - FFFE</span></span>  <br/> |<span data-ttu-id="c6388-134">属性定义由客户端和偶尔服务通过[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)和[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法按姓名标识提供程序。</span><span class="sxs-lookup"><span data-stu-id="c6388-134">Properties defined by clients and occasionally service providers that are identified by name through the [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) and [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) methods.</span></span>  <br/> |
|<span data-ttu-id="c6388-135">FFFF</span><span class="sxs-lookup"><span data-stu-id="c6388-135">FFFF</span></span>  <br/> |<span data-ttu-id="c6388-136">通过 MAPI 供 PROP_ID_INVALID 的特殊的错误值。</span><span class="sxs-lookup"><span data-stu-id="c6388-136">Reserved by MAPI for the special error value PROP_ID_INVALID.</span></span>  <br/> |
   
<span data-ttu-id="c6388-137">3000 之间的范围和 3FFF 供与邮件或收件人不相关的属性。</span><span class="sxs-lookup"><span data-stu-id="c6388-137">The range between 3000 and 3FFF is reserved for properties that are not related to either messages or recipients.</span></span> <span data-ttu-id="c6388-138">MAPI 将此范围分为子范围的类型的对象;下表显示了此进一步细分。</span><span class="sxs-lookup"><span data-stu-id="c6388-138">MAPI divides this range into sub-ranges by types of object; the following table shows this further breakdown.</span></span> 
  
|<span data-ttu-id="c6388-139">**标识符范围**</span><span class="sxs-lookup"><span data-stu-id="c6388-139">**Identifier range**</span></span>|<span data-ttu-id="c6388-140">**属性类型**</span><span class="sxs-lookup"><span data-stu-id="c6388-140">**Type of property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c6388-141">3000-33FF</span><span class="sxs-lookup"><span data-stu-id="c6388-141">3000 - 33FF</span></span>  <br/> |<span data-ttu-id="c6388-142">多个对象，如**PR_DISPLAY_NAME**和**PR_ENTRYID**显示的常见属性。</span><span class="sxs-lookup"><span data-stu-id="c6388-142">Common properties that appear on multiple objects, such as **PR_DISPLAY_NAME** and **PR_ENTRYID**.</span></span>  <br/> |
|<span data-ttu-id="c6388-143">3400-35FF</span><span class="sxs-lookup"><span data-stu-id="c6388-143">3400 - 35FF</span></span>  <br/> |<span data-ttu-id="c6388-144">消息存储库属性</span><span class="sxs-lookup"><span data-stu-id="c6388-144">Message store properties</span></span>  <br/> |
|<span data-ttu-id="c6388-145">3600-36FF</span><span class="sxs-lookup"><span data-stu-id="c6388-145">3600 - 36FF</span></span>  <br/> |<span data-ttu-id="c6388-146">文件夹和通讯簿容器属性</span><span class="sxs-lookup"><span data-stu-id="c6388-146">Folder and address book container properties</span></span>  <br/> |
|<span data-ttu-id="c6388-147">3700-38FF</span><span class="sxs-lookup"><span data-stu-id="c6388-147">3700 - 38FF</span></span>  <br/> |<span data-ttu-id="c6388-148">附件属性</span><span class="sxs-lookup"><span data-stu-id="c6388-148">Attachment properties</span></span>  <br/> |
|<span data-ttu-id="c6388-149">3900-39FF</span><span class="sxs-lookup"><span data-stu-id="c6388-149">3900 - 39FF</span></span>  <br/> |<span data-ttu-id="c6388-150">通讯簿属性</span><span class="sxs-lookup"><span data-stu-id="c6388-150">Address book properties</span></span>  <br/> |
|<span data-ttu-id="c6388-151">3A00-3BFF</span><span class="sxs-lookup"><span data-stu-id="c6388-151">3A00 - 3BFF</span></span>  <br/> |<span data-ttu-id="c6388-152">消息的用户属性</span><span class="sxs-lookup"><span data-stu-id="c6388-152">Messaging user properties</span></span>  <br/> |
|<span data-ttu-id="c6388-153">3C 00-3CFF</span><span class="sxs-lookup"><span data-stu-id="c6388-153">3C00 - 3CFF</span></span>  <br/> |<span data-ttu-id="c6388-154">通讯组列表属性</span><span class="sxs-lookup"><span data-stu-id="c6388-154">Distribution list properties</span></span>  <br/> |
|<span data-ttu-id="c6388-155">三维 00-3DFF</span><span class="sxs-lookup"><span data-stu-id="c6388-155">3D00 - 3DFF</span></span>  <br/> |<span data-ttu-id="c6388-156">配置文件属性</span><span class="sxs-lookup"><span data-stu-id="c6388-156">Profile properties</span></span>  <br/> |
|<span data-ttu-id="c6388-157">3E00-3FFF</span><span class="sxs-lookup"><span data-stu-id="c6388-157">3E00 - 3FFF</span></span>  <br/> |<span data-ttu-id="c6388-158">状态对象属性</span><span class="sxs-lookup"><span data-stu-id="c6388-158">Status object properties</span></span>  <br/> |
   

