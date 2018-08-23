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
ms.openlocfilehash: 100d59a0fd95fcad1976e82aebf6892227c08ec9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564911"
---
# <a name="pidtagdepth-canonical-property"></a><span data-ttu-id="c370a-103">PidTagDepth 规范属性</span><span class="sxs-lookup"><span data-stu-id="c370a-103">PidTagDepth Canonical Property</span></span>

  
  
<span data-ttu-id="c370a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c370a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c370a-105">包含一个整数，表示相对级别的缩进或深度层次结构表中的对象。</span><span class="sxs-lookup"><span data-stu-id="c370a-105">Contains an integer that represents the relative level of indentation, or depth, of an object in a hierarchy table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c370a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c370a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c370a-107">PR_DEPTH</span><span class="sxs-lookup"><span data-stu-id="c370a-107">PR_DEPTH</span></span>  <br/> |
|<span data-ttu-id="c370a-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="c370a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c370a-109">0x3005</span><span class="sxs-lookup"><span data-stu-id="c370a-109">0x3005</span></span>  <br/> |
|<span data-ttu-id="c370a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c370a-110">Data type:</span></span>  <br/> |<span data-ttu-id="c370a-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="c370a-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="c370a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c370a-112">Area:</span></span>  <br/> |<span data-ttu-id="c370a-113">常见的 MAPI</span><span class="sxs-lookup"><span data-stu-id="c370a-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c370a-114">注解</span><span class="sxs-lookup"><span data-stu-id="c370a-114">Remarks</span></span>

<span data-ttu-id="c370a-115">此属性还可以内容表或层次结构表中的层次结构深度中指定行分类的级别。</span><span class="sxs-lookup"><span data-stu-id="c370a-115">This property can also specify the categorization level of a row in a contents table or the hierarchy depth in a hierarchy table.</span></span> <span data-ttu-id="c370a-116">其中零表示最左边的类别，是从零开始，深度。</span><span class="sxs-lookup"><span data-stu-id="c370a-116">The depth is zero-based, where zero represents the leftmost category.</span></span> <span data-ttu-id="c370a-117">在所有情况下，属性值表示相对值，而不是一个绝对的值。</span><span class="sxs-lookup"><span data-stu-id="c370a-117">In all cases, the property value represents a relative value rather than an absolute value.</span></span> <span data-ttu-id="c370a-118">在层次结构表中，例如，深度值是相对于从中检索到的层次结构表的容器。</span><span class="sxs-lookup"><span data-stu-id="c370a-118">In the hierarchy table, for example, the depth value is relative to the container from which the hierarchy table was retrieved.</span></span> <span data-ttu-id="c370a-119">从根容器，深度不代表绝对深度。</span><span class="sxs-lookup"><span data-stu-id="c370a-119">The depth does not represent an absolute depth from the root container.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="c370a-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="c370a-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c370a-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="c370a-121">Protocol specifications</span></span>

<span data-ttu-id="c370a-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c370a-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c370a-123">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="c370a-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="c370a-124">[[MS OXCTABL]](http://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c370a-124">[[MS-OXCTABL]](http://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c370a-125">包含允许的操作的核心 table 对象。</span><span class="sxs-lookup"><span data-stu-id="c370a-125">Includes permissible operations for the core table objects.</span></span>
    
<span data-ttu-id="c370a-126">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c370a-126">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c370a-127">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="c370a-127">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c370a-128">头文件</span><span class="sxs-lookup"><span data-stu-id="c370a-128">Header files</span></span>

<span data-ttu-id="c370a-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c370a-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="c370a-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c370a-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="c370a-131">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="c370a-131">Mapitags.h</span></span>
  
> <span data-ttu-id="c370a-132">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c370a-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c370a-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c370a-133">See also</span></span>



[<span data-ttu-id="c370a-134">PidTagObjectType 规范属性</span><span class="sxs-lookup"><span data-stu-id="c370a-134">PidTagObjectType Canonical Property</span></span>](pidtagobjecttype-canonical-property.md)
  
[<span data-ttu-id="c370a-135">PidTagSelectable 规范属性</span><span class="sxs-lookup"><span data-stu-id="c370a-135">PidTagSelectable Canonical Property</span></span>](pidtagselectable-canonical-property.md)


[<span data-ttu-id="c370a-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c370a-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c370a-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c370a-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c370a-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c370a-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c370a-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c370a-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

