---
title: 邮件存储功能
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d9167cd2-fc88-46b1-9a26-151955fb606c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 092cf56aea2e246fbb7ef2016a2662a1f67f889b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439518"
---
# <a name="message-store-features"></a><span data-ttu-id="3a2c6-103">邮件存储功能</span><span class="sxs-lookup"><span data-stu-id="3a2c6-103">Message Store Features</span></span>

  
  
<span data-ttu-id="3a2c6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3a2c6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3a2c6-105">邮件存储提供程序比其他 MAPI 服务提供商更复杂，因为邮件存储提供程序可以实施更广泛的可选功能。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-105">Message store providers are more complex than other MAPI service providers in that message store providers have a wider range of optional features they can implement.</span></span> <span data-ttu-id="3a2c6-106">邮件存储提供程序所需的功能列表相当短。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-106">The list of required features for a message store provider is fairly short.</span></span> <span data-ttu-id="3a2c6-107">但是，典型的邮件存储提供程序将支持许多可选功能，因为大多数 MAPI 客户端都非常有用或需要许多可选功能。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-107">However, a typical message store provider will support a number of optional features, because many of the optional features are very useful or required by most MAPI clients.</span></span> <span data-ttu-id="3a2c6-108">下表列出了邮件存储提供程序可以实现的主要功能，以及每个功能对于所有邮件存储提供程序和默认邮件存储提供程序是必需还是可选。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-108">The following table lists the major features that message store providers can implement and whether each feature is required or optional for all message store providers and for default message store providers.</span></span>
  
|<span data-ttu-id="3a2c6-109">**功能**</span><span class="sxs-lookup"><span data-stu-id="3a2c6-109">**Feature**</span></span>|<span data-ttu-id="3a2c6-110">**全部**</span><span class="sxs-lookup"><span data-stu-id="3a2c6-110">**All**</span></span>|<span data-ttu-id="3a2c6-111">**默认**</span><span class="sxs-lookup"><span data-stu-id="3a2c6-111">**Default**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3a2c6-112">通过 MAPI 状态表提供状态。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-112">Providing status with the MAPI status table.</span></span>  <br/> |<span data-ttu-id="3a2c6-113">必需</span><span class="sxs-lookup"><span data-stu-id="3a2c6-113">Required</span></span>  <br/> |<span data-ttu-id="3a2c6-114">必需</span><span class="sxs-lookup"><span data-stu-id="3a2c6-114">Required</span></span>  <br/> |
|<span data-ttu-id="3a2c6-115">实现文件夹对象。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-115">Implementing folder objects.</span></span>  <br/> |<span data-ttu-id="3a2c6-116">必需</span><span class="sxs-lookup"><span data-stu-id="3a2c6-116">Required</span></span>  <br/> |<span data-ttu-id="3a2c6-117">必需</span><span class="sxs-lookup"><span data-stu-id="3a2c6-117">Required</span></span>  <br/> |
|<span data-ttu-id="3a2c6-118">实现 message 对象。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-118">Implementing message objects.</span></span>  <br/> |<span data-ttu-id="3a2c6-119">必需</span><span class="sxs-lookup"><span data-stu-id="3a2c6-119">Required</span></span>  <br/> |<span data-ttu-id="3a2c6-120">必需</span><span class="sxs-lookup"><span data-stu-id="3a2c6-120">Required</span></span>  <br/> |
|<span data-ttu-id="3a2c6-121">提供已读和未读报表。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-121">Providing read and nonread reports.</span></span>  <br/> |<span data-ttu-id="3a2c6-122">必需</span><span class="sxs-lookup"><span data-stu-id="3a2c6-122">Required</span></span>  <br/> |<span data-ttu-id="3a2c6-123">必需</span><span class="sxs-lookup"><span data-stu-id="3a2c6-123">Required</span></span>  <br/> |
|<span data-ttu-id="3a2c6-124">提供进度接口。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-124">Providing a progress interface.</span></span>  <br/> |<span data-ttu-id="3a2c6-125">必需</span><span class="sxs-lookup"><span data-stu-id="3a2c6-125">Required</span></span>  <br/> |<span data-ttu-id="3a2c6-126">必需</span><span class="sxs-lookup"><span data-stu-id="3a2c6-126">Required</span></span>  <br/> |
|<span data-ttu-id="3a2c6-127">提供配置接口。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-127">Providing a configuration interface.</span></span>  <br/> |<span data-ttu-id="3a2c6-128">必需</span><span class="sxs-lookup"><span data-stu-id="3a2c6-128">Required</span></span>  <br/> |<span data-ttu-id="3a2c6-129">必需</span><span class="sxs-lookup"><span data-stu-id="3a2c6-129">Required</span></span>  <br/> |
|<span data-ttu-id="3a2c6-130">支持表单和视图支持的关联内容表。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-130">Supporting associated contents tables for form and view support.</span></span>  <br/> |<span data-ttu-id="3a2c6-131">可选</span><span class="sxs-lookup"><span data-stu-id="3a2c6-131">Optional</span></span>  <br/> |<span data-ttu-id="3a2c6-132">可选</span><span class="sxs-lookup"><span data-stu-id="3a2c6-132">Optional</span></span>  <br/> |
|<span data-ttu-id="3a2c6-133">使用邮件存储提供程序发送邮件。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-133">Sending messages with the message store provider.</span></span>  <br/> |<span data-ttu-id="3a2c6-134">可选</span><span class="sxs-lookup"><span data-stu-id="3a2c6-134">Optional</span></span>  <br/> |<span data-ttu-id="3a2c6-135">必需</span><span class="sxs-lookup"><span data-stu-id="3a2c6-135">Required</span></span>  <br/> |
|<span data-ttu-id="3a2c6-136">使用邮件存储提供程序接收邮件。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-136">Receiving messages with the message store provider.</span></span>  <br/> |<span data-ttu-id="3a2c6-137">可选</span><span class="sxs-lookup"><span data-stu-id="3a2c6-137">Optional</span></span>  <br/> |<span data-ttu-id="3a2c6-138">必需</span><span class="sxs-lookup"><span data-stu-id="3a2c6-138">Required</span></span>  <br/> |
|<span data-ttu-id="3a2c6-139">支持邮件附件。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-139">Supporting message attachments.</span></span>  <br/> |<span data-ttu-id="3a2c6-140">可选</span><span class="sxs-lookup"><span data-stu-id="3a2c6-140">Optional</span></span>  <br/> |<span data-ttu-id="3a2c6-141">可选</span><span class="sxs-lookup"><span data-stu-id="3a2c6-141">Optional</span></span>  <br/> |
|<span data-ttu-id="3a2c6-142">支持邮件的富文本格式。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-142">Supporting Rich Text Format for messages.</span></span>  <br/> |<span data-ttu-id="3a2c6-143">可选</span><span class="sxs-lookup"><span data-stu-id="3a2c6-143">Optional</span></span>  <br/> |<span data-ttu-id="3a2c6-144">可选</span><span class="sxs-lookup"><span data-stu-id="3a2c6-144">Optional</span></span>  <br/> |
|<span data-ttu-id="3a2c6-145">提供通知。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-145">Providing notifications.</span></span>  <br/> |<span data-ttu-id="3a2c6-146">可选</span><span class="sxs-lookup"><span data-stu-id="3a2c6-146">Optional</span></span>  <br/> |<span data-ttu-id="3a2c6-147">可选</span><span class="sxs-lookup"><span data-stu-id="3a2c6-147">Optional</span></span>  <br/> |
|<span data-ttu-id="3a2c6-148">支持搜索。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-148">Supporting searches.</span></span>  <br/> |<span data-ttu-id="3a2c6-149">可选</span><span class="sxs-lookup"><span data-stu-id="3a2c6-149">Optional</span></span>  <br/> |<span data-ttu-id="3a2c6-150">可选</span><span class="sxs-lookup"><span data-stu-id="3a2c6-150">Optional</span></span>  <br/> |
|<span data-ttu-id="3a2c6-151">支持紧密耦合的邮件存储/传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-151">Supporting tightly coupled message store/transport providers.</span></span>  <br/> |<span data-ttu-id="3a2c6-152">可选</span><span class="sxs-lookup"><span data-stu-id="3a2c6-152">Optional</span></span>  <br/> |<span data-ttu-id="3a2c6-153">可选</span><span class="sxs-lookup"><span data-stu-id="3a2c6-153">Optional</span></span>  <br/> |
|<span data-ttu-id="3a2c6-154">支持不重复使用条目标识符。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-154">Supporting non-reuse of entry identifiers.</span></span>  <br/> |<span data-ttu-id="3a2c6-155">可选</span><span class="sxs-lookup"><span data-stu-id="3a2c6-155">Optional</span></span>  <br/> |<span data-ttu-id="3a2c6-156">可选</span><span class="sxs-lookup"><span data-stu-id="3a2c6-156">Optional</span></span>  <br/> |
   
<span data-ttu-id="3a2c6-157">许多可选功能可以通过在邮件存储对象的 **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md) 属性中设置各种标志来向 MAPI 和客户端应用程序) 。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-157">Many of the optional features can be advertised to MAPI and client applications by setting various flags in the message store object's **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property.</span></span> <span data-ttu-id="3a2c6-158">所需功能没有与其关联的标志。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-158">The required features do not have flags associated with them.</span></span> <span data-ttu-id="3a2c6-159">**PR_STORE_SUPPORT_MASK** 邮件存储、文件夹和邮件对象上必须具有此权限。</span><span class="sxs-lookup"><span data-stu-id="3a2c6-159">**PR_STORE_SUPPORT_MASK** is required on message store, folder, and message objects.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3a2c6-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a2c6-160">See also</span></span>



[<span data-ttu-id="3a2c6-161">开发 MAPI 邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="3a2c6-161">Developing a MAPI Message Store Provider</span></span>](developing-a-mapi-message-store-provider.md)

