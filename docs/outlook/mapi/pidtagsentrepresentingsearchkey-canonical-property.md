---
title: PidTagSentRepresentingSearchKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSentRepresentingSearchKey
api_type:
- COM
ms.assetid: 7a49b944-cef1-4642-9208-b137fd61171a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a9361f3027453742acbe50c3de01d860289cd0ed
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356684"
---
# <a name="pidtagsentrepresentingsearchkey-canonical-property"></a><span data-ttu-id="9ef40-103">PidTagSentRepresentingSearchKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="9ef40-103">PidTagSentRepresentingSearchKey Canonical Property</span></span>

  
  
<span data-ttu-id="9ef40-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9ef40-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9ef40-105">包含由发件人代表的邮件传递用户的搜索密钥。</span><span class="sxs-lookup"><span data-stu-id="9ef40-105">Contains the search key for the messaging user represented by the sender.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9ef40-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9ef40-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9ef40-107">PR_SENT_REPRESENTING_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="9ef40-107">PR_SENT_REPRESENTING_SEARCH_KEY</span></span>  <br/> |
|<span data-ttu-id="9ef40-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="9ef40-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9ef40-109">0x003B</span><span class="sxs-lookup"><span data-stu-id="9ef40-109">0x003B</span></span>  <br/> |
|<span data-ttu-id="9ef40-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9ef40-110">Data type:</span></span>  <br/> |<span data-ttu-id="9ef40-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="9ef40-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="9ef40-112">区域：</span><span class="sxs-lookup"><span data-stu-id="9ef40-112">Area:</span></span>  <br/> |<span data-ttu-id="9ef40-113">地址</span><span class="sxs-lookup"><span data-stu-id="9ef40-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9ef40-114">备注</span><span class="sxs-lookup"><span data-stu-id="9ef40-114">Remarks</span></span>

<span data-ttu-id="9ef40-115">此属性是发件人所代表的邮件用户的地址属性之一。</span><span class="sxs-lookup"><span data-stu-id="9ef40-115">This property is one of the address properties for the messaging user who is being represented by the sender.</span></span> <span data-ttu-id="9ef40-116">当客户端应用程序代表另一个客户端发送邮件时，它应当将表示的所有发件人属性设置为该客户端的值。</span><span class="sxs-lookup"><span data-stu-id="9ef40-116">When a client application sends a message on behalf of another client, it should set all the represented sender properties to the values for that client.</span></span> <span data-ttu-id="9ef40-117">邮件用户代表自己发送的邮件通常不会设置表示的发件人属性。</span><span class="sxs-lookup"><span data-stu-id="9ef40-117">A messaging user sending on its own behalf typically leaves the represented sender properties unset.</span></span>
  
<span data-ttu-id="9ef40-118">如果发送客户端已设置此属性，则传出传输提供程序必须始终保持该属性不变。</span><span class="sxs-lookup"><span data-stu-id="9ef40-118">The outgoing transport provider must always leave this property unchanged if it has been set by the sending client.</span></span> <span data-ttu-id="9ef40-119">如果未设置，传输提供程序应在邮件的出站副本上将其设置为 **PR_SENDER_SEARCH_KEY** ([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md)) ，并在本地副本上将其保持未设置状态。</span><span class="sxs-lookup"><span data-stu-id="9ef40-119">If it is unset, the transport provider should set it to **PR_SENDER_SEARCH_KEY** ([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md)) on the outbound copy of the message, and leave it unset on the local copy.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="9ef40-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="9ef40-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="9ef40-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="9ef40-121">Protocol specifications</span></span>

<span data-ttu-id="9ef40-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9ef40-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9ef40-123">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="9ef40-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="9ef40-124">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9ef40-124">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9ef40-125">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="9ef40-125">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="9ef40-126">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9ef40-126">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9ef40-127">处理客户端和服务器之间数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="9ef40-127">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="9ef40-128">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9ef40-128">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9ef40-129">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间转换。</span><span class="sxs-lookup"><span data-stu-id="9ef40-129">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="9ef40-130">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9ef40-130">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9ef40-131">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="9ef40-131">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="9ef40-132">[[MS-OXOPOST]](https://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9ef40-132">[[MS-OXOPOST]](https://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9ef40-133">指定 post 对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="9ef40-133">Specifies the properties and operations that are permissible for post objects.</span></span>
    
<span data-ttu-id="9ef40-134">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9ef40-134">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9ef40-135">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="9ef40-135">Specifies the properties and operations that are permissible for contact and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="9ef40-136">头文件</span><span class="sxs-lookup"><span data-stu-id="9ef40-136">Header files</span></span>

<span data-ttu-id="9ef40-137">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9ef40-137">Mapidefs.h</span></span>
  
> <span data-ttu-id="9ef40-138">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9ef40-138">Provides data type definitions.</span></span>
    
<span data-ttu-id="9ef40-139">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="9ef40-139">Mapitags.h</span></span>
  
> <span data-ttu-id="9ef40-140">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="9ef40-140">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9ef40-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ef40-141">See also</span></span>



[<span data-ttu-id="9ef40-142">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9ef40-142">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9ef40-143">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9ef40-143">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9ef40-144">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9ef40-144">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9ef40-145">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9ef40-145">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

