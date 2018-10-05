---
title: PidTagTnefCorrelationKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagTnefCorrelationKey
api_type:
- COM
ms.assetid: a7f05c8c-59b4-4d5b-8e70-ebcde5f2ed45
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e38cf93523c14d2d58c48e24a79249674298b4b2
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393843"
---
# <a name="pidtagtnefcorrelationkey-canonical-property"></a><span data-ttu-id="f09eb-103">PidTagTnefCorrelationKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="f09eb-103">PidTagTnefCorrelationKey Canonical Property</span></span>

  
  
<span data-ttu-id="f09eb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f09eb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f09eb-105">包含一个值，对应一条消息的传输中性封装格式 (TNEF) 附件。</span><span class="sxs-lookup"><span data-stu-id="f09eb-105">Contains a value that correlates a Transport Neutral Encapsulation Format (TNEF) attachment with a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f09eb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f09eb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f09eb-107">PR_TNEF_CORRELATION_KEY</span><span class="sxs-lookup"><span data-stu-id="f09eb-107">PR_TNEF_CORRELATION_KEY</span></span>  <br/> |
|<span data-ttu-id="f09eb-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="f09eb-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f09eb-109">0x007f 来</span><span class="sxs-lookup"><span data-stu-id="f09eb-109">0x007F</span></span>  <br/> |
|<span data-ttu-id="f09eb-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f09eb-110">Data type:</span></span>  <br/> |<span data-ttu-id="f09eb-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="f09eb-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="f09eb-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f09eb-112">Area:</span></span>  <br/> |<span data-ttu-id="f09eb-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="f09eb-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f09eb-114">说明</span><span class="sxs-lookup"><span data-stu-id="f09eb-114">Remarks</span></span>

<span data-ttu-id="f09eb-115">建议 TNEF 附件子对象公开此属性。</span><span class="sxs-lookup"><span data-stu-id="f09eb-115">It is recommended that TNEF attachment sub-objects expose this property.</span></span> <span data-ttu-id="f09eb-116">此属性确定的入站的 TNEF 文件属于附加到邮件。</span><span class="sxs-lookup"><span data-stu-id="f09eb-116">This property determines whether or not an inbound TNEF file belongs to the message it is attached to.</span></span> <span data-ttu-id="f09eb-117">主要由传输提供程序和网关使用它。</span><span class="sxs-lookup"><span data-stu-id="f09eb-117">It is used primarily by transport providers and gateways.</span></span>
  
<span data-ttu-id="f09eb-118">对出站邮件传输提供程序应计算对该邮件，唯一的二进制值或使用现有值满足唯一性要求，如消息标识符。</span><span class="sxs-lookup"><span data-stu-id="f09eb-118">On an outbound message, the transport provider should compute a binary value unique to that message, or use an existing value that satisfies the uniqueness requirement, such as a message identifier.</span></span> <span data-ttu-id="f09eb-119">传输提供程序应将此值存储在此属性，然后调用它封装的[ITnef::AddProps](itnef-addprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="f09eb-119">The transport provider should store this value in this property and then call the [ITnef::AddProps](itnef-addprops.md) method to encapsulate it.</span></span> <span data-ttu-id="f09eb-120">相同的值还应存储在提供程序，如邮件头定义的位置中的传输信封。</span><span class="sxs-lookup"><span data-stu-id="f09eb-120">The same value should also be stored in the transport envelope in a place defined by the provider, such as the message header.</span></span> 
  
<span data-ttu-id="f09eb-121">对入站邮件传输提供程序应呼叫确实 TNEF 附件[ITnef::ExtractProps](itnef-extractprops.md)方法，然后将此属性存储在传输信封中的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="f09eb-121">On an inbound message, the transport provider should call the [ITnef::ExtractProps](itnef-extractprops.md) method to decapsulate the TNEF attachment and then compare this property with the value stored in the transport envelope.</span></span> <span data-ttu-id="f09eb-122">如果值匹配，通常应处理 TNEF，即，应使用 TNEF 附件从提取的所有属性。</span><span class="sxs-lookup"><span data-stu-id="f09eb-122">If the values match, TNEF should be processed normally, that is, all the properties extracted from the TNEF attachment should be used.</span></span> <span data-ttu-id="f09eb-123">如果值不匹配，应忽略 TNEF 附件中的所有属性。</span><span class="sxs-lookup"><span data-stu-id="f09eb-123">If the values do not match, all the properties from the TNEF attachment should be ignored.</span></span> <span data-ttu-id="f09eb-124">如果未设置此属性，应考虑 TNEF 文件属于此消息，并应从其提取的其他属性。</span><span class="sxs-lookup"><span data-stu-id="f09eb-124">If this property is not set, the TNEF file should be considered to belong to this message, and the other properties extracted from it should be used.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="f09eb-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="f09eb-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f09eb-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="f09eb-126">Protocol specifications</span></span>

<span data-ttu-id="f09eb-127">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f09eb-127">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f09eb-128">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="f09eb-128">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="f09eb-129">[[MS OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f09eb-129">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f09eb-130">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="f09eb-130">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="f09eb-131">[[MS OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f09eb-131">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f09eb-132">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="f09eb-132">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="f09eb-133">[[MS OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f09eb-133">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f09eb-134">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="f09eb-134">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f09eb-135">头文件</span><span class="sxs-lookup"><span data-stu-id="f09eb-135">Header files</span></span>

<span data-ttu-id="f09eb-136">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f09eb-136">Mapidefs.h</span></span>
  
> <span data-ttu-id="f09eb-137">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f09eb-137">Provides data type definitions.</span></span>
    
<span data-ttu-id="f09eb-138">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f09eb-138">Mapitags.h</span></span>
  
> <span data-ttu-id="f09eb-139">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f09eb-139">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f09eb-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f09eb-140">See also</span></span>



[<span data-ttu-id="f09eb-141">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f09eb-141">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f09eb-142">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f09eb-142">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f09eb-143">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f09eb-143">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f09eb-144">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f09eb-144">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

