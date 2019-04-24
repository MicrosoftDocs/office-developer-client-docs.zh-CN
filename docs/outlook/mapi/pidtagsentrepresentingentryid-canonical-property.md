---
title: PidTagSentRepresentingEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSentRepresentingEntryId
api_type:
- COM
ms.assetid: f23bde8b-94cc-48c8-891a-166aa39aa3ee
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 87d8fa21ed641b40ee679a4b5fc8d68b1050ab0e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359085"
---
# <a name="pidtagsentrepresentingentryid-canonical-property"></a><span data-ttu-id="b13f5-103">PidTagSentRepresentingEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="b13f5-103">PidTagSentRepresentingEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="b13f5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b13f5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b13f5-105">包含发件人代表的邮件用户的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="b13f5-105">Contains the entry identifier for the messaging user represented by the sender.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b13f5-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b13f5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b13f5-107">PR_SENT_REPRESENTING_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="b13f5-107">PR_SENT_REPRESENTING_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="b13f5-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="b13f5-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b13f5-109">0x0041</span><span class="sxs-lookup"><span data-stu-id="b13f5-109">0x0041</span></span>  <br/> |
|<span data-ttu-id="b13f5-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b13f5-110">Data type:</span></span>  <br/> |<span data-ttu-id="b13f5-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="b13f5-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="b13f5-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b13f5-112">Area:</span></span>  <br/> |<span data-ttu-id="b13f5-113">Address</span><span class="sxs-lookup"><span data-stu-id="b13f5-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b13f5-114">注解</span><span class="sxs-lookup"><span data-stu-id="b13f5-114">Remarks</span></span>

<span data-ttu-id="b13f5-115">此属性是发件人表示的邮件用户的地址属性之一。</span><span class="sxs-lookup"><span data-stu-id="b13f5-115">This property is one of the address properties for the messaging user being represented by the sender.</span></span> <span data-ttu-id="b13f5-116">当客户端应用代表另一个客户端发送邮件时, 它应将所有表示的发件人属性设置为该客户端的值。</span><span class="sxs-lookup"><span data-stu-id="b13f5-116">When a client application sends a message on behalf of another client, it should set all the represented sender properties to the values for that client.</span></span> <span data-ttu-id="b13f5-117">邮件用户代表自己发送通常会将表示的发件人属性设置为未设置。</span><span class="sxs-lookup"><span data-stu-id="b13f5-117">A messaging user sending on its own behalf typically leaves the represented sender properties unset.</span></span>
  
<span data-ttu-id="b13f5-118">如果发送客户端已设置传出传输提供程序, 则该提供程序必须始终将此属性保持不变。</span><span class="sxs-lookup"><span data-stu-id="b13f5-118">The outgoing transport provider must always leave this property unchanged if it has been set by the sending client.</span></span> <span data-ttu-id="b13f5-119">如果它未设置, 则传输提供程序应将其设置为邮件的出站副本上的**PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)), 并将其保留在本地副本上。</span><span class="sxs-lookup"><span data-stu-id="b13f5-119">If it is unset, the transport provider should set it to **PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)) on the outbound copy of the message, and leave it unset on the local copy.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="b13f5-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="b13f5-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b13f5-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="b13f5-121">Protocol specifications</span></span>

<span data-ttu-id="b13f5-122">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b13f5-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b13f5-123">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b13f5-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b13f5-124">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b13f5-124">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b13f5-125">指定允许用于电子邮件对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="b13f5-125">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="b13f5-126">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b13f5-126">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b13f5-127">处理客户端与服务器之间的数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="b13f5-127">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="b13f5-128">[[毫秒-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b13f5-128">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b13f5-129">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="b13f5-129">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="b13f5-130">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b13f5-130">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b13f5-131">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="b13f5-131">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="b13f5-132">[[毫秒-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b13f5-132">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b13f5-133">指定用于连接邮箱和将邮箱配置为代理的方法, 以及当邮件和日历对象代表其他用户操作时与这些对象的交互。</span><span class="sxs-lookup"><span data-stu-id="b13f5-133">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
<span data-ttu-id="b13f5-134">[[毫秒-OXOPOST]](https://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b13f5-134">[[MS-OXOPOST]](https://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b13f5-135">指定允许用于 post 对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="b13f5-135">Specifies the properties and operations that are permissible for post objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b13f5-136">头文件</span><span class="sxs-lookup"><span data-stu-id="b13f5-136">Header files</span></span>

<span data-ttu-id="b13f5-137">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="b13f5-137">Mapidefs.h</span></span>
  
> <span data-ttu-id="b13f5-138">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b13f5-138">Provides data type definitions.</span></span>
    
<span data-ttu-id="b13f5-139">Mapitags</span><span class="sxs-lookup"><span data-stu-id="b13f5-139">Mapitags.h</span></span>
  
> <span data-ttu-id="b13f5-140">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b13f5-140">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b13f5-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b13f5-141">See also</span></span>



[<span data-ttu-id="b13f5-142">PidTagEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="b13f5-142">PidTagEntryId Canonical Property</span></span>](pidtagentryid-canonical-property.md)


[<span data-ttu-id="b13f5-143">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b13f5-143">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b13f5-144">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b13f5-144">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b13f5-145">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b13f5-145">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b13f5-146">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b13f5-146">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

