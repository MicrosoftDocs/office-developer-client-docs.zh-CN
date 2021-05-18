---
title: PidTagImportance 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagImportance
api_type:
- HeaderDef
ms.assetid: 274dd444-a863-4b53-bdbc-3763c375c43c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6bef8b05f2fbf94b74ee126b80dfc6ae0c5e9d11
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327921"
---
# <a name="pidtagimportance-canonical-property"></a><span data-ttu-id="d82ba-103">PidTagImportance 规范属性</span><span class="sxs-lookup"><span data-stu-id="d82ba-103">PidTagImportance Canonical Property</span></span>

  
  
<span data-ttu-id="d82ba-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d82ba-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d82ba-105">包含一个值，该值指示邮件发件人对邮件重要性的意见。</span><span class="sxs-lookup"><span data-stu-id="d82ba-105">Contains a value that indicates the message sender's opinion of the importance of a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d82ba-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d82ba-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d82ba-107">PR_IMPORTANCE</span><span class="sxs-lookup"><span data-stu-id="d82ba-107">PR_IMPORTANCE</span></span>  <br/> |
|<span data-ttu-id="d82ba-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d82ba-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d82ba-109">0x0017</span><span class="sxs-lookup"><span data-stu-id="d82ba-109">0x0017</span></span>  <br/> |
|<span data-ttu-id="d82ba-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d82ba-110">Data type:</span></span>  <br/> |<span data-ttu-id="d82ba-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="d82ba-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="d82ba-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d82ba-112">Area:</span></span>  <br/> |<span data-ttu-id="d82ba-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="d82ba-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d82ba-114">备注</span><span class="sxs-lookup"><span data-stu-id="d82ba-114">Remarks</span></span>

<span data-ttu-id="d82ba-115">不应混淆 **此属性PR_PRIORITY (** [PidTagPriority](pidtagpriority-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d82ba-115">This property and the **PR_PRIORITY** ([PidTagPriority](pidtagpriority-canonical-property.md)) property should not be confused.</span></span> <span data-ttu-id="d82ba-116">Importance 指示给用户的值，而优先级指示邮件系统软件应发送邮件的顺序或速度。</span><span class="sxs-lookup"><span data-stu-id="d82ba-116">Importance indicates a value to users, while priority indicates the order or speed at which the message should be sent by the messaging system software.</span></span> <span data-ttu-id="d82ba-117">优先级越高，通常表示成本越高。</span><span class="sxs-lookup"><span data-stu-id="d82ba-117">Higher priority usually indicates a higher cost.</span></span> <span data-ttu-id="d82ba-118">较高的重要性通常与用户界面的不同显示相关联。</span><span class="sxs-lookup"><span data-stu-id="d82ba-118">Higher importance usually is associated with a different display by the user interface.</span></span> 
  
<span data-ttu-id="d82ba-119">此属性可以正好具有下列值之一：</span><span class="sxs-lookup"><span data-stu-id="d82ba-119">This property can have exactly one of the following values:</span></span>
  
<span data-ttu-id="d82ba-120">IMPORTANCE_LOW</span><span class="sxs-lookup"><span data-stu-id="d82ba-120">IMPORTANCE_LOW</span></span> 
  
> <span data-ttu-id="d82ba-121">邮件的重要性较低。</span><span class="sxs-lookup"><span data-stu-id="d82ba-121">The message has low importance.</span></span>
    
<span data-ttu-id="d82ba-122">IMPORTANCE_HIGH</span><span class="sxs-lookup"><span data-stu-id="d82ba-122">IMPORTANCE_HIGH</span></span> 
  
> <span data-ttu-id="d82ba-123">邮件重要性较高。</span><span class="sxs-lookup"><span data-stu-id="d82ba-123">The message has high importance.</span></span>
    
<span data-ttu-id="d82ba-124">IMPORTANCE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="d82ba-124">IMPORTANCE_NORMAL</span></span> 
  
> <span data-ttu-id="d82ba-125">邮件具有普通的重要性。</span><span class="sxs-lookup"><span data-stu-id="d82ba-125">The message has normal importance.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="d82ba-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="d82ba-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d82ba-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="d82ba-127">Protocol specifications</span></span>

<span data-ttu-id="d82ba-128">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d82ba-128">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d82ba-129">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="d82ba-129">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d82ba-130">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d82ba-130">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d82ba-131">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="d82ba-131">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d82ba-132">头文件</span><span class="sxs-lookup"><span data-stu-id="d82ba-132">Header files</span></span>

<span data-ttu-id="d82ba-133">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d82ba-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="d82ba-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d82ba-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="d82ba-135">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d82ba-135">Mapitags.h</span></span>
  
> <span data-ttu-id="d82ba-136">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d82ba-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d82ba-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d82ba-137">See also</span></span>



[<span data-ttu-id="d82ba-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d82ba-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d82ba-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d82ba-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d82ba-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d82ba-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d82ba-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d82ba-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

