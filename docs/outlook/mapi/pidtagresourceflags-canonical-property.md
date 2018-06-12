---
title: PidTagResourceFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagResourceFlags
api_type:
- COM
ms.assetid: 69be9ad3-006a-459e-9cd4-eb3f609d71ad
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: dae917b3e536aee5f24879edc3ccf0736e7c9f34
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778222"
---
# <a name="pidtagresourceflags-canonical-property"></a><span data-ttu-id="386a5-103">PidTagResourceFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="386a5-103">PidTagResourceFlags Canonical Property</span></span>

  
  
<span data-ttu-id="386a5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="386a5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="386a5-105">包含消息服务和提供程序的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="386a5-105">Contains a bitmask of flags for message services and providers.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="386a5-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="386a5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="386a5-107">PR_RESOURCE_FLAGS</span><span class="sxs-lookup"><span data-stu-id="386a5-107">PR_RESOURCE_FLAGS</span></span>  <br/> |
|<span data-ttu-id="386a5-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="386a5-108">Identifier:</span></span>  <br/> |<span data-ttu-id="386a5-109">0x3009</span><span class="sxs-lookup"><span data-stu-id="386a5-109">0x3009</span></span>  <br/> |
|<span data-ttu-id="386a5-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="386a5-110">Data type:</span></span>  <br/> |<span data-ttu-id="386a5-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="386a5-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="386a5-112">区域：</span><span class="sxs-lookup"><span data-stu-id="386a5-112">Area:</span></span>  <br/> |<span data-ttu-id="386a5-113">常见的 MAPI</span><span class="sxs-lookup"><span data-stu-id="386a5-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="386a5-114">备注</span><span class="sxs-lookup"><span data-stu-id="386a5-114">Remarks</span></span>

<span data-ttu-id="386a5-115">此属性描述了消息服务、 服务提供商或状态对象的特征。</span><span class="sxs-lookup"><span data-stu-id="386a5-115">This property describes the characteristics of a message service, a service provider, or a status object.</span></span> <span data-ttu-id="386a5-116">为此属性设置的标志取决于其上下文。</span><span class="sxs-lookup"><span data-stu-id="386a5-116">The flags that are set for this property depend on its context.</span></span> <span data-ttu-id="386a5-117">例如，一些标志是仅供状态对象和其他标志仅用于邮件服务表中的列。</span><span class="sxs-lookup"><span data-stu-id="386a5-117">For example, some flags are valid only for status objects and other flags only for columns in the message service table.</span></span> 
  
<span data-ttu-id="386a5-118">标志是三个类： 静态和动态的可修改。</span><span class="sxs-lookup"><span data-stu-id="386a5-118">The flags are of three classes: static, modifiable, and dynamic.</span></span> <span data-ttu-id="386a5-119">通过 MAPI 从 MAPISVC 数据设置静态标志。INF 和永远不会改变。</span><span class="sxs-lookup"><span data-stu-id="386a5-119">Static flags are set by MAPI from data in MAPISVC.INF and never altered.</span></span> <span data-ttu-id="386a5-120">从 MAPISVC 通过 MAPI 设置可修改标志。INF 但可以随后更改。</span><span class="sxs-lookup"><span data-stu-id="386a5-120">Modifiable flags are set by MAPI from MAPISVC.INF but can be subsequently changed.</span></span> <span data-ttu-id="386a5-121">可以设置并通过 MAPI 方法来重置动态的标志。</span><span class="sxs-lookup"><span data-stu-id="386a5-121">Dynamic flags can be set and reset by MAPI methods.</span></span>
  
<span data-ttu-id="386a5-122">对于邮件服务，可以在此属性设置一个或多个以下标志：</span><span class="sxs-lookup"><span data-stu-id="386a5-122">For a message service, one or more of the following flags can be set in this property:</span></span>
  
<span data-ttu-id="386a5-123">SERVICE_CREATE_WITH_STORE</span><span class="sxs-lookup"><span data-stu-id="386a5-123">SERVICE_CREATE_WITH_STORE</span></span> 
  
> <span data-ttu-id="386a5-124">保留。</span><span class="sxs-lookup"><span data-stu-id="386a5-124">Reserved.</span></span> <span data-ttu-id="386a5-125">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="386a5-125">Do not use.</span></span>
    
<span data-ttu-id="386a5-126">SERVICE_DEFAULT_STORE</span><span class="sxs-lookup"><span data-stu-id="386a5-126">SERVICE_DEFAULT_STORE</span></span> 
  
> <span data-ttu-id="386a5-127">动态。</span><span class="sxs-lookup"><span data-stu-id="386a5-127">Dynamic.</span></span> <span data-ttu-id="386a5-128">邮件服务包含默认存储。</span><span class="sxs-lookup"><span data-stu-id="386a5-128">The message service contains the default store.</span></span> <span data-ttu-id="386a5-129">提示用户确认删除或移动配置文件利用此服务之前，应显示的用户界面。</span><span class="sxs-lookup"><span data-stu-id="386a5-129">A user interface should be displayed prompting the user for confirmation before deleting or moving this service out of the profile.</span></span> 
    
<span data-ttu-id="386a5-130">SERVICE_NO_PRIMARY_IDENTITY</span><span class="sxs-lookup"><span data-stu-id="386a5-130">SERVICE_NO_PRIMARY_IDENTITY</span></span> 
  
> <span data-ttu-id="386a5-131">静态。</span><span class="sxs-lookup"><span data-stu-id="386a5-131">Static.</span></span> <span data-ttu-id="386a5-132">应设置为指示无邮件服务中的提供程序可以使用提供标识服务级别标记。</span><span class="sxs-lookup"><span data-stu-id="386a5-132">The service level flag that should be set to indicate that none of the providers in the message service can be used to supply an identity.</span></span> <span data-ttu-id="386a5-133">此标志或 SERVICE_PRIMARY_IDENTITY 应设置，但不是能同时。</span><span class="sxs-lookup"><span data-stu-id="386a5-133">Either this flag or SERVICE_PRIMARY_IDENTITY should be set, but not both.</span></span>
    
<span data-ttu-id="386a5-134">SERVICE_PRIMARY_IDENTITY</span><span class="sxs-lookup"><span data-stu-id="386a5-134">SERVICE_PRIMARY_IDENTITY</span></span> 
  
> <span data-ttu-id="386a5-135">可修改。</span><span class="sxs-lookup"><span data-stu-id="386a5-135">Modifiable.</span></span> <span data-ttu-id="386a5-136">相应的消息服务包含一些主要标识用于此会话的提供程序。</span><span class="sxs-lookup"><span data-stu-id="386a5-136">The corresponding message service contains the provider used for the primary identity for this session.</span></span> <span data-ttu-id="386a5-137">使用[IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md)来设置此标志。</span><span class="sxs-lookup"><span data-stu-id="386a5-137">Use [IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md) to set this flag.</span></span> <span data-ttu-id="386a5-138">此标志或 SERVICE_NO_PRIMARY_IDENTITY 应设置，但不是能同时。</span><span class="sxs-lookup"><span data-stu-id="386a5-138">Either this flag or SERVICE_NO_PRIMARY_IDENTITY should be set, but not both.</span></span> 
    
<span data-ttu-id="386a5-139">SERVICE_SINGLE_COPY</span><span class="sxs-lookup"><span data-stu-id="386a5-139">SERVICE_SINGLE_COPY</span></span> 
  
> <span data-ttu-id="386a5-140">静态。</span><span class="sxs-lookup"><span data-stu-id="386a5-140">Static.</span></span> <span data-ttu-id="386a5-141">创建或将此消息服务复制到配置文件服务已存在任何尝试将失败。</span><span class="sxs-lookup"><span data-stu-id="386a5-141">Any attempt to create or copy this message service into a profile where the service already exists will fail.</span></span> <span data-ttu-id="386a5-142">若要创建的单个副本消息服务，请添加到 MAPISVC 中的服务一节的**PR_RESOURCE_FLAGS**属性。INF 和设置此标志。</span><span class="sxs-lookup"><span data-stu-id="386a5-142">To create a single copy message service add the **PR_RESOURCE_FLAGS** property to the service's section in MAPISVC.INF and set this flag.</span></span> 
    
<span data-ttu-id="386a5-143">对于服务提供商，一个或多个以下标志可以设置**PR_RESOURCE_FLAGS**中：</span><span class="sxs-lookup"><span data-stu-id="386a5-143">For a service provider, one or more of the following flags can be set in **PR_RESOURCE_FLAGS**:</span></span>
  
<span data-ttu-id="386a5-144">HOOK_INBOUND</span><span class="sxs-lookup"><span data-stu-id="386a5-144">HOOK_INBOUND</span></span> 
  
> <span data-ttu-id="386a5-145">静态。</span><span class="sxs-lookup"><span data-stu-id="386a5-145">Static.</span></span> <span data-ttu-id="386a5-146">后台处理程序挂接需要处理入站的邮件。</span><span class="sxs-lookup"><span data-stu-id="386a5-146">The spooler hook needs to process inbound messages.</span></span>
    
<span data-ttu-id="386a5-147">HOOK_OUTBOUND</span><span class="sxs-lookup"><span data-stu-id="386a5-147">HOOK_OUTBOUND</span></span> 
  
> <span data-ttu-id="386a5-148">静态。</span><span class="sxs-lookup"><span data-stu-id="386a5-148">Static.</span></span> <span data-ttu-id="386a5-149">后台处理程序挂接需要处理出站邮件。</span><span class="sxs-lookup"><span data-stu-id="386a5-149">The spooler hook needs to process outbound messages.</span></span> 
    
<span data-ttu-id="386a5-150">STATUS_DEFAULT_OUTBOUND</span><span class="sxs-lookup"><span data-stu-id="386a5-150">STATUS_DEFAULT_OUTBOUND</span></span> 
  
> <span data-ttu-id="386a5-151">可修改。</span><span class="sxs-lookup"><span data-stu-id="386a5-151">Modifiable.</span></span> <span data-ttu-id="386a5-152">如果配置文件包含此传输提供程序的多个实例，此标识应该应用于出站邮件。</span><span class="sxs-lookup"><span data-stu-id="386a5-152">This identity should be applied to outbound messages if the profile contains multiple instances of this transport provider.</span></span> <span data-ttu-id="386a5-153">如果在配置文件中显示单个传输提供程序的多个实例，则可以发生此错误。</span><span class="sxs-lookup"><span data-stu-id="386a5-153">This can happen if multiple instances of a single transport provider appear in the profile.</span></span>
    
<span data-ttu-id="386a5-154">STATUS_DEFAULT_STORE</span><span class="sxs-lookup"><span data-stu-id="386a5-154">STATUS_DEFAULT_STORE</span></span> 
  
> <span data-ttu-id="386a5-155">可修改。</span><span class="sxs-lookup"><span data-stu-id="386a5-155">Modifiable.</span></span> <span data-ttu-id="386a5-156">此消息存储是配置文件的默认存储。</span><span class="sxs-lookup"><span data-stu-id="386a5-156">This message store is the default store for the profile.</span></span> 
    
<span data-ttu-id="386a5-157">STATUS_NEED_IPM_TREE</span><span class="sxs-lookup"><span data-stu-id="386a5-157">STATUS_NEED_IPM_TREE</span></span> 
  
> <span data-ttu-id="386a5-158">动态。</span><span class="sxs-lookup"><span data-stu-id="386a5-158">Dynamic.</span></span> <span data-ttu-id="386a5-159">此消息存储，包括人际邮件 (IPM) 根文件夹中的标准文件夹尚未验证。</span><span class="sxs-lookup"><span data-stu-id="386a5-159">The standard folders in this message store, including the interpersonal message (IPM) root folder, have not yet been verified.</span></span> <span data-ttu-id="386a5-160">MAPI 设置，并清除此标志。</span><span class="sxs-lookup"><span data-stu-id="386a5-160">MAPI sets and clears this flag.</span></span> 
    
<span data-ttu-id="386a5-161">STATUS_NO_DEFAULT_STORE</span><span class="sxs-lookup"><span data-stu-id="386a5-161">STATUS_NO_DEFAULT_STORE</span></span> 
  
> <span data-ttu-id="386a5-162">静态。</span><span class="sxs-lookup"><span data-stu-id="386a5-162">Static.</span></span> <span data-ttu-id="386a5-163">此消息存储不能成为默认的邮件存储配置文件。</span><span class="sxs-lookup"><span data-stu-id="386a5-163">This message store is incapable of becoming the default message store for the profile.</span></span>
    
<span data-ttu-id="386a5-164">STATUS_NO_PRIMARY_IDENTITY</span><span class="sxs-lookup"><span data-stu-id="386a5-164">STATUS_NO_PRIMARY_IDENTITY</span></span> 
  
> <span data-ttu-id="386a5-165">静态。</span><span class="sxs-lookup"><span data-stu-id="386a5-165">Static.</span></span> <span data-ttu-id="386a5-166">此提供程序不提供其状态行中的标识。</span><span class="sxs-lookup"><span data-stu-id="386a5-166">This provider does not furnish an identity in its status row.</span></span> <span data-ttu-id="386a5-167">必须设置此标志或 STATUS_PRIMARY_IDENTITY。</span><span class="sxs-lookup"><span data-stu-id="386a5-167">Either this flag or STATUS_PRIMARY_IDENTITY must be set.</span></span>
    
<span data-ttu-id="386a5-168">STATUS_OWN_STORE</span><span class="sxs-lookup"><span data-stu-id="386a5-168">STATUS_OWN_STORE</span></span> 
  
> <span data-ttu-id="386a5-169">静态。</span><span class="sxs-lookup"><span data-stu-id="386a5-169">Static.</span></span> <span data-ttu-id="386a5-170">此传输提供程序紧密结合的消息存储，并提供其状态行中的**PR_OWN_STORE_ENTRYID** ([PidTagOwnStoreEntryId](pidtagownstoreentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="386a5-170">This transport provider is tightly coupled with a message store and furnishes the **PR_OWN_STORE_ENTRYID** ([PidTagOwnStoreEntryId](pidtagownstoreentryid-canonical-property.md)) property in its status row.</span></span>
    
<span data-ttu-id="386a5-171">STATUS_PRIMARY_IDENTITY</span><span class="sxs-lookup"><span data-stu-id="386a5-171">STATUS_PRIMARY_IDENTITY</span></span> 
  
> <span data-ttu-id="386a5-172">可修改。</span><span class="sxs-lookup"><span data-stu-id="386a5-172">Modifiable.</span></span> <span data-ttu-id="386a5-173">此提供程序提供的主要标识会话;从[IMAPISession::QueryIdentity](imapisession-queryidentity.md)返回 furnishing 标识的对象的项标识符。</span><span class="sxs-lookup"><span data-stu-id="386a5-173">This provider furnishes the primary identity for the session; the entry identifier for the object furnishing the identity is returned from [IMAPISession::QueryIdentity](imapisession-queryidentity.md).</span></span> <span data-ttu-id="386a5-174">必须设置此标志或**STATUS_NO_PRIMARY_IDENTITY** 。</span><span class="sxs-lookup"><span data-stu-id="386a5-174">Either this flag or **STATUS_NO_PRIMARY_IDENTITY** must be set.</span></span> 
    
<span data-ttu-id="386a5-175">STATUS_PRIMARY_STORE</span><span class="sxs-lookup"><span data-stu-id="386a5-175">STATUS_PRIMARY_STORE</span></span> 
  
> <span data-ttu-id="386a5-176">可修改。</span><span class="sxs-lookup"><span data-stu-id="386a5-176">Modifiable.</span></span> <span data-ttu-id="386a5-177">此消息存储是用于客户端应用程序登录。</span><span class="sxs-lookup"><span data-stu-id="386a5-177">This message store is to be used when a client application logs on.</span></span> <span data-ttu-id="386a5-178">打开后，应将此存储设置为默认配置文件存储。</span><span class="sxs-lookup"><span data-stu-id="386a5-178">Once opened, this store should be set as the default store for the profile.</span></span> 
    
<span data-ttu-id="386a5-179">STATUS_SECONDARY_STORE</span><span class="sxs-lookup"><span data-stu-id="386a5-179">STATUS_SECONDARY_STORE</span></span> 
  
> <span data-ttu-id="386a5-180">可修改。</span><span class="sxs-lookup"><span data-stu-id="386a5-180">Modifiable.</span></span> <span data-ttu-id="386a5-181">此消息存储是用于如果客户端应用程序在登录时，主存储不可用。</span><span class="sxs-lookup"><span data-stu-id="386a5-181">This message store is to be used if the primary store is not available when a client application logs on.</span></span> <span data-ttu-id="386a5-182">打开后，应将此存储设置为默认配置文件存储。</span><span class="sxs-lookup"><span data-stu-id="386a5-182">Once opened, this store should be set as the default store for the profile.</span></span> 
    
<span data-ttu-id="386a5-183">STATUS_SIMPLE_STORE</span><span class="sxs-lookup"><span data-stu-id="386a5-183">STATUS_SIMPLE_STORE</span></span> 
  
> <span data-ttu-id="386a5-184">动态。</span><span class="sxs-lookup"><span data-stu-id="386a5-184">Dynamic.</span></span> <span data-ttu-id="386a5-185">此消息存储将使用任务的简单 MAPI 作为其默认邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="386a5-185">This message store will be used by Simple MAPI as its default message store.</span></span>
    
<span data-ttu-id="386a5-186">STATUS_TEMP_SECTION</span><span class="sxs-lookup"><span data-stu-id="386a5-186">STATUS_TEMP_SECTION</span></span> 
  
> <span data-ttu-id="386a5-187">动态。</span><span class="sxs-lookup"><span data-stu-id="386a5-187">Dynamic.</span></span> <span data-ttu-id="386a5-188">此消息存储不应该发布消息存储表中，注销后将删除其从配置文件。</span><span class="sxs-lookup"><span data-stu-id="386a5-188">This message store should not be published in the message store table and will be deleted from the profile after logoff.</span></span> 
    
<span data-ttu-id="386a5-189">STATUS_XP_PREFER_LAST</span><span class="sxs-lookup"><span data-stu-id="386a5-189">STATUS_XP_PREFER_LAST</span></span> 
  
> <span data-ttu-id="386a5-190">静态。</span><span class="sxs-lookup"><span data-stu-id="386a5-190">Static.</span></span> <span data-ttu-id="386a5-191">此传输要求选择多个传输提供程序时能够将邮件传输发送消息的最后一个传输。</span><span class="sxs-lookup"><span data-stu-id="386a5-191">This transport expects to be the last transport selected to send a message when multiple transport providers are able to transmit the message.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="386a5-192">相关资源</span><span class="sxs-lookup"><span data-stu-id="386a5-192">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="386a5-193">头文件</span><span class="sxs-lookup"><span data-stu-id="386a5-193">Header files</span></span>

<span data-ttu-id="386a5-194">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="386a5-194">Mapidefs.h</span></span>
  
> <span data-ttu-id="386a5-195">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="386a5-195">Provides data type definitions.</span></span>
    
<span data-ttu-id="386a5-196">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="386a5-196">Mapitags.h</span></span>
  
> <span data-ttu-id="386a5-197">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="386a5-197">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="386a5-198">另请参阅</span><span class="sxs-lookup"><span data-stu-id="386a5-198">See also</span></span>



[<span data-ttu-id="386a5-199">IMsgServiceAdmin::MsgServiceTransportOrder</span><span class="sxs-lookup"><span data-stu-id="386a5-199">IMsgServiceAdmin::MsgServiceTransportOrder</span></span>](imsgserviceadmin-msgservicetransportorder.md)
  
[<span data-ttu-id="386a5-200">PidTagIdentityEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="386a5-200">PidTagIdentityEntryId Canonical Property</span></span>](pidtagidentityentryid-canonical-property.md)


[<span data-ttu-id="386a5-201">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="386a5-201">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="386a5-202">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="386a5-202">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="386a5-203">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="386a5-203">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="386a5-204">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="386a5-204">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

