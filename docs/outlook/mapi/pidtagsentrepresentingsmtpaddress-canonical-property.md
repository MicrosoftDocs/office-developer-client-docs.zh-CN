---
title: PidTagSentRepresentingSmtpAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 5ed122a2-0967-4de3-a2ee-69f81ae77b16
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a9114b1c9c3f5b09c5636f7d55d7111dd86afc06
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341935"
---
# <a name="pidtagsentrepresentingsmtpaddress-canonical-property"></a><span data-ttu-id="4cad3-103">PidTagSentRepresentingSmtpAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="4cad3-103">PidTagSentRepresentingSmtpAddress Canonical Property</span></span>

  
  
<span data-ttu-id="4cad3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4cad3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4cad3-105">包含发件人代表的邮件用户的简单邮件传输协议 (SMTP) 电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="4cad3-105">Contains the Simple Mail Transport Protocol (SMTP) email address for the messaging user who is represented by the sender.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4cad3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4cad3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4cad3-107">PR_SENT_REPRESENTING_SMTP_ADDRESS、PR_SENT_REPRESENTING_SMTP_ADDRESS_A、PR_SENT_REPRESENTING_SMTP_ADDRESS_W</span><span class="sxs-lookup"><span data-stu-id="4cad3-107">PR_SENT_REPRESENTING_SMTP_ADDRESS, PR_SENT_REPRESENTING_SMTP_ADDRESS_A, PR_SENT_REPRESENTING_SMTP_ADDRESS_W</span></span>  <br/> |
|<span data-ttu-id="4cad3-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="4cad3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4cad3-109">0x5D02</span><span class="sxs-lookup"><span data-stu-id="4cad3-109">0x5D02</span></span>  <br/> |
|<span data-ttu-id="4cad3-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4cad3-110">Data type:</span></span>  <br/> |<span data-ttu-id="4cad3-111">PT_UNICODE、PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="4cad3-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="4cad3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4cad3-112">Area:</span></span>  <br/> |<span data-ttu-id="4cad3-113">Address</span><span class="sxs-lookup"><span data-stu-id="4cad3-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4cad3-114">注解</span><span class="sxs-lookup"><span data-stu-id="4cad3-114">Remarks</span></span>

<span data-ttu-id="4cad3-115">此属性是发件人表示的邮件用户的地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="4cad3-115">This property is an example of the address properties for the messaging user being represented by the sender.</span></span> <span data-ttu-id="4cad3-116">当客户端应用代表另一个客户端发送邮件时, 它应将所有表示的发件人属性设置为该客户端的值。</span><span class="sxs-lookup"><span data-stu-id="4cad3-116">When a client application sends a message on behalf of another client, it should set all the represented sender properties to the values for that client.</span></span> <span data-ttu-id="4cad3-117">邮件用户代表自己发送通常会将表示的发件人属性设置为未设置。</span><span class="sxs-lookup"><span data-stu-id="4cad3-117">A messaging user sending on its own behalf typically leaves the represented sender properties unset.</span></span>
  
<span data-ttu-id="4cad3-118">如果发送客户端已设置传出传输提供程序, 则该提供程序必须始终将此属性保持不变。</span><span class="sxs-lookup"><span data-stu-id="4cad3-118">The outgoing transport provider must always leave this property unchanged if it has been set by the sending client.</span></span> <span data-ttu-id="4cad3-119">如果它未设置, 则传输提供程序应将其设置为邮件的出站副本上的**PR_SENDER_SMTP_ADDRESS** ([PidTagSenderSmtpAddress](pidtagsendersmtpaddress-canonical-property.md)) 属性, 并将其保留在本地副本上。</span><span class="sxs-lookup"><span data-stu-id="4cad3-119">If it is unset, the transport provider should set it to the **PR_SENDER_SMTP_ADDRESS** ([PidTagSenderSmtpAddress](pidtagsendersmtpaddress-canonical-property.md)) property on the outbound copy of the message, and leave it unset on the local copy.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="4cad3-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="4cad3-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4cad3-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="4cad3-121">Protocol specifications</span></span>

<span data-ttu-id="4cad3-122">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4cad3-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4cad3-123">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="4cad3-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4cad3-124">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4cad3-124">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4cad3-125">指定允许用于电子邮件对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="4cad3-125">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="4cad3-126">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4cad3-126">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4cad3-127">处理客户端与服务器之间的数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="4cad3-127">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="4cad3-128">[[毫秒-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4cad3-128">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4cad3-129">指定用于连接邮箱和将邮箱配置为代理的方法, 以及当邮件和日历对象代表其他用户操作时与这些对象的交互。</span><span class="sxs-lookup"><span data-stu-id="4cad3-129">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
<span data-ttu-id="4cad3-130">[[毫秒-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4cad3-130">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4cad3-131">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="4cad3-131">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="4cad3-132">[[毫秒-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4cad3-132">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4cad3-133">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="4cad3-133">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="4cad3-134">[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4cad3-134">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4cad3-135">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="4cad3-135">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="4cad3-136">[[毫秒-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4cad3-136">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4cad3-137">将邮件和附件对象编码并解码为高效流表示形式。</span><span class="sxs-lookup"><span data-stu-id="4cad3-137">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4cad3-138">头文件</span><span class="sxs-lookup"><span data-stu-id="4cad3-138">Header files</span></span>

<span data-ttu-id="4cad3-139">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="4cad3-139">Mapidefs.h</span></span>
  
> <span data-ttu-id="4cad3-140">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4cad3-140">Provides data type definitions.</span></span>
    
<span data-ttu-id="4cad3-141">Mapitags</span><span class="sxs-lookup"><span data-stu-id="4cad3-141">Mapitags.h</span></span>
  
> <span data-ttu-id="4cad3-142">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4cad3-142">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4cad3-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4cad3-143">See also</span></span>



[<span data-ttu-id="4cad3-144">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4cad3-144">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4cad3-145">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4cad3-145">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4cad3-146">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4cad3-146">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4cad3-147">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4cad3-147">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

