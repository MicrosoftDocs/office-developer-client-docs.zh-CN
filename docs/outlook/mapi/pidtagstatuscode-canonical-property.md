---
title: PidTagStatusCode 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStatusCode
api_type:
- COM
ms.assetid: e29190c5-52c3-4ef7-98db-699487c54325
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: efd0dcc8fc01fa433cbbf30936244e4818f8b14a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778453"
---
# <a name="pidtagstatuscode-canonical-property"></a><span data-ttu-id="e67c7-103">PidTagStatusCode 规范属性</span><span class="sxs-lookup"><span data-stu-id="e67c7-103">PidTagStatusCode Canonical Property</span></span>

  
  
<span data-ttu-id="e67c7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e67c7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e67c7-105">包含这些标志指示会话资源的当前状态的位掩码。</span><span class="sxs-lookup"><span data-stu-id="e67c7-105">Contains a bitmask of flags that indicate the current status of a session resource.</span></span> <span data-ttu-id="e67c7-106">所有服务提供商都设置状态代码一样 MAPI 子系统、 MAPI 后台处理程序和集成的通讯簿的状态报告。</span><span class="sxs-lookup"><span data-stu-id="e67c7-106">All service providers set status codes as does MAPI to report on the status of the subsystem, the MAPI spooler, and the integrated address book.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e67c7-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e67c7-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="e67c7-108">PR_STATUS_CODE</span><span class="sxs-lookup"><span data-stu-id="e67c7-108">PR_STATUS_CODE</span></span>  <br/> |
|<span data-ttu-id="e67c7-109">标识符：</span><span class="sxs-lookup"><span data-stu-id="e67c7-109">Identifier:</span></span>  <br/> |<span data-ttu-id="e67c7-110">0x3E04</span><span class="sxs-lookup"><span data-stu-id="e67c7-110">0x3E04</span></span>  <br/> |
|<span data-ttu-id="e67c7-111">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e67c7-111">Data type:</span></span>  <br/> |<span data-ttu-id="e67c7-112">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="e67c7-112">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="e67c7-113">区域：</span><span class="sxs-lookup"><span data-stu-id="e67c7-113">Area:</span></span>  <br/> |<span data-ttu-id="e67c7-114">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="e67c7-114">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e67c7-115">说明</span><span class="sxs-lookup"><span data-stu-id="e67c7-115">Remarks</span></span>

<span data-ttu-id="e67c7-116">状态代码必须 Mapisvc.inf 文件中出现的所有提供商。</span><span class="sxs-lookup"><span data-stu-id="e67c7-116">The status code must appear in the Mapisvc.inf file for all providers.</span></span> 
  
<span data-ttu-id="e67c7-117">通过 MAPI 和所有服务提供商实现状态对象。</span><span class="sxs-lookup"><span data-stu-id="e67c7-117">Status objects are implemented by MAPI and by all service providers.</span></span> <span data-ttu-id="e67c7-118">有两组状态代码、 的所有状态对象的一组和传输提供程序的另一组有效的值。</span><span class="sxs-lookup"><span data-stu-id="e67c7-118">There are two sets of valid values for status codes, one set for all status objects and another set for transport providers only.</span></span> <span data-ttu-id="e67c7-119">所有状态对象可以将此属性都设置为下列值：</span><span class="sxs-lookup"><span data-stu-id="e67c7-119">All status objects can set this property to the following values:</span></span>
  
<span data-ttu-id="e67c7-120">STATUS_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e67c7-120">STATUS_AVAILABLE</span></span> 
  
> <span data-ttu-id="e67c7-121">指示资源正常工作。</span><span class="sxs-lookup"><span data-stu-id="e67c7-121">Indicates that the resource is operational.</span></span>
    
<span data-ttu-id="e67c7-122">STATUS_FAILURE</span><span class="sxs-lookup"><span data-stu-id="e67c7-122">STATUS_FAILURE</span></span> 
  
> <span data-ttu-id="e67c7-123">指示资源遇到问题。</span><span class="sxs-lookup"><span data-stu-id="e67c7-123">Indicates that the resource is experiencing a problem.</span></span> <span data-ttu-id="e67c7-124">服务提供程序 STATUS_FAILURE 指示提供程序可能很快将关闭结束当前会话。</span><span class="sxs-lookup"><span data-stu-id="e67c7-124">For service providers, STATUS_FAILURE indicates that the provider might soon be shut down to end the current session.</span></span>
    
<span data-ttu-id="e67c7-125">STATUS_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="e67c7-125">STATUS_OFFLINE</span></span> 
  
> <span data-ttu-id="e67c7-126">指示仅本地数据或服务都是可用。</span><span class="sxs-lookup"><span data-stu-id="e67c7-126">Indicates that only local data or services are available.</span></span>
    
<span data-ttu-id="e67c7-127">传输提供程序还可以设置其状态对象的**PR_STATUS_CODE**属性为下列值：</span><span class="sxs-lookup"><span data-stu-id="e67c7-127">Transport providers can also set their status objects' **PR_STATUS_CODE** properties to the following values:</span></span> 
  
<span data-ttu-id="e67c7-128">STATUS_INBOUND_ACTIVE</span><span class="sxs-lookup"><span data-stu-id="e67c7-128">STATUS_INBOUND_ACTIVE</span></span> 
  
> <span data-ttu-id="e67c7-129">指示的传输提供程序接收的入站的邮件。</span><span class="sxs-lookup"><span data-stu-id="e67c7-129">Indicates that the transport provider is receiving an inbound message.</span></span> 
    
<span data-ttu-id="e67c7-130">STATUS_INBOUND_ENABLED</span><span class="sxs-lookup"><span data-stu-id="e67c7-130">STATUS_INBOUND_ENABLED</span></span> 
  
> <span data-ttu-id="e67c7-131">指示的传输提供程序可接受入站的邮件。</span><span class="sxs-lookup"><span data-stu-id="e67c7-131">Indicates that the transport provider can receive inbound messages.</span></span>
    
<span data-ttu-id="e67c7-132">STATUS_INBOUND_FLUSH</span><span class="sxs-lookup"><span data-stu-id="e67c7-132">STATUS_INBOUND_FLUSH</span></span> 
  
> <span data-ttu-id="e67c7-133">指示的传输提供程序从入站队列中下载邮件。</span><span class="sxs-lookup"><span data-stu-id="e67c7-133">Indicates that the transport provider is downloading messages from the inbound queue.</span></span>
    
<span data-ttu-id="e67c7-134">STATUS_OUTBOUND_ACTIVE</span><span class="sxs-lookup"><span data-stu-id="e67c7-134">STATUS_OUTBOUND_ACTIVE</span></span> 
  
> <span data-ttu-id="e67c7-135">指示的传输提供程序接收出站邮件。</span><span class="sxs-lookup"><span data-stu-id="e67c7-135">Indicates that the transport provider is receiving an outbound message.</span></span> 
    
<span data-ttu-id="e67c7-136">STATUS_OUTBOUND_ENABLED</span><span class="sxs-lookup"><span data-stu-id="e67c7-136">STATUS_OUTBOUND_ENABLED</span></span> 
  
> <span data-ttu-id="e67c7-137">指示的传输提供程序可以处理出站邮件。</span><span class="sxs-lookup"><span data-stu-id="e67c7-137">Indicates that the transport provider can handle outbound messages.</span></span>
    
<span data-ttu-id="e67c7-138">STATUS_OUTBOUND_FLUSH</span><span class="sxs-lookup"><span data-stu-id="e67c7-138">STATUS_OUTBOUND_FLUSH</span></span> 
  
> <span data-ttu-id="e67c7-139">指示的传输提供程序为上载从其出站队列的消息。</span><span class="sxs-lookup"><span data-stu-id="e67c7-139">Indicates that the transport provider is uploading messages from its outbound queue.</span></span>
    
<span data-ttu-id="e67c7-140">STATUS_REMOTE_ACCESS</span><span class="sxs-lookup"><span data-stu-id="e67c7-140">STATUS_REMOTE_ACCESS</span></span> 
  
> <span data-ttu-id="e67c7-141">指示的传输提供程序支持远程访问。</span><span class="sxs-lookup"><span data-stu-id="e67c7-141">Indicates that the transport provider supports remote access.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="e67c7-142">相关资源</span><span class="sxs-lookup"><span data-stu-id="e67c7-142">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="e67c7-143">头文件</span><span class="sxs-lookup"><span data-stu-id="e67c7-143">Header files</span></span>

<span data-ttu-id="e67c7-144">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e67c7-144">Mapidefs.h</span></span>
  
> <span data-ttu-id="e67c7-145">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e67c7-145">Provides data type definitions.</span></span>
    
<span data-ttu-id="e67c7-146">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e67c7-146">Mapitags.h</span></span>
  
> <span data-ttu-id="e67c7-147">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e67c7-147">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e67c7-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e67c7-148">See also</span></span>



[<span data-ttu-id="e67c7-149">PidTagStatusString 规范属性</span><span class="sxs-lookup"><span data-stu-id="e67c7-149">PidTagStatusString Canonical Property</span></span>](pidtagstatusstring-canonical-property.md)


[<span data-ttu-id="e67c7-150">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e67c7-150">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e67c7-151">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e67c7-151">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e67c7-152">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e67c7-152">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e67c7-153">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e67c7-153">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

