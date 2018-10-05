---
title: PidTagReceivedRepresentingAddressType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReceivedRepresentingAddressType
api_type:
- COM
ms.assetid: c342bb2a-157e-4748-bf21-0926f95e5312
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9592057757b7bad0c2400f8b1c720ef0146bb9a7
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398848"
---
# <a name="pidtagreceivedrepresentingaddresstype-canonical-property"></a><span data-ttu-id="464e9-103">PidTagReceivedRepresentingAddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="464e9-103">PidTagReceivedRepresentingAddressType Canonical Property</span></span>

  
  
<span data-ttu-id="464e9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="464e9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="464e9-105">包含由实际接收邮件的用户的邮件用户的地址类型。</span><span class="sxs-lookup"><span data-stu-id="464e9-105">Contains the address type for the messaging user who is represented by the user actually receiving the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="464e9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="464e9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="464e9-107">PR_RCVD_REPRESENTING_ADDRTYPE，PR_RCVD_REPRESENTING_ADDRTYPE_A，PR_RCVD_REPRESENTING_ADDRTYPE_W</span><span class="sxs-lookup"><span data-stu-id="464e9-107">PR_RCVD_REPRESENTING_ADDRTYPE, PR_RCVD_REPRESENTING_ADDRTYPE_A, PR_RCVD_REPRESENTING_ADDRTYPE_W</span></span>  <br/> |
|<span data-ttu-id="464e9-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="464e9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="464e9-109">0x0077</span><span class="sxs-lookup"><span data-stu-id="464e9-109">0x0077</span></span>  <br/> |
|<span data-ttu-id="464e9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="464e9-110">Data type:</span></span>  <br/> |<span data-ttu-id="464e9-111">PT_UNICODE PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="464e9-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="464e9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="464e9-112">Area:</span></span>  <br/> |<span data-ttu-id="464e9-113">Address</span><span class="sxs-lookup"><span data-stu-id="464e9-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="464e9-114">说明</span><span class="sxs-lookup"><span data-stu-id="464e9-114">Remarks</span></span>

<span data-ttu-id="464e9-115">这些属性是由接收用户的邮件用户的地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="464e9-115">These properties are examples of the address properties for the messaging user who is being represented by the receiving user.</span></span> <span data-ttu-id="464e9-116">它必须由传入传输提供程序，也是负责授权或的代理人的验证设置。</span><span class="sxs-lookup"><span data-stu-id="464e9-116">It must be set by the incoming transport provider, which is also responsible for authorization or verification of the delegate.</span></span> <span data-ttu-id="464e9-117">如果正在表示没有消息的用户，此属性应设置为**PR_RECEIVED_BY_ADDRTYPE** ([PidTagReceivedByAddressType](pidtagreceivedbyaddresstype-canonical-property.md)) 属性中包含的地址类型。</span><span class="sxs-lookup"><span data-stu-id="464e9-117">If no messaging user is being represented, this property should be set to the address type contained in the **PR_RECEIVED_BY_ADDRTYPE** ([PidTagReceivedByAddressType](pidtagreceivedbyaddresstype-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="464e9-118">代表另一个客户端接收的邮件的回复客户端应用程序应复制此属性中收到的邮件到答复的**PR_SENT_REPRESENTING_ADDRTYPE** ([PidTagSentRepresentingAddressType](pidtagsentrepresentingaddresstype-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="464e9-118">A client application replying to a message received on behalf of another client should copy this property from the received message into the **PR_SENT_REPRESENTING_ADDRTYPE** ([PidTagSentRepresentingAddressType](pidtagsentrepresentingaddresstype-canonical-property.md)) property for the reply.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="464e9-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="464e9-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="464e9-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="464e9-120">Protocol specifications</span></span>

<span data-ttu-id="464e9-121">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="464e9-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="464e9-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="464e9-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="464e9-123">[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="464e9-123">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="464e9-124">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="464e9-124">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="464e9-125">[[MS OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="464e9-125">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="464e9-126">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="464e9-126">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="464e9-127">[[MS OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="464e9-127">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="464e9-128">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="464e9-128">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="464e9-129">[[MS OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="464e9-129">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="464e9-130">指定用于连接到和它们代表另一个用户操作时，作为代理人，以及与邮件和日历的对象交互配置邮箱的方法。</span><span class="sxs-lookup"><span data-stu-id="464e9-130">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
<span data-ttu-id="464e9-131">[[MS OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="464e9-131">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="464e9-132">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="464e9-132">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="464e9-133">头文件</span><span class="sxs-lookup"><span data-stu-id="464e9-133">Header files</span></span>

<span data-ttu-id="464e9-134">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="464e9-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="464e9-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="464e9-135">Provides data type definitions.</span></span>
    
<span data-ttu-id="464e9-136">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="464e9-136">Mapitags.h</span></span>
  
> <span data-ttu-id="464e9-137">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="464e9-137">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="464e9-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="464e9-138">See also</span></span>



[<span data-ttu-id="464e9-139">PidTagAddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="464e9-139">PidTagAddressType Canonical Property</span></span>](pidtagaddresstype-canonical-property.md)


[<span data-ttu-id="464e9-140">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="464e9-140">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="464e9-141">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="464e9-141">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="464e9-142">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="464e9-142">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="464e9-143">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="464e9-143">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

