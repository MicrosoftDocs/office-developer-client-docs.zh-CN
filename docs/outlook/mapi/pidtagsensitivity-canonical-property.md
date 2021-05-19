---
title: PidTagSensitivity 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSensitivity
api_type:
- COM
ms.assetid: 5b678475-f2a8-4831-ad68-11654e09c821
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: eab8ce71d28a672d7069a1c16da5cd2cc2e149f7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342502"
---
# <a name="pidtagsensitivity-canonical-property"></a><span data-ttu-id="ea4c1-103">PidTagSensitivity 规范属性</span><span class="sxs-lookup"><span data-stu-id="ea4c1-103">PidTagSensitivity Canonical Property</span></span>

  
  
<span data-ttu-id="ea4c1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ea4c1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ea4c1-105">包含一个值，该值指示邮件发件人对邮件的敏感度的意见。</span><span class="sxs-lookup"><span data-stu-id="ea4c1-105">Contains a value that indicates the message sender's opinion of the sensitivity of a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ea4c1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ea4c1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ea4c1-107">PR_SENSITIVITY</span><span class="sxs-lookup"><span data-stu-id="ea4c1-107">PR_SENSITIVITY</span></span>  <br/> |
|<span data-ttu-id="ea4c1-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ea4c1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ea4c1-109">0x0036</span><span class="sxs-lookup"><span data-stu-id="ea4c1-109">0x0036</span></span>  <br/> |
|<span data-ttu-id="ea4c1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ea4c1-110">Data type:</span></span>  <br/> |<span data-ttu-id="ea4c1-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="ea4c1-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="ea4c1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ea4c1-112">Area:</span></span>  <br/> |<span data-ttu-id="ea4c1-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="ea4c1-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ea4c1-114">备注</span><span class="sxs-lookup"><span data-stu-id="ea4c1-114">Remarks</span></span>

<span data-ttu-id="ea4c1-115">建议邮件对象公开此属性。</span><span class="sxs-lookup"><span data-stu-id="ea4c1-115">It is recommended that message objects expose this property.</span></span>
  
<span data-ttu-id="ea4c1-116">此属性可以正好具有下列值之一：</span><span class="sxs-lookup"><span data-stu-id="ea4c1-116">This property can have exactly one of the following values:</span></span>
  
<span data-ttu-id="ea4c1-117">SENSITIVITY_NONE</span><span class="sxs-lookup"><span data-stu-id="ea4c1-117">SENSITIVITY_NONE</span></span> 
  
> <span data-ttu-id="ea4c1-118">邮件没有特殊的敏感度。</span><span class="sxs-lookup"><span data-stu-id="ea4c1-118">The message has no special sensitivity.</span></span>
    
<span data-ttu-id="ea4c1-119">SENSITIVITY_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="ea4c1-119">SENSITIVITY_PERSONAL</span></span> 
  
> <span data-ttu-id="ea4c1-120">邮件是个人邮件。</span><span class="sxs-lookup"><span data-stu-id="ea4c1-120">The message is personal.</span></span>
    
<span data-ttu-id="ea4c1-121">SENSITIVITY_PRIVATE</span><span class="sxs-lookup"><span data-stu-id="ea4c1-121">SENSITIVITY_PRIVATE</span></span> 
  
> <span data-ttu-id="ea4c1-122">邮件是私有的。</span><span class="sxs-lookup"><span data-stu-id="ea4c1-122">The message is private.</span></span>
    
<span data-ttu-id="ea4c1-123">SENSITIVITY_COMPANY_CONFIDENTIAL</span><span class="sxs-lookup"><span data-stu-id="ea4c1-123">SENSITIVITY_COMPANY_CONFIDENTIAL</span></span> 
  
> <span data-ttu-id="ea4c1-124">邮件被指定为公司机密。</span><span class="sxs-lookup"><span data-stu-id="ea4c1-124">The message is designated company confidential.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="ea4c1-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="ea4c1-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ea4c1-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="ea4c1-126">Protocol specifications</span></span>

<span data-ttu-id="ea4c1-127">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ea4c1-127">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ea4c1-128">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="ea4c1-128">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ea4c1-129">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ea4c1-129">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ea4c1-130">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="ea4c1-130">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ea4c1-131">头文件</span><span class="sxs-lookup"><span data-stu-id="ea4c1-131">Header files</span></span>

<span data-ttu-id="ea4c1-132">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ea4c1-132">Mapidefs.h</span></span>
  
> <span data-ttu-id="ea4c1-133">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ea4c1-133">Provides data type definitions.</span></span>
    
<span data-ttu-id="ea4c1-134">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ea4c1-134">Mapitags.h</span></span>
  
> <span data-ttu-id="ea4c1-135">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ea4c1-135">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ea4c1-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea4c1-136">See also</span></span>



[<span data-ttu-id="ea4c1-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ea4c1-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ea4c1-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ea4c1-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ea4c1-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ea4c1-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ea4c1-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ea4c1-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

