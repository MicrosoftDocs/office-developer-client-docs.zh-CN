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
# <a name="pidtagimportance-canonical-property"></a><span data-ttu-id="bbfc4-103">PidTagImportance 规范属性</span><span class="sxs-lookup"><span data-stu-id="bbfc4-103">PidTagImportance Canonical Property</span></span>

  
  
<span data-ttu-id="bbfc4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bbfc4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bbfc4-105">包含一个值, 该值指示邮件发件人对邮件重要性的评价。</span><span class="sxs-lookup"><span data-stu-id="bbfc4-105">Contains a value that indicates the message sender's opinion of the importance of a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="bbfc4-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="bbfc4-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="bbfc4-107">PR_IMPORTANCE</span><span class="sxs-lookup"><span data-stu-id="bbfc4-107">PR_IMPORTANCE</span></span>  <br/> |
|<span data-ttu-id="bbfc4-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="bbfc4-108">Identifier:</span></span>  <br/> |<span data-ttu-id="bbfc4-109">0x0017</span><span class="sxs-lookup"><span data-stu-id="bbfc4-109">0x0017</span></span>  <br/> |
|<span data-ttu-id="bbfc4-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="bbfc4-110">Data type:</span></span>  <br/> |<span data-ttu-id="bbfc4-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="bbfc4-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="bbfc4-112">区域：</span><span class="sxs-lookup"><span data-stu-id="bbfc4-112">Area:</span></span>  <br/> |<span data-ttu-id="bbfc4-113">常规邮件</span><span class="sxs-lookup"><span data-stu-id="bbfc4-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bbfc4-114">注解</span><span class="sxs-lookup"><span data-stu-id="bbfc4-114">Remarks</span></span>

<span data-ttu-id="bbfc4-115">不应混淆此属性和**PR_PRIORITY** ([PidTagPriority](pidtagpriority-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="bbfc4-115">This property and the **PR_PRIORITY** ([PidTagPriority](pidtagpriority-canonical-property.md)) property should not be confused.</span></span> <span data-ttu-id="bbfc4-116">重要性指示对用户的值, 而 priority 表示邮件系统软件发送邮件的顺序或速度。</span><span class="sxs-lookup"><span data-stu-id="bbfc4-116">Importance indicates a value to users, while priority indicates the order or speed at which the message should be sent by the messaging system software.</span></span> <span data-ttu-id="bbfc4-117">较高的优先级通常表示较高的成本。</span><span class="sxs-lookup"><span data-stu-id="bbfc4-117">Higher priority usually indicates a higher cost.</span></span> <span data-ttu-id="bbfc4-118">较高的重要性通常与用户界面中的不同显示相关联。</span><span class="sxs-lookup"><span data-stu-id="bbfc4-118">Higher importance usually is associated with a different display by the user interface.</span></span> 
  
<span data-ttu-id="bbfc4-119">此属性可以具有下列值之一:</span><span class="sxs-lookup"><span data-stu-id="bbfc4-119">This property can have exactly one of the following values:</span></span>
  
<span data-ttu-id="bbfc4-120">IMPORTANCE_LOW</span><span class="sxs-lookup"><span data-stu-id="bbfc4-120">IMPORTANCE_LOW</span></span> 
  
> <span data-ttu-id="bbfc4-121">邮件的重要性较低。</span><span class="sxs-lookup"><span data-stu-id="bbfc4-121">The message has low importance.</span></span>
    
<span data-ttu-id="bbfc4-122">IMPORTANCE_HIGH</span><span class="sxs-lookup"><span data-stu-id="bbfc4-122">IMPORTANCE_HIGH</span></span> 
  
> <span data-ttu-id="bbfc4-123">邮件重要性较高。</span><span class="sxs-lookup"><span data-stu-id="bbfc4-123">The message has high importance.</span></span>
    
<span data-ttu-id="bbfc4-124">IMPORTANCE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="bbfc4-124">IMPORTANCE_NORMAL</span></span> 
  
> <span data-ttu-id="bbfc4-125">邮件具有普通重要性。</span><span class="sxs-lookup"><span data-stu-id="bbfc4-125">The message has normal importance.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="bbfc4-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="bbfc4-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="bbfc4-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="bbfc4-127">Protocol specifications</span></span>

<span data-ttu-id="bbfc4-128">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bbfc4-128">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="bbfc4-129">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="bbfc4-129">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="bbfc4-130">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bbfc4-130">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="bbfc4-131">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="bbfc4-131">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="bbfc4-132">头文件</span><span class="sxs-lookup"><span data-stu-id="bbfc4-132">Header files</span></span>

<span data-ttu-id="bbfc4-133">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="bbfc4-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="bbfc4-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="bbfc4-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="bbfc4-135">Mapitags</span><span class="sxs-lookup"><span data-stu-id="bbfc4-135">Mapitags.h</span></span>
  
> <span data-ttu-id="bbfc4-136">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="bbfc4-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bbfc4-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bbfc4-137">See also</span></span>



[<span data-ttu-id="bbfc4-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="bbfc4-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="bbfc4-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="bbfc4-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="bbfc4-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="bbfc4-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="bbfc4-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="bbfc4-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

