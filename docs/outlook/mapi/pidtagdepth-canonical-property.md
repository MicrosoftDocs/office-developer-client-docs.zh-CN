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
# <a name="pidtagdepth-canonical-property"></a><span data-ttu-id="491c8-103">PidTagDepth 规范属性</span><span class="sxs-lookup"><span data-stu-id="491c8-103">PidTagDepth Canonical Property</span></span>

  
  
<span data-ttu-id="491c8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="491c8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="491c8-105">包含一个整数，该整数代表层次结构表中对象的相对缩进级别或深度。</span><span class="sxs-lookup"><span data-stu-id="491c8-105">Contains an integer that represents the relative level of indentation, or depth, of an object in a hierarchy table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="491c8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="491c8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="491c8-107">PR_DEPTH</span><span class="sxs-lookup"><span data-stu-id="491c8-107">PR_DEPTH</span></span>  <br/> |
|<span data-ttu-id="491c8-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="491c8-108">Identifier:</span></span>  <br/> |<span data-ttu-id="491c8-109">0x3005</span><span class="sxs-lookup"><span data-stu-id="491c8-109">0x3005</span></span>  <br/> |
|<span data-ttu-id="491c8-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="491c8-110">Data type:</span></span>  <br/> |<span data-ttu-id="491c8-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="491c8-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="491c8-112">区域：</span><span class="sxs-lookup"><span data-stu-id="491c8-112">Area:</span></span>  <br/> |<span data-ttu-id="491c8-113">MAPI common</span><span class="sxs-lookup"><span data-stu-id="491c8-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="491c8-114">备注</span><span class="sxs-lookup"><span data-stu-id="491c8-114">Remarks</span></span>

<span data-ttu-id="491c8-115">此属性还可以指定内容表中行的分类级别或层次结构表中的层次结构深度。</span><span class="sxs-lookup"><span data-stu-id="491c8-115">This property can also specify the categorization level of a row in a contents table or the hierarchy depth in a hierarchy table.</span></span> <span data-ttu-id="491c8-116">深度从零开始，其中零表示最左边的类别。</span><span class="sxs-lookup"><span data-stu-id="491c8-116">The depth is zero-based, where zero represents the leftmost category.</span></span> <span data-ttu-id="491c8-117">在所有情况下，属性值表示相对值，而不是绝对值。</span><span class="sxs-lookup"><span data-stu-id="491c8-117">In all cases, the property value represents a relative value rather than an absolute value.</span></span> <span data-ttu-id="491c8-118">例如，在层次结构表中，深度值相对于从中检索层次结构表的容器。</span><span class="sxs-lookup"><span data-stu-id="491c8-118">In the hierarchy table, for example, the depth value is relative to the container from which the hierarchy table was retrieved.</span></span> <span data-ttu-id="491c8-119">深度不表示根容器的绝对深度。</span><span class="sxs-lookup"><span data-stu-id="491c8-119">The depth does not represent an absolute depth from the root container.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="491c8-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="491c8-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="491c8-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="491c8-121">Protocol specifications</span></span>

<span data-ttu-id="491c8-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="491c8-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="491c8-123">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="491c8-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="491c8-124">[[MS-OXCTABL]](https://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="491c8-124">[[MS-OXCTABL]](https://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="491c8-125">包括核心表对象的允许操作。</span><span class="sxs-lookup"><span data-stu-id="491c8-125">Includes permissible operations for the core table objects.</span></span>
    
<span data-ttu-id="491c8-126">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="491c8-126">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="491c8-127">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="491c8-127">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="491c8-128">头文件</span><span class="sxs-lookup"><span data-stu-id="491c8-128">Header files</span></span>

<span data-ttu-id="491c8-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="491c8-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="491c8-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="491c8-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="491c8-131">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="491c8-131">Mapitags.h</span></span>
  
> <span data-ttu-id="491c8-132">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="491c8-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="491c8-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="491c8-133">See also</span></span>



[<span data-ttu-id="491c8-134">PidTagObjectType 规范属性</span><span class="sxs-lookup"><span data-stu-id="491c8-134">PidTagObjectType Canonical Property</span></span>](pidtagobjecttype-canonical-property.md)
  
[<span data-ttu-id="491c8-135">PidTagSelectable 规范属性</span><span class="sxs-lookup"><span data-stu-id="491c8-135">PidTagSelectable Canonical Property</span></span>](pidtagselectable-canonical-property.md)


[<span data-ttu-id="491c8-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="491c8-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="491c8-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="491c8-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="491c8-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="491c8-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="491c8-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="491c8-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

