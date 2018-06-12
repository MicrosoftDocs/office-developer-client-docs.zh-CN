---
title: PidTagSentRepresentingEmailAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSentRepresentingEmailAddress
api_type:
- COM
ms.assetid: 5fa4edde-475c-4568-946b-73eb08f97a61
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 1ed8797a9f9de223d8ec15bc0eae963ff1e93be4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778393"
---
# <a name="pidtagsentrepresentingemailaddress-canonical-property"></a><span data-ttu-id="3f423-103">PidTagSentRepresentingEmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="3f423-103">PidTagSentRepresentingEmailAddress Canonical Property</span></span>

  
  
<span data-ttu-id="3f423-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3f423-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3f423-105">包含由发件人的邮件用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3f423-105">Contains the email address for the messaging user who is represented by the sender.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3f423-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="3f423-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3f423-107">PR_SENT_REPRESENTING_EMAIL_ADDRESS，PR_SENT_REPRESENTING_EMAIL_ADDRESS_A，PR_SENT_REPRESENTING_EMAIL_ADDRESS_W</span><span class="sxs-lookup"><span data-stu-id="3f423-107">PR_SENT_REPRESENTING_EMAIL_ADDRESS, PR_SENT_REPRESENTING_EMAIL_ADDRESS_A, PR_SENT_REPRESENTING_EMAIL_ADDRESS_W</span></span>  <br/> |
|<span data-ttu-id="3f423-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="3f423-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3f423-109">0x0065</span><span class="sxs-lookup"><span data-stu-id="3f423-109">0x0065</span></span>  <br/> |
|<span data-ttu-id="3f423-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3f423-110">Data type:</span></span>  <br/> |<span data-ttu-id="3f423-111">PT_UNICODE PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="3f423-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="3f423-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3f423-112">Area:</span></span>  <br/> |<span data-ttu-id="3f423-113">Address</span><span class="sxs-lookup"><span data-stu-id="3f423-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3f423-114">备注</span><span class="sxs-lookup"><span data-stu-id="3f423-114">Remarks</span></span>

<span data-ttu-id="3f423-115">这些属性是正在表示发件人的邮件用户的地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="3f423-115">These properties are examples of the address properties for the messaging user being represented by the sender.</span></span> <span data-ttu-id="3f423-116">当客户端应用程序发送消息代表另一个客户端时，它应为该客户端的值设置所有表示发件人属性。</span><span class="sxs-lookup"><span data-stu-id="3f423-116">When a client application sends a message on behalf of another client, it should set all the represented sender properties to the values for that client.</span></span> <span data-ttu-id="3f423-117">通常在其自己的代表发送消息用户离开表示发件人属性未设置。</span><span class="sxs-lookup"><span data-stu-id="3f423-117">A messaging user sending on its own behalf typically leaves the represented sender properties unset.</span></span>
  
<span data-ttu-id="3f423-118">传出的传输提供程序必须始终保持不变，如果已发送的客户端设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="3f423-118">The outgoing transport provider must always leave these properties unchanged if it has been set by the sending client.</span></span> <span data-ttu-id="3f423-119">如果未设置，传输提供程序应出站邮件，副本上将其设置为**PR_SENDER_EMAIL_ADDRESS** ([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md)) 属性，而保持它未设置的本地副本。</span><span class="sxs-lookup"><span data-stu-id="3f423-119">If it is unset, the transport provider should set it to the **PR_SENDER_EMAIL_ADDRESS** ([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md)) property on the outbound copy of the message, and leave it unset on the local copy.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="3f423-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="3f423-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3f423-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="3f423-121">Protocol specifications</span></span>

<span data-ttu-id="3f423-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3f423-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3f423-123">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="3f423-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="3f423-124">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3f423-124">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3f423-125">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="3f423-125">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="3f423-126">[[MS OXORSS]](http://msdn.microsoft.com/library/53bc9634-0040-4b5a-aecd-29781d826009%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3f423-126">[[MS-OXORSS]](http://msdn.microsoft.com/library/53bc9634-0040-4b5a-aecd-29781d826009%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3f423-127">指定的属性和表示 RSS 项目的操作。</span><span class="sxs-lookup"><span data-stu-id="3f423-127">Specifies the properties and operations that represent RSS items.</span></span>
    
<span data-ttu-id="3f423-128">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3f423-128">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3f423-129">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="3f423-129">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="3f423-130">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3f423-130">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3f423-131">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="3f423-131">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="3f423-132">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3f423-132">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3f423-133">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="3f423-133">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="3f423-134">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3f423-134">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3f423-135">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="3f423-135">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="3f423-136">[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3f423-136">[[MS-OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3f423-137">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="3f423-137">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3f423-138">头文件</span><span class="sxs-lookup"><span data-stu-id="3f423-138">Header files</span></span>

<span data-ttu-id="3f423-139">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3f423-139">Mapidefs.h</span></span>
  
> <span data-ttu-id="3f423-140">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3f423-140">Provides data type definitions.</span></span>
    
<span data-ttu-id="3f423-141">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="3f423-141">Mapitags.h</span></span>
  
> <span data-ttu-id="3f423-142">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3f423-142">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3f423-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f423-143">See also</span></span>



[<span data-ttu-id="3f423-144">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3f423-144">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3f423-145">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3f423-145">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3f423-146">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3f423-146">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3f423-147">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3f423-147">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

