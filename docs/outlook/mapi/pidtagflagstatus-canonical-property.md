---
title: PidTagFlagStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFlagStatus
api_type:
- HeaderDef
ms.assetid: b5117360-0939-4535-83fe-3b4a240b5217
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 38df67757082bd12e008e56632ec7e6961ba9d42
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777616"
---
# <a name="pidtagflagstatus-canonical-property"></a><span data-ttu-id="6c63b-103">PidTagFlagStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="6c63b-103">PidTagFlagStatus Canonical Property</span></span>

  
  
<span data-ttu-id="6c63b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6c63b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6c63b-105">指定的消息对象的标志状态。</span><span class="sxs-lookup"><span data-stu-id="6c63b-105">Specifies the flag state of the message object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6c63b-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="6c63b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6c63b-107">PR_FLAG_STATUS</span><span class="sxs-lookup"><span data-stu-id="6c63b-107">PR_FLAG_STATUS</span></span>  <br/> |
|<span data-ttu-id="6c63b-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="6c63b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6c63b-109">0x1090</span><span class="sxs-lookup"><span data-stu-id="6c63b-109">0x1090</span></span>  <br/> |
|<span data-ttu-id="6c63b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6c63b-110">Data type:</span></span>  <br/> |<span data-ttu-id="6c63b-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="6c63b-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="6c63b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6c63b-112">Area:</span></span>  <br/> |<span data-ttu-id="6c63b-113">其他</span><span class="sxs-lookup"><span data-stu-id="6c63b-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6c63b-114">备注</span><span class="sxs-lookup"><span data-stu-id="6c63b-114">Remarks</span></span>

<span data-ttu-id="6c63b-115">此属性必须存在会议相关对象上,，它应不存在于 task 对象。</span><span class="sxs-lookup"><span data-stu-id="6c63b-115">This property must not exist on a meeting-related object, and it should not exist on a task object.</span></span> <span data-ttu-id="6c63b-116">当在其他消息对象上设置时，此属性必须设置为下列值之一：</span><span class="sxs-lookup"><span data-stu-id="6c63b-116">When set on other message objects, this property must be set to one of the following values:</span></span>
  
|<span data-ttu-id="6c63b-117">**数值**</span><span class="sxs-lookup"><span data-stu-id="6c63b-117">**Numeric value**</span></span>|<span data-ttu-id="6c63b-118">**名称**</span><span class="sxs-lookup"><span data-stu-id="6c63b-118">**Name**</span></span>|<span data-ttu-id="6c63b-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="6c63b-119">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6c63b-120">不存在</span><span class="sxs-lookup"><span data-stu-id="6c63b-120">Not present</span></span>  <br/> |<span data-ttu-id="6c63b-121">N/A</span><span class="sxs-lookup"><span data-stu-id="6c63b-121">N/A</span></span>  <br/> |<span data-ttu-id="6c63b-122">未标记</span><span class="sxs-lookup"><span data-stu-id="6c63b-122">Unflagged</span></span>  <br/> |
|<span data-ttu-id="6c63b-123">0x00000001</span><span class="sxs-lookup"><span data-stu-id="6c63b-123">0x00000001</span></span>  <br/> |<span data-ttu-id="6c63b-124">followupComplete</span><span class="sxs-lookup"><span data-stu-id="6c63b-124">followupComplete</span></span>  <br/> |<span data-ttu-id="6c63b-125">标记完成</span><span class="sxs-lookup"><span data-stu-id="6c63b-125">Flagged complete</span></span>  <br/> |
|<span data-ttu-id="6c63b-126">0x00000002</span><span class="sxs-lookup"><span data-stu-id="6c63b-126">0x00000002</span></span>  <br/> |<span data-ttu-id="6c63b-127">followupFlagged</span><span class="sxs-lookup"><span data-stu-id="6c63b-127">followupFlagged</span></span>  <br/> |<span data-ttu-id="6c63b-128">标记</span><span class="sxs-lookup"><span data-stu-id="6c63b-128">Flagged</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="6c63b-129">相关资源</span><span class="sxs-lookup"><span data-stu-id="6c63b-129">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6c63b-130">协议规范</span><span class="sxs-lookup"><span data-stu-id="6c63b-130">Protocol specifications</span></span>

<span data-ttu-id="6c63b-131">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6c63b-131">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6c63b-132">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="6c63b-132">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6c63b-133">[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6c63b-133">[[MS-OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6c63b-134">指定的属性和与标记的操作。</span><span class="sxs-lookup"><span data-stu-id="6c63b-134">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6c63b-135">头文件</span><span class="sxs-lookup"><span data-stu-id="6c63b-135">Header files</span></span>

<span data-ttu-id="6c63b-136">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6c63b-136">Mapidefs.h</span></span>
  
> <span data-ttu-id="6c63b-137">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6c63b-137">Provides data type definitions.</span></span>
    
<span data-ttu-id="6c63b-138">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="6c63b-138">Mapitags.h</span></span>
  
> <span data-ttu-id="6c63b-139">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6c63b-139">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6c63b-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c63b-140">See also</span></span>



[<span data-ttu-id="6c63b-141">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6c63b-141">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6c63b-142">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6c63b-142">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6c63b-143">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6c63b-143">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6c63b-144">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6c63b-144">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

