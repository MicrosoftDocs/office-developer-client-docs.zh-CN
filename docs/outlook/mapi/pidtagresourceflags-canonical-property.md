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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2fb9eed0beaf7269ac90a021dae650355484ebc2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436228"
---
# <a name="pidtagresourceflags-canonical-property"></a><span data-ttu-id="fe78d-103">PidTagResourceFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="fe78d-103">PidTagResourceFlags Canonical Property</span></span>

  
  
<span data-ttu-id="fe78d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fe78d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fe78d-105">包含邮件服务和提供程序标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="fe78d-105">Contains a bitmask of flags for message services and providers.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fe78d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="fe78d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="fe78d-107">PR_RESOURCE_FLAGS</span><span class="sxs-lookup"><span data-stu-id="fe78d-107">PR_RESOURCE_FLAGS</span></span>  <br/> |
|<span data-ttu-id="fe78d-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="fe78d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="fe78d-109">0x3009</span><span class="sxs-lookup"><span data-stu-id="fe78d-109">0x3009</span></span>  <br/> |
|<span data-ttu-id="fe78d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fe78d-110">Data type:</span></span>  <br/> |<span data-ttu-id="fe78d-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="fe78d-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="fe78d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="fe78d-112">Area:</span></span>  <br/> |<span data-ttu-id="fe78d-113">MAPI common</span><span class="sxs-lookup"><span data-stu-id="fe78d-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fe78d-114">备注</span><span class="sxs-lookup"><span data-stu-id="fe78d-114">Remarks</span></span>

<span data-ttu-id="fe78d-115">此属性描述邮件服务、服务提供商或状态对象的特征。</span><span class="sxs-lookup"><span data-stu-id="fe78d-115">This property describes the characteristics of a message service, a service provider, or a status object.</span></span> <span data-ttu-id="fe78d-116">为此属性设置的标志取决于其上下文。</span><span class="sxs-lookup"><span data-stu-id="fe78d-116">The flags that are set for this property depend on its context.</span></span> <span data-ttu-id="fe78d-117">例如，某些标志仅对状态对象有效，其他标志仅对邮件服务表中的列有效。</span><span class="sxs-lookup"><span data-stu-id="fe78d-117">For example, some flags are valid only for status objects and other flags only for columns in the message service table.</span></span> 
  
<span data-ttu-id="fe78d-118">标志有三个类：静态、可修改和动态。</span><span class="sxs-lookup"><span data-stu-id="fe78d-118">The flags are of three classes: static, modifiable, and dynamic.</span></span> <span data-ttu-id="fe78d-119">静态标志由 MAPI 从 MAPISVC 数据设置。INF，从不更改。</span><span class="sxs-lookup"><span data-stu-id="fe78d-119">Static flags are set by MAPI from data in MAPISVC.INF and never altered.</span></span> <span data-ttu-id="fe78d-120">可修改标志由 MAPISVC 中的 MAPI 设置。INF，但可以随后更改。</span><span class="sxs-lookup"><span data-stu-id="fe78d-120">Modifiable flags are set by MAPI from MAPISVC.INF but can be subsequently changed.</span></span> <span data-ttu-id="fe78d-121">可通过 MAPI 方法设置和重置动态标志。</span><span class="sxs-lookup"><span data-stu-id="fe78d-121">Dynamic flags can be set and reset by MAPI methods.</span></span>
  
<span data-ttu-id="fe78d-122">对于邮件服务，可以在此属性中设置以下一个或多个标志：</span><span class="sxs-lookup"><span data-stu-id="fe78d-122">For a message service, one or more of the following flags can be set in this property:</span></span>
  
<span data-ttu-id="fe78d-123">SERVICE_CREATE_WITH_STORE</span><span class="sxs-lookup"><span data-stu-id="fe78d-123">SERVICE_CREATE_WITH_STORE</span></span> 
  
> <span data-ttu-id="fe78d-124">保留。</span><span class="sxs-lookup"><span data-stu-id="fe78d-124">Reserved.</span></span> <span data-ttu-id="fe78d-125">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="fe78d-125">Do not use.</span></span>
    
<span data-ttu-id="fe78d-126">SERVICE_DEFAULT_STORE</span><span class="sxs-lookup"><span data-stu-id="fe78d-126">SERVICE_DEFAULT_STORE</span></span> 
  
> <span data-ttu-id="fe78d-127">动态。</span><span class="sxs-lookup"><span data-stu-id="fe78d-127">Dynamic.</span></span> <span data-ttu-id="fe78d-128">邮件服务包含默认存储。</span><span class="sxs-lookup"><span data-stu-id="fe78d-128">The message service contains the default store.</span></span> <span data-ttu-id="fe78d-129">在从配置文件中删除或移动此服务之前，应显示一个用户界面，提示用户进行确认。</span><span class="sxs-lookup"><span data-stu-id="fe78d-129">A user interface should be displayed prompting the user for confirmation before deleting or moving this service out of the profile.</span></span> 
    
<span data-ttu-id="fe78d-130">SERVICE_NO_PRIMARY_IDENTITY</span><span class="sxs-lookup"><span data-stu-id="fe78d-130">SERVICE_NO_PRIMARY_IDENTITY</span></span> 
  
> <span data-ttu-id="fe78d-131">静态。</span><span class="sxs-lookup"><span data-stu-id="fe78d-131">Static.</span></span> <span data-ttu-id="fe78d-132">应设置为指示邮件服务中任何提供程序均不能用于提供标识的服务级别标志。</span><span class="sxs-lookup"><span data-stu-id="fe78d-132">The service level flag that should be set to indicate that none of the providers in the message service can be used to supply an identity.</span></span> <span data-ttu-id="fe78d-133">应设置此SERVICE_PRIMARY_IDENTITY，但不能同时设置这两者。</span><span class="sxs-lookup"><span data-stu-id="fe78d-133">Either this flag or SERVICE_PRIMARY_IDENTITY should be set, but not both.</span></span>
    
<span data-ttu-id="fe78d-134">SERVICE_PRIMARY_IDENTITY</span><span class="sxs-lookup"><span data-stu-id="fe78d-134">SERVICE_PRIMARY_IDENTITY</span></span> 
  
> <span data-ttu-id="fe78d-135">可修改。</span><span class="sxs-lookup"><span data-stu-id="fe78d-135">Modifiable.</span></span> <span data-ttu-id="fe78d-136">相应的邮件服务包含用于此会话的主标识的提供程序。</span><span class="sxs-lookup"><span data-stu-id="fe78d-136">The corresponding message service contains the provider used for the primary identity for this session.</span></span> <span data-ttu-id="fe78d-137">使用 [IMsgServiceAdmin：：SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md) 设置此标志。</span><span class="sxs-lookup"><span data-stu-id="fe78d-137">Use [IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md) to set this flag.</span></span> <span data-ttu-id="fe78d-138">应设置此SERVICE_NO_PRIMARY_IDENTITY，但不能同时设置这两者。</span><span class="sxs-lookup"><span data-stu-id="fe78d-138">Either this flag or SERVICE_NO_PRIMARY_IDENTITY should be set, but not both.</span></span> 
    
<span data-ttu-id="fe78d-139">SERVICE_SINGLE_COPY</span><span class="sxs-lookup"><span data-stu-id="fe78d-139">SERVICE_SINGLE_COPY</span></span> 
  
> <span data-ttu-id="fe78d-140">静态。</span><span class="sxs-lookup"><span data-stu-id="fe78d-140">Static.</span></span> <span data-ttu-id="fe78d-141">创建此邮件服务或将其复制到已存在该服务的配置文件的任何尝试都将失败。</span><span class="sxs-lookup"><span data-stu-id="fe78d-141">Any attempt to create or copy this message service into a profile where the service already exists will fail.</span></span> <span data-ttu-id="fe78d-142">若要创建单个副本邮件服务 **，PR_RESOURCE_FLAGS属性** 添加到 MAPISVC 中的服务部分。INF 并设置此标志。</span><span class="sxs-lookup"><span data-stu-id="fe78d-142">To create a single copy message service add the **PR_RESOURCE_FLAGS** property to the service's section in MAPISVC.INF and set this flag.</span></span> 
    
<span data-ttu-id="fe78d-143">对于服务提供商，可以在"服务"中设置以下一个或多个 **PR_RESOURCE_FLAGS：**</span><span class="sxs-lookup"><span data-stu-id="fe78d-143">For a service provider, one or more of the following flags can be set in **PR_RESOURCE_FLAGS**:</span></span>
  
<span data-ttu-id="fe78d-144">HOOK_INBOUND</span><span class="sxs-lookup"><span data-stu-id="fe78d-144">HOOK_INBOUND</span></span> 
  
> <span data-ttu-id="fe78d-145">静态。</span><span class="sxs-lookup"><span data-stu-id="fe78d-145">Static.</span></span> <span data-ttu-id="fe78d-146">后台处理程序挂钩需要处理入站邮件。</span><span class="sxs-lookup"><span data-stu-id="fe78d-146">The spooler hook needs to process inbound messages.</span></span>
    
<span data-ttu-id="fe78d-147">HOOK_OUTBOUND</span><span class="sxs-lookup"><span data-stu-id="fe78d-147">HOOK_OUTBOUND</span></span> 
  
> <span data-ttu-id="fe78d-148">静态。</span><span class="sxs-lookup"><span data-stu-id="fe78d-148">Static.</span></span> <span data-ttu-id="fe78d-149">后台处理程序挂钩需要处理出站邮件。</span><span class="sxs-lookup"><span data-stu-id="fe78d-149">The spooler hook needs to process outbound messages.</span></span> 
    
<span data-ttu-id="fe78d-150">STATUS_DEFAULT_OUTBOUND</span><span class="sxs-lookup"><span data-stu-id="fe78d-150">STATUS_DEFAULT_OUTBOUND</span></span> 
  
> <span data-ttu-id="fe78d-151">可修改。</span><span class="sxs-lookup"><span data-stu-id="fe78d-151">Modifiable.</span></span> <span data-ttu-id="fe78d-152">如果配置文件包含此传输提供程序的多个实例，则此标识应应用于出站邮件。</span><span class="sxs-lookup"><span data-stu-id="fe78d-152">This identity should be applied to outbound messages if the profile contains multiple instances of this transport provider.</span></span> <span data-ttu-id="fe78d-153">如果单个传输提供程序的多个实例出现在配置文件中，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="fe78d-153">This can happen if multiple instances of a single transport provider appear in the profile.</span></span>
    
<span data-ttu-id="fe78d-154">STATUS_DEFAULT_STORE</span><span class="sxs-lookup"><span data-stu-id="fe78d-154">STATUS_DEFAULT_STORE</span></span> 
  
> <span data-ttu-id="fe78d-155">可修改。</span><span class="sxs-lookup"><span data-stu-id="fe78d-155">Modifiable.</span></span> <span data-ttu-id="fe78d-156">此消息存储是配置文件的默认存储。</span><span class="sxs-lookup"><span data-stu-id="fe78d-156">This message store is the default store for the profile.</span></span> 
    
<span data-ttu-id="fe78d-157">STATUS_NEED_IPM_TREE</span><span class="sxs-lookup"><span data-stu-id="fe78d-157">STATUS_NEED_IPM_TREE</span></span> 
  
> <span data-ttu-id="fe78d-158">动态。</span><span class="sxs-lookup"><span data-stu-id="fe78d-158">Dynamic.</span></span> <span data-ttu-id="fe78d-159">此邮件存储中的标准文件夹（包括 iPM (IPM) 文件夹）尚未验证。</span><span class="sxs-lookup"><span data-stu-id="fe78d-159">The standard folders in this message store, including the interpersonal message (IPM) root folder, have not yet been verified.</span></span> <span data-ttu-id="fe78d-160">MAPI 设置并清除此标志。</span><span class="sxs-lookup"><span data-stu-id="fe78d-160">MAPI sets and clears this flag.</span></span> 
    
<span data-ttu-id="fe78d-161">STATUS_NO_DEFAULT_STORE</span><span class="sxs-lookup"><span data-stu-id="fe78d-161">STATUS_NO_DEFAULT_STORE</span></span> 
  
> <span data-ttu-id="fe78d-162">静态。</span><span class="sxs-lookup"><span data-stu-id="fe78d-162">Static.</span></span> <span data-ttu-id="fe78d-163">此邮件存储无法成为配置文件的默认邮件存储。</span><span class="sxs-lookup"><span data-stu-id="fe78d-163">This message store is incapable of becoming the default message store for the profile.</span></span>
    
<span data-ttu-id="fe78d-164">STATUS_NO_PRIMARY_IDENTITY</span><span class="sxs-lookup"><span data-stu-id="fe78d-164">STATUS_NO_PRIMARY_IDENTITY</span></span> 
  
> <span data-ttu-id="fe78d-165">静态。</span><span class="sxs-lookup"><span data-stu-id="fe78d-165">Static.</span></span> <span data-ttu-id="fe78d-166">此提供程序不在其状态行中提供标识。</span><span class="sxs-lookup"><span data-stu-id="fe78d-166">This provider does not furnish an identity in its status row.</span></span> <span data-ttu-id="fe78d-167">必须设置此STATUS_PRIMARY_IDENTITY或标记。</span><span class="sxs-lookup"><span data-stu-id="fe78d-167">Either this flag or STATUS_PRIMARY_IDENTITY must be set.</span></span>
    
<span data-ttu-id="fe78d-168">STATUS_OWN_STORE</span><span class="sxs-lookup"><span data-stu-id="fe78d-168">STATUS_OWN_STORE</span></span> 
  
> <span data-ttu-id="fe78d-169">静态。</span><span class="sxs-lookup"><span data-stu-id="fe78d-169">Static.</span></span> <span data-ttu-id="fe78d-170">此传输提供程序与邮件存储紧密结合，并在其状态PR_OWN_STORE_ENTRYID ( [PidTagOwnStoreEntryId) PidTagOwnStoreEntryId](pidtagownstoreentryid-canonical-property.md)属性。</span><span class="sxs-lookup"><span data-stu-id="fe78d-170">This transport provider is tightly coupled with a message store and furnishes the **PR_OWN_STORE_ENTRYID** ([PidTagOwnStoreEntryId](pidtagownstoreentryid-canonical-property.md)) property in its status row.</span></span>
    
<span data-ttu-id="fe78d-171">STATUS_PRIMARY_IDENTITY</span><span class="sxs-lookup"><span data-stu-id="fe78d-171">STATUS_PRIMARY_IDENTITY</span></span> 
  
> <span data-ttu-id="fe78d-172">可修改。</span><span class="sxs-lookup"><span data-stu-id="fe78d-172">Modifiable.</span></span> <span data-ttu-id="fe78d-173">此提供程序提供会话的主标识;提供标识的对象的条目标识符从 [IMAPISession：：QueryIdentity 返回](imapisession-queryidentity.md)。</span><span class="sxs-lookup"><span data-stu-id="fe78d-173">This provider furnishes the primary identity for the session; the entry identifier for the object furnishing the identity is returned from [IMAPISession::QueryIdentity](imapisession-queryidentity.md).</span></span> <span data-ttu-id="fe78d-174">必须设置此 **STATUS_NO_PRIMARY_IDENTITY** 或标记。</span><span class="sxs-lookup"><span data-stu-id="fe78d-174">Either this flag or **STATUS_NO_PRIMARY_IDENTITY** must be set.</span></span> 
    
<span data-ttu-id="fe78d-175">STATUS_PRIMARY_STORE</span><span class="sxs-lookup"><span data-stu-id="fe78d-175">STATUS_PRIMARY_STORE</span></span> 
  
> <span data-ttu-id="fe78d-176">可修改。</span><span class="sxs-lookup"><span data-stu-id="fe78d-176">Modifiable.</span></span> <span data-ttu-id="fe78d-177">此消息存储是在客户端应用程序登录时使用的。</span><span class="sxs-lookup"><span data-stu-id="fe78d-177">This message store is to be used when a client application logs on.</span></span> <span data-ttu-id="fe78d-178">打开后，此存储应设置为配置文件的默认存储。</span><span class="sxs-lookup"><span data-stu-id="fe78d-178">Once opened, this store should be set as the default store for the profile.</span></span> 
    
<span data-ttu-id="fe78d-179">STATUS_SECONDARY_STORE</span><span class="sxs-lookup"><span data-stu-id="fe78d-179">STATUS_SECONDARY_STORE</span></span> 
  
> <span data-ttu-id="fe78d-180">可修改。</span><span class="sxs-lookup"><span data-stu-id="fe78d-180">Modifiable.</span></span> <span data-ttu-id="fe78d-181">如果主存储在客户端应用程序登录时不可用，则使用此消息存储。</span><span class="sxs-lookup"><span data-stu-id="fe78d-181">This message store is to be used if the primary store is not available when a client application logs on.</span></span> <span data-ttu-id="fe78d-182">打开后，此存储应设置为配置文件的默认存储。</span><span class="sxs-lookup"><span data-stu-id="fe78d-182">Once opened, this store should be set as the default store for the profile.</span></span> 
    
<span data-ttu-id="fe78d-183">STATUS_SIMPLE_STORE</span><span class="sxs-lookup"><span data-stu-id="fe78d-183">STATUS_SIMPLE_STORE</span></span> 
  
> <span data-ttu-id="fe78d-184">动态。</span><span class="sxs-lookup"><span data-stu-id="fe78d-184">Dynamic.</span></span> <span data-ttu-id="fe78d-185">简单 MAPI 将此消息存储用作其默认邮件存储。</span><span class="sxs-lookup"><span data-stu-id="fe78d-185">This message store will be used by Simple MAPI as its default message store.</span></span>
    
<span data-ttu-id="fe78d-186">STATUS_TEMP_SECTION</span><span class="sxs-lookup"><span data-stu-id="fe78d-186">STATUS_TEMP_SECTION</span></span> 
  
> <span data-ttu-id="fe78d-187">动态。</span><span class="sxs-lookup"><span data-stu-id="fe78d-187">Dynamic.</span></span> <span data-ttu-id="fe78d-188">此消息存储不应在邮件存储表中发布，并且将在注销后从配置文件中删除。</span><span class="sxs-lookup"><span data-stu-id="fe78d-188">This message store should not be published in the message store table and will be deleted from the profile after logoff.</span></span> 
    
<span data-ttu-id="fe78d-189">STATUS_XP_PREFER_LAST</span><span class="sxs-lookup"><span data-stu-id="fe78d-189">STATUS_XP_PREFER_LAST</span></span> 
  
> <span data-ttu-id="fe78d-190">静态。</span><span class="sxs-lookup"><span data-stu-id="fe78d-190">Static.</span></span> <span data-ttu-id="fe78d-191">当多个传输提供程序能够传输邮件时，此传输预期是最后一次选择发送邮件的传输。</span><span class="sxs-lookup"><span data-stu-id="fe78d-191">This transport expects to be the last transport selected to send a message when multiple transport providers are able to transmit the message.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="fe78d-192">相关资源</span><span class="sxs-lookup"><span data-stu-id="fe78d-192">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="fe78d-193">头文件</span><span class="sxs-lookup"><span data-stu-id="fe78d-193">Header files</span></span>

<span data-ttu-id="fe78d-194">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fe78d-194">Mapidefs.h</span></span>
  
> <span data-ttu-id="fe78d-195">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fe78d-195">Provides data type definitions.</span></span>
    
<span data-ttu-id="fe78d-196">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="fe78d-196">Mapitags.h</span></span>
  
> <span data-ttu-id="fe78d-197">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="fe78d-197">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fe78d-198">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe78d-198">See also</span></span>



[<span data-ttu-id="fe78d-199">IMsgServiceAdmin::MsgServiceTransportOrder</span><span class="sxs-lookup"><span data-stu-id="fe78d-199">IMsgServiceAdmin::MsgServiceTransportOrder</span></span>](imsgserviceadmin-msgservicetransportorder.md)
  
[<span data-ttu-id="fe78d-200">PidTagIdentityEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="fe78d-200">PidTagIdentityEntryId Canonical Property</span></span>](pidtagidentityentryid-canonical-property.md)


[<span data-ttu-id="fe78d-201">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fe78d-201">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fe78d-202">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fe78d-202">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fe78d-203">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="fe78d-203">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fe78d-204">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fe78d-204">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

