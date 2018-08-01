---
title: PidTagReceivedBySearchKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReceivedBySearchKey
api_type:
- COM
ms.assetid: 4b37555a-1d07-4f42-95e3-b8fa37ed0c3b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a139c39c5814b22d9b55bc937a7c300d89f1d5bc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778148"
---
# <a name="pidtagreceivedbysearchkey-canonical-property"></a><span data-ttu-id="b35bb-103">PidTagReceivedBySearchKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="b35bb-103">PidTagReceivedBySearchKey Canonical Property</span></span>

  
  
<span data-ttu-id="b35bb-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b35bb-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b35bb-105">包含消息中接收的消息的用户的搜索键。</span><span class="sxs-lookup"><span data-stu-id="b35bb-105">Contains the search key of the messaging user who receives the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b35bb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b35bb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b35bb-107">PR_RECEIVED_BY_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="b35bb-107">PR_RECEIVED_BY_SEARCH_KEY</span></span>  <br/> |
|<span data-ttu-id="b35bb-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="b35bb-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b35bb-109">0x0051</span><span class="sxs-lookup"><span data-stu-id="b35bb-109">0x0051</span></span>  <br/> |
|<span data-ttu-id="b35bb-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b35bb-110">Data type:</span></span>  <br/> |<span data-ttu-id="b35bb-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="b35bb-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="b35bb-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b35bb-112">Area:</span></span>  <br/> |<span data-ttu-id="b35bb-113">Address</span><span class="sxs-lookup"><span data-stu-id="b35bb-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b35bb-114">说明</span><span class="sxs-lookup"><span data-stu-id="b35bb-114">Remarks</span></span>

<span data-ttu-id="b35bb-115">此属性是一个收到邮件的邮件用户的地址属性。</span><span class="sxs-lookup"><span data-stu-id="b35bb-115">This property is one of the address properties for the messaging user who receives the message.</span></span> <span data-ttu-id="b35bb-116">它必须由传入传输提供程序设置。</span><span class="sxs-lookup"><span data-stu-id="b35bb-116">It must be set by the incoming transport provider.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="b35bb-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="b35bb-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b35bb-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="b35bb-118">Protocol specifications</span></span>

<span data-ttu-id="b35bb-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b35bb-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b35bb-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="b35bb-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b35bb-121">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b35bb-121">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b35bb-122">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="b35bb-122">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="b35bb-123">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b35bb-123">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b35bb-124">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="b35bb-124">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="b35bb-125">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b35bb-125">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b35bb-126">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="b35bb-126">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="b35bb-127">[[MS OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b35bb-127">[[MS-OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b35bb-128">指定用于连接到和它们代表另一个用户操作时，作为代理人，以及与邮件和日历的对象交互配置邮箱的方法。</span><span class="sxs-lookup"><span data-stu-id="b35bb-128">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
<span data-ttu-id="b35bb-129">[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b35bb-129">[[MS-OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b35bb-130">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="b35bb-130">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b35bb-131">头文件</span><span class="sxs-lookup"><span data-stu-id="b35bb-131">Header files</span></span>

<span data-ttu-id="b35bb-132">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b35bb-132">Mapidefs.h</span></span>
  
> <span data-ttu-id="b35bb-133">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b35bb-133">Provides data type definitions.</span></span>
    
<span data-ttu-id="b35bb-134">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b35bb-134">Mapitags.h</span></span>
  
> <span data-ttu-id="b35bb-135">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b35bb-135">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b35bb-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b35bb-136">See also</span></span>



[<span data-ttu-id="b35bb-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b35bb-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b35bb-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b35bb-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b35bb-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b35bb-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b35bb-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b35bb-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

