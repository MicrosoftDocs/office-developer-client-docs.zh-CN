---
title: PidTagDepth 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDepth
api_type:
- HeaderDef
ms.assetid: 04d444a5-e97f-48e6-89a5-8a6cb2136408
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 75d390edd06aaf826f6b8c2d996e4e08bf6a7334
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360849"
---
# <a name="pidtagdepth-canonical-property"></a><span data-ttu-id="0f7e6-103">PidTagDepth 规范属性</span><span class="sxs-lookup"><span data-stu-id="0f7e6-103">PidTagDepth Canonical Property</span></span>

  
  
<span data-ttu-id="0f7e6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0f7e6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0f7e6-105">包含一个 integer 类型的值, 该值代表层次结构表中的对象的缩进或深度的相对级别。</span><span class="sxs-lookup"><span data-stu-id="0f7e6-105">Contains an integer that represents the relative level of indentation, or depth, of an object in a hierarchy table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0f7e6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0f7e6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0f7e6-107">PR_DEPTH</span><span class="sxs-lookup"><span data-stu-id="0f7e6-107">PR_DEPTH</span></span>  <br/> |
|<span data-ttu-id="0f7e6-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="0f7e6-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0f7e6-109">0x3005</span><span class="sxs-lookup"><span data-stu-id="0f7e6-109">0x3005</span></span>  <br/> |
|<span data-ttu-id="0f7e6-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0f7e6-110">Data type:</span></span>  <br/> |<span data-ttu-id="0f7e6-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="0f7e6-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="0f7e6-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0f7e6-112">Area:</span></span>  <br/> |<span data-ttu-id="0f7e6-113">MAPI 通用</span><span class="sxs-lookup"><span data-stu-id="0f7e6-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0f7e6-114">注解</span><span class="sxs-lookup"><span data-stu-id="0f7e6-114">Remarks</span></span>

<span data-ttu-id="0f7e6-115">此属性还可以指定内容表中行的分类级别或层次结构中的层次结构深度表中的层次结构深度。</span><span class="sxs-lookup"><span data-stu-id="0f7e6-115">This property can also specify the categorization level of a row in a contents table or the hierarchy depth in a hierarchy table.</span></span> <span data-ttu-id="0f7e6-116">深度是从零开始的, 其中0表示最左边的类别。</span><span class="sxs-lookup"><span data-stu-id="0f7e6-116">The depth is zero-based, where zero represents the leftmost category.</span></span> <span data-ttu-id="0f7e6-117">在所有情况下, 属性值都代表相对值而不是绝对值。</span><span class="sxs-lookup"><span data-stu-id="0f7e6-117">In all cases, the property value represents a relative value rather than an absolute value.</span></span> <span data-ttu-id="0f7e6-118">例如, 在层次结构表中, 深度值相对于从中检索层次结构表的容器。</span><span class="sxs-lookup"><span data-stu-id="0f7e6-118">In the hierarchy table, for example, the depth value is relative to the container from which the hierarchy table was retrieved.</span></span> <span data-ttu-id="0f7e6-119">深度并不表示根容器的绝对深度。</span><span class="sxs-lookup"><span data-stu-id="0f7e6-119">The depth does not represent an absolute depth from the root container.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="0f7e6-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="0f7e6-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0f7e6-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="0f7e6-121">Protocol specifications</span></span>

<span data-ttu-id="0f7e6-122">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0f7e6-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0f7e6-123">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="0f7e6-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0f7e6-124">[[毫秒-OXCTABL]](https://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0f7e6-124">[[MS-OXCTABL]](https://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0f7e6-125">包括核心表对象的允许操作。</span><span class="sxs-lookup"><span data-stu-id="0f7e6-125">Includes permissible operations for the core table objects.</span></span>
    
<span data-ttu-id="0f7e6-126">[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0f7e6-126">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0f7e6-127">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="0f7e6-127">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0f7e6-128">头文件</span><span class="sxs-lookup"><span data-stu-id="0f7e6-128">Header files</span></span>

<span data-ttu-id="0f7e6-129">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="0f7e6-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="0f7e6-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0f7e6-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="0f7e6-131">Mapitags</span><span class="sxs-lookup"><span data-stu-id="0f7e6-131">Mapitags.h</span></span>
  
> <span data-ttu-id="0f7e6-132">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0f7e6-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0f7e6-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f7e6-133">See also</span></span>



[<span data-ttu-id="0f7e6-134">PidTagObjectType 规范属性</span><span class="sxs-lookup"><span data-stu-id="0f7e6-134">PidTagObjectType Canonical Property</span></span>](pidtagobjecttype-canonical-property.md)
  
[<span data-ttu-id="0f7e6-135">PidTagSelectable 规范属性</span><span class="sxs-lookup"><span data-stu-id="0f7e6-135">PidTagSelectable Canonical Property</span></span>](pidtagselectable-canonical-property.md)


[<span data-ttu-id="0f7e6-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0f7e6-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0f7e6-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0f7e6-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0f7e6-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0f7e6-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0f7e6-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0f7e6-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

