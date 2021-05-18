---
title: PidTagToDoItemFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagToDoItemFlags
api_type:
- COM
ms.assetid: bb7ccb45-ce08-4d22-9259-db15cd267e34
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6ddc7231afef0a224b92be7fe86216e56200ab70
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32284481"
---
# <a name="pidtagtodoitemflags-canonical-property"></a><span data-ttu-id="56256-103">PidTagToDoItemFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="56256-103">PidTagToDoItemFlags Canonical Property</span></span>

  
  
<span data-ttu-id="56256-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="56256-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="56256-105">表示To-Do标记的条件。</span><span class="sxs-lookup"><span data-stu-id="56256-105">Represents a To-Do item's flagged condition.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="56256-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="56256-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="56256-107">PR_TODO_ITEM_FLAGS</span><span class="sxs-lookup"><span data-stu-id="56256-107">PR_TODO_ITEM_FLAGS</span></span>  <br/> |
|<span data-ttu-id="56256-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="56256-108">Identifier:</span></span>  <br/> |<span data-ttu-id="56256-109">0x0E2B</span><span class="sxs-lookup"><span data-stu-id="56256-109">0x0E2B</span></span>  <br/> |
|<span data-ttu-id="56256-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="56256-110">Data type:</span></span>  <br/> |<span data-ttu-id="56256-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="56256-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="56256-112">区域：</span><span class="sxs-lookup"><span data-stu-id="56256-112">Area:</span></span>  <br/> |<span data-ttu-id="56256-113">MAPI 不可传输</span><span class="sxs-lookup"><span data-stu-id="56256-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="56256-114">备注</span><span class="sxs-lookup"><span data-stu-id="56256-114">Remarks</span></span>

<span data-ttu-id="56256-115">此属性是位字段，如果下表中的关联条件适用，则每个位应设置为 1，否则为 0。</span><span class="sxs-lookup"><span data-stu-id="56256-115">This property is a bit field in which each bit should be set to 1 if the associated condition in the following table applies, otherwise 0.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="56256-116">数值</span><span class="sxs-lookup"><span data-stu-id="56256-116">Numeric value</span></span>  <br/> |<span data-ttu-id="56256-117">名称</span><span class="sxs-lookup"><span data-stu-id="56256-117">Name</span></span>  <br/> |<span data-ttu-id="56256-118">说明</span><span class="sxs-lookup"><span data-stu-id="56256-118">Description</span></span>  <br/> |
|<span data-ttu-id="56256-119">不存在</span><span class="sxs-lookup"><span data-stu-id="56256-119">Not present</span></span>  <br/> |<span data-ttu-id="56256-120">不适用</span><span class="sxs-lookup"><span data-stu-id="56256-120">N/A</span></span>  <br/> |<span data-ttu-id="56256-121">未标记</span><span class="sxs-lookup"><span data-stu-id="56256-121">Unflagged</span></span>  <br/> |
|<span data-ttu-id="56256-122">1</span><span class="sxs-lookup"><span data-stu-id="56256-122">1</span></span>  <br/> |<span data-ttu-id="56256-123">todoTimeFlagged</span><span class="sxs-lookup"><span data-stu-id="56256-123">todoTimeFlagged</span></span>  <br/> |<span data-ttu-id="56256-124">对象已标记时间</span><span class="sxs-lookup"><span data-stu-id="56256-124">Object is time flagged</span></span>  <br/> |
|<span data-ttu-id="56256-125">8 </span><span class="sxs-lookup"><span data-stu-id="56256-125">8</span></span>  <br/> |<span data-ttu-id="56256-126">todoRecipientFlagged</span><span class="sxs-lookup"><span data-stu-id="56256-126">todoRecipientFlagged</span></span>  <br/> |<span data-ttu-id="56256-127">应仅在草稿邮件对象上设置，这意味着对象已标记为收件人。</span><span class="sxs-lookup"><span data-stu-id="56256-127">Should only be set on a draft message object, and it means that the object is flagged for recipients.</span></span>  <br/> |
   
<span data-ttu-id="56256-128">保留表中未指定的所有位。</span><span class="sxs-lookup"><span data-stu-id="56256-128">All bits that are not specified in the table are reserved.</span></span> <span data-ttu-id="56256-129">必须忽略它们，但如果设置它们，应保留它们。</span><span class="sxs-lookup"><span data-stu-id="56256-129">They must be ignored, but should be preserved if they are set.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="56256-130">相关资源</span><span class="sxs-lookup"><span data-stu-id="56256-130">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="56256-131">协议规范</span><span class="sxs-lookup"><span data-stu-id="56256-131">Protocol specifications</span></span>

<span data-ttu-id="56256-132">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="56256-132">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="56256-133">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="56256-133">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="56256-134">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="56256-134">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="56256-135">指定与标记相关的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="56256-135">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="56256-136">头文件</span><span class="sxs-lookup"><span data-stu-id="56256-136">Header files</span></span>

<span data-ttu-id="56256-137">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="56256-137">Mapidefs.h</span></span>
  
> <span data-ttu-id="56256-138">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="56256-138">Provides data type definitions.</span></span>
    
<span data-ttu-id="56256-139">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="56256-139">Mapitags.h</span></span>
  
> <span data-ttu-id="56256-140">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="56256-140">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="56256-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56256-141">See also</span></span>



[<span data-ttu-id="56256-142">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="56256-142">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="56256-143">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="56256-143">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="56256-144">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="56256-144">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="56256-145">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="56256-145">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

