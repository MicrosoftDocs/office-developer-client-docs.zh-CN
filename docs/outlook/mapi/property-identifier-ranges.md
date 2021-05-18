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
ms.openlocfilehash: cdf1eae945cddf9eb76a2b7a2532d5dc6568beac
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422703"
---
# <a name="property-identifier-ranges"></a><span data-ttu-id="3eb84-103">属性标识符范围</span><span class="sxs-lookup"><span data-stu-id="3eb84-103">Property Identifier Ranges</span></span>

  
  
<span data-ttu-id="3eb84-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3eb84-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3eb84-105">下表总结了属性标识符的不同范围，并描述了每个范围中属性的所有者。</span><span class="sxs-lookup"><span data-stu-id="3eb84-105">The following table summarizes the different ranges for property identifiers, describing the owner for the properties in each range.</span></span>
  
|<span data-ttu-id="3eb84-106">**标识符范围**</span><span class="sxs-lookup"><span data-stu-id="3eb84-106">**Identifier range**</span></span>|<span data-ttu-id="3eb84-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="3eb84-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3eb84-108">0000</span><span class="sxs-lookup"><span data-stu-id="3eb84-108">0000</span></span>  <br/> |<span data-ttu-id="3eb84-109">由 MAPI 保留，用于特殊 **PR_NULL。**</span><span class="sxs-lookup"><span data-stu-id="3eb84-109">Reserved by MAPI for the special value **PR_NULL**.</span></span>  <br/> |
|<span data-ttu-id="3eb84-110">0001 - 0BFF</span><span class="sxs-lookup"><span data-stu-id="3eb84-110">0001 - 0BFF</span></span>  <br/> |<span data-ttu-id="3eb84-111">MAPI 定义的邮件信封属性。</span><span class="sxs-lookup"><span data-stu-id="3eb84-111">Message envelope properties defined by MAPI.</span></span>  <br/> |
|<span data-ttu-id="3eb84-112">0C00 - 0DFF</span><span class="sxs-lookup"><span data-stu-id="3eb84-112">0C00 - 0DFF</span></span>  <br/> |<span data-ttu-id="3eb84-113">由 MAPI 定义的收件人属性。</span><span class="sxs-lookup"><span data-stu-id="3eb84-113">Recipient properties defined by MAPI.</span></span>  <br/> |
|<span data-ttu-id="3eb84-114">0E00 - 0FFF</span><span class="sxs-lookup"><span data-stu-id="3eb84-114">0E00 - 0FFF</span></span>  <br/> |<span data-ttu-id="3eb84-115">MAPI 定义的不可传输邮件属性。</span><span class="sxs-lookup"><span data-stu-id="3eb84-115">Non-transmittable message properties defined by MAPI.</span></span>  <br/> |
|<span data-ttu-id="3eb84-116">1000 - 2FFF</span><span class="sxs-lookup"><span data-stu-id="3eb84-116">1000 - 2FFF</span></span>  <br/> |<span data-ttu-id="3eb84-117">MAPI 定义的邮件内容属性。</span><span class="sxs-lookup"><span data-stu-id="3eb84-117">Message content properties defined by MAPI.</span></span>  <br/> |
|<span data-ttu-id="3eb84-118">3000 - 3FFF</span><span class="sxs-lookup"><span data-stu-id="3eb84-118">3000 - 3FFF</span></span>  <br/> |<span data-ttu-id="3eb84-119">除 MAPI 定义的邮件和收件人外的对象的属性。</span><span class="sxs-lookup"><span data-stu-id="3eb84-119">Properties for objects other than messages and recipients defined by MAPI.</span></span>  <br/> |
|<span data-ttu-id="3eb84-120">4000 - 57FF</span><span class="sxs-lookup"><span data-stu-id="3eb84-120">4000 - 57FF</span></span>  <br/> |<span data-ttu-id="3eb84-121">由传输提供程序定义的邮件信封属性。</span><span class="sxs-lookup"><span data-stu-id="3eb84-121">Message envelope properties defined by transport providers.</span></span>  <br/> |
|<span data-ttu-id="3eb84-122">5800 - 5FFF</span><span class="sxs-lookup"><span data-stu-id="3eb84-122">5800 - 5FFF</span></span>  <br/> |<span data-ttu-id="3eb84-123">由传输和通讯簿提供程序定义的收件人属性。</span><span class="sxs-lookup"><span data-stu-id="3eb84-123">Recipient properties defined by transport and address book providers.</span></span>  <br/> |
|<span data-ttu-id="3eb84-124">6000 - 65FF</span><span class="sxs-lookup"><span data-stu-id="3eb84-124">6000 - 65FF</span></span>  <br/> |<span data-ttu-id="3eb84-125">客户端定义的不可传输邮件属性。</span><span class="sxs-lookup"><span data-stu-id="3eb84-125">Non-transmittable message properties defined by clients.</span></span>  <br/> |
|<span data-ttu-id="3eb84-126">6600 - 67FF</span><span class="sxs-lookup"><span data-stu-id="3eb84-126">6600 - 67FF</span></span>  <br/> |<span data-ttu-id="3eb84-127">服务提供商定义的不可传输属性。</span><span class="sxs-lookup"><span data-stu-id="3eb84-127">Non-transmittable properties defined by a service provider.</span></span> <span data-ttu-id="3eb84-128">这些属性对于用户可见或不可见。</span><span class="sxs-lookup"><span data-stu-id="3eb84-128">These properties can be visible or invisible to users.</span></span>  <br/> |
|<span data-ttu-id="3eb84-129">6800 - 7BFF</span><span class="sxs-lookup"><span data-stu-id="3eb84-129">6800 - 7BFF</span></span>  <br/> |<span data-ttu-id="3eb84-130">由这些类的创建者定义的自定义邮件类的邮件内容属性。</span><span class="sxs-lookup"><span data-stu-id="3eb84-130">Message content properties for custom message classes defined by creators of those classes.</span></span>  <br/> |
|<span data-ttu-id="3eb84-131">7C00 - 7FFF</span><span class="sxs-lookup"><span data-stu-id="3eb84-131">7C00 - 7FFF</span></span>  <br/> |<span data-ttu-id="3eb84-132">由这些类的创建者定义的自定义邮件类的不可传输属性。</span><span class="sxs-lookup"><span data-stu-id="3eb84-132">Non-transmittable properties for custom message classes defined by creators of those classes.</span></span>  <br/> |
|<span data-ttu-id="3eb84-133">8000 - FFFE</span><span class="sxs-lookup"><span data-stu-id="3eb84-133">8000 - FFFE</span></span>  <br/> |<span data-ttu-id="3eb84-134">由客户端和有时通过 [IMAPIProp：：GetNamesFromIDs](imapiprop-getnamesfromids.md) 和 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 方法按名称标识的属性。</span><span class="sxs-lookup"><span data-stu-id="3eb84-134">Properties defined by clients and occasionally service providers that are identified by name through the [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) and [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) methods.</span></span>  <br/> |
|<span data-ttu-id="3eb84-135">FFFF</span><span class="sxs-lookup"><span data-stu-id="3eb84-135">FFFF</span></span>  <br/> |<span data-ttu-id="3eb84-136">由 MAPI 保留，用于特殊错误PROP_ID_INVALID。</span><span class="sxs-lookup"><span data-stu-id="3eb84-136">Reserved by MAPI for the special error value PROP_ID_INVALID.</span></span>  <br/> |
   
<span data-ttu-id="3eb84-137">3000 到 3FFF 之间的范围为与邮件或收件人不相关的属性保留。</span><span class="sxs-lookup"><span data-stu-id="3eb84-137">The range between 3000 and 3FFF is reserved for properties that are not related to either messages or recipients.</span></span> <span data-ttu-id="3eb84-138">MAPI 按对象类型将此范围划分为子范围;下表显示了此进一步细分。</span><span class="sxs-lookup"><span data-stu-id="3eb84-138">MAPI divides this range into sub-ranges by types of object; the following table shows this further breakdown.</span></span> 
  
|<span data-ttu-id="3eb84-139">**标识符范围**</span><span class="sxs-lookup"><span data-stu-id="3eb84-139">**Identifier range**</span></span>|<span data-ttu-id="3eb84-140">**属性类型**</span><span class="sxs-lookup"><span data-stu-id="3eb84-140">**Type of property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3eb84-141">3000 - 33FF</span><span class="sxs-lookup"><span data-stu-id="3eb84-141">3000 - 33FF</span></span>  <br/> |<span data-ttu-id="3eb84-142">出现在多个对象上的常见属性，如 **PR_DISPLAY_NAME** 和 **PR_ENTRYID**。</span><span class="sxs-lookup"><span data-stu-id="3eb84-142">Common properties that appear on multiple objects, such as **PR_DISPLAY_NAME** and **PR_ENTRYID**.</span></span>  <br/> |
|<span data-ttu-id="3eb84-143">3400 - 35FF</span><span class="sxs-lookup"><span data-stu-id="3eb84-143">3400 - 35FF</span></span>  <br/> |<span data-ttu-id="3eb84-144">邮件存储属性</span><span class="sxs-lookup"><span data-stu-id="3eb84-144">Message store properties</span></span>  <br/> |
|<span data-ttu-id="3eb84-145">3600 - 36FF</span><span class="sxs-lookup"><span data-stu-id="3eb84-145">3600 - 36FF</span></span>  <br/> |<span data-ttu-id="3eb84-146">文件夹和通讯簿容器属性</span><span class="sxs-lookup"><span data-stu-id="3eb84-146">Folder and address book container properties</span></span>  <br/> |
|<span data-ttu-id="3eb84-147">3700 - 38FF</span><span class="sxs-lookup"><span data-stu-id="3eb84-147">3700 - 38FF</span></span>  <br/> |<span data-ttu-id="3eb84-148">附件属性</span><span class="sxs-lookup"><span data-stu-id="3eb84-148">Attachment properties</span></span>  <br/> |
|<span data-ttu-id="3eb84-149">3900 - 39FF</span><span class="sxs-lookup"><span data-stu-id="3eb84-149">3900 - 39FF</span></span>  <br/> |<span data-ttu-id="3eb84-150">通讯簿属性</span><span class="sxs-lookup"><span data-stu-id="3eb84-150">Address book properties</span></span>  <br/> |
|<span data-ttu-id="3eb84-151">3A00 - 3BFF</span><span class="sxs-lookup"><span data-stu-id="3eb84-151">3A00 - 3BFF</span></span>  <br/> |<span data-ttu-id="3eb84-152">邮件传递用户属性</span><span class="sxs-lookup"><span data-stu-id="3eb84-152">Messaging user properties</span></span>  <br/> |
|<span data-ttu-id="3eb84-153">3C00 - 3CFF</span><span class="sxs-lookup"><span data-stu-id="3eb84-153">3C00 - 3CFF</span></span>  <br/> |<span data-ttu-id="3eb84-154">通讯组列表属性</span><span class="sxs-lookup"><span data-stu-id="3eb84-154">Distribution list properties</span></span>  <br/> |
|<span data-ttu-id="3eb84-155">3D00 - 3DFF</span><span class="sxs-lookup"><span data-stu-id="3eb84-155">3D00 - 3DFF</span></span>  <br/> |<span data-ttu-id="3eb84-156">配置文件属性</span><span class="sxs-lookup"><span data-stu-id="3eb84-156">Profile properties</span></span>  <br/> |
|<span data-ttu-id="3eb84-157">3E00 - 3FFF</span><span class="sxs-lookup"><span data-stu-id="3eb84-157">3E00 - 3FFF</span></span>  <br/> |<span data-ttu-id="3eb84-158">Status 对象属性</span><span class="sxs-lookup"><span data-stu-id="3eb84-158">Status object properties</span></span>  <br/> |
   

