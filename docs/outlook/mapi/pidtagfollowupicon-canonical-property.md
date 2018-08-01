---
title: PidTagFollowupIcon 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFollowupIcon
api_type:
- HeaderDef
ms.assetid: 374cef41-141a-491b-8dd1-eaf1a2044204
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 39840f27d67daca625daea08555ab89d5a362e63
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777635"
---
# <a name="pidtagfollowupicon-canonical-property"></a><span data-ttu-id="b630e-103">PidTagFollowupIcon 规范属性</span><span class="sxs-lookup"><span data-stu-id="b630e-103">PidTagFollowupIcon Canonical Property</span></span>

  
  
<span data-ttu-id="b630e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b630e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b630e-105">指定消息对象的标志的颜色。</span><span class="sxs-lookup"><span data-stu-id="b630e-105">Specifies the flag color of the message object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b630e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b630e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b630e-107">PR_FOLLOWUP_ICON</span><span class="sxs-lookup"><span data-stu-id="b630e-107">PR_FOLLOWUP_ICON</span></span>  <br/> |
|<span data-ttu-id="b630e-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="b630e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b630e-109">0x1095</span><span class="sxs-lookup"><span data-stu-id="b630e-109">0x1095</span></span>  <br/> |
|<span data-ttu-id="b630e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b630e-110">Data type:</span></span>  <br/> |<span data-ttu-id="b630e-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="b630e-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="b630e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b630e-112">Area:</span></span>  <br/> |<span data-ttu-id="b630e-113">重命名邮件文件夹</span><span class="sxs-lookup"><span data-stu-id="b630e-113">Rename message folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b630e-114">说明</span><span class="sxs-lookup"><span data-stu-id="b630e-114">Remarks</span></span>

<span data-ttu-id="b630e-115">此属性必须存在除非**PR_FLAG_STATUS** ([PidTagFlagStatus](pidtagflagstatus-canonical-property.md)) 属性的值设置为"followupFlagged"，或 message 对象是会议相关对象。</span><span class="sxs-lookup"><span data-stu-id="b630e-115">This property must not exist unless the value of the **PR_FLAG_STATUS** ([PidTagFlagStatus](pidtagflagstatus-canonical-property.md)) property is set to "followupFlagged", or the message object is a meeting-related object.</span></span> <span data-ttu-id="b630e-116">此属性不应存在对任务对象。</span><span class="sxs-lookup"><span data-stu-id="b630e-116">This property should not exist on a task object.</span></span> <span data-ttu-id="b630e-117">当在其他消息对象上设置时，此属性必须设置为下列值之一。</span><span class="sxs-lookup"><span data-stu-id="b630e-117">When set on other message objects, this property must be set to one of the following values.</span></span>
  
|<span data-ttu-id="b630e-118">**数值**</span><span class="sxs-lookup"><span data-stu-id="b630e-118">**Numeric value**</span></span>|<span data-ttu-id="b630e-119">**名称**</span><span class="sxs-lookup"><span data-stu-id="b630e-119">**Name**</span></span>|<span data-ttu-id="b630e-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="b630e-120">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b630e-121">不存在</span><span class="sxs-lookup"><span data-stu-id="b630e-121">Not present</span></span>  <br/> |<span data-ttu-id="b630e-122">不适用</span><span class="sxs-lookup"><span data-stu-id="b630e-122">N/A</span></span>  <br/> |<span data-ttu-id="b630e-123">无颜色</span><span class="sxs-lookup"><span data-stu-id="b630e-123">No color</span></span>  <br/> |
|<span data-ttu-id="b630e-124">1</span><span class="sxs-lookup"><span data-stu-id="b630e-124">1</span></span>  <br/> |<span data-ttu-id="b630e-125">followupIcon1</span><span class="sxs-lookup"><span data-stu-id="b630e-125">followupIcon1</span></span>  <br/> |<span data-ttu-id="b630e-126">紫色标志</span><span class="sxs-lookup"><span data-stu-id="b630e-126">Purple flag</span></span>  <br/> |
|<span data-ttu-id="b630e-127">2</span><span class="sxs-lookup"><span data-stu-id="b630e-127">2</span></span>  <br/> |<span data-ttu-id="b630e-128">followupIcon2</span><span class="sxs-lookup"><span data-stu-id="b630e-128">followupIcon2</span></span>  <br/> |<span data-ttu-id="b630e-129">橙色标志</span><span class="sxs-lookup"><span data-stu-id="b630e-129">Orange flag</span></span>  <br/> |
|<span data-ttu-id="b630e-130">3</span><span class="sxs-lookup"><span data-stu-id="b630e-130">3</span></span>  <br/> |<span data-ttu-id="b630e-131">followupIcon3</span><span class="sxs-lookup"><span data-stu-id="b630e-131">followupIcon3</span></span>  <br/> |<span data-ttu-id="b630e-132">绿色标志</span><span class="sxs-lookup"><span data-stu-id="b630e-132">Green flag</span></span>  <br/> |
|<span data-ttu-id="b630e-133">4</span><span class="sxs-lookup"><span data-stu-id="b630e-133">4</span></span>  <br/> |<span data-ttu-id="b630e-134">followupIcon4</span><span class="sxs-lookup"><span data-stu-id="b630e-134">followupIcon4</span></span>  <br/> |<span data-ttu-id="b630e-135">黄色标志</span><span class="sxs-lookup"><span data-stu-id="b630e-135">Yellow flag</span></span>  <br/> |
|<span data-ttu-id="b630e-136">5</span><span class="sxs-lookup"><span data-stu-id="b630e-136">5</span></span>  <br/> |<span data-ttu-id="b630e-137">followupIcon5</span><span class="sxs-lookup"><span data-stu-id="b630e-137">followupIcon5</span></span>  <br/> |<span data-ttu-id="b630e-138">蓝色标志</span><span class="sxs-lookup"><span data-stu-id="b630e-138">Blue flag</span></span>  <br/> |
|<span data-ttu-id="b630e-139">6</span><span class="sxs-lookup"><span data-stu-id="b630e-139">6</span></span>  <br/> |<span data-ttu-id="b630e-140">followupIcon6</span><span class="sxs-lookup"><span data-stu-id="b630e-140">followupIcon6</span></span>  <br/> |<span data-ttu-id="b630e-141">红色标志</span><span class="sxs-lookup"><span data-stu-id="b630e-141">Red flag</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="b630e-142">相关资源</span><span class="sxs-lookup"><span data-stu-id="b630e-142">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b630e-143">协议规范</span><span class="sxs-lookup"><span data-stu-id="b630e-143">Protocol specifications</span></span>

<span data-ttu-id="b630e-144">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b630e-144">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b630e-145">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="b630e-145">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b630e-146">[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b630e-146">[[MS-OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b630e-147">指定的属性和与标记的操作。</span><span class="sxs-lookup"><span data-stu-id="b630e-147">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b630e-148">头文件</span><span class="sxs-lookup"><span data-stu-id="b630e-148">Header files</span></span>

<span data-ttu-id="b630e-149">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b630e-149">Mapidefs.h</span></span>
  
> <span data-ttu-id="b630e-150">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b630e-150">Provides data type definitions.</span></span>
    
<span data-ttu-id="b630e-151">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b630e-151">Mapitags.h</span></span>
  
> <span data-ttu-id="b630e-152">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b630e-152">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b630e-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b630e-153">See also</span></span>



[<span data-ttu-id="b630e-154">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b630e-154">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b630e-155">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b630e-155">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b630e-156">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b630e-156">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b630e-157">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b630e-157">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

