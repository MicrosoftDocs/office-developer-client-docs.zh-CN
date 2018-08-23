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
ms.openlocfilehash: 8fa96736b5404d84c6ab48851b916c5ab987ae2a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593919"
---
# <a name="pidtagfollowupicon-canonical-property"></a><span data-ttu-id="96583-103">PidTagFollowupIcon 规范属性</span><span class="sxs-lookup"><span data-stu-id="96583-103">PidTagFollowupIcon Canonical Property</span></span>

  
  
<span data-ttu-id="96583-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="96583-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="96583-105">指定消息对象的标志的颜色。</span><span class="sxs-lookup"><span data-stu-id="96583-105">Specifies the flag color of the message object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="96583-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="96583-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="96583-107">PR_FOLLOWUP_ICON</span><span class="sxs-lookup"><span data-stu-id="96583-107">PR_FOLLOWUP_ICON</span></span>  <br/> |
|<span data-ttu-id="96583-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="96583-108">Identifier:</span></span>  <br/> |<span data-ttu-id="96583-109">0x1095</span><span class="sxs-lookup"><span data-stu-id="96583-109">0x1095</span></span>  <br/> |
|<span data-ttu-id="96583-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="96583-110">Data type:</span></span>  <br/> |<span data-ttu-id="96583-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="96583-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="96583-112">区域：</span><span class="sxs-lookup"><span data-stu-id="96583-112">Area:</span></span>  <br/> |<span data-ttu-id="96583-113">重命名邮件文件夹</span><span class="sxs-lookup"><span data-stu-id="96583-113">Rename message folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="96583-114">注解</span><span class="sxs-lookup"><span data-stu-id="96583-114">Remarks</span></span>

<span data-ttu-id="96583-115">此属性必须存在除非**PR_FLAG_STATUS** ([PidTagFlagStatus](pidtagflagstatus-canonical-property.md)) 属性的值设置为"followupFlagged"，或 message 对象是会议相关对象。</span><span class="sxs-lookup"><span data-stu-id="96583-115">This property must not exist unless the value of the **PR_FLAG_STATUS** ([PidTagFlagStatus](pidtagflagstatus-canonical-property.md)) property is set to "followupFlagged", or the message object is a meeting-related object.</span></span> <span data-ttu-id="96583-116">此属性不应存在对任务对象。</span><span class="sxs-lookup"><span data-stu-id="96583-116">This property should not exist on a task object.</span></span> <span data-ttu-id="96583-117">当在其他消息对象上设置时，此属性必须设置为下列值之一。</span><span class="sxs-lookup"><span data-stu-id="96583-117">When set on other message objects, this property must be set to one of the following values.</span></span>
  
|<span data-ttu-id="96583-118">**数值**</span><span class="sxs-lookup"><span data-stu-id="96583-118">**Numeric value**</span></span>|<span data-ttu-id="96583-119">**名称**</span><span class="sxs-lookup"><span data-stu-id="96583-119">**Name**</span></span>|<span data-ttu-id="96583-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="96583-120">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="96583-121">不存在</span><span class="sxs-lookup"><span data-stu-id="96583-121">Not present</span></span>  <br/> |<span data-ttu-id="96583-122">不适用</span><span class="sxs-lookup"><span data-stu-id="96583-122">N/A</span></span>  <br/> |<span data-ttu-id="96583-123">无颜色</span><span class="sxs-lookup"><span data-stu-id="96583-123">No color</span></span>  <br/> |
|<span data-ttu-id="96583-124">1</span><span class="sxs-lookup"><span data-stu-id="96583-124">1</span></span>  <br/> |<span data-ttu-id="96583-125">followupIcon1</span><span class="sxs-lookup"><span data-stu-id="96583-125">followupIcon1</span></span>  <br/> |<span data-ttu-id="96583-126">紫色标志</span><span class="sxs-lookup"><span data-stu-id="96583-126">Purple flag</span></span>  <br/> |
|<span data-ttu-id="96583-127">2</span><span class="sxs-lookup"><span data-stu-id="96583-127">2</span></span>  <br/> |<span data-ttu-id="96583-128">followupIcon2</span><span class="sxs-lookup"><span data-stu-id="96583-128">followupIcon2</span></span>  <br/> |<span data-ttu-id="96583-129">橙色标志</span><span class="sxs-lookup"><span data-stu-id="96583-129">Orange flag</span></span>  <br/> |
|<span data-ttu-id="96583-130">3</span><span class="sxs-lookup"><span data-stu-id="96583-130">3</span></span>  <br/> |<span data-ttu-id="96583-131">followupIcon3</span><span class="sxs-lookup"><span data-stu-id="96583-131">followupIcon3</span></span>  <br/> |<span data-ttu-id="96583-132">绿色标志</span><span class="sxs-lookup"><span data-stu-id="96583-132">Green flag</span></span>  <br/> |
|<span data-ttu-id="96583-133">4</span><span class="sxs-lookup"><span data-stu-id="96583-133">4</span></span>  <br/> |<span data-ttu-id="96583-134">followupIcon4</span><span class="sxs-lookup"><span data-stu-id="96583-134">followupIcon4</span></span>  <br/> |<span data-ttu-id="96583-135">黄色标志</span><span class="sxs-lookup"><span data-stu-id="96583-135">Yellow flag</span></span>  <br/> |
|<span data-ttu-id="96583-136">5</span><span class="sxs-lookup"><span data-stu-id="96583-136">5</span></span>  <br/> |<span data-ttu-id="96583-137">followupIcon5</span><span class="sxs-lookup"><span data-stu-id="96583-137">followupIcon5</span></span>  <br/> |<span data-ttu-id="96583-138">蓝色标志</span><span class="sxs-lookup"><span data-stu-id="96583-138">Blue flag</span></span>  <br/> |
|<span data-ttu-id="96583-139">6</span><span class="sxs-lookup"><span data-stu-id="96583-139">6</span></span>  <br/> |<span data-ttu-id="96583-140">followupIcon6</span><span class="sxs-lookup"><span data-stu-id="96583-140">followupIcon6</span></span>  <br/> |<span data-ttu-id="96583-141">红色标志</span><span class="sxs-lookup"><span data-stu-id="96583-141">Red flag</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="96583-142">相关资源</span><span class="sxs-lookup"><span data-stu-id="96583-142">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="96583-143">协议规范</span><span class="sxs-lookup"><span data-stu-id="96583-143">Protocol specifications</span></span>

<span data-ttu-id="96583-144">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="96583-144">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="96583-145">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="96583-145">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="96583-146">[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="96583-146">[[MS-OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="96583-147">指定的属性和与标记的操作。</span><span class="sxs-lookup"><span data-stu-id="96583-147">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="96583-148">头文件</span><span class="sxs-lookup"><span data-stu-id="96583-148">Header files</span></span>

<span data-ttu-id="96583-149">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="96583-149">Mapidefs.h</span></span>
  
> <span data-ttu-id="96583-150">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="96583-150">Provides data type definitions.</span></span>
    
<span data-ttu-id="96583-151">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="96583-151">Mapitags.h</span></span>
  
> <span data-ttu-id="96583-152">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="96583-152">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="96583-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96583-153">See also</span></span>



[<span data-ttu-id="96583-154">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="96583-154">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="96583-155">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="96583-155">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="96583-156">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="96583-156">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="96583-157">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="96583-157">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

