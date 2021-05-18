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
ms.openlocfilehash: 205b6ddc2b65297d69a2223aab7b745b223ee553
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316280"
---
# <a name="pidtagfollowupicon-canonical-property"></a><span data-ttu-id="327b0-103">PidTagFollowupIcon 规范属性</span><span class="sxs-lookup"><span data-stu-id="327b0-103">PidTagFollowupIcon Canonical Property</span></span>

  
  
<span data-ttu-id="327b0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="327b0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="327b0-105">指定邮件对象的标志颜色。</span><span class="sxs-lookup"><span data-stu-id="327b0-105">Specifies the flag color of the message object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="327b0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="327b0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="327b0-107">PR_FOLLOWUP_ICON</span><span class="sxs-lookup"><span data-stu-id="327b0-107">PR_FOLLOWUP_ICON</span></span>  <br/> |
|<span data-ttu-id="327b0-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="327b0-108">Identifier:</span></span>  <br/> |<span data-ttu-id="327b0-109">0x1095</span><span class="sxs-lookup"><span data-stu-id="327b0-109">0x1095</span></span>  <br/> |
|<span data-ttu-id="327b0-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="327b0-110">Data type:</span></span>  <br/> |<span data-ttu-id="327b0-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="327b0-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="327b0-112">区域：</span><span class="sxs-lookup"><span data-stu-id="327b0-112">Area:</span></span>  <br/> |<span data-ttu-id="327b0-113">重命名邮件文件夹</span><span class="sxs-lookup"><span data-stu-id="327b0-113">Rename message folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="327b0-114">备注</span><span class="sxs-lookup"><span data-stu-id="327b0-114">Remarks</span></span>

<span data-ttu-id="327b0-115">此属性必须不存在，除非 **PR_FLAG_STATUS** ([PidTagFlagStatus](pidtagflagstatus-canonical-property.md)) 属性的值设置为"followupFlagged"，或者邮件对象是会议相关的对象。</span><span class="sxs-lookup"><span data-stu-id="327b0-115">This property must not exist unless the value of the **PR_FLAG_STATUS** ([PidTagFlagStatus](pidtagflagstatus-canonical-property.md)) property is set to "followupFlagged", or the message object is a meeting-related object.</span></span> <span data-ttu-id="327b0-116">此属性不应存在于任务对象上。</span><span class="sxs-lookup"><span data-stu-id="327b0-116">This property should not exist on a task object.</span></span> <span data-ttu-id="327b0-117">在其他邮件对象上设置时，此属性必须设置为下列值之一。</span><span class="sxs-lookup"><span data-stu-id="327b0-117">When set on other message objects, this property must be set to one of the following values.</span></span>
  
|<span data-ttu-id="327b0-118">**数值**</span><span class="sxs-lookup"><span data-stu-id="327b0-118">**Numeric value**</span></span>|<span data-ttu-id="327b0-119">**名称**</span><span class="sxs-lookup"><span data-stu-id="327b0-119">**Name**</span></span>|<span data-ttu-id="327b0-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="327b0-120">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="327b0-121">不存在</span><span class="sxs-lookup"><span data-stu-id="327b0-121">Not present</span></span>  <br/> |<span data-ttu-id="327b0-122">不适用</span><span class="sxs-lookup"><span data-stu-id="327b0-122">N/A</span></span>  <br/> |<span data-ttu-id="327b0-123">无颜色</span><span class="sxs-lookup"><span data-stu-id="327b0-123">No color</span></span>  <br/> |
|<span data-ttu-id="327b0-124">1</span><span class="sxs-lookup"><span data-stu-id="327b0-124">1</span></span>  <br/> |<span data-ttu-id="327b0-125">followupIcon1</span><span class="sxs-lookup"><span data-stu-id="327b0-125">followupIcon1</span></span>  <br/> |<span data-ttu-id="327b0-126">紫色标志</span><span class="sxs-lookup"><span data-stu-id="327b0-126">Purple flag</span></span>  <br/> |
|<span data-ttu-id="327b0-127">2</span><span class="sxs-lookup"><span data-stu-id="327b0-127">2</span></span>  <br/> |<span data-ttu-id="327b0-128">followupIcon2</span><span class="sxs-lookup"><span data-stu-id="327b0-128">followupIcon2</span></span>  <br/> |<span data-ttu-id="327b0-129">橙色标志</span><span class="sxs-lookup"><span data-stu-id="327b0-129">Orange flag</span></span>  <br/> |
|<span data-ttu-id="327b0-130">3</span><span class="sxs-lookup"><span data-stu-id="327b0-130">3</span></span>  <br/> |<span data-ttu-id="327b0-131">followupIcon3</span><span class="sxs-lookup"><span data-stu-id="327b0-131">followupIcon3</span></span>  <br/> |<span data-ttu-id="327b0-132">绿色标志</span><span class="sxs-lookup"><span data-stu-id="327b0-132">Green flag</span></span>  <br/> |
|<span data-ttu-id="327b0-133">4 </span><span class="sxs-lookup"><span data-stu-id="327b0-133">4</span></span>  <br/> |<span data-ttu-id="327b0-134">followupIcon4</span><span class="sxs-lookup"><span data-stu-id="327b0-134">followupIcon4</span></span>  <br/> |<span data-ttu-id="327b0-135">黄色标志</span><span class="sxs-lookup"><span data-stu-id="327b0-135">Yellow flag</span></span>  <br/> |
|<span data-ttu-id="327b0-136">5 </span><span class="sxs-lookup"><span data-stu-id="327b0-136">5</span></span>  <br/> |<span data-ttu-id="327b0-137">followupIcon5</span><span class="sxs-lookup"><span data-stu-id="327b0-137">followupIcon5</span></span>  <br/> |<span data-ttu-id="327b0-138">蓝色标志</span><span class="sxs-lookup"><span data-stu-id="327b0-138">Blue flag</span></span>  <br/> |
|<span data-ttu-id="327b0-139">6 </span><span class="sxs-lookup"><span data-stu-id="327b0-139">6</span></span>  <br/> |<span data-ttu-id="327b0-140">followupIcon6</span><span class="sxs-lookup"><span data-stu-id="327b0-140">followupIcon6</span></span>  <br/> |<span data-ttu-id="327b0-141">红色标志</span><span class="sxs-lookup"><span data-stu-id="327b0-141">Red flag</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="327b0-142">相关资源</span><span class="sxs-lookup"><span data-stu-id="327b0-142">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="327b0-143">协议规范</span><span class="sxs-lookup"><span data-stu-id="327b0-143">Protocol specifications</span></span>

<span data-ttu-id="327b0-144">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="327b0-144">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="327b0-145">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="327b0-145">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="327b0-146">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="327b0-146">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="327b0-147">指定与标记相关的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="327b0-147">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="327b0-148">头文件</span><span class="sxs-lookup"><span data-stu-id="327b0-148">Header files</span></span>

<span data-ttu-id="327b0-149">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="327b0-149">Mapidefs.h</span></span>
  
> <span data-ttu-id="327b0-150">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="327b0-150">Provides data type definitions.</span></span>
    
<span data-ttu-id="327b0-151">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="327b0-151">Mapitags.h</span></span>
  
> <span data-ttu-id="327b0-152">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="327b0-152">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="327b0-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="327b0-153">See also</span></span>



[<span data-ttu-id="327b0-154">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="327b0-154">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="327b0-155">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="327b0-155">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="327b0-156">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="327b0-156">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="327b0-157">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="327b0-157">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

