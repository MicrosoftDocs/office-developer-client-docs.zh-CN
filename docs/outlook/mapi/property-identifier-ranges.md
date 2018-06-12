---
title: 属性标识符范围
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c01e95bb-be25-490d-880b-60674f890258
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: aee199cbbd05606d20378023f103fa122f1457f2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778566"
---
# <a name="property-identifier-ranges"></a><span data-ttu-id="38677-103">属性标识符范围</span><span class="sxs-lookup"><span data-stu-id="38677-103">Property Identifier Ranges</span></span>

  
  
<span data-ttu-id="38677-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="38677-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="38677-105">下表总结了不同属性标识符，描述每个范围中的属性的所有者的范围。</span><span class="sxs-lookup"><span data-stu-id="38677-105">The following table summarizes the different ranges for property identifiers, describing the owner for the properties in each range.</span></span>
  
|<span data-ttu-id="38677-106">**标识符范围**</span><span class="sxs-lookup"><span data-stu-id="38677-106">**Identifier range**</span></span>|<span data-ttu-id="38677-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="38677-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38677-108">0000</span><span class="sxs-lookup"><span data-stu-id="38677-108">0000</span></span>  <br/> |<span data-ttu-id="38677-109">通过 MAPI 供特殊值**PR_NULL**。</span><span class="sxs-lookup"><span data-stu-id="38677-109">Reserved by MAPI for the special value **PR_NULL**.</span></span>  <br/> |
|<span data-ttu-id="38677-110">0001-0BFF</span><span class="sxs-lookup"><span data-stu-id="38677-110">0001 - 0BFF</span></span>  <br/> |<span data-ttu-id="38677-111">定义的 MAPI 邮件信封属性。</span><span class="sxs-lookup"><span data-stu-id="38677-111">Message envelope properties defined by MAPI.</span></span>  <br/> |
|<span data-ttu-id="38677-112">0 C 00-0DFF</span><span class="sxs-lookup"><span data-stu-id="38677-112">0C00 - 0DFF</span></span>  <br/> |<span data-ttu-id="38677-113">定义的 MAPI 的收件人属性。</span><span class="sxs-lookup"><span data-stu-id="38677-113">Recipient properties defined by MAPI.</span></span>  <br/> |
|<span data-ttu-id="38677-114">0E00-0FFF</span><span class="sxs-lookup"><span data-stu-id="38677-114">0E00 - 0FFF</span></span>  <br/> |<span data-ttu-id="38677-115">非可传送消息定义 MAPI 的属性。</span><span class="sxs-lookup"><span data-stu-id="38677-115">Non-transmittable message properties defined by MAPI.</span></span>  <br/> |
|<span data-ttu-id="38677-116">1000-2FFF</span><span class="sxs-lookup"><span data-stu-id="38677-116">1000 - 2FFF</span></span>  <br/> |<span data-ttu-id="38677-117">定义的 MAPI 邮件内容属性。</span><span class="sxs-lookup"><span data-stu-id="38677-117">Message content properties defined by MAPI.</span></span>  <br/> |
|<span data-ttu-id="38677-118">3000-3FFF</span><span class="sxs-lookup"><span data-stu-id="38677-118">3000 - 3FFF</span></span>  <br/> |<span data-ttu-id="38677-119">邮件和收件人的 MAPI 定义以外的对象的属性。</span><span class="sxs-lookup"><span data-stu-id="38677-119">Properties for objects other than messages and recipients defined by MAPI.</span></span>  <br/> |
|<span data-ttu-id="38677-120">4000-57FF</span><span class="sxs-lookup"><span data-stu-id="38677-120">4000 - 57FF</span></span>  <br/> |<span data-ttu-id="38677-121">邮件信封属性由传输提供程序定义。</span><span class="sxs-lookup"><span data-stu-id="38677-121">Message envelope properties defined by transport providers.</span></span>  <br/> |
|<span data-ttu-id="38677-122">5800-5FFF</span><span class="sxs-lookup"><span data-stu-id="38677-122">5800 - 5FFF</span></span>  <br/> |<span data-ttu-id="38677-123">由传输和通讯簿提供程序定义的收件人属性。</span><span class="sxs-lookup"><span data-stu-id="38677-123">Recipient properties defined by transport and address book providers.</span></span>  <br/> |
|<span data-ttu-id="38677-124">6000-65FF</span><span class="sxs-lookup"><span data-stu-id="38677-124">6000 - 65FF</span></span>  <br/> |<span data-ttu-id="38677-125">定义由客户端的非可传送邮件属性。</span><span class="sxs-lookup"><span data-stu-id="38677-125">Non-transmittable message properties defined by clients.</span></span>  <br/> |
|<span data-ttu-id="38677-126">6600-67FF</span><span class="sxs-lookup"><span data-stu-id="38677-126">6600 - 67FF</span></span>  <br/> |<span data-ttu-id="38677-127">定义由服务提供商的非可传送属性。</span><span class="sxs-lookup"><span data-stu-id="38677-127">Non-transmittable properties defined by a service provider.</span></span> <span data-ttu-id="38677-128">这些属性可以是用户可见或不可见。</span><span class="sxs-lookup"><span data-stu-id="38677-128">These properties can be visible or invisible to users.</span></span>  <br/> |
|<span data-ttu-id="38677-129">6800-7BFF</span><span class="sxs-lookup"><span data-stu-id="38677-129">6800 - 7BFF</span></span>  <br/> |<span data-ttu-id="38677-130">自定义邮件类定义这些类的创建者的消息内容属性。</span><span class="sxs-lookup"><span data-stu-id="38677-130">Message content properties for custom message classes defined by creators of those classes.</span></span>  <br/> |
|<span data-ttu-id="38677-131">7C 00-7FFF</span><span class="sxs-lookup"><span data-stu-id="38677-131">7C00 - 7FFF</span></span>  <br/> |<span data-ttu-id="38677-132">自定义邮件类定义这些类的创建者的非可传送属性。</span><span class="sxs-lookup"><span data-stu-id="38677-132">Non-transmittable properties for custom message classes defined by creators of those classes.</span></span>  <br/> |
|<span data-ttu-id="38677-133">8000-FFFE</span><span class="sxs-lookup"><span data-stu-id="38677-133">8000 - FFFE</span></span>  <br/> |<span data-ttu-id="38677-134">属性定义由客户端和偶尔服务通过[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)和[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法按姓名标识提供程序。</span><span class="sxs-lookup"><span data-stu-id="38677-134">Properties defined by clients and occasionally service providers that are identified by name through the [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) and [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) methods.</span></span>  <br/> |
|<span data-ttu-id="38677-135">FFFF</span><span class="sxs-lookup"><span data-stu-id="38677-135">FFFF</span></span>  <br/> |<span data-ttu-id="38677-136">通过 MAPI 供 PROP_ID_INVALID 的特殊的错误值。</span><span class="sxs-lookup"><span data-stu-id="38677-136">Reserved by MAPI for the special error value PROP_ID_INVALID.</span></span>  <br/> |
   
<span data-ttu-id="38677-137">3000 之间的范围和 3FFF 供与邮件或收件人不相关的属性。</span><span class="sxs-lookup"><span data-stu-id="38677-137">The range between 3000 and 3FFF is reserved for properties that are not related to either messages or recipients.</span></span> <span data-ttu-id="38677-138">MAPI 将此范围分为子范围的类型的对象;下表显示了此进一步细分。</span><span class="sxs-lookup"><span data-stu-id="38677-138">MAPI divides this range into sub-ranges by types of object; the following table shows this further breakdown.</span></span> 
  
|<span data-ttu-id="38677-139">**标识符范围**</span><span class="sxs-lookup"><span data-stu-id="38677-139">**Identifier range**</span></span>|<span data-ttu-id="38677-140">**属性类型**</span><span class="sxs-lookup"><span data-stu-id="38677-140">**Type of property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38677-141">3000-33FF</span><span class="sxs-lookup"><span data-stu-id="38677-141">3000 - 33FF</span></span>  <br/> |<span data-ttu-id="38677-142">多个对象，如**PR_DISPLAY_NAME**和**PR_ENTRYID**显示的常见属性。</span><span class="sxs-lookup"><span data-stu-id="38677-142">Common properties that appear on multiple objects, such as **PR_DISPLAY_NAME** and **PR_ENTRYID**.</span></span>  <br/> |
|<span data-ttu-id="38677-143">3400-35FF</span><span class="sxs-lookup"><span data-stu-id="38677-143">3400 - 35FF</span></span>  <br/> |<span data-ttu-id="38677-144">消息存储库属性</span><span class="sxs-lookup"><span data-stu-id="38677-144">Message store properties</span></span>  <br/> |
|<span data-ttu-id="38677-145">3600-36FF</span><span class="sxs-lookup"><span data-stu-id="38677-145">3600 - 36FF</span></span>  <br/> |<span data-ttu-id="38677-146">文件夹和通讯簿容器属性</span><span class="sxs-lookup"><span data-stu-id="38677-146">Folder and address book container properties</span></span>  <br/> |
|<span data-ttu-id="38677-147">3700-38FF</span><span class="sxs-lookup"><span data-stu-id="38677-147">3700 - 38FF</span></span>  <br/> |<span data-ttu-id="38677-148">附件属性</span><span class="sxs-lookup"><span data-stu-id="38677-148">Attachment properties</span></span>  <br/> |
|<span data-ttu-id="38677-149">3900-39FF</span><span class="sxs-lookup"><span data-stu-id="38677-149">3900 - 39FF</span></span>  <br/> |<span data-ttu-id="38677-150">通讯簿属性</span><span class="sxs-lookup"><span data-stu-id="38677-150">Address book properties</span></span>  <br/> |
|<span data-ttu-id="38677-151">3A00-3BFF</span><span class="sxs-lookup"><span data-stu-id="38677-151">3A00 - 3BFF</span></span>  <br/> |<span data-ttu-id="38677-152">消息的用户属性</span><span class="sxs-lookup"><span data-stu-id="38677-152">Messaging user properties</span></span>  <br/> |
|<span data-ttu-id="38677-153">3C 00-3CFF</span><span class="sxs-lookup"><span data-stu-id="38677-153">3C00 - 3CFF</span></span>  <br/> |<span data-ttu-id="38677-154">通讯组列表属性</span><span class="sxs-lookup"><span data-stu-id="38677-154">Distribution list properties</span></span>  <br/> |
|<span data-ttu-id="38677-155">三维 00-3DFF</span><span class="sxs-lookup"><span data-stu-id="38677-155">3D00 - 3DFF</span></span>  <br/> |<span data-ttu-id="38677-156">配置文件属性</span><span class="sxs-lookup"><span data-stu-id="38677-156">Profile properties</span></span>  <br/> |
|<span data-ttu-id="38677-157">3E00-3FFF</span><span class="sxs-lookup"><span data-stu-id="38677-157">3E00 - 3FFF</span></span>  <br/> |<span data-ttu-id="38677-158">状态对象属性</span><span class="sxs-lookup"><span data-stu-id="38677-158">Status object properties</span></span>  <br/> |
   

