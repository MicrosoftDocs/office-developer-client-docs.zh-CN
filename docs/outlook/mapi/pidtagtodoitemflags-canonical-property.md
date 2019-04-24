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
# <a name="pidtagtodoitemflags-canonical-property"></a><span data-ttu-id="b9cf0-103">PidTagToDoItemFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="b9cf0-103">PidTagToDoItemFlags Canonical Property</span></span>

  
  
<span data-ttu-id="b9cf0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b9cf0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b9cf0-105">表示待办事项的标记条件。</span><span class="sxs-lookup"><span data-stu-id="b9cf0-105">Represents a To-Do item's flagged condition.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b9cf0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b9cf0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b9cf0-107">PR_TODO_ITEM_FLAGS</span><span class="sxs-lookup"><span data-stu-id="b9cf0-107">PR_TODO_ITEM_FLAGS</span></span>  <br/> |
|<span data-ttu-id="b9cf0-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="b9cf0-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b9cf0-109">0x0E2B</span><span class="sxs-lookup"><span data-stu-id="b9cf0-109">0x0E2B</span></span>  <br/> |
|<span data-ttu-id="b9cf0-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b9cf0-110">Data type:</span></span>  <br/> |<span data-ttu-id="b9cf0-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="b9cf0-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="b9cf0-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b9cf0-112">Area:</span></span>  <br/> |<span data-ttu-id="b9cf0-113">MAPI 非传输</span><span class="sxs-lookup"><span data-stu-id="b9cf0-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b9cf0-114">注解</span><span class="sxs-lookup"><span data-stu-id="b9cf0-114">Remarks</span></span>

<span data-ttu-id="b9cf0-115">此属性是一个位域, 如果下表中的关联条件适用, 则每个位应设置为 1, 否则为0。</span><span class="sxs-lookup"><span data-stu-id="b9cf0-115">This property is a bit field in which each bit should be set to 1 if the associated condition in the following table applies, otherwise 0.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="b9cf0-116">数字值</span><span class="sxs-lookup"><span data-stu-id="b9cf0-116">Numeric value</span></span>  <br/> |<span data-ttu-id="b9cf0-117">名称</span><span class="sxs-lookup"><span data-stu-id="b9cf0-117">Name</span></span>  <br/> |<span data-ttu-id="b9cf0-118">说明</span><span class="sxs-lookup"><span data-stu-id="b9cf0-118">Description</span></span>  <br/> |
|<span data-ttu-id="b9cf0-119">不存在</span><span class="sxs-lookup"><span data-stu-id="b9cf0-119">Not present</span></span>  <br/> |<span data-ttu-id="b9cf0-120">不适用</span><span class="sxs-lookup"><span data-stu-id="b9cf0-120">N/A</span></span>  <br/> |<span data-ttu-id="b9cf0-121">标记</span><span class="sxs-lookup"><span data-stu-id="b9cf0-121">Unflagged</span></span>  <br/> |
|<span data-ttu-id="b9cf0-122">1</span><span class="sxs-lookup"><span data-stu-id="b9cf0-122">1</span></span>  <br/> |<span data-ttu-id="b9cf0-123">todoTimeFlagged</span><span class="sxs-lookup"><span data-stu-id="b9cf0-123">todoTimeFlagged</span></span>  <br/> |<span data-ttu-id="b9cf0-124">对象已标记时间</span><span class="sxs-lookup"><span data-stu-id="b9cf0-124">Object is time flagged</span></span>  <br/> |
|<span data-ttu-id="b9cf0-125">utf-8</span><span class="sxs-lookup"><span data-stu-id="b9cf0-125">8</span></span>  <br/> |<span data-ttu-id="b9cf0-126">todoRecipientFlagged</span><span class="sxs-lookup"><span data-stu-id="b9cf0-126">todoRecipientFlagged</span></span>  <br/> |<span data-ttu-id="b9cf0-127">只应对草稿邮件对象设置, 这意味着该对象会被标记为收件人。</span><span class="sxs-lookup"><span data-stu-id="b9cf0-127">Should only be set on a draft message object, and it means that the object is flagged for recipients.</span></span>  <br/> |
   
<span data-ttu-id="b9cf0-128">未在表中指定的所有位都将保留。</span><span class="sxs-lookup"><span data-stu-id="b9cf0-128">All bits that are not specified in the table are reserved.</span></span> <span data-ttu-id="b9cf0-129">必须忽略它们, 如果设置它们, 应将其保留。</span><span class="sxs-lookup"><span data-stu-id="b9cf0-129">They must be ignored, but should be preserved if they are set.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="b9cf0-130">相关资源</span><span class="sxs-lookup"><span data-stu-id="b9cf0-130">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b9cf0-131">协议规范</span><span class="sxs-lookup"><span data-stu-id="b9cf0-131">Protocol specifications</span></span>

<span data-ttu-id="b9cf0-132">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b9cf0-132">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b9cf0-133">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b9cf0-133">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b9cf0-134">[[毫秒-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b9cf0-134">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b9cf0-135">指定与标记相关的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="b9cf0-135">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b9cf0-136">头文件</span><span class="sxs-lookup"><span data-stu-id="b9cf0-136">Header files</span></span>

<span data-ttu-id="b9cf0-137">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="b9cf0-137">Mapidefs.h</span></span>
  
> <span data-ttu-id="b9cf0-138">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b9cf0-138">Provides data type definitions.</span></span>
    
<span data-ttu-id="b9cf0-139">Mapitags</span><span class="sxs-lookup"><span data-stu-id="b9cf0-139">Mapitags.h</span></span>
  
> <span data-ttu-id="b9cf0-140">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b9cf0-140">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b9cf0-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9cf0-141">See also</span></span>



[<span data-ttu-id="b9cf0-142">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b9cf0-142">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b9cf0-143">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b9cf0-143">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b9cf0-144">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b9cf0-144">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b9cf0-145">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b9cf0-145">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

