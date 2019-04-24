---
title: 邮件存储区功能
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d9167cd2-fc88-46b1-9a26-151955fb606c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 092cf56aea2e246fbb7ef2016a2662a1f67f889b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356901"
---
# <a name="message-store-features"></a><span data-ttu-id="a8ea4-103">邮件存储区功能</span><span class="sxs-lookup"><span data-stu-id="a8ea4-103">Message Store Features</span></span>

  
  
<span data-ttu-id="a8ea4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a8ea4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a8ea4-105">邮件存储提供程序比其他 MAPI 服务提供程序更复杂的是, 邮件存储提供程序提供了可实施的更广泛的可选功能。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-105">Message store providers are more complex than other MAPI service providers in that message store providers have a wider range of optional features they can implement.</span></span> <span data-ttu-id="a8ea4-106">邮件存储提供程序所需功能的列表相当短。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-106">The list of required features for a message store provider is fairly short.</span></span> <span data-ttu-id="a8ea4-107">但是, 典型的邮件存储提供程序将支持许多可选功能, 因为很多可选功能非常有用, 或者大多数 MAPI 客户端都是必需的。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-107">However, a typical message store provider will support a number of optional features, because many of the optional features are very useful or required by most MAPI clients.</span></span> <span data-ttu-id="a8ea4-108">下表列出了邮件存储提供程序可以实现的主要功能, 以及每个功能是否为所有邮件存储提供程序和默认邮件存储提供程序都是必需的还是可选的。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-108">The following table lists the major features that message store providers can implement and whether each feature is required or optional for all message store providers and for default message store providers.</span></span>
  
|<span data-ttu-id="a8ea4-109">**功能**</span><span class="sxs-lookup"><span data-stu-id="a8ea4-109">**Feature**</span></span>|<span data-ttu-id="a8ea4-110">**All**</span><span class="sxs-lookup"><span data-stu-id="a8ea4-110">**All**</span></span>|<span data-ttu-id="a8ea4-111">**Default**</span><span class="sxs-lookup"><span data-stu-id="a8ea4-111">**Default**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a8ea4-112">提供 MAPI 状态表的状态。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-112">Providing status with the MAPI status table.</span></span>  <br/> |<span data-ttu-id="a8ea4-113">必需</span><span class="sxs-lookup"><span data-stu-id="a8ea4-113">Required</span></span>  <br/> |<span data-ttu-id="a8ea4-114">必需</span><span class="sxs-lookup"><span data-stu-id="a8ea4-114">Required</span></span>  <br/> |
|<span data-ttu-id="a8ea4-115">实现 folder 对象。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-115">Implementing folder objects.</span></span>  <br/> |<span data-ttu-id="a8ea4-116">必需</span><span class="sxs-lookup"><span data-stu-id="a8ea4-116">Required</span></span>  <br/> |<span data-ttu-id="a8ea4-117">必需</span><span class="sxs-lookup"><span data-stu-id="a8ea4-117">Required</span></span>  <br/> |
|<span data-ttu-id="a8ea4-118">实现 message 对象。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-118">Implementing message objects.</span></span>  <br/> |<span data-ttu-id="a8ea4-119">必需</span><span class="sxs-lookup"><span data-stu-id="a8ea4-119">Required</span></span>  <br/> |<span data-ttu-id="a8ea4-120">必需</span><span class="sxs-lookup"><span data-stu-id="a8ea4-120">Required</span></span>  <br/> |
|<span data-ttu-id="a8ea4-121">提供已读和未读报表。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-121">Providing read and nonread reports.</span></span>  <br/> |<span data-ttu-id="a8ea4-122">必需</span><span class="sxs-lookup"><span data-stu-id="a8ea4-122">Required</span></span>  <br/> |<span data-ttu-id="a8ea4-123">必需</span><span class="sxs-lookup"><span data-stu-id="a8ea4-123">Required</span></span>  <br/> |
|<span data-ttu-id="a8ea4-124">提供进度接口。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-124">Providing a progress interface.</span></span>  <br/> |<span data-ttu-id="a8ea4-125">必需</span><span class="sxs-lookup"><span data-stu-id="a8ea4-125">Required</span></span>  <br/> |<span data-ttu-id="a8ea4-126">必需</span><span class="sxs-lookup"><span data-stu-id="a8ea4-126">Required</span></span>  <br/> |
|<span data-ttu-id="a8ea4-127">提供配置接口。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-127">Providing a configuration interface.</span></span>  <br/> |<span data-ttu-id="a8ea4-128">必需</span><span class="sxs-lookup"><span data-stu-id="a8ea4-128">Required</span></span>  <br/> |<span data-ttu-id="a8ea4-129">必需</span><span class="sxs-lookup"><span data-stu-id="a8ea4-129">Required</span></span>  <br/> |
|<span data-ttu-id="a8ea4-130">支持表单和视图支持关联的内容表。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-130">Supporting associated contents tables for form and view support.</span></span>  <br/> |<span data-ttu-id="a8ea4-131">可选</span><span class="sxs-lookup"><span data-stu-id="a8ea4-131">Optional</span></span>  <br/> |<span data-ttu-id="a8ea4-132">可选</span><span class="sxs-lookup"><span data-stu-id="a8ea4-132">Optional</span></span>  <br/> |
|<span data-ttu-id="a8ea4-133">使用邮件存储提供程序发送邮件。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-133">Sending messages with the message store provider.</span></span>  <br/> |<span data-ttu-id="a8ea4-134">可选</span><span class="sxs-lookup"><span data-stu-id="a8ea4-134">Optional</span></span>  <br/> |<span data-ttu-id="a8ea4-135">必需</span><span class="sxs-lookup"><span data-stu-id="a8ea4-135">Required</span></span>  <br/> |
|<span data-ttu-id="a8ea4-136">使用邮件存储提供程序接收邮件。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-136">Receiving messages with the message store provider.</span></span>  <br/> |<span data-ttu-id="a8ea4-137">可选</span><span class="sxs-lookup"><span data-stu-id="a8ea4-137">Optional</span></span>  <br/> |<span data-ttu-id="a8ea4-138">必需</span><span class="sxs-lookup"><span data-stu-id="a8ea4-138">Required</span></span>  <br/> |
|<span data-ttu-id="a8ea4-139">支持邮件附件。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-139">Supporting message attachments.</span></span>  <br/> |<span data-ttu-id="a8ea4-140">可选</span><span class="sxs-lookup"><span data-stu-id="a8ea4-140">Optional</span></span>  <br/> |<span data-ttu-id="a8ea4-141">可选</span><span class="sxs-lookup"><span data-stu-id="a8ea4-141">Optional</span></span>  <br/> |
|<span data-ttu-id="a8ea4-142">支持邮件的 rtf 格式。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-142">Supporting Rich Text Format for messages.</span></span>  <br/> |<span data-ttu-id="a8ea4-143">可选</span><span class="sxs-lookup"><span data-stu-id="a8ea4-143">Optional</span></span>  <br/> |<span data-ttu-id="a8ea4-144">可选</span><span class="sxs-lookup"><span data-stu-id="a8ea4-144">Optional</span></span>  <br/> |
|<span data-ttu-id="a8ea4-145">提供通知。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-145">Providing notifications.</span></span>  <br/> |<span data-ttu-id="a8ea4-146">可选</span><span class="sxs-lookup"><span data-stu-id="a8ea4-146">Optional</span></span>  <br/> |<span data-ttu-id="a8ea4-147">可选</span><span class="sxs-lookup"><span data-stu-id="a8ea4-147">Optional</span></span>  <br/> |
|<span data-ttu-id="a8ea4-148">支持搜索。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-148">Supporting searches.</span></span>  <br/> |<span data-ttu-id="a8ea4-149">可选</span><span class="sxs-lookup"><span data-stu-id="a8ea4-149">Optional</span></span>  <br/> |<span data-ttu-id="a8ea4-150">可选</span><span class="sxs-lookup"><span data-stu-id="a8ea4-150">Optional</span></span>  <br/> |
|<span data-ttu-id="a8ea4-151">支持紧密结合的邮件存储/传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-151">Supporting tightly coupled message store/transport providers.</span></span>  <br/> |<span data-ttu-id="a8ea4-152">可选</span><span class="sxs-lookup"><span data-stu-id="a8ea4-152">Optional</span></span>  <br/> |<span data-ttu-id="a8ea4-153">可选</span><span class="sxs-lookup"><span data-stu-id="a8ea4-153">Optional</span></span>  <br/> |
|<span data-ttu-id="a8ea4-154">支持不重复使用条目标识符。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-154">Supporting non-reuse of entry identifiers.</span></span>  <br/> |<span data-ttu-id="a8ea4-155">可选</span><span class="sxs-lookup"><span data-stu-id="a8ea4-155">Optional</span></span>  <br/> |<span data-ttu-id="a8ea4-156">可选</span><span class="sxs-lookup"><span data-stu-id="a8ea4-156">Optional</span></span>  <br/> |
   
<span data-ttu-id="a8ea4-157">通过在邮件存储对象的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中设置各种标志, 可以将许多可选功能公布到 MAPI 和客户端应用程序中。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-157">Many of the optional features can be advertised to MAPI and client applications by setting various flags in the message store object's **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property.</span></span> <span data-ttu-id="a8ea4-158">所需的功能没有与之关联的标志。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-158">The required features do not have flags associated with them.</span></span> <span data-ttu-id="a8ea4-159">**PR_STORE_SUPPORT_MASK**对邮件存储、文件夹和邮件对象是必需的。</span><span class="sxs-lookup"><span data-stu-id="a8ea4-159">**PR_STORE_SUPPORT_MASK** is required on message store, folder, and message objects.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a8ea4-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8ea4-160">See also</span></span>



[<span data-ttu-id="a8ea4-161">开发 MAPI 邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="a8ea4-161">Developing a MAPI Message Store Provider</span></span>](developing-a-mapi-message-store-provider.md)

