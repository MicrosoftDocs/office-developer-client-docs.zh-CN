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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25388264"
---
# <a name="pidtagrpcoverhttpflags-canonical-property"></a><span data-ttu-id="22335-103">PidTagRpcOverHttpFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="22335-103">PidTagRpcOverHttpFlags Canonical Property</span></span>

  
  
<span data-ttu-id="22335-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="22335-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="22335-105">包含 Microsoft Office Outlook 用于使用远程过程调用 (RPC) 通过超文本传输协议 (HTTP) 连接到 Microsoft Exchange Server 配置文件中的设置。</span><span class="sxs-lookup"><span data-stu-id="22335-105">Contains the settings in a profile used by Microsoft Office Outlook to connect to Microsoft Exchange Server by using a remote procedure call (RPC) over Hypertext Transfer Protocol (HTTP).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="22335-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="22335-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="22335-107">PR_ROH_FLAGS</span><span class="sxs-lookup"><span data-stu-id="22335-107">PR_ROH_FLAGS</span></span>  <br/> |
|<span data-ttu-id="22335-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="22335-108">Identifier:</span></span>  <br/> |<span data-ttu-id="22335-109">0x6623</span><span class="sxs-lookup"><span data-stu-id="22335-109">0x6623</span></span>  <br/> |
|<span data-ttu-id="22335-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="22335-110">Data type:</span></span>  <br/> |<span data-ttu-id="22335-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="22335-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="22335-112">区域：</span><span class="sxs-lookup"><span data-stu-id="22335-112">Area:</span></span>  <br/> |<span data-ttu-id="22335-113">其他</span><span class="sxs-lookup"><span data-stu-id="22335-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="22335-114">说明</span><span class="sxs-lookup"><span data-stu-id="22335-114">Remarks</span></span>

<span data-ttu-id="22335-115">**PR_ROH_FLAGS**属性存储在邮件应用程序编程接口 (MAPI) 配置文件的全局配置文件部分中。</span><span class="sxs-lookup"><span data-stu-id="22335-115">The **PR_ROH_FLAGS** property is stored in the Global Profile Section of a Messaging Application Programming Interface (MAPI) profile.</span></span> <span data-ttu-id="22335-116">**PR_ROH_FLAGS**的值是一个位掩码，一个或多个以下标志组成。</span><span class="sxs-lookup"><span data-stu-id="22335-116">The value of **PR_ROH_FLAGS** is a bitmask that is made up of one or more of the following flags.</span></span> 
  
|<span data-ttu-id="22335-117">**名称**</span><span class="sxs-lookup"><span data-stu-id="22335-117">**Name**</span></span>|<span data-ttu-id="22335-118">**值**</span><span class="sxs-lookup"><span data-stu-id="22335-118">**Value**</span></span>|<span data-ttu-id="22335-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="22335-119">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="22335-120">**ROHFLAGS_USE_ROH**</span><span class="sxs-lookup"><span data-stu-id="22335-120">**ROHFLAGS_USE_ROH**</span></span> <br/> |<span data-ttu-id="22335-121">0x1</span><span class="sxs-lookup"><span data-stu-id="22335-121">0x1</span></span>  <br/> |<span data-ttu-id="22335-122">连接到 Exchange 服务器使用 RPC over HTTP。</span><span class="sxs-lookup"><span data-stu-id="22335-122">Connect to the Exchange Server using RPC over HTTP.</span></span>  <br/> |
|<span data-ttu-id="22335-123">**ROHFLAGS_SSL_ONLY**</span><span class="sxs-lookup"><span data-stu-id="22335-123">**ROHFLAGS_SSL_ONLY**</span></span> <br/> |<span data-ttu-id="22335-124">0x2</span><span class="sxs-lookup"><span data-stu-id="22335-124">0x2</span></span>  <br/> |<span data-ttu-id="22335-125">连接到 Exchange 服务器仅使用安全套接字层 (SSL)。</span><span class="sxs-lookup"><span data-stu-id="22335-125">Connect to the Exchange Server using Secure Socket Layer (SSL) only.</span></span>  <br/> |
|<span data-ttu-id="22335-126">**ROHFLAGS_MUTUAL_AUTH**</span><span class="sxs-lookup"><span data-stu-id="22335-126">**ROHFLAGS_MUTUAL_AUTH**</span></span> <br/> |<span data-ttu-id="22335-127">0x4</span><span class="sxs-lookup"><span data-stu-id="22335-127">0x4</span></span>  <br/> |<span data-ttu-id="22335-128">相互验证会话时通过使用 SSL 连接。</span><span class="sxs-lookup"><span data-stu-id="22335-128">Mutually authenticate the session when connecting by using SSL.</span></span>  <br/> |
|<span data-ttu-id="22335-129">**ROHFLAGS_HTTP_FIRST_ON_FAST**</span><span class="sxs-lookup"><span data-stu-id="22335-129">**ROHFLAGS_HTTP_FIRST_ON_FAST**</span></span> <br/> |<span data-ttu-id="22335-130">0x8</span><span class="sxs-lookup"><span data-stu-id="22335-130">0x8</span></span>  <br/> |<span data-ttu-id="22335-131">在快速网络中，通过先使用 HTTP 连接。</span><span class="sxs-lookup"><span data-stu-id="22335-131">On fast networks, connect by using HTTP first.</span></span> <span data-ttu-id="22335-132">然后，通过使用 tcp/ip 进行连接。</span><span class="sxs-lookup"><span data-stu-id="22335-132">Then, connect by using TCP/IP.</span></span>  <br/> |
|<span data-ttu-id="22335-133">**ROHFLAGS_HTTP_FIRST_ON_SLOW**</span><span class="sxs-lookup"><span data-stu-id="22335-133">**ROHFLAGS_HTTP_FIRST_ON_SLOW**</span></span> <br/> |<span data-ttu-id="22335-134">0x20</span><span class="sxs-lookup"><span data-stu-id="22335-134">0x20</span></span>  <br/> |<span data-ttu-id="22335-135">在慢速网络上通过先使用 HTTP 连接。</span><span class="sxs-lookup"><span data-stu-id="22335-135">On slow networks, connect by using HTTP first.</span></span> <span data-ttu-id="22335-136">然后，通过使用 tcp/ip 进行连接。</span><span class="sxs-lookup"><span data-stu-id="22335-136">Then, connect by using TCP/IP.</span></span>  <br/> |
   
<span data-ttu-id="22335-137">例如，若要设置**PR_ROH_FLAGS**打开 RPC over HTTP，需要 SSL，并指定应低速连接时，首先使用 HTTP 协议的属性设置为**PR_ROH_FLAGS**属性的值`ROHFLAGS_USE_ROH | ROHFLAGS_SSL_ONLY | ROHFLAGS_HTTP_FIRST_ON_SLOW`即等于 0x23。</span><span class="sxs-lookup"><span data-stu-id="22335-137">For example, to set the **PR_ROH_FLAGS** property to turn on RPC over HTTP, to require SSL, and to specify that the HTTP protocol should be used first on slow connections, set the value of the **PR_ROH_FLAGS** property to  `ROHFLAGS_USE_ROH | ROHFLAGS_SSL_ONLY | ROHFLAGS_HTTP_FIRST_ON_SLOW` which is equal to 0x23.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="22335-138">相关资源</span><span class="sxs-lookup"><span data-stu-id="22335-138">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="22335-139">协议规范</span><span class="sxs-lookup"><span data-stu-id="22335-139">Protocol specifications</span></span>

<span data-ttu-id="22335-140">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="22335-140">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="22335-141">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="22335-141">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="22335-142">[[MS OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="22335-142">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="22335-143">定义所使用的基本的数据结构中远程操作。</span><span class="sxs-lookup"><span data-stu-id="22335-143">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="22335-144">[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="22335-144">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="22335-145">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="22335-145">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="22335-146">头文件</span><span class="sxs-lookup"><span data-stu-id="22335-146">Header files</span></span>

<span data-ttu-id="22335-147">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="22335-147">Mapidefs.h</span></span>
  
> <span data-ttu-id="22335-148">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="22335-148">Provides data type definitions.</span></span>
    
<span data-ttu-id="22335-149">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="22335-149">Mapitags.h</span></span>
  
> <span data-ttu-id="22335-150">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="22335-150">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="22335-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22335-151">See also</span></span>



[<span data-ttu-id="22335-152">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="22335-152">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="22335-153">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="22335-153">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="22335-154">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="22335-154">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="22335-155">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="22335-155">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

