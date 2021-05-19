---
title: PidTagPriority 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagPriority
api_type:
- COM
ms.assetid: 0f3a628f-5f8e-4716-98cc-868bd3400ba9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b9c0f5ebeae21d6d683bbb5def727d29a34bcdb6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339429"
---
# <a name="pidtagpriority-canonical-property"></a><span data-ttu-id="3a3d0-103">PidTagPriority 规范属性</span><span class="sxs-lookup"><span data-stu-id="3a3d0-103">PidTagPriority Canonical Property</span></span>

  
  
<span data-ttu-id="3a3d0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3a3d0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3a3d0-105">包含邮件的相对优先级。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-105">Contains the relative priority of a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3a3d0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3a3d0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3a3d0-107">PR_PRIORITY</span><span class="sxs-lookup"><span data-stu-id="3a3d0-107">PR_PRIORITY</span></span>  <br/> |
|<span data-ttu-id="3a3d0-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="3a3d0-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3a3d0-109">0x0026</span><span class="sxs-lookup"><span data-stu-id="3a3d0-109">0x0026</span></span>  <br/> |
|<span data-ttu-id="3a3d0-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3a3d0-110">Data type:</span></span>  <br/> |<span data-ttu-id="3a3d0-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="3a3d0-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="3a3d0-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3a3d0-112">Area:</span></span>  <br/> |<span data-ttu-id="3a3d0-113">电子邮件</span><span class="sxs-lookup"><span data-stu-id="3a3d0-113">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3a3d0-114">备注</span><span class="sxs-lookup"><span data-stu-id="3a3d0-114">Remarks</span></span>

<span data-ttu-id="3a3d0-115">不应混淆此属性 **PR_IMPORTANCE (** [PidTagImportance](pidtagimportance-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-115">This property and the **PR_IMPORTANCE** ([PidTagImportance](pidtagimportance-canonical-property.md)) property should not be confused.</span></span> <span data-ttu-id="3a3d0-116">Importance 指示给用户的值，而优先级指示邮件系统软件应发送邮件的顺序或速度。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-116">Importance indicates a value to users, while priority indicates the order or speed at which the message should be sent by the messaging system software.</span></span> <span data-ttu-id="3a3d0-117">优先级越高，通常表示成本越高。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-117">Higher priority usually indicates a higher cost.</span></span> <span data-ttu-id="3a3d0-118">较高的重要性通常与用户界面的不同显示相关联。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-118">Higher importance usually is associated with a different display by the user interface.</span></span>
  
<span data-ttu-id="3a3d0-119">报告邮件的优先级应该与报告的原始邮件的优先级相同。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-119">The priority of a report message should be the same as the priority of the original message being reported.</span></span>
  
<span data-ttu-id="3a3d0-120">此属性可以正好具有下列值之一：</span><span class="sxs-lookup"><span data-stu-id="3a3d0-120">This property can have exactly one of the following values:</span></span>
  
<span data-ttu-id="3a3d0-121">PRIO_NONURGENT</span><span class="sxs-lookup"><span data-stu-id="3a3d0-121">PRIO_NONURGENT</span></span> 
  
> <span data-ttu-id="3a3d0-122">邮件不紧急。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-122">The message is not urgent.</span></span>
    
<span data-ttu-id="3a3d0-123">PRIO_NORMAL</span><span class="sxs-lookup"><span data-stu-id="3a3d0-123">PRIO_NORMAL</span></span> 
  
> <span data-ttu-id="3a3d0-124">邮件具有普通优先级。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-124">The message has normal priority.</span></span>
    
<span data-ttu-id="3a3d0-125">PRIO_URGENT</span><span class="sxs-lookup"><span data-stu-id="3a3d0-125">PRIO_URGENT</span></span> 
  
> <span data-ttu-id="3a3d0-126">邮件是紧急邮件。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-126">The message is urgent.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="3a3d0-127">相关资源</span><span class="sxs-lookup"><span data-stu-id="3a3d0-127">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3a3d0-128">协议规范</span><span class="sxs-lookup"><span data-stu-id="3a3d0-128">Protocol specifications</span></span>

<span data-ttu-id="3a3d0-129">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3a3d0-129">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3a3d0-130">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-130">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="3a3d0-131">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3a3d0-131">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3a3d0-132">指定允许对电子邮件对象执行的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-132">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3a3d0-133">头文件</span><span class="sxs-lookup"><span data-stu-id="3a3d0-133">Header files</span></span>

<span data-ttu-id="3a3d0-134">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3a3d0-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="3a3d0-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-135">Provides data type definitions.</span></span>
    
<span data-ttu-id="3a3d0-136">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="3a3d0-136">Mapitags.h</span></span>
  
> <span data-ttu-id="3a3d0-137">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-137">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3a3d0-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a3d0-138">See also</span></span>



[<span data-ttu-id="3a3d0-139">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3a3d0-139">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3a3d0-140">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3a3d0-140">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3a3d0-141">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3a3d0-141">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3a3d0-142">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3a3d0-142">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

