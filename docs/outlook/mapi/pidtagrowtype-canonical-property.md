---
title: PidTagRowType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRowType
api_type:
- COM
ms.assetid: d57ce5c8-1f60-4709-b86a-4468c4208dfe
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 7fdb8781c39d7814ff2c38ff4df4545511d28a5f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778247"
---
# <a name="pidtagrowtype-canonical-property"></a><span data-ttu-id="48c05-103">PidTagRowType 规范属性</span><span class="sxs-lookup"><span data-stu-id="48c05-103">PidTagRowType Canonical Property</span></span>

  
  
<span data-ttu-id="48c05-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="48c05-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="48c05-105">包含一个值，指示的表中的行类型。</span><span class="sxs-lookup"><span data-stu-id="48c05-105">Contains a value that indicates the type of a row in a table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="48c05-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="48c05-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="48c05-107">PR_ROW_TYPE</span><span class="sxs-lookup"><span data-stu-id="48c05-107">PR_ROW_TYPE</span></span>  <br/> |
|<span data-ttu-id="48c05-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="48c05-108">Identifier:</span></span>  <br/> |<span data-ttu-id="48c05-109">0x0FF5</span><span class="sxs-lookup"><span data-stu-id="48c05-109">0x0FF5</span></span>  <br/> |
|<span data-ttu-id="48c05-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="48c05-110">Data type:</span></span>  <br/> |<span data-ttu-id="48c05-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="48c05-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="48c05-112">区域：</span><span class="sxs-lookup"><span data-stu-id="48c05-112">Area:</span></span>  <br/> |<span data-ttu-id="48c05-113">MAPI 非可传送</span><span class="sxs-lookup"><span data-stu-id="48c05-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="48c05-114">备注</span><span class="sxs-lookup"><span data-stu-id="48c05-114">Remarks</span></span>

<span data-ttu-id="48c05-115">此属性仅在内容表上显示。</span><span class="sxs-lookup"><span data-stu-id="48c05-115">This property appears only on contents tables.</span></span> <span data-ttu-id="48c05-116">类别仅存在时，该项目。</span><span class="sxs-lookup"><span data-stu-id="48c05-116">A category only exists when it has items.</span></span>
  
<span data-ttu-id="48c05-117">此属性可以具有完全下列值之一：</span><span class="sxs-lookup"><span data-stu-id="48c05-117">This property can have exactly one of the following values:</span></span>
  
<span data-ttu-id="48c05-118">TBL_LEAF_ROW</span><span class="sxs-lookup"><span data-stu-id="48c05-118">TBL_LEAF_ROW</span></span> 
  
> <span data-ttu-id="48c05-119">代表实际数据，而不是类别行。</span><span class="sxs-lookup"><span data-stu-id="48c05-119">Represents actual data, rather than a category row.</span></span>
    
<span data-ttu-id="48c05-120">TBL_EMPTY_CATEGORY</span><span class="sxs-lookup"><span data-stu-id="48c05-120">TBL_EMPTY_CATEGORY</span></span> 
  
> <span data-ttu-id="48c05-121">当前未使用。</span><span class="sxs-lookup"><span data-stu-id="48c05-121">Not currently used.</span></span>
    
<span data-ttu-id="48c05-122">TBL_EXPANDED_CATEGORY</span><span class="sxs-lookup"><span data-stu-id="48c05-122">TBL_EXPANDED_CATEGORY</span></span> 
  
> <span data-ttu-id="48c05-123">展开类别;用户界面通常显示此旁边其减号 （-）。</span><span class="sxs-lookup"><span data-stu-id="48c05-123">The category is expanded; the user interface usually displays this with the minus sign ( - ) next to it.</span></span>
    
<span data-ttu-id="48c05-124">TBL_COLLAPSED_CATEGORY</span><span class="sxs-lookup"><span data-stu-id="48c05-124">TBL_COLLAPSED_CATEGORY</span></span> 
  
> <span data-ttu-id="48c05-125">折叠类别;用户界面通常显示此它旁边的加号 （+）。</span><span class="sxs-lookup"><span data-stu-id="48c05-125">The category is collapsed; the user interface usually displays this with the plus sign (+) next to it.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="48c05-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="48c05-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="48c05-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="48c05-127">Protocol specifications</span></span>

<span data-ttu-id="48c05-128">[[MS OXCTABL]](http://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="48c05-128">[[MS-OXCTABL]](http://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="48c05-129">包含允许的操作的核心 table 对象。</span><span class="sxs-lookup"><span data-stu-id="48c05-129">Includes permissible operations for the core table objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="48c05-130">头文件</span><span class="sxs-lookup"><span data-stu-id="48c05-130">Header files</span></span>

<span data-ttu-id="48c05-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="48c05-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="48c05-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="48c05-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="48c05-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="48c05-133">Mapitags.h</span></span>
  
> <span data-ttu-id="48c05-134">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="48c05-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="48c05-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48c05-135">See also</span></span>



[<span data-ttu-id="48c05-136">PidTagRowid 规范属性</span><span class="sxs-lookup"><span data-stu-id="48c05-136">PidTagRowid Canonical Property</span></span>](pidtagrowid-canonical-property.md)


[<span data-ttu-id="48c05-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="48c05-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="48c05-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="48c05-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="48c05-139">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="48c05-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="48c05-140">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="48c05-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
