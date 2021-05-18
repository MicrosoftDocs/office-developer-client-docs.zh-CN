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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8e2df13f4e9c5d1d636c4f71ea6805ac031899e9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314929"
---
# <a name="pidtagsentrepresentingname-canonical-property"></a><span data-ttu-id="5b4a1-103">PidTagSentRepresentingName 规范属性</span><span class="sxs-lookup"><span data-stu-id="5b4a1-103">PidTagSentRepresentingName Canonical Property</span></span>

  
  
<span data-ttu-id="5b4a1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5b4a1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5b4a1-105">包含显示名称代表的邮件用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="5b4a1-105">Contains the display name for the messaging user represented by the sender.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5b4a1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5b4a1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5b4a1-107">PR_SENT_REPRESENTING_NAME、PR_SENT_REPRESENTING_NAME_A、PR_SENT_REPRESENTING_NAME_W</span><span class="sxs-lookup"><span data-stu-id="5b4a1-107">PR_SENT_REPRESENTING_NAME, PR_SENT_REPRESENTING_NAME_A, PR_SENT_REPRESENTING_NAME_W</span></span>  <br/> |
|<span data-ttu-id="5b4a1-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="5b4a1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5b4a1-109">0x0042</span><span class="sxs-lookup"><span data-stu-id="5b4a1-109">0x0042</span></span>  <br/> |
|<span data-ttu-id="5b4a1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5b4a1-110">Data type:</span></span>  <br/> |<span data-ttu-id="5b4a1-111">PT_UNICODE、PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="5b4a1-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="5b4a1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5b4a1-112">Area:</span></span>  <br/> |<span data-ttu-id="5b4a1-113">地址</span><span class="sxs-lookup"><span data-stu-id="5b4a1-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5b4a1-114">备注</span><span class="sxs-lookup"><span data-stu-id="5b4a1-114">Remarks</span></span>

<span data-ttu-id="5b4a1-115">这些属性是发件人所代表的邮件用户的地址属性示例。</span><span class="sxs-lookup"><span data-stu-id="5b4a1-115">These properties are examples of the address properties for the messaging user being represented by the sender.</span></span> <span data-ttu-id="5b4a1-116">当客户端应用程序代表另一个客户端发送邮件时，它应当将表示的所有发件人属性设置为该客户端的值。</span><span class="sxs-lookup"><span data-stu-id="5b4a1-116">When a client application sends a message on behalf of another client, it should set all the represented sender properties to the values for that client.</span></span> <span data-ttu-id="5b4a1-117">邮件用户代表自己发送的邮件通常不会设置表示的发件人属性。</span><span class="sxs-lookup"><span data-stu-id="5b4a1-117">A messaging user sending on its own behalf typically leaves the represented sender properties unset.</span></span>
  
<span data-ttu-id="5b4a1-118">如果发送客户端已设置此属性，则传出传输提供程序必须始终保持该属性不变。</span><span class="sxs-lookup"><span data-stu-id="5b4a1-118">The outgoing transport provider must always leave this property unchanged if it has been set by the sending client.</span></span> <span data-ttu-id="5b4a1-119">如果未设置，传输提供程序应在邮件的出站副本上将其设置为 **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) ，并在本地副本上将其保持未设置状态。</span><span class="sxs-lookup"><span data-stu-id="5b4a1-119">If it is unset, the transport provider should set it to **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) on the outbound copy of the message, and leave it unset on the local copy.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5b4a1-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="5b4a1-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5b4a1-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="5b4a1-121">Protocol specifications</span></span>

<span data-ttu-id="5b4a1-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5b4a1-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5b4a1-123">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="5b4a1-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5b4a1-124">[[MS-OXOMSG]](https://msdn.microsoft.com/library/cc433482%28EXCHG.80%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5b4a1-124">[[MS-OXOMSG]](https://msdn.microsoft.com/library/cc433482%28EXCHG.80%29.aspx)</span></span>
  
> <span data-ttu-id="5b4a1-125">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="5b4a1-125">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="5b4a1-126">[[MS-OXORSS]](https://msdn.microsoft.com/library/cc463884%28EXCHG.80%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5b4a1-126">[[MS-OXORSS]](https://msdn.microsoft.com/library/cc463884%28EXCHG.80%29.aspx)</span></span>
  
> <span data-ttu-id="5b4a1-127">指定表示 RSS 项目的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="5b4a1-127">Specifies the properties and operations that represent RSS items.</span></span>
    
<span data-ttu-id="5b4a1-128">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5b4a1-128">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5b4a1-129">处理客户端和服务器之间数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="5b4a1-129">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="5b4a1-130">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5b4a1-130">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5b4a1-131">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间转换。</span><span class="sxs-lookup"><span data-stu-id="5b4a1-131">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="5b4a1-132">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5b4a1-132">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5b4a1-133">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="5b4a1-133">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="5b4a1-134">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5b4a1-134">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5b4a1-135">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="5b4a1-135">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="5b4a1-136">[[MS-OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5b4a1-136">[[MS-OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5b4a1-137">指定客户端和服务器配置数据的位置和属性，例如共享类别列表和工作时间。</span><span class="sxs-lookup"><span data-stu-id="5b4a1-137">Specifies the location and properties of client and server configuration data, such as shared category lists and working hours.</span></span>
    
<span data-ttu-id="5b4a1-138">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5b4a1-138">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5b4a1-139">指定用于连接邮箱和将邮箱配置为代理的方法，以及代表其他用户操作时与邮件和日历对象的交互的方法。</span><span class="sxs-lookup"><span data-stu-id="5b4a1-139">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
<span data-ttu-id="5b4a1-140">[[MS-OXOPOST]](https://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5b4a1-140">[[MS-OXOPOST]](https://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5b4a1-141">指定 post 对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="5b4a1-141">Specifies the properties and operations that are permissible for post objects.</span></span>
    
<span data-ttu-id="5b4a1-142">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5b4a1-142">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5b4a1-143">指定联系人和个人通讯组列表对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="5b4a1-143">Specifies the properties and operations that are permissible for contact and personal distribution list objects.</span></span>
    
<span data-ttu-id="5b4a1-144">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5b4a1-144">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5b4a1-145">将邮件和附件对象编码和解码为有效的流表示形式。</span><span class="sxs-lookup"><span data-stu-id="5b4a1-145">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5b4a1-146">头文件</span><span class="sxs-lookup"><span data-stu-id="5b4a1-146">Header files</span></span>

<span data-ttu-id="5b4a1-147">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5b4a1-147">Mapidefs.h</span></span>
  
> <span data-ttu-id="5b4a1-148">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5b4a1-148">Provides data type definitions.</span></span>
    
<span data-ttu-id="5b4a1-149">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="5b4a1-149">Mapitags.h</span></span>
  
> <span data-ttu-id="5b4a1-150">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5b4a1-150">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5b4a1-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b4a1-151">See also</span></span>



[<span data-ttu-id="5b4a1-152">PidTagDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="5b4a1-152">PidTagDisplayName Canonical Property</span></span>](pidtagdisplayname-canonical-property.md)


[<span data-ttu-id="5b4a1-153">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5b4a1-153">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5b4a1-154">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5b4a1-154">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5b4a1-155">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5b4a1-155">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5b4a1-156">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5b4a1-156">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

