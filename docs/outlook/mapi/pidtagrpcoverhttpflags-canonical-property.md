---
title: PidTagRpcOverHttpFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c8b30768-cf83-450d-9fe2-567a5e0c2f57
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 151aa730f2ae6a4d39ffa474eb7ecd79ed5602eb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778235"
---
# <a name="pidtagrpcoverhttpflags-canonical-property"></a><span data-ttu-id="37b62-103">PidTagRpcOverHttpFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="37b62-103">PidTagRpcOverHttpFlags Canonical Property</span></span>

  
  
<span data-ttu-id="37b62-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="37b62-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="37b62-105">包含 Microsoft Office Outlook 用于使用远程过程调用 (RPC) 通过超文本传输协议 (HTTP) 连接到 Microsoft Exchange Server 配置文件中的设置。</span><span class="sxs-lookup"><span data-stu-id="37b62-105">Contains the settings in a profile used by Microsoft Office Outlook to connect to Microsoft Exchange Server by using a remote procedure call (RPC) over Hypertext Transfer Protocol (HTTP).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="37b62-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="37b62-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="37b62-107">PR_ROH_FLAGS</span><span class="sxs-lookup"><span data-stu-id="37b62-107">PR_ROH_FLAGS</span></span>  <br/> |
|<span data-ttu-id="37b62-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="37b62-108">Identifier:</span></span>  <br/> |<span data-ttu-id="37b62-109">0x6623</span><span class="sxs-lookup"><span data-stu-id="37b62-109">0x6623</span></span>  <br/> |
|<span data-ttu-id="37b62-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="37b62-110">Data type:</span></span>  <br/> |<span data-ttu-id="37b62-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="37b62-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="37b62-112">区域：</span><span class="sxs-lookup"><span data-stu-id="37b62-112">Area:</span></span>  <br/> |<span data-ttu-id="37b62-113">其他</span><span class="sxs-lookup"><span data-stu-id="37b62-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="37b62-114">备注</span><span class="sxs-lookup"><span data-stu-id="37b62-114">Remarks</span></span>

<span data-ttu-id="37b62-115">**PR_ROH_FLAGS**属性存储在邮件应用程序编程接口 (MAPI) 配置文件的全局配置文件部分中。</span><span class="sxs-lookup"><span data-stu-id="37b62-115">The **PR_ROH_FLAGS** property is stored in the Global Profile Section of a Messaging Application Programming Interface (MAPI) profile.</span></span> <span data-ttu-id="37b62-116">**PR_ROH_FLAGS**的值是一个位掩码，一个或多个以下标志组成。</span><span class="sxs-lookup"><span data-stu-id="37b62-116">The value of **PR_ROH_FLAGS** is a bitmask that is made up of one or more of the following flags.</span></span> 
  
|<span data-ttu-id="37b62-117">**名称**</span><span class="sxs-lookup"><span data-stu-id="37b62-117">**Name**</span></span>|<span data-ttu-id="37b62-118">**值**</span><span class="sxs-lookup"><span data-stu-id="37b62-118">**Value**</span></span>|<span data-ttu-id="37b62-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="37b62-119">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="37b62-120">**ROHFLAGS_USE_ROH**</span><span class="sxs-lookup"><span data-stu-id="37b62-120">**ROHFLAGS_USE_ROH**</span></span> <br/> |<span data-ttu-id="37b62-121">0x1</span><span class="sxs-lookup"><span data-stu-id="37b62-121">0x1</span></span>  <br/> |<span data-ttu-id="37b62-122">连接到 Exchange 服务器使用 RPC over HTTP。</span><span class="sxs-lookup"><span data-stu-id="37b62-122">Connect to the Exchange Server using RPC over HTTP.</span></span>  <br/> |
|<span data-ttu-id="37b62-123">**ROHFLAGS_SSL_ONLY**</span><span class="sxs-lookup"><span data-stu-id="37b62-123">**ROHFLAGS_SSL_ONLY**</span></span> <br/> |<span data-ttu-id="37b62-124">0x2</span><span class="sxs-lookup"><span data-stu-id="37b62-124">0x2</span></span>  <br/> |<span data-ttu-id="37b62-125">连接到 Exchange 服务器仅使用安全套接字层 (SSL)。</span><span class="sxs-lookup"><span data-stu-id="37b62-125">Connect to the Exchange Server using Secure Socket Layer (SSL) only.</span></span>  <br/> |
|<span data-ttu-id="37b62-126">**ROHFLAGS_MUTUAL_AUTH**</span><span class="sxs-lookup"><span data-stu-id="37b62-126">**ROHFLAGS_MUTUAL_AUTH**</span></span> <br/> |<span data-ttu-id="37b62-127">0x4</span><span class="sxs-lookup"><span data-stu-id="37b62-127">0x4</span></span>  <br/> |<span data-ttu-id="37b62-128">相互验证会话时通过使用 SSL 连接。</span><span class="sxs-lookup"><span data-stu-id="37b62-128">Mutually authenticate the session when connecting by using SSL.</span></span>  <br/> |
|<span data-ttu-id="37b62-129">**ROHFLAGS_HTTP_FIRST_ON_FAST**</span><span class="sxs-lookup"><span data-stu-id="37b62-129">**ROHFLAGS_HTTP_FIRST_ON_FAST**</span></span> <br/> |<span data-ttu-id="37b62-130">0x8</span><span class="sxs-lookup"><span data-stu-id="37b62-130">0x8</span></span>  <br/> |<span data-ttu-id="37b62-131">在快速网络中，通过先使用 HTTP 连接。</span><span class="sxs-lookup"><span data-stu-id="37b62-131">On fast networks, connect by using HTTP first.</span></span> <span data-ttu-id="37b62-132">然后，通过使用 tcp/ip 进行连接。</span><span class="sxs-lookup"><span data-stu-id="37b62-132">Then, connect by using TCP/IP.</span></span>  <br/> |
|<span data-ttu-id="37b62-133">**ROHFLAGS_HTTP_FIRST_ON_SLOW**</span><span class="sxs-lookup"><span data-stu-id="37b62-133">**ROHFLAGS_HTTP_FIRST_ON_SLOW**</span></span> <br/> |<span data-ttu-id="37b62-134">0x20</span><span class="sxs-lookup"><span data-stu-id="37b62-134">0x20</span></span>  <br/> |<span data-ttu-id="37b62-135">在慢速网络上通过先使用 HTTP 连接。</span><span class="sxs-lookup"><span data-stu-id="37b62-135">On slow networks, connect by using HTTP first.</span></span> <span data-ttu-id="37b62-136">然后，通过使用 tcp/ip 进行连接。</span><span class="sxs-lookup"><span data-stu-id="37b62-136">Then, connect by using TCP/IP.</span></span>  <br/> |
   
<span data-ttu-id="37b62-137">例如，若要设置**PR_ROH_FLAGS**打开 RPC over HTTP，需要 SSL，并指定应低速连接时，首先使用 HTTP 协议的属性设置为**PR_ROH_FLAGS**属性的值`ROHFLAGS_USE_ROH | ROHFLAGS_SSL_ONLY | ROHFLAGS_HTTP_FIRST_ON_SLOW`即等于 0x23。</span><span class="sxs-lookup"><span data-stu-id="37b62-137">For example, to set the **PR_ROH_FLAGS** property to turn on RPC over HTTP, to require SSL, and to specify that the HTTP protocol should be used first on slow connections, set the value of the **PR_ROH_FLAGS** property to  `ROHFLAGS_USE_ROH | ROHFLAGS_SSL_ONLY | ROHFLAGS_HTTP_FIRST_ON_SLOW` which is equal to 0x23.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="37b62-138">相关资源</span><span class="sxs-lookup"><span data-stu-id="37b62-138">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="37b62-139">协议规范</span><span class="sxs-lookup"><span data-stu-id="37b62-139">Protocol specifications</span></span>

<span data-ttu-id="37b62-140">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="37b62-140">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="37b62-141">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="37b62-141">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="37b62-142">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="37b62-142">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="37b62-143">定义所使用的基本的数据结构中远程操作。</span><span class="sxs-lookup"><span data-stu-id="37b62-143">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="37b62-144">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="37b62-144">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="37b62-145">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="37b62-145">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="37b62-146">头文件</span><span class="sxs-lookup"><span data-stu-id="37b62-146">Header files</span></span>

<span data-ttu-id="37b62-147">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="37b62-147">Mapidefs.h</span></span>
  
> <span data-ttu-id="37b62-148">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="37b62-148">Provides data type definitions.</span></span>
    
<span data-ttu-id="37b62-149">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="37b62-149">Mapitags.h</span></span>
  
> <span data-ttu-id="37b62-150">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="37b62-150">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="37b62-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37b62-151">See also</span></span>



[<span data-ttu-id="37b62-152">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="37b62-152">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="37b62-153">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="37b62-153">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="37b62-154">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="37b62-154">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="37b62-155">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="37b62-155">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

