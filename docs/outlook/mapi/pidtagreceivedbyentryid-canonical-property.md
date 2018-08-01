---
title: PidTagReceivedByEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReceivedByEntryId
api_type:
- COM
ms.assetid: 737f8584-fc52-4324-ac40-2fc554a3095d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e7d457c898a1b8c733913de0fbb2fbfe9542dc9c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778118"
---
# <a name="pidtagreceivedbyentryid-canonical-property"></a><span data-ttu-id="4d4fd-103">PidTagReceivedByEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="4d4fd-103">PidTagReceivedByEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="4d4fd-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4d4fd-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4d4fd-105">包含实际收到邮件的邮件用户的项标识符。</span><span class="sxs-lookup"><span data-stu-id="4d4fd-105">Contains the entry identifier of the messaging user who actually receives the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4d4fd-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4d4fd-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4d4fd-107">PR_RECEIVED_BY_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="4d4fd-107">PR_RECEIVED_BY_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="4d4fd-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="4d4fd-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4d4fd-109">0x003F</span><span class="sxs-lookup"><span data-stu-id="4d4fd-109">0x003F</span></span>  <br/> |
|<span data-ttu-id="4d4fd-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4d4fd-110">Data type:</span></span>  <br/> |<span data-ttu-id="4d4fd-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="4d4fd-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="4d4fd-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4d4fd-112">Area:</span></span>  <br/> |<span data-ttu-id="4d4fd-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="4d4fd-113">Address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4d4fd-114">说明</span><span class="sxs-lookup"><span data-stu-id="4d4fd-114">Remarks</span></span>

<span data-ttu-id="4d4fd-115">此属性是一个收到邮件的邮件用户的地址属性。</span><span class="sxs-lookup"><span data-stu-id="4d4fd-115">This property is one of the address properties for the messaging user who receives the message.</span></span> <span data-ttu-id="4d4fd-116">它必须由传入传输提供程序设置。</span><span class="sxs-lookup"><span data-stu-id="4d4fd-116">It must be set by the incoming transport provider.</span></span>
  
<span data-ttu-id="4d4fd-117">此属性对应于 X.400 传递信封每封邮件 MH_T_ 属性。</span><span class="sxs-lookup"><span data-stu-id="4d4fd-117">This property corresponds to an X.400 delivery envelope per-message MH_T_ attribute.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="4d4fd-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="4d4fd-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4d4fd-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="4d4fd-119">Protocol specifications</span></span>

<span data-ttu-id="4d4fd-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4d4fd-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4d4fd-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="4d4fd-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4d4fd-122">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4d4fd-122">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4d4fd-123">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="4d4fd-123">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="4d4fd-124">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4d4fd-124">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4d4fd-125">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="4d4fd-125">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="4d4fd-126">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4d4fd-126">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4d4fd-127">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议项目之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="4d4fd-127">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting items.</span></span>
    
<span data-ttu-id="4d4fd-128">[[MS OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4d4fd-128">[[MS-OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4d4fd-129">指定用于连接到和它们代表另一个用户操作时，作为代理人，以及与邮件和日历的对象交互配置邮箱的方法。</span><span class="sxs-lookup"><span data-stu-id="4d4fd-129">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
<span data-ttu-id="4d4fd-130">[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4d4fd-130">[[MS-OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4d4fd-131">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="4d4fd-131">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4d4fd-132">头文件</span><span class="sxs-lookup"><span data-stu-id="4d4fd-132">Header files</span></span>

<span data-ttu-id="4d4fd-133">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4d4fd-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="4d4fd-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4d4fd-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="4d4fd-135">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="4d4fd-135">Mapitags.h</span></span>
  
> <span data-ttu-id="4d4fd-136">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4d4fd-136">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4d4fd-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d4fd-137">See also</span></span>



[<span data-ttu-id="4d4fd-138">PidTagEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="4d4fd-138">PidTagEntryId Canonical Property</span></span>](pidtagentryid-canonical-property.md)


[<span data-ttu-id="4d4fd-139">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4d4fd-139">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4d4fd-140">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4d4fd-140">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4d4fd-141">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4d4fd-141">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4d4fd-142">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4d4fd-142">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

