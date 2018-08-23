---
title: PidTagTransportMessageHeaders 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagTransportMessageHeaders
api_type:
- COM
ms.assetid: 9f8e3f20-6454-4dfd-9b35-e0401abac6b3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 16c3684176de765a10b5bac620ea65a824cfe83a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588760"
---
# <a name="pidtagtransportmessageheaders-canonical-property"></a><span data-ttu-id="53124-103">PidTagTransportMessageHeaders 规范属性</span><span class="sxs-lookup"><span data-stu-id="53124-103">PidTagTransportMessageHeaders Canonical Property</span></span>

  
  
<span data-ttu-id="53124-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="53124-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="53124-105">包含特定于传输的消息信封信息。</span><span class="sxs-lookup"><span data-stu-id="53124-105">Contains transport-specific message envelope information.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="53124-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="53124-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="53124-107">PR_TRANSPORT_MESSAGE_HEADERS，PR_TRANSPORT_MESSAGE_HEADERS_A，PR_TRANSPORT_MESSAGE_HEADERS_W</span><span class="sxs-lookup"><span data-stu-id="53124-107">PR_TRANSPORT_MESSAGE_HEADERS, PR_TRANSPORT_MESSAGE_HEADERS_A, PR_TRANSPORT_MESSAGE_HEADERS_W</span></span>  <br/> |
|<span data-ttu-id="53124-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="53124-108">Identifier:</span></span>  <br/> |<span data-ttu-id="53124-109">0x007D</span><span class="sxs-lookup"><span data-stu-id="53124-109">0x007D</span></span>  <br/> |
|<span data-ttu-id="53124-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="53124-110">Data type:</span></span>  <br/> |<span data-ttu-id="53124-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="53124-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="53124-112">区域：</span><span class="sxs-lookup"><span data-stu-id="53124-112">Area:</span></span>  <br/> |<span data-ttu-id="53124-113">电子邮件</span><span class="sxs-lookup"><span data-stu-id="53124-113">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="53124-114">注解</span><span class="sxs-lookup"><span data-stu-id="53124-114">Remarks</span></span>

<span data-ttu-id="53124-115">传输提供程序可以生成入站邮件邮件头信息。</span><span class="sxs-lookup"><span data-stu-id="53124-115">The transport provider can generate the message header information for inbound messages.</span></span>
  
<span data-ttu-id="53124-116">这些属性提供放弃传输邮件头信息，或将它放前面的消息文本的替代项。</span><span class="sxs-lookup"><span data-stu-id="53124-116">These properties offer an alternative to either discarding the transport message header information or prepending it to the message text.</span></span> <span data-ttu-id="53124-117">客户端可以选择要显示的信息。</span><span class="sxs-lookup"><span data-stu-id="53124-117">The client can choose whether or not to display the information.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="53124-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="53124-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="53124-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="53124-119">Protocol specifications</span></span>

<span data-ttu-id="53124-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="53124-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="53124-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="53124-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="53124-122">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="53124-122">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="53124-123">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="53124-123">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
<span data-ttu-id="53124-124">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="53124-124">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="53124-125">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="53124-125">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="53124-126">头文件</span><span class="sxs-lookup"><span data-stu-id="53124-126">Header files</span></span>

<span data-ttu-id="53124-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="53124-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="53124-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="53124-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="53124-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="53124-129">Mapitags.h</span></span>
  
> <span data-ttu-id="53124-130">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="53124-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="53124-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53124-131">See also</span></span>



[<span data-ttu-id="53124-132">PidTagBody 规范属性</span><span class="sxs-lookup"><span data-stu-id="53124-132">PidTagBody Canonical Property</span></span>](pidtagbody-canonical-property.md)


[<span data-ttu-id="53124-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="53124-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="53124-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="53124-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="53124-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="53124-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="53124-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="53124-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

