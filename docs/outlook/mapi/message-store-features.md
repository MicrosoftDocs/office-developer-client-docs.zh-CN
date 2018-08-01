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
ms.openlocfilehash: a26701b5b0f9f31277a442321e5e3016cfcb4d1e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776505"
---
# <a name="message-store-features"></a><span data-ttu-id="2fe1a-103">邮件存储区功能</span><span class="sxs-lookup"><span data-stu-id="2fe1a-103">Message Store Features</span></span>

  
  
<span data-ttu-id="2fe1a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2fe1a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2fe1a-105">消息存储提供程序是比其他 MAPI 服务提供商更复杂的这是的消息存储提供程序具有更广泛的可选它们可以实现的功能。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-105">Message store providers are more complex than other MAPI service providers in that message store providers have a wider range of optional features they can implement.</span></span> <span data-ttu-id="2fe1a-106">相当简短消息存储提供程序所需的功能的列表。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-106">The list of required features for a message store provider is fairly short.</span></span> <span data-ttu-id="2fe1a-107">但是，典型的消息存储提供程序将支持大量的可选功能，因为的许多可选功能都非常有用或必需的大多数 MAPI 客户端。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-107">However, a typical message store provider will support a number of optional features, because many of the optional features are very useful or required by most MAPI clients.</span></span> <span data-ttu-id="2fe1a-108">下表列出了消息存储提供程序可以实现和每个功能是否必需或可选的所有消息存储提供程序和默认消息存储提供程序的主要功能。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-108">The following table lists the major features that message store providers can implement and whether each feature is required or optional for all message store providers and for default message store providers.</span></span>
  
|<span data-ttu-id="2fe1a-109">**功能**</span><span class="sxs-lookup"><span data-stu-id="2fe1a-109">**Feature**</span></span>|<span data-ttu-id="2fe1a-110">**All**</span><span class="sxs-lookup"><span data-stu-id="2fe1a-110">**All**</span></span>|<span data-ttu-id="2fe1a-111">**Default**</span><span class="sxs-lookup"><span data-stu-id="2fe1a-111">**Default**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2fe1a-112">MAPI 状态表中提供状态。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-112">Providing status with the MAPI status table.</span></span>  <br/> |<span data-ttu-id="2fe1a-113">必需</span><span class="sxs-lookup"><span data-stu-id="2fe1a-113">Required</span></span>  <br/> |<span data-ttu-id="2fe1a-114">必需</span><span class="sxs-lookup"><span data-stu-id="2fe1a-114">Required</span></span>  <br/> |
|<span data-ttu-id="2fe1a-115">实现文件夹对象。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-115">Implementing folder objects.</span></span>  <br/> |<span data-ttu-id="2fe1a-116">必需</span><span class="sxs-lookup"><span data-stu-id="2fe1a-116">Required</span></span>  <br/> |<span data-ttu-id="2fe1a-117">必需</span><span class="sxs-lookup"><span data-stu-id="2fe1a-117">Required</span></span>  <br/> |
|<span data-ttu-id="2fe1a-118">实现消息对象。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-118">Implementing message objects.</span></span>  <br/> |<span data-ttu-id="2fe1a-119">必需</span><span class="sxs-lookup"><span data-stu-id="2fe1a-119">Required</span></span>  <br/> |<span data-ttu-id="2fe1a-120">必需</span><span class="sxs-lookup"><span data-stu-id="2fe1a-120">Required</span></span>  <br/> |
|<span data-ttu-id="2fe1a-121">提供读取和 nonread 报告。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-121">Providing read and nonread reports.</span></span>  <br/> |<span data-ttu-id="2fe1a-122">必需</span><span class="sxs-lookup"><span data-stu-id="2fe1a-122">Required</span></span>  <br/> |<span data-ttu-id="2fe1a-123">必需</span><span class="sxs-lookup"><span data-stu-id="2fe1a-123">Required</span></span>  <br/> |
|<span data-ttu-id="2fe1a-124">提供进度接口。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-124">Providing a progress interface.</span></span>  <br/> |<span data-ttu-id="2fe1a-125">必需</span><span class="sxs-lookup"><span data-stu-id="2fe1a-125">Required</span></span>  <br/> |<span data-ttu-id="2fe1a-126">必需</span><span class="sxs-lookup"><span data-stu-id="2fe1a-126">Required</span></span>  <br/> |
|<span data-ttu-id="2fe1a-127">提供配置界面。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-127">Providing a configuration interface.</span></span>  <br/> |<span data-ttu-id="2fe1a-128">必需</span><span class="sxs-lookup"><span data-stu-id="2fe1a-128">Required</span></span>  <br/> |<span data-ttu-id="2fe1a-129">必需</span><span class="sxs-lookup"><span data-stu-id="2fe1a-129">Required</span></span>  <br/> |
|<span data-ttu-id="2fe1a-130">表单和视图支持关联的内容表。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-130">Supporting associated contents tables for form and view support.</span></span>  <br/> |<span data-ttu-id="2fe1a-131">可选</span><span class="sxs-lookup"><span data-stu-id="2fe1a-131">Optional</span></span>  <br/> |<span data-ttu-id="2fe1a-132">可选</span><span class="sxs-lookup"><span data-stu-id="2fe1a-132">Optional</span></span>  <br/> |
|<span data-ttu-id="2fe1a-133">发送邮件的邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-133">Sending messages with the message store provider.</span></span>  <br/> |<span data-ttu-id="2fe1a-134">可选</span><span class="sxs-lookup"><span data-stu-id="2fe1a-134">Optional</span></span>  <br/> |<span data-ttu-id="2fe1a-135">必需</span><span class="sxs-lookup"><span data-stu-id="2fe1a-135">Required</span></span>  <br/> |
|<span data-ttu-id="2fe1a-136">消息存储提供程序接收消息。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-136">Receiving messages with the message store provider.</span></span>  <br/> |<span data-ttu-id="2fe1a-137">可选</span><span class="sxs-lookup"><span data-stu-id="2fe1a-137">Optional</span></span>  <br/> |<span data-ttu-id="2fe1a-138">必需</span><span class="sxs-lookup"><span data-stu-id="2fe1a-138">Required</span></span>  <br/> |
|<span data-ttu-id="2fe1a-139">支持邮件附件。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-139">Supporting message attachments.</span></span>  <br/> |<span data-ttu-id="2fe1a-140">可选</span><span class="sxs-lookup"><span data-stu-id="2fe1a-140">Optional</span></span>  <br/> |<span data-ttu-id="2fe1a-141">可选</span><span class="sxs-lookup"><span data-stu-id="2fe1a-141">Optional</span></span>  <br/> |
|<span data-ttu-id="2fe1a-142">支持的邮件的富文本格式。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-142">Supporting Rich Text Format for messages.</span></span>  <br/> |<span data-ttu-id="2fe1a-143">可选</span><span class="sxs-lookup"><span data-stu-id="2fe1a-143">Optional</span></span>  <br/> |<span data-ttu-id="2fe1a-144">可选</span><span class="sxs-lookup"><span data-stu-id="2fe1a-144">Optional</span></span>  <br/> |
|<span data-ttu-id="2fe1a-145">提供通知。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-145">Providing notifications.</span></span>  <br/> |<span data-ttu-id="2fe1a-146">可选</span><span class="sxs-lookup"><span data-stu-id="2fe1a-146">Optional</span></span>  <br/> |<span data-ttu-id="2fe1a-147">可选</span><span class="sxs-lookup"><span data-stu-id="2fe1a-147">Optional</span></span>  <br/> |
|<span data-ttu-id="2fe1a-148">支持搜索。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-148">Supporting searches.</span></span>  <br/> |<span data-ttu-id="2fe1a-149">可选</span><span class="sxs-lookup"><span data-stu-id="2fe1a-149">Optional</span></span>  <br/> |<span data-ttu-id="2fe1a-150">可选</span><span class="sxs-lookup"><span data-stu-id="2fe1a-150">Optional</span></span>  <br/> |
|<span data-ttu-id="2fe1a-151">支持紧密耦合消息存储/传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-151">Supporting tightly coupled message store/transport providers.</span></span>  <br/> |<span data-ttu-id="2fe1a-152">可选</span><span class="sxs-lookup"><span data-stu-id="2fe1a-152">Optional</span></span>  <br/> |<span data-ttu-id="2fe1a-153">可选</span><span class="sxs-lookup"><span data-stu-id="2fe1a-153">Optional</span></span>  <br/> |
|<span data-ttu-id="2fe1a-154">支持非重复使用的项标识符。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-154">Supporting non-reuse of entry identifiers.</span></span>  <br/> |<span data-ttu-id="2fe1a-155">可选</span><span class="sxs-lookup"><span data-stu-id="2fe1a-155">Optional</span></span>  <br/> |<span data-ttu-id="2fe1a-156">可选</span><span class="sxs-lookup"><span data-stu-id="2fe1a-156">Optional</span></span>  <br/> |
   
<span data-ttu-id="2fe1a-157">多个可选功能可以被播发到 MAPI，并通过设置各种标志邮件中的客户端应用程序存储对象的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-157">Many of the optional features can be advertised to MAPI and client applications by setting various flags in the message store object's **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property.</span></span> <span data-ttu-id="2fe1a-158">所需的功能不具有与其关联的标志。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-158">The required features do not have flags associated with them.</span></span> <span data-ttu-id="2fe1a-159">消息存储库、 文件夹和消息对象上需要**PR_STORE_SUPPORT_MASK** 。</span><span class="sxs-lookup"><span data-stu-id="2fe1a-159">**PR_STORE_SUPPORT_MASK** is required on message store, folder, and message objects.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2fe1a-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2fe1a-160">See also</span></span>



[<span data-ttu-id="2fe1a-161">开发 MAPI 邮件存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="2fe1a-161">Developing a MAPI Message Store Provider</span></span>](developing-a-mapi-message-store-provider.md)

