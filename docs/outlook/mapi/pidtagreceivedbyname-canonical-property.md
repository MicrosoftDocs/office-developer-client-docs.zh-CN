---
title: PidTagReceivedByName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReceivedByName
api_type:
- COM
ms.assetid: edd29217-74bb-4321-82fd-65f0fbfd05f8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 039a51c2bb4cf1fe2a83e2ba144a87462b5d6d0c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359211"
---
# <a name="pidtagreceivedbyname-canonical-property"></a><span data-ttu-id="221cc-103">PidTagReceivedByName 规范属性</span><span class="sxs-lookup"><span data-stu-id="221cc-103">PidTagReceivedByName Canonical Property</span></span>

  
  
<span data-ttu-id="221cc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="221cc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="221cc-105">包含显示名称消息的用户的联系人。</span><span class="sxs-lookup"><span data-stu-id="221cc-105">Contains the display name of the messaging user who receives the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="221cc-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="221cc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="221cc-107">PR_RECEIVED_BY_NAME、PR_RECEIVED_BY_NAME_A、PR_RECEIVED_BY_NAME_W</span><span class="sxs-lookup"><span data-stu-id="221cc-107">PR_RECEIVED_BY_NAME, PR_RECEIVED_BY_NAME_A, PR_RECEIVED_BY_NAME_W</span></span>  <br/> |
|<span data-ttu-id="221cc-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="221cc-108">Identifier:</span></span>  <br/> |<span data-ttu-id="221cc-109">0x0040</span><span class="sxs-lookup"><span data-stu-id="221cc-109">0x0040</span></span>  <br/> |
|<span data-ttu-id="221cc-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="221cc-110">Data type:</span></span>  <br/> |<span data-ttu-id="221cc-111">PT_UNICODE、PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="221cc-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="221cc-112">区域：</span><span class="sxs-lookup"><span data-stu-id="221cc-112">Area:</span></span>  <br/> |<span data-ttu-id="221cc-113">地址</span><span class="sxs-lookup"><span data-stu-id="221cc-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="221cc-114">备注</span><span class="sxs-lookup"><span data-stu-id="221cc-114">Remarks</span></span>

<span data-ttu-id="221cc-115">这些属性是接收邮件的邮件用户的地址属性示例。</span><span class="sxs-lookup"><span data-stu-id="221cc-115">These properties are an example of the address properties for the messaging user who receives the message.</span></span> <span data-ttu-id="221cc-116">它们必须由传入传输提供程序设置。</span><span class="sxs-lookup"><span data-stu-id="221cc-116">They must be set by the incoming transport provider.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="221cc-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="221cc-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="221cc-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="221cc-118">Protocol specifications</span></span>

<span data-ttu-id="221cc-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="221cc-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="221cc-120">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="221cc-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="221cc-121">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="221cc-121">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="221cc-122">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="221cc-122">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="221cc-123">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="221cc-123">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="221cc-124">处理客户端和服务器之间数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="221cc-124">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="221cc-125">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="221cc-125">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="221cc-126">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间转换。</span><span class="sxs-lookup"><span data-stu-id="221cc-126">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="221cc-127">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="221cc-127">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="221cc-128">指定用于连接邮箱和将邮箱配置为代理的方法，以及代表其他用户操作时与邮件和日历对象的交互的方法。</span><span class="sxs-lookup"><span data-stu-id="221cc-128">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
<span data-ttu-id="221cc-129">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="221cc-129">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="221cc-130">将邮件和附件对象编码和解码为有效的流表示形式。</span><span class="sxs-lookup"><span data-stu-id="221cc-130">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="221cc-131">头文件</span><span class="sxs-lookup"><span data-stu-id="221cc-131">Header files</span></span>

<span data-ttu-id="221cc-132">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="221cc-132">Mapidefs.h</span></span>
  
> <span data-ttu-id="221cc-133">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="221cc-133">Provides data type definitions.</span></span>
    
<span data-ttu-id="221cc-134">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="221cc-134">Mapitags.h</span></span>
  
> <span data-ttu-id="221cc-135">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="221cc-135">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="221cc-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="221cc-136">See also</span></span>



[<span data-ttu-id="221cc-137">PidTagDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="221cc-137">PidTagDisplayName Canonical Property</span></span>](pidtagdisplayname-canonical-property.md)


[<span data-ttu-id="221cc-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="221cc-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="221cc-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="221cc-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="221cc-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="221cc-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="221cc-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="221cc-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

