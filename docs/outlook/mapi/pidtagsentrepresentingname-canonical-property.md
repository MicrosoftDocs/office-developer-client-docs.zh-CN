---
title: PidTagSentRepresentingName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: bfee6c5e-d4c6-442e-af71-23156569fed5
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 5417b73fe13937a74bc01520a2dd9db359e894ed
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778403"
---
# <a name="pidtagsentrepresentingname-canonical-property"></a><span data-ttu-id="669eb-103">PidTagSentRepresentingName 规范属性</span><span class="sxs-lookup"><span data-stu-id="669eb-103">PidTagSentRepresentingName Canonical Property</span></span>

  
  
<span data-ttu-id="669eb-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="669eb-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="669eb-105">包含表示发件人的邮件用户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="669eb-105">Contains the display name for the messaging user represented by the sender.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="669eb-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="669eb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="669eb-107">PR_SENT_REPRESENTING_NAME，PR_SENT_REPRESENTING_NAME_A，PR_SENT_REPRESENTING_NAME_W</span><span class="sxs-lookup"><span data-stu-id="669eb-107">PR_SENT_REPRESENTING_NAME, PR_SENT_REPRESENTING_NAME_A, PR_SENT_REPRESENTING_NAME_W</span></span>  <br/> |
|<span data-ttu-id="669eb-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="669eb-108">Identifier:</span></span>  <br/> |<span data-ttu-id="669eb-109">0x0042</span><span class="sxs-lookup"><span data-stu-id="669eb-109">0x0042</span></span>  <br/> |
|<span data-ttu-id="669eb-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="669eb-110">Data type:</span></span>  <br/> |<span data-ttu-id="669eb-111">PT_UNICODE PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="669eb-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="669eb-112">区域：</span><span class="sxs-lookup"><span data-stu-id="669eb-112">Area:</span></span>  <br/> |<span data-ttu-id="669eb-113">Address</span><span class="sxs-lookup"><span data-stu-id="669eb-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="669eb-114">备注</span><span class="sxs-lookup"><span data-stu-id="669eb-114">Remarks</span></span>

<span data-ttu-id="669eb-115">这些属性是正在表示发件人的邮件用户的地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="669eb-115">These properties are examples of the address properties for the messaging user being represented by the sender.</span></span> <span data-ttu-id="669eb-116">当客户端应用程序发送消息代表另一个客户端时，它应为该客户端的值设置所有表示发件人属性。</span><span class="sxs-lookup"><span data-stu-id="669eb-116">When a client application sends a message on behalf of another client, it should set all the represented sender properties to the values for that client.</span></span> <span data-ttu-id="669eb-117">通常在其自己的代表发送消息用户离开表示发件人属性未设置。</span><span class="sxs-lookup"><span data-stu-id="669eb-117">A messaging user sending on its own behalf typically leaves the represented sender properties unset.</span></span>
  
<span data-ttu-id="669eb-118">传出的传输提供程序必须始终保持不变，如果已发送的客户端设置此属性。</span><span class="sxs-lookup"><span data-stu-id="669eb-118">The outgoing transport provider must always leave this property unchanged if it has been set by the sending client.</span></span> <span data-ttu-id="669eb-119">如果未设置它，应出站邮件，副本上将其设置为**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) 传输提供程序并将其上的本地副本中保留未设置。</span><span class="sxs-lookup"><span data-stu-id="669eb-119">If it is unset, the transport provider should set it to **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) on the outbound copy of the message, and leave it unset on the local copy.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="669eb-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="669eb-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="669eb-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="669eb-121">Protocol specifications</span></span>

<span data-ttu-id="669eb-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="669eb-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="669eb-123">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="669eb-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="669eb-124">[[MS OXOMSG]](http://msdn.microsoft.com/zh-cn/library/cc433482%28EXCHG.80%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="669eb-124">[[MS-OXOMSG]](http://msdn.microsoft.com/zh-cn/library/cc433482%28EXCHG.80%29.aspx)</span></span>
  
> <span data-ttu-id="669eb-125">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="669eb-125">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="669eb-126">[[MS OXORSS]](http://msdn.microsoft.com/zh-cn/library/cc463884%28EXCHG.80%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="669eb-126">[[MS-OXORSS]](http://msdn.microsoft.com/zh-cn/library/cc463884%28EXCHG.80%29.aspx)</span></span>
  
> <span data-ttu-id="669eb-127">指定的属性和表示 RSS 项目的操作。</span><span class="sxs-lookup"><span data-stu-id="669eb-127">Specifies the properties and operations that represent RSS items.</span></span>
    
<span data-ttu-id="669eb-128">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="669eb-128">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="669eb-129">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="669eb-129">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="669eb-130">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="669eb-130">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="669eb-131">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="669eb-131">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="669eb-132">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="669eb-132">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="669eb-133">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="669eb-133">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="669eb-134">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="669eb-134">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="669eb-135">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="669eb-135">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="669eb-136">[[MS OXOCFG]](http://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="669eb-136">[[MS-OXOCFG]](http://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="669eb-137">指定的位置和客户端和服务器配置数据，如共享的类别列表和工作时间的属性。</span><span class="sxs-lookup"><span data-stu-id="669eb-137">Specifies the location and properties of client and server configuration data, such as shared category lists and working hours.</span></span>
    
<span data-ttu-id="669eb-138">[[MS OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="669eb-138">[[MS-OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="669eb-139">指定用于连接到和它们代表另一个用户操作时，作为代理人，以及与邮件和日历的对象交互配置邮箱的方法。</span><span class="sxs-lookup"><span data-stu-id="669eb-139">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
<span data-ttu-id="669eb-140">[[MS OXOPOST]](http://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="669eb-140">[[MS-OXOPOST]](http://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="669eb-141">指定的属性和允许的操作的 post 对象。</span><span class="sxs-lookup"><span data-stu-id="669eb-141">Specifies the properties and operations that are permissible for post objects.</span></span>
    
<span data-ttu-id="669eb-142">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="669eb-142">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="669eb-143">指定的属性和允许的联系人和个人通讯组列表对象的操作。</span><span class="sxs-lookup"><span data-stu-id="669eb-143">Specifies the properties and operations that are permissible for contact and personal distribution list objects.</span></span>
    
<span data-ttu-id="669eb-144">[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="669eb-144">[[MS-OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="669eb-145">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="669eb-145">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="669eb-146">头文件</span><span class="sxs-lookup"><span data-stu-id="669eb-146">Header files</span></span>

<span data-ttu-id="669eb-147">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="669eb-147">Mapidefs.h</span></span>
  
> <span data-ttu-id="669eb-148">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="669eb-148">Provides data type definitions.</span></span>
    
<span data-ttu-id="669eb-149">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="669eb-149">Mapitags.h</span></span>
  
> <span data-ttu-id="669eb-150">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="669eb-150">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="669eb-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="669eb-151">See also</span></span>



[<span data-ttu-id="669eb-152">PidTagDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="669eb-152">PidTagDisplayName Canonical Property</span></span>](pidtagdisplayname-canonical-property.md)


[<span data-ttu-id="669eb-153">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="669eb-153">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="669eb-154">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="669eb-154">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="669eb-155">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="669eb-155">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="669eb-156">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="669eb-156">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

