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
# <a name="pidtagsentrepresentingaddresstype-canonical-property"></a><span data-ttu-id="4e0f6-103">PidTagSentRepresentingAddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="4e0f6-103">PidTagSentRepresentingAddressType Canonical Property</span></span>

  
  
<span data-ttu-id="4e0f6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4e0f6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4e0f6-105">包含发件人所代表的邮件用户的地址类型。</span><span class="sxs-lookup"><span data-stu-id="4e0f6-105">Contains the address type for the messaging user who is represented by the sender.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4e0f6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4e0f6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4e0f6-107">PR_SENT_REPRESENTING_ADDRTYPE、PR_SENT_REPRESENTING_ADDRTYPE_A、PR_SENT_REPRESENTING_ADDRTYPE_W</span><span class="sxs-lookup"><span data-stu-id="4e0f6-107">PR_SENT_REPRESENTING_ADDRTYPE, PR_SENT_REPRESENTING_ADDRTYPE_A, PR_SENT_REPRESENTING_ADDRTYPE_W</span></span>  <br/> |
|<span data-ttu-id="4e0f6-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="4e0f6-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4e0f6-109">0x0064</span><span class="sxs-lookup"><span data-stu-id="4e0f6-109">0x0064</span></span>  <br/> |
|<span data-ttu-id="4e0f6-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4e0f6-110">Data type:</span></span>  <br/> |<span data-ttu-id="4e0f6-111">PT_UNICODE、PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="4e0f6-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="4e0f6-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4e0f6-112">Area:</span></span>  <br/> |<span data-ttu-id="4e0f6-113">地址</span><span class="sxs-lookup"><span data-stu-id="4e0f6-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4e0f6-114">备注</span><span class="sxs-lookup"><span data-stu-id="4e0f6-114">Remarks</span></span>

<span data-ttu-id="4e0f6-115">这些属性是发件人所代表的邮件用户的地址属性示例。</span><span class="sxs-lookup"><span data-stu-id="4e0f6-115">These properties are examples of the address properties for the messaging user being represented by the sender.</span></span> <span data-ttu-id="4e0f6-116">当客户端应用程序代表另一个客户端发送邮件时，它应当将表示的所有发件人属性设置为该客户端的值。</span><span class="sxs-lookup"><span data-stu-id="4e0f6-116">When a client application sends a message on behalf of another client, it should set all the represented sender properties to the values for that client.</span></span> <span data-ttu-id="4e0f6-117">邮件用户代表自己发送的邮件通常不会设置表示的发件人属性。</span><span class="sxs-lookup"><span data-stu-id="4e0f6-117">A messaging user sending on its own behalf typically leaves the represented sender properties unset.</span></span>
  
<span data-ttu-id="4e0f6-118">如果发送客户端已设置此属性，则传出传输提供程序必须始终保持该属性不变。</span><span class="sxs-lookup"><span data-stu-id="4e0f6-118">The outgoing transport provider must always leave this property unchanged if it has been set by the sending client.</span></span> <span data-ttu-id="4e0f6-119">如果未设置，传输提供程序应将其设置为邮件的出站副本上的 **PR_SENDER_ADDRTYPE** ([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md)) 属性，并保留在本地副本上未设置。</span><span class="sxs-lookup"><span data-stu-id="4e0f6-119">If it is unset, the transport provider should set it to the **PR_SENDER_ADDRTYPE** ([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md)) property on the outbound copy of the message, and leave it unset on the local copy.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="4e0f6-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="4e0f6-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4e0f6-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="4e0f6-121">Protocol specifications</span></span>

<span data-ttu-id="4e0f6-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4e0f6-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4e0f6-123">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="4e0f6-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4e0f6-124">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4e0f6-124">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4e0f6-125">处理客户端和服务器之间数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="4e0f6-125">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="4e0f6-126">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4e0f6-126">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4e0f6-127">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间转换。</span><span class="sxs-lookup"><span data-stu-id="4e0f6-127">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="4e0f6-128">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4e0f6-128">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4e0f6-129">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="4e0f6-129">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="4e0f6-130">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4e0f6-130">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4e0f6-131">指定用于连接邮箱和将邮箱配置为代理的方法，以及代表其他用户操作时与邮件和日历对象的交互的方法。</span><span class="sxs-lookup"><span data-stu-id="4e0f6-131">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
<span data-ttu-id="4e0f6-132">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4e0f6-132">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4e0f6-133">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="4e0f6-133">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="4e0f6-134">[[MS-OXOPOST]](https://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4e0f6-134">[[MS-OXOPOST]](https://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4e0f6-135">指定 post 对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="4e0f6-135">Specifies the properties and operations that are permissible for post objects.</span></span>
    
<span data-ttu-id="4e0f6-136">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4e0f6-136">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4e0f6-137">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="4e0f6-137">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="4e0f6-138">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4e0f6-138">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4e0f6-139">将邮件和附件对象编码和解码为有效的流表示形式。</span><span class="sxs-lookup"><span data-stu-id="4e0f6-139">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4e0f6-140">头文件</span><span class="sxs-lookup"><span data-stu-id="4e0f6-140">Header files</span></span>

<span data-ttu-id="4e0f6-141">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4e0f6-141">Mapidefs.h</span></span>
  
> <span data-ttu-id="4e0f6-142">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4e0f6-142">Provides data type definitions.</span></span>
    
<span data-ttu-id="4e0f6-143">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="4e0f6-143">Mapitags.h</span></span>
  
> <span data-ttu-id="4e0f6-144">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4e0f6-144">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4e0f6-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e0f6-145">See also</span></span>



[<span data-ttu-id="4e0f6-146">PidTagAddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="4e0f6-146">PidTagAddressType Canonical Property</span></span>](pidtagaddresstype-canonical-property.md)


[<span data-ttu-id="4e0f6-147">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4e0f6-147">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4e0f6-148">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4e0f6-148">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4e0f6-149">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4e0f6-149">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4e0f6-150">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4e0f6-150">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

