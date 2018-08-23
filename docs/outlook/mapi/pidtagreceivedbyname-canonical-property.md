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
ms.openlocfilehash: d5afe0cfff03feafeb8299780b9402cef3282632
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577070"
---
# <a name="pidtagreceivedbyname-canonical-property"></a><span data-ttu-id="9e979-103">PidTagReceivedByName 规范属性</span><span class="sxs-lookup"><span data-stu-id="9e979-103">PidTagReceivedByName Canonical Property</span></span>

  
  
<span data-ttu-id="9e979-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9e979-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9e979-105">包含消息中接收的消息的用户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="9e979-105">Contains the display name of the messaging user who receives the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9e979-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9e979-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9e979-107">PR_RECEIVED_BY_NAME，PR_RECEIVED_BY_NAME_A，PR_RECEIVED_BY_NAME_W</span><span class="sxs-lookup"><span data-stu-id="9e979-107">PR_RECEIVED_BY_NAME, PR_RECEIVED_BY_NAME_A, PR_RECEIVED_BY_NAME_W</span></span>  <br/> |
|<span data-ttu-id="9e979-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="9e979-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9e979-109">0x0040</span><span class="sxs-lookup"><span data-stu-id="9e979-109">0x0040</span></span>  <br/> |
|<span data-ttu-id="9e979-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9e979-110">Data type:</span></span>  <br/> |<span data-ttu-id="9e979-111">PT_UNICODE PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="9e979-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="9e979-112">区域：</span><span class="sxs-lookup"><span data-stu-id="9e979-112">Area:</span></span>  <br/> |<span data-ttu-id="9e979-113">Address</span><span class="sxs-lookup"><span data-stu-id="9e979-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9e979-114">注解</span><span class="sxs-lookup"><span data-stu-id="9e979-114">Remarks</span></span>

<span data-ttu-id="9e979-115">这些属性是个收到邮件的邮件用户的地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="9e979-115">These properties are an example of the address properties for the messaging user who receives the message.</span></span> <span data-ttu-id="9e979-116">它们必须由传入传输提供程序设置。</span><span class="sxs-lookup"><span data-stu-id="9e979-116">They must be set by the incoming transport provider.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="9e979-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="9e979-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="9e979-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="9e979-118">Protocol specifications</span></span>

<span data-ttu-id="9e979-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9e979-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9e979-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="9e979-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="9e979-121">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9e979-121">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9e979-122">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="9e979-122">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="9e979-123">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9e979-123">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9e979-124">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="9e979-124">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="9e979-125">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9e979-125">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9e979-126">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="9e979-126">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="9e979-127">[[MS OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9e979-127">[[MS-OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9e979-128">指定用于连接到和它们代表另一个用户操作时，作为代理人，以及与邮件和日历的对象交互配置邮箱的方法。</span><span class="sxs-lookup"><span data-stu-id="9e979-128">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
<span data-ttu-id="9e979-129">[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9e979-129">[[MS-OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9e979-130">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="9e979-130">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="9e979-131">头文件</span><span class="sxs-lookup"><span data-stu-id="9e979-131">Header files</span></span>

<span data-ttu-id="9e979-132">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9e979-132">Mapidefs.h</span></span>
  
> <span data-ttu-id="9e979-133">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9e979-133">Provides data type definitions.</span></span>
    
<span data-ttu-id="9e979-134">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="9e979-134">Mapitags.h</span></span>
  
> <span data-ttu-id="9e979-135">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="9e979-135">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9e979-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e979-136">See also</span></span>



[<span data-ttu-id="9e979-137">PidTagDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="9e979-137">PidTagDisplayName Canonical Property</span></span>](pidtagdisplayname-canonical-property.md)


[<span data-ttu-id="9e979-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9e979-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9e979-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9e979-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9e979-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9e979-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9e979-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9e979-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

