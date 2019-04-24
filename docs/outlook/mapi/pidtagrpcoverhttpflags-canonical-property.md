---
title: PidTagRpcOverHttpFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c8b30768-cf83-450d-9fe2-567a5e0c2f57
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cf1f3b4d72426fb5f80decdc074a622b140657c8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327445"
---
# <a name="pidtagrpcoverhttpflags-canonical-property"></a><span data-ttu-id="e4b74-103">PidTagRpcOverHttpFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="e4b74-103">PidTagRpcOverHttpFlags Canonical Property</span></span>

  
  
<span data-ttu-id="e4b74-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e4b74-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e4b74-105">包含由 Microsoft Office Outlook 用于通过超文本传输协议 (HTTP) 使用远程过程调用 (RPC) 连接到 microsoft Exchange Server 的配置文件中的设置。</span><span class="sxs-lookup"><span data-stu-id="e4b74-105">Contains the settings in a profile used by Microsoft Office Outlook to connect to Microsoft Exchange Server by using a remote procedure call (RPC) over Hypertext Transfer Protocol (HTTP).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e4b74-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e4b74-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e4b74-107">PR_ROH_FLAGS</span><span class="sxs-lookup"><span data-stu-id="e4b74-107">PR_ROH_FLAGS</span></span>  <br/> |
|<span data-ttu-id="e4b74-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="e4b74-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e4b74-109">0x6623</span><span class="sxs-lookup"><span data-stu-id="e4b74-109">0x6623</span></span>  <br/> |
|<span data-ttu-id="e4b74-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e4b74-110">Data type:</span></span>  <br/> |<span data-ttu-id="e4b74-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="e4b74-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="e4b74-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e4b74-112">Area:</span></span>  <br/> |<span data-ttu-id="e4b74-113">其他</span><span class="sxs-lookup"><span data-stu-id="e4b74-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e4b74-114">注解</span><span class="sxs-lookup"><span data-stu-id="e4b74-114">Remarks</span></span>

<span data-ttu-id="e4b74-115">**PR_ROH_FLAGS**属性存储在邮件应用程序编程接口 (MAPI) 配置文件的 "全局配置文件" 部分中。</span><span class="sxs-lookup"><span data-stu-id="e4b74-115">The **PR_ROH_FLAGS** property is stored in the Global Profile Section of a Messaging Application Programming Interface (MAPI) profile.</span></span> <span data-ttu-id="e4b74-116">**PR_ROH_FLAGS**的值是由一个或多个下列标志组成的位掩码。</span><span class="sxs-lookup"><span data-stu-id="e4b74-116">The value of **PR_ROH_FLAGS** is a bitmask that is made up of one or more of the following flags.</span></span> 
  
|<span data-ttu-id="e4b74-117">**Name**</span><span class="sxs-lookup"><span data-stu-id="e4b74-117">**Name**</span></span>|<span data-ttu-id="e4b74-118">**Value**</span><span class="sxs-lookup"><span data-stu-id="e4b74-118">**Value**</span></span>|<span data-ttu-id="e4b74-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="e4b74-119">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e4b74-120">**ROHFLAGS_USE_ROH**</span><span class="sxs-lookup"><span data-stu-id="e4b74-120">**ROHFLAGS_USE_ROH**</span></span> <br/> |<span data-ttu-id="e4b74-121">0x1</span><span class="sxs-lookup"><span data-stu-id="e4b74-121">0x1</span></span>  <br/> |<span data-ttu-id="e4b74-122">使用 RPC over HTTP 连接到 Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="e4b74-122">Connect to the Exchange Server using RPC over HTTP.</span></span>  <br/> |
|<span data-ttu-id="e4b74-123">**ROHFLAGS_SSL_ONLY**</span><span class="sxs-lookup"><span data-stu-id="e4b74-123">**ROHFLAGS_SSL_ONLY**</span></span> <br/> |<span data-ttu-id="e4b74-124">0x2</span><span class="sxs-lookup"><span data-stu-id="e4b74-124">0x2</span></span>  <br/> |<span data-ttu-id="e4b74-125">仅使用安全套接字层 (SSL) 连接到 Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="e4b74-125">Connect to the Exchange Server using Secure Socket Layer (SSL) only.</span></span>  <br/> |
|<span data-ttu-id="e4b74-126">**ROHFLAGS_MUTUAL_AUTH**</span><span class="sxs-lookup"><span data-stu-id="e4b74-126">**ROHFLAGS_MUTUAL_AUTH**</span></span> <br/> |<span data-ttu-id="e4b74-127">0x4</span><span class="sxs-lookup"><span data-stu-id="e4b74-127">0x4</span></span>  <br/> |<span data-ttu-id="e4b74-128">使用 SSL 连接时相互验证会话。</span><span class="sxs-lookup"><span data-stu-id="e4b74-128">Mutually authenticate the session when connecting by using SSL.</span></span>  <br/> |
|<span data-ttu-id="e4b74-129">**ROHFLAGS_HTTP_FIRST_ON_FAST**</span><span class="sxs-lookup"><span data-stu-id="e4b74-129">**ROHFLAGS_HTTP_FIRST_ON_FAST**</span></span> <br/> |<span data-ttu-id="e4b74-130">0x8</span><span class="sxs-lookup"><span data-stu-id="e4b74-130">0x8</span></span>  <br/> |<span data-ttu-id="e4b74-131">在快速网络中, 先使用 HTTP 进行连接。</span><span class="sxs-lookup"><span data-stu-id="e4b74-131">On fast networks, connect by using HTTP first.</span></span> <span data-ttu-id="e4b74-132">然后, 使用 tcp/ip 进行连接。</span><span class="sxs-lookup"><span data-stu-id="e4b74-132">Then, connect by using TCP/IP.</span></span>  <br/> |
|<span data-ttu-id="e4b74-133">**ROHFLAGS_HTTP_FIRST_ON_SLOW**</span><span class="sxs-lookup"><span data-stu-id="e4b74-133">**ROHFLAGS_HTTP_FIRST_ON_SLOW**</span></span> <br/> |<span data-ttu-id="e4b74-134">0x20</span><span class="sxs-lookup"><span data-stu-id="e4b74-134">0x20</span></span>  <br/> |<span data-ttu-id="e4b74-135">在低速网络中, 先使用 HTTP 进行连接。</span><span class="sxs-lookup"><span data-stu-id="e4b74-135">On slow networks, connect by using HTTP first.</span></span> <span data-ttu-id="e4b74-136">然后, 使用 tcp/ip 进行连接。</span><span class="sxs-lookup"><span data-stu-id="e4b74-136">Then, connect by using TCP/IP.</span></span>  <br/> |
   
<span data-ttu-id="e4b74-137">例如, 若要将**PR_ROH_FLAGS**属性设置为启用 RPC over HTTP, 需要 SSL, 并指定应首先在低速连接上使用 HTTP 协议, 请将**PR_ROH_FLAGS**属性`ROHFLAGS_USE_ROH | ROHFLAGS_SSL_ONLY | ROHFLAGS_HTTP_FIRST_ON_SLOW`的值设置为等于0x23 的值。</span><span class="sxs-lookup"><span data-stu-id="e4b74-137">For example, to set the **PR_ROH_FLAGS** property to turn on RPC over HTTP, to require SSL, and to specify that the HTTP protocol should be used first on slow connections, set the value of the **PR_ROH_FLAGS** property to  `ROHFLAGS_USE_ROH | ROHFLAGS_SSL_ONLY | ROHFLAGS_HTTP_FIRST_ON_SLOW` which is equal to 0x23.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="e4b74-138">相关资源</span><span class="sxs-lookup"><span data-stu-id="e4b74-138">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e4b74-139">协议规范</span><span class="sxs-lookup"><span data-stu-id="e4b74-139">Protocol specifications</span></span>

<span data-ttu-id="e4b74-140">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e4b74-140">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e4b74-141">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="e4b74-141">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e4b74-142">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e4b74-142">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e4b74-143">定义在远程操作中使用的基本数据结构。</span><span class="sxs-lookup"><span data-stu-id="e4b74-143">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="e4b74-144">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e4b74-144">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e4b74-145">指定允许用于电子邮件对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="e4b74-145">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e4b74-146">头文件</span><span class="sxs-lookup"><span data-stu-id="e4b74-146">Header files</span></span>

<span data-ttu-id="e4b74-147">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="e4b74-147">Mapidefs.h</span></span>
  
> <span data-ttu-id="e4b74-148">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e4b74-148">Provides data type definitions.</span></span>
    
<span data-ttu-id="e4b74-149">Mapitags</span><span class="sxs-lookup"><span data-stu-id="e4b74-149">Mapitags.h</span></span>
  
> <span data-ttu-id="e4b74-150">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e4b74-150">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e4b74-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4b74-151">See also</span></span>



[<span data-ttu-id="e4b74-152">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e4b74-152">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e4b74-153">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e4b74-153">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e4b74-154">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e4b74-154">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e4b74-155">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e4b74-155">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

