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
# <a name="property-identifier-ranges"></a><span data-ttu-id="51276-103">属性标识符范围</span><span class="sxs-lookup"><span data-stu-id="51276-103">Property Identifier Ranges</span></span>

  
  
<span data-ttu-id="51276-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="51276-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="51276-105">下表汇总了属性标识符的不同范围, 描述了每个范围中的属性的所有者。</span><span class="sxs-lookup"><span data-stu-id="51276-105">The following table summarizes the different ranges for property identifiers, describing the owner for the properties in each range.</span></span>
  
|<span data-ttu-id="51276-106">**标识符范围**</span><span class="sxs-lookup"><span data-stu-id="51276-106">**Identifier range**</span></span>|<span data-ttu-id="51276-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="51276-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="51276-108">0000</span><span class="sxs-lookup"><span data-stu-id="51276-108">0000</span></span>  <br/> |<span data-ttu-id="51276-109">由 MAPI 为特殊值**PR_NULL**保留。</span><span class="sxs-lookup"><span data-stu-id="51276-109">Reserved by MAPI for the special value **PR_NULL**.</span></span>  <br/> |
|<span data-ttu-id="51276-110">0001-0BFF</span><span class="sxs-lookup"><span data-stu-id="51276-110">0001 - 0BFF</span></span>  <br/> |<span data-ttu-id="51276-111">由 MAPI 定义的邮件信封属性。</span><span class="sxs-lookup"><span data-stu-id="51276-111">Message envelope properties defined by MAPI.</span></span>  <br/> |
|<span data-ttu-id="51276-112">0C00-0DFF</span><span class="sxs-lookup"><span data-stu-id="51276-112">0C00 - 0DFF</span></span>  <br/> |<span data-ttu-id="51276-113">MAPI 定义的收件人属性。</span><span class="sxs-lookup"><span data-stu-id="51276-113">Recipient properties defined by MAPI.</span></span>  <br/> |
|<span data-ttu-id="51276-114">0E00-0FFF</span><span class="sxs-lookup"><span data-stu-id="51276-114">0E00 - 0FFF</span></span>  <br/> |<span data-ttu-id="51276-115">由 MAPI 定义的非传输邮件属性。</span><span class="sxs-lookup"><span data-stu-id="51276-115">Non-transmittable message properties defined by MAPI.</span></span>  <br/> |
|<span data-ttu-id="51276-116">1000-2FFF</span><span class="sxs-lookup"><span data-stu-id="51276-116">1000 - 2FFF</span></span>  <br/> |<span data-ttu-id="51276-117">MAPI 定义的邮件内容属性。</span><span class="sxs-lookup"><span data-stu-id="51276-117">Message content properties defined by MAPI.</span></span>  <br/> |
|<span data-ttu-id="51276-118">3000-3FFF</span><span class="sxs-lookup"><span data-stu-id="51276-118">3000 - 3FFF</span></span>  <br/> |<span data-ttu-id="51276-119">除 MAPI 定义的邮件和收件人以外的其他对象的属性。</span><span class="sxs-lookup"><span data-stu-id="51276-119">Properties for objects other than messages and recipients defined by MAPI.</span></span>  <br/> |
|<span data-ttu-id="51276-120">4000-57FF</span><span class="sxs-lookup"><span data-stu-id="51276-120">4000 - 57FF</span></span>  <br/> |<span data-ttu-id="51276-121">由传输提供程序定义的邮件信封属性。</span><span class="sxs-lookup"><span data-stu-id="51276-121">Message envelope properties defined by transport providers.</span></span>  <br/> |
|<span data-ttu-id="51276-122">5800-5FFF</span><span class="sxs-lookup"><span data-stu-id="51276-122">5800 - 5FFF</span></span>  <br/> |<span data-ttu-id="51276-123">由传输和通讯簿提供程序定义的收件人属性。</span><span class="sxs-lookup"><span data-stu-id="51276-123">Recipient properties defined by transport and address book providers.</span></span>  <br/> |
|<span data-ttu-id="51276-124">6000-65FF</span><span class="sxs-lookup"><span data-stu-id="51276-124">6000 - 65FF</span></span>  <br/> |<span data-ttu-id="51276-125">由客户端定义的非传输邮件属性。</span><span class="sxs-lookup"><span data-stu-id="51276-125">Non-transmittable message properties defined by clients.</span></span>  <br/> |
|<span data-ttu-id="51276-126">6600-67FF</span><span class="sxs-lookup"><span data-stu-id="51276-126">6600 - 67FF</span></span>  <br/> |<span data-ttu-id="51276-127">由服务提供程序定义的非传输属性。</span><span class="sxs-lookup"><span data-stu-id="51276-127">Non-transmittable properties defined by a service provider.</span></span> <span data-ttu-id="51276-128">这些属性可对用户可见或不可见。</span><span class="sxs-lookup"><span data-stu-id="51276-128">These properties can be visible or invisible to users.</span></span>  <br/> |
|<span data-ttu-id="51276-129">6800-7BFF</span><span class="sxs-lookup"><span data-stu-id="51276-129">6800 - 7BFF</span></span>  <br/> |<span data-ttu-id="51276-130">由这些类的创建者定义的自定义邮件类的邮件内容属性。</span><span class="sxs-lookup"><span data-stu-id="51276-130">Message content properties for custom message classes defined by creators of those classes.</span></span>  <br/> |
|<span data-ttu-id="51276-131">7C00-7FFF</span><span class="sxs-lookup"><span data-stu-id="51276-131">7C00 - 7FFF</span></span>  <br/> |<span data-ttu-id="51276-132">由这些类的创建者定义的自定义邮件类的非传输属性。</span><span class="sxs-lookup"><span data-stu-id="51276-132">Non-transmittable properties for custom message classes defined by creators of those classes.</span></span>  <br/> |
|<span data-ttu-id="51276-133">8000-FFFE</span><span class="sxs-lookup"><span data-stu-id="51276-133">8000 - FFFE</span></span>  <br/> |<span data-ttu-id="51276-134">由由 name 通过[IMAPIProp:: GetNamesFromIDs](imapiprop-getnamesfromids.md)和[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)方法标识的客户端和偶尔服务提供程序定义的属性。</span><span class="sxs-lookup"><span data-stu-id="51276-134">Properties defined by clients and occasionally service providers that are identified by name through the [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) and [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) methods.</span></span>  <br/> |
|<span data-ttu-id="51276-135">FFFF</span><span class="sxs-lookup"><span data-stu-id="51276-135">FFFF</span></span>  <br/> |<span data-ttu-id="51276-136">由 MAPI 为特殊错误值保留 PROP_ID_INVALID。</span><span class="sxs-lookup"><span data-stu-id="51276-136">Reserved by MAPI for the special error value PROP_ID_INVALID.</span></span>  <br/> |
   
<span data-ttu-id="51276-137">3000和3FFF 之间的范围是为与邮件或收件人不相关的属性而预留的。</span><span class="sxs-lookup"><span data-stu-id="51276-137">The range between 3000 and 3FFF is reserved for properties that are not related to either messages or recipients.</span></span> <span data-ttu-id="51276-138">MAPI 按对象类型将此范围划分为子范围;下表显示了此进一步细目。</span><span class="sxs-lookup"><span data-stu-id="51276-138">MAPI divides this range into sub-ranges by types of object; the following table shows this further breakdown.</span></span> 
  
|<span data-ttu-id="51276-139">**标识符范围**</span><span class="sxs-lookup"><span data-stu-id="51276-139">**Identifier range**</span></span>|<span data-ttu-id="51276-140">**属性的类型**</span><span class="sxs-lookup"><span data-stu-id="51276-140">**Type of property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="51276-141">3000-33FF</span><span class="sxs-lookup"><span data-stu-id="51276-141">3000 - 33FF</span></span>  <br/> |<span data-ttu-id="51276-142">出现在多个对象 (如**PR_DISPLAY_NAME**和**PR_ENTRYID**) 上的常见属性。</span><span class="sxs-lookup"><span data-stu-id="51276-142">Common properties that appear on multiple objects, such as **PR_DISPLAY_NAME** and **PR_ENTRYID**.</span></span>  <br/> |
|<span data-ttu-id="51276-143">3400-35FF</span><span class="sxs-lookup"><span data-stu-id="51276-143">3400 - 35FF</span></span>  <br/> |<span data-ttu-id="51276-144">邮件存储库属性</span><span class="sxs-lookup"><span data-stu-id="51276-144">Message store properties</span></span>  <br/> |
|<span data-ttu-id="51276-145">3600-36FF</span><span class="sxs-lookup"><span data-stu-id="51276-145">3600 - 36FF</span></span>  <br/> |<span data-ttu-id="51276-146">文件夹和通讯簿容器属性</span><span class="sxs-lookup"><span data-stu-id="51276-146">Folder and address book container properties</span></span>  <br/> |
|<span data-ttu-id="51276-147">3700-38FF</span><span class="sxs-lookup"><span data-stu-id="51276-147">3700 - 38FF</span></span>  <br/> |<span data-ttu-id="51276-148">附件属性</span><span class="sxs-lookup"><span data-stu-id="51276-148">Attachment properties</span></span>  <br/> |
|<span data-ttu-id="51276-149">3900-39FF</span><span class="sxs-lookup"><span data-stu-id="51276-149">3900 - 39FF</span></span>  <br/> |<span data-ttu-id="51276-150">通讯簿属性</span><span class="sxs-lookup"><span data-stu-id="51276-150">Address book properties</span></span>  <br/> |
|<span data-ttu-id="51276-151">3A00-3BFF</span><span class="sxs-lookup"><span data-stu-id="51276-151">3A00 - 3BFF</span></span>  <br/> |<span data-ttu-id="51276-152">邮件用户属性</span><span class="sxs-lookup"><span data-stu-id="51276-152">Messaging user properties</span></span>  <br/> |
|<span data-ttu-id="51276-153">3C00-3CFF</span><span class="sxs-lookup"><span data-stu-id="51276-153">3C00 - 3CFF</span></span>  <br/> |<span data-ttu-id="51276-154">通讯组列表属性</span><span class="sxs-lookup"><span data-stu-id="51276-154">Distribution list properties</span></span>  <br/> |
|<span data-ttu-id="51276-155">3D00-3DFF</span><span class="sxs-lookup"><span data-stu-id="51276-155">3D00 - 3DFF</span></span>  <br/> |<span data-ttu-id="51276-156">配置文件属性</span><span class="sxs-lookup"><span data-stu-id="51276-156">Profile properties</span></span>  <br/> |
|<span data-ttu-id="51276-157">3E00-3FFF</span><span class="sxs-lookup"><span data-stu-id="51276-157">3E00 - 3FFF</span></span>  <br/> |<span data-ttu-id="51276-158">Status 对象属性</span><span class="sxs-lookup"><span data-stu-id="51276-158">Status object properties</span></span>  <br/> |
   

