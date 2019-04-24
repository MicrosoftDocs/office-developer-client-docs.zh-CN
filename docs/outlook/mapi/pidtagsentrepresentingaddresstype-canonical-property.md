---
title: PidTagSentRepresentingAddressType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSentRepresentingAddressType
api_type:
- COM
ms.assetid: 6ecbf653-1faf-47bd-81a4-20157859fdfd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bbf1ae0d7b38886fe08af2ad13f1a2be6b6e01cc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342572"
---
# <a name="pidtagsentrepresentingaddresstype-canonical-property"></a><span data-ttu-id="57fed-103">PidTagSentRepresentingAddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="57fed-103">PidTagSentRepresentingAddressType Canonical Property</span></span>

  
  
<span data-ttu-id="57fed-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="57fed-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="57fed-105">包含发件人代表的邮件用户的地址类型。</span><span class="sxs-lookup"><span data-stu-id="57fed-105">Contains the address type for the messaging user who is represented by the sender.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="57fed-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="57fed-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="57fed-107">PR_SENT_REPRESENTING_ADDRTYPE、PR_SENT_REPRESENTING_ADDRTYPE_A、PR_SENT_REPRESENTING_ADDRTYPE_W</span><span class="sxs-lookup"><span data-stu-id="57fed-107">PR_SENT_REPRESENTING_ADDRTYPE, PR_SENT_REPRESENTING_ADDRTYPE_A, PR_SENT_REPRESENTING_ADDRTYPE_W</span></span>  <br/> |
|<span data-ttu-id="57fed-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="57fed-108">Identifier:</span></span>  <br/> |<span data-ttu-id="57fed-109">0x0064</span><span class="sxs-lookup"><span data-stu-id="57fed-109">0x0064</span></span>  <br/> |
|<span data-ttu-id="57fed-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="57fed-110">Data type:</span></span>  <br/> |<span data-ttu-id="57fed-111">PT_UNICODE、PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="57fed-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="57fed-112">区域：</span><span class="sxs-lookup"><span data-stu-id="57fed-112">Area:</span></span>  <br/> |<span data-ttu-id="57fed-113">Address</span><span class="sxs-lookup"><span data-stu-id="57fed-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="57fed-114">注解</span><span class="sxs-lookup"><span data-stu-id="57fed-114">Remarks</span></span>

<span data-ttu-id="57fed-115">这些属性是发件人表示的邮件用户的地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="57fed-115">These properties are examples of the address properties for the messaging user being represented by the sender.</span></span> <span data-ttu-id="57fed-116">当客户端应用代表另一个客户端发送邮件时, 它应将所有表示的发件人属性设置为该客户端的值。</span><span class="sxs-lookup"><span data-stu-id="57fed-116">When a client application sends a message on behalf of another client, it should set all the represented sender properties to the values for that client.</span></span> <span data-ttu-id="57fed-117">邮件用户代表自己发送通常会将表示的发件人属性设置为未设置。</span><span class="sxs-lookup"><span data-stu-id="57fed-117">A messaging user sending on its own behalf typically leaves the represented sender properties unset.</span></span>
  
<span data-ttu-id="57fed-118">如果发送客户端已设置传出传输提供程序, 则该提供程序必须始终将此属性保持不变。</span><span class="sxs-lookup"><span data-stu-id="57fed-118">The outgoing transport provider must always leave this property unchanged if it has been set by the sending client.</span></span> <span data-ttu-id="57fed-119">如果它未设置, 则传输提供程序应将其设置为邮件的出站副本上的**PR_SENDER_ADDRTYPE** ([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md)) 属性, 并将其保留在本地副本上。</span><span class="sxs-lookup"><span data-stu-id="57fed-119">If it is unset, the transport provider should set it to the **PR_SENDER_ADDRTYPE** ([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md)) property on the outbound copy of the message, and leave it unset on the local copy.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="57fed-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="57fed-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="57fed-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="57fed-121">Protocol specifications</span></span>

<span data-ttu-id="57fed-122">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="57fed-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="57fed-123">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="57fed-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="57fed-124">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="57fed-124">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="57fed-125">处理客户端与服务器之间的数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="57fed-125">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="57fed-126">[[毫秒-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="57fed-126">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="57fed-127">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="57fed-127">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="57fed-128">[[毫秒-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="57fed-128">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="57fed-129">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="57fed-129">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="57fed-130">[[毫秒-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="57fed-130">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="57fed-131">指定用于连接邮箱和将邮箱配置为代理的方法, 以及当邮件和日历对象代表其他用户操作时与这些对象的交互。</span><span class="sxs-lookup"><span data-stu-id="57fed-131">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
<span data-ttu-id="57fed-132">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="57fed-132">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="57fed-133">指定允许用于电子邮件对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="57fed-133">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="57fed-134">[[毫秒-OXOPOST]](https://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="57fed-134">[[MS-OXOPOST]](https://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="57fed-135">指定允许用于 post 对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="57fed-135">Specifies the properties and operations that are permissible for post objects.</span></span>
    
<span data-ttu-id="57fed-136">[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="57fed-136">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="57fed-137">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="57fed-137">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="57fed-138">[[毫秒-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="57fed-138">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="57fed-139">将邮件和附件对象编码并解码为高效流表示形式。</span><span class="sxs-lookup"><span data-stu-id="57fed-139">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="57fed-140">头文件</span><span class="sxs-lookup"><span data-stu-id="57fed-140">Header files</span></span>

<span data-ttu-id="57fed-141">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="57fed-141">Mapidefs.h</span></span>
  
> <span data-ttu-id="57fed-142">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="57fed-142">Provides data type definitions.</span></span>
    
<span data-ttu-id="57fed-143">Mapitags</span><span class="sxs-lookup"><span data-stu-id="57fed-143">Mapitags.h</span></span>
  
> <span data-ttu-id="57fed-144">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="57fed-144">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="57fed-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57fed-145">See also</span></span>



[<span data-ttu-id="57fed-146">PidTagAddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="57fed-146">PidTagAddressType Canonical Property</span></span>](pidtagaddresstype-canonical-property.md)


[<span data-ttu-id="57fed-147">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="57fed-147">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="57fed-148">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="57fed-148">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="57fed-149">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="57fed-149">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="57fed-150">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="57fed-150">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

