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
ms.openlocfilehash: 751be8abe02dfb1d5bab2bcbbbc0cbd2a8243f85
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418512"
---
# <a name="pidtagstatuscode-canonical-property"></a><span data-ttu-id="0d4c9-103">PidTagStatusCode 规范属性</span><span class="sxs-lookup"><span data-stu-id="0d4c9-103">PidTagStatusCode Canonical Property</span></span>

  
  
<span data-ttu-id="0d4c9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0d4c9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0d4c9-105">包含指示会话资源的当前状态的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="0d4c9-105">Contains a bitmask of flags that indicate the current status of a session resource.</span></span> <span data-ttu-id="0d4c9-106">所有服务提供程序都会将状态代码设置为 mapi, 以报告子系统的状态、MAPI 后台处理程序和集成的通讯簿。</span><span class="sxs-lookup"><span data-stu-id="0d4c9-106">All service providers set status codes as does MAPI to report on the status of the subsystem, the MAPI spooler, and the integrated address book.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0d4c9-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0d4c9-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="0d4c9-108">PR_STATUS_CODE</span><span class="sxs-lookup"><span data-stu-id="0d4c9-108">PR_STATUS_CODE</span></span>  <br/> |
|<span data-ttu-id="0d4c9-109">标识符:</span><span class="sxs-lookup"><span data-stu-id="0d4c9-109">Identifier:</span></span>  <br/> |<span data-ttu-id="0d4c9-110">0x3E04</span><span class="sxs-lookup"><span data-stu-id="0d4c9-110">0x3E04</span></span>  <br/> |
|<span data-ttu-id="0d4c9-111">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0d4c9-111">Data type:</span></span>  <br/> |<span data-ttu-id="0d4c9-112">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="0d4c9-112">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="0d4c9-113">区域：</span><span class="sxs-lookup"><span data-stu-id="0d4c9-113">Area:</span></span>  <br/> |<span data-ttu-id="0d4c9-114">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="0d4c9-114">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0d4c9-115">说明</span><span class="sxs-lookup"><span data-stu-id="0d4c9-115">Remarks</span></span>

<span data-ttu-id="0d4c9-116">状态代码必须出现在所有提供程序的 mapisvc.inf 文件中。</span><span class="sxs-lookup"><span data-stu-id="0d4c9-116">The status code must appear in the Mapisvc.inf file for all providers.</span></span> 
  
<span data-ttu-id="0d4c9-117">Status 对象由 MAPI 和所有服务提供商实现。</span><span class="sxs-lookup"><span data-stu-id="0d4c9-117">Status objects are implemented by MAPI and by all service providers.</span></span> <span data-ttu-id="0d4c9-118">状态代码有两组有效值, 一组用于所有状态对象, 另一组用于传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="0d4c9-118">There are two sets of valid values for status codes, one set for all status objects and another set for transport providers only.</span></span> <span data-ttu-id="0d4c9-119">所有 status 对象均可将此属性设置为以下值:</span><span class="sxs-lookup"><span data-stu-id="0d4c9-119">All status objects can set this property to the following values:</span></span>
  
<span data-ttu-id="0d4c9-120">STATUS_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0d4c9-120">STATUS_AVAILABLE</span></span> 
  
> <span data-ttu-id="0d4c9-121">指示资源是可操作的。</span><span class="sxs-lookup"><span data-stu-id="0d4c9-121">Indicates that the resource is operational.</span></span>
    
<span data-ttu-id="0d4c9-122">STATUS_FAILURE</span><span class="sxs-lookup"><span data-stu-id="0d4c9-122">STATUS_FAILURE</span></span> 
  
> <span data-ttu-id="0d4c9-123">指示资源遇到问题。</span><span class="sxs-lookup"><span data-stu-id="0d4c9-123">Indicates that the resource is experiencing a problem.</span></span> <span data-ttu-id="0d4c9-124">对于服务提供程序, STATUS_FAILURE 指示可能很快会关闭提供程序以结束当前会话。</span><span class="sxs-lookup"><span data-stu-id="0d4c9-124">For service providers, STATUS_FAILURE indicates that the provider might soon be shut down to end the current session.</span></span>
    
<span data-ttu-id="0d4c9-125">STATUS_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="0d4c9-125">STATUS_OFFLINE</span></span> 
  
> <span data-ttu-id="0d4c9-126">指示仅本地数据或服务可用。</span><span class="sxs-lookup"><span data-stu-id="0d4c9-126">Indicates that only local data or services are available.</span></span>
    
<span data-ttu-id="0d4c9-127">传输提供程序还可以将其 status 对象的**PR_STATUS_CODE**属性设置为以下值:</span><span class="sxs-lookup"><span data-stu-id="0d4c9-127">Transport providers can also set their status objects' **PR_STATUS_CODE** properties to the following values:</span></span> 
  
<span data-ttu-id="0d4c9-128">STATUS_INBOUND_ACTIVE</span><span class="sxs-lookup"><span data-stu-id="0d4c9-128">STATUS_INBOUND_ACTIVE</span></span> 
  
> <span data-ttu-id="0d4c9-129">指示传输提供程序正在接收入站邮件。</span><span class="sxs-lookup"><span data-stu-id="0d4c9-129">Indicates that the transport provider is receiving an inbound message.</span></span> 
    
<span data-ttu-id="0d4c9-130">STATUS_INBOUND_ENABLED</span><span class="sxs-lookup"><span data-stu-id="0d4c9-130">STATUS_INBOUND_ENABLED</span></span> 
  
> <span data-ttu-id="0d4c9-131">指示传输提供程序可以接收入站邮件。</span><span class="sxs-lookup"><span data-stu-id="0d4c9-131">Indicates that the transport provider can receive inbound messages.</span></span>
    
<span data-ttu-id="0d4c9-132">STATUS_INBOUND_FLUSH</span><span class="sxs-lookup"><span data-stu-id="0d4c9-132">STATUS_INBOUND_FLUSH</span></span> 
  
> <span data-ttu-id="0d4c9-133">指示传输提供程序正在从入站队列下载邮件。</span><span class="sxs-lookup"><span data-stu-id="0d4c9-133">Indicates that the transport provider is downloading messages from the inbound queue.</span></span>
    
<span data-ttu-id="0d4c9-134">STATUS_OUTBOUND_ACTIVE</span><span class="sxs-lookup"><span data-stu-id="0d4c9-134">STATUS_OUTBOUND_ACTIVE</span></span> 
  
> <span data-ttu-id="0d4c9-135">指示传输提供程序正在接收出站邮件。</span><span class="sxs-lookup"><span data-stu-id="0d4c9-135">Indicates that the transport provider is receiving an outbound message.</span></span> 
    
<span data-ttu-id="0d4c9-136">STATUS_OUTBOUND_ENABLED</span><span class="sxs-lookup"><span data-stu-id="0d4c9-136">STATUS_OUTBOUND_ENABLED</span></span> 
  
> <span data-ttu-id="0d4c9-137">指示传输提供程序可以处理出站邮件。</span><span class="sxs-lookup"><span data-stu-id="0d4c9-137">Indicates that the transport provider can handle outbound messages.</span></span>
    
<span data-ttu-id="0d4c9-138">STATUS_OUTBOUND_FLUSH</span><span class="sxs-lookup"><span data-stu-id="0d4c9-138">STATUS_OUTBOUND_FLUSH</span></span> 
  
> <span data-ttu-id="0d4c9-139">指示传输提供程序正在从其出站队列中上载邮件。</span><span class="sxs-lookup"><span data-stu-id="0d4c9-139">Indicates that the transport provider is uploading messages from its outbound queue.</span></span>
    
<span data-ttu-id="0d4c9-140">STATUS_REMOTE_ACCESS</span><span class="sxs-lookup"><span data-stu-id="0d4c9-140">STATUS_REMOTE_ACCESS</span></span> 
  
> <span data-ttu-id="0d4c9-141">指示传输提供程序支持远程访问。</span><span class="sxs-lookup"><span data-stu-id="0d4c9-141">Indicates that the transport provider supports remote access.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="0d4c9-142">相关资源</span><span class="sxs-lookup"><span data-stu-id="0d4c9-142">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="0d4c9-143">头文件</span><span class="sxs-lookup"><span data-stu-id="0d4c9-143">Header files</span></span>

<span data-ttu-id="0d4c9-144">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="0d4c9-144">Mapidefs.h</span></span>
  
> <span data-ttu-id="0d4c9-145">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0d4c9-145">Provides data type definitions.</span></span>
    
<span data-ttu-id="0d4c9-146">Mapitags</span><span class="sxs-lookup"><span data-stu-id="0d4c9-146">Mapitags.h</span></span>
  
> <span data-ttu-id="0d4c9-147">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0d4c9-147">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0d4c9-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d4c9-148">See also</span></span>



[<span data-ttu-id="0d4c9-149">PidTagStatusString 规范属性</span><span class="sxs-lookup"><span data-stu-id="0d4c9-149">PidTagStatusString Canonical Property</span></span>](pidtagstatusstring-canonical-property.md)


[<span data-ttu-id="0d4c9-150">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0d4c9-150">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0d4c9-151">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0d4c9-151">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0d4c9-152">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0d4c9-152">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0d4c9-153">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0d4c9-153">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

