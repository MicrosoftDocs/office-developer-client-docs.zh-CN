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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341949"
---
# <a name="pidtagtnefcorrelationkey-canonical-property"></a><span data-ttu-id="dd6cf-103">PidTagTnefCorrelationKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="dd6cf-103">PidTagTnefCorrelationKey Canonical Property</span></span>

  
  
<span data-ttu-id="dd6cf-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dd6cf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dd6cf-105">包含一个值, 该值将传输中性封装格式 (TNEF) 附件与邮件关联起来。</span><span class="sxs-lookup"><span data-stu-id="dd6cf-105">Contains a value that correlates a Transport Neutral Encapsulation Format (TNEF) attachment with a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dd6cf-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="dd6cf-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="dd6cf-107">PR_TNEF_CORRELATION_KEY</span><span class="sxs-lookup"><span data-stu-id="dd6cf-107">PR_TNEF_CORRELATION_KEY</span></span>  <br/> |
|<span data-ttu-id="dd6cf-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="dd6cf-108">Identifier:</span></span>  <br/> |<span data-ttu-id="dd6cf-109">0x007F</span><span class="sxs-lookup"><span data-stu-id="dd6cf-109">0x007F</span></span>  <br/> |
|<span data-ttu-id="dd6cf-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="dd6cf-110">Data type:</span></span>  <br/> |<span data-ttu-id="dd6cf-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="dd6cf-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="dd6cf-112">区域：</span><span class="sxs-lookup"><span data-stu-id="dd6cf-112">Area:</span></span>  <br/> |<span data-ttu-id="dd6cf-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="dd6cf-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dd6cf-114">注解</span><span class="sxs-lookup"><span data-stu-id="dd6cf-114">Remarks</span></span>

<span data-ttu-id="dd6cf-115">建议 TNEF 附件子对象公开此属性。</span><span class="sxs-lookup"><span data-stu-id="dd6cf-115">It is recommended that TNEF attachment sub-objects expose this property.</span></span> <span data-ttu-id="dd6cf-116">此属性确定入站 TNEF 文件是否属于它所附加到的邮件。</span><span class="sxs-lookup"><span data-stu-id="dd6cf-116">This property determines whether or not an inbound TNEF file belongs to the message it is attached to.</span></span> <span data-ttu-id="dd6cf-117">它主要由传输提供程序和网关使用。</span><span class="sxs-lookup"><span data-stu-id="dd6cf-117">It is used primarily by transport providers and gateways.</span></span>
  
<span data-ttu-id="dd6cf-118">在出站邮件中, 传输提供程序应计算该邮件的唯一的二进制值, 或使用满足唯一性要求的现有值, 例如邮件标识符。</span><span class="sxs-lookup"><span data-stu-id="dd6cf-118">On an outbound message, the transport provider should compute a binary value unique to that message, or use an existing value that satisfies the uniqueness requirement, such as a message identifier.</span></span> <span data-ttu-id="dd6cf-119">传输提供程序应将此值存储在此属性中, 然后调用[ITnef:: AddProps](itnef-addprops.md)方法将其封装。</span><span class="sxs-lookup"><span data-stu-id="dd6cf-119">The transport provider should store this value in this property and then call the [ITnef::AddProps](itnef-addprops.md) method to encapsulate it.</span></span> <span data-ttu-id="dd6cf-120">相同的值还应存储在传输信封中, 在提供商定义的位置 (如邮件头) 中。</span><span class="sxs-lookup"><span data-stu-id="dd6cf-120">The same value should also be stored in the transport envelope in a place defined by the provider, such as the message header.</span></span> 
  
<span data-ttu-id="dd6cf-121">在入站邮件中, 传输提供程序应调用[ITnef:: ExtractProps](itnef-extractprops.md)方法以 decapsulate TNEF 附件, 然后将此属性与存储在传输信封中的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="dd6cf-121">On an inbound message, the transport provider should call the [ITnef::ExtractProps](itnef-extractprops.md) method to decapsulate the TNEF attachment and then compare this property with the value stored in the transport envelope.</span></span> <span data-ttu-id="dd6cf-122">如果值匹配, TNEF 应正常处理, 也就是说, 应使用从 TNEF 附件提取的所有属性。</span><span class="sxs-lookup"><span data-stu-id="dd6cf-122">If the values match, TNEF should be processed normally, that is, all the properties extracted from the TNEF attachment should be used.</span></span> <span data-ttu-id="dd6cf-123">如果值不匹配, 应忽略 TNEF 附件中的所有属性。</span><span class="sxs-lookup"><span data-stu-id="dd6cf-123">If the values do not match, all the properties from the TNEF attachment should be ignored.</span></span> <span data-ttu-id="dd6cf-124">如果未设置此属性, 则 TNEF 文件应被视为属于此邮件, 并且应使用从该邮件中提取的其他属性。</span><span class="sxs-lookup"><span data-stu-id="dd6cf-124">If this property is not set, the TNEF file should be considered to belong to this message, and the other properties extracted from it should be used.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="dd6cf-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="dd6cf-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="dd6cf-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="dd6cf-126">Protocol specifications</span></span>

<span data-ttu-id="dd6cf-127">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dd6cf-127">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dd6cf-128">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="dd6cf-128">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="dd6cf-129">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dd6cf-129">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dd6cf-130">处理客户端与服务器之间的数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="dd6cf-130">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="dd6cf-131">[[毫秒-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dd6cf-131">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dd6cf-132">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="dd6cf-132">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="dd6cf-133">[[毫秒-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dd6cf-133">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dd6cf-134">将邮件和附件对象编码并解码为高效流表示形式。</span><span class="sxs-lookup"><span data-stu-id="dd6cf-134">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="dd6cf-135">头文件</span><span class="sxs-lookup"><span data-stu-id="dd6cf-135">Header files</span></span>

<span data-ttu-id="dd6cf-136">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="dd6cf-136">Mapidefs.h</span></span>
  
> <span data-ttu-id="dd6cf-137">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="dd6cf-137">Provides data type definitions.</span></span>
    
<span data-ttu-id="dd6cf-138">Mapitags</span><span class="sxs-lookup"><span data-stu-id="dd6cf-138">Mapitags.h</span></span>
  
> <span data-ttu-id="dd6cf-139">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="dd6cf-139">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dd6cf-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd6cf-140">See also</span></span>



[<span data-ttu-id="dd6cf-141">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="dd6cf-141">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="dd6cf-142">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="dd6cf-142">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="dd6cf-143">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="dd6cf-143">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="dd6cf-144">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="dd6cf-144">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

