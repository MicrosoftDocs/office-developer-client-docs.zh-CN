---
title: PidTagAlternateRecipient 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAlternateRecipient
api_type:
- HeaderDef
ms.assetid: df787b60-2f53-42ac-89b5-1b52c906f472
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7c304de3184e49044d3f83cef1f1ebaac019b2ee
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360093"
---
# <a name="pidtagalternaterecipient-canonical-property"></a><span data-ttu-id="72dad-103">PidTagAlternateRecipient 规范属性</span><span class="sxs-lookup"><span data-stu-id="72dad-103">PidTagAlternateRecipient Canonical Property</span></span>

  
  
<span data-ttu-id="72dad-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="72dad-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="72dad-105">包含原始收件人指定的备用收件人的条目标识符列表。</span><span class="sxs-lookup"><span data-stu-id="72dad-105">Contains a list of entry identifiers for alternate recipients designated by the original recipient.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="72dad-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="72dad-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="72dad-107">PR_ALTERNATE_RECIPIENT</span><span class="sxs-lookup"><span data-stu-id="72dad-107">PR_ALTERNATE_RECIPIENT</span></span>  <br/> |
|<span data-ttu-id="72dad-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="72dad-108">Identifier:</span></span>  <br/> |<span data-ttu-id="72dad-109">0x3A01</span><span class="sxs-lookup"><span data-stu-id="72dad-109">0x3A01</span></span>  <br/> |
|<span data-ttu-id="72dad-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="72dad-110">Data type:</span></span>  <br/> |<span data-ttu-id="72dad-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="72dad-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="72dad-112">区域：</span><span class="sxs-lookup"><span data-stu-id="72dad-112">Area:</span></span>  <br/> |<span data-ttu-id="72dad-113">地址</span><span class="sxs-lookup"><span data-stu-id="72dad-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="72dad-114">备注</span><span class="sxs-lookup"><span data-stu-id="72dad-114">Remarks</span></span>

<span data-ttu-id="72dad-115">此属性用于自动转发的邮件。</span><span class="sxs-lookup"><span data-stu-id="72dad-115">This property is used for auto forwarded messages.</span></span> <span data-ttu-id="72dad-116">它包含备用 [收件人的 FLATENTRYLIST](flatentrylist.md) 结构。</span><span class="sxs-lookup"><span data-stu-id="72dad-116">It contains a [FLATENTRYLIST](flatentrylist.md) structure of alternate recipients.</span></span> <span data-ttu-id="72dad-117">如果不允许自动前向或尚未指定备用收件人，则生成未送达报告。</span><span class="sxs-lookup"><span data-stu-id="72dad-117">If autoforwarding is not permitted or if no alternate recipient has been designated, a nondelivery report is generated.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="72dad-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="72dad-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="72dad-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="72dad-119">Protocol specifications</span></span>

<span data-ttu-id="72dad-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="72dad-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="72dad-121">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="72dad-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="72dad-122">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="72dad-122">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="72dad-123">处理客户端和服务器之间数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="72dad-123">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="72dad-124">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="72dad-124">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="72dad-125">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间转换。</span><span class="sxs-lookup"><span data-stu-id="72dad-125">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="72dad-126">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="72dad-126">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="72dad-127">将邮件和附件对象编码和解码为有效的流表示形式。</span><span class="sxs-lookup"><span data-stu-id="72dad-127">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="72dad-128">头文件</span><span class="sxs-lookup"><span data-stu-id="72dad-128">Header files</span></span>

<span data-ttu-id="72dad-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="72dad-129">Mapitags.h</span></span>
  
> <span data-ttu-id="72dad-130">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="72dad-130">Contains definitions of properties listed as associated properties.</span></span>
    
<span data-ttu-id="72dad-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="72dad-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="72dad-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="72dad-132">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="72dad-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72dad-133">See also</span></span>



[<span data-ttu-id="72dad-134">FLATENTRYLIST</span><span class="sxs-lookup"><span data-stu-id="72dad-134">FLATENTRYLIST</span></span>](flatentrylist.md)


[<span data-ttu-id="72dad-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="72dad-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="72dad-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="72dad-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="72dad-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="72dad-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="72dad-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="72dad-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

