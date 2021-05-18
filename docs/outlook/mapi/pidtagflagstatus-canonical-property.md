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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bca8fccaa43bb3157b3d4e2af7d6aafa64972b41
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316294"
---
# <a name="pidtagflagstatus-canonical-property"></a><span data-ttu-id="1ac80-103">PidTagFlagStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="1ac80-103">PidTagFlagStatus Canonical Property</span></span>

  
  
<span data-ttu-id="1ac80-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1ac80-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1ac80-105">指定邮件对象的标志状态。</span><span class="sxs-lookup"><span data-stu-id="1ac80-105">Specifies the flag state of the message object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1ac80-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1ac80-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1ac80-107">PR_FLAG_STATUS</span><span class="sxs-lookup"><span data-stu-id="1ac80-107">PR_FLAG_STATUS</span></span>  <br/> |
|<span data-ttu-id="1ac80-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="1ac80-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1ac80-109">0x1090</span><span class="sxs-lookup"><span data-stu-id="1ac80-109">0x1090</span></span>  <br/> |
|<span data-ttu-id="1ac80-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1ac80-110">Data type:</span></span>  <br/> |<span data-ttu-id="1ac80-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="1ac80-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="1ac80-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1ac80-112">Area:</span></span>  <br/> |<span data-ttu-id="1ac80-113">其他</span><span class="sxs-lookup"><span data-stu-id="1ac80-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1ac80-114">备注</span><span class="sxs-lookup"><span data-stu-id="1ac80-114">Remarks</span></span>

<span data-ttu-id="1ac80-115">此属性不能存在于与会议相关的对象上，并且不应存在于任务对象上。</span><span class="sxs-lookup"><span data-stu-id="1ac80-115">This property must not exist on a meeting-related object, and it should not exist on a task object.</span></span> <span data-ttu-id="1ac80-116">在其他邮件对象上设置时，此属性必须设置为下列值之一：</span><span class="sxs-lookup"><span data-stu-id="1ac80-116">When set on other message objects, this property must be set to one of the following values:</span></span>
  
|<span data-ttu-id="1ac80-117">**数值**</span><span class="sxs-lookup"><span data-stu-id="1ac80-117">**Numeric value**</span></span>|<span data-ttu-id="1ac80-118">**名称**</span><span class="sxs-lookup"><span data-stu-id="1ac80-118">**Name**</span></span>|<span data-ttu-id="1ac80-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="1ac80-119">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1ac80-120">不存在</span><span class="sxs-lookup"><span data-stu-id="1ac80-120">Not present</span></span>  <br/> |<span data-ttu-id="1ac80-121">不适用</span><span class="sxs-lookup"><span data-stu-id="1ac80-121">N/A</span></span>  <br/> |<span data-ttu-id="1ac80-122">未标记</span><span class="sxs-lookup"><span data-stu-id="1ac80-122">Unflagged</span></span>  <br/> |
|<span data-ttu-id="1ac80-123">0x00000001</span><span class="sxs-lookup"><span data-stu-id="1ac80-123">0x00000001</span></span>  <br/> |<span data-ttu-id="1ac80-124">followupComplete</span><span class="sxs-lookup"><span data-stu-id="1ac80-124">followupComplete</span></span>  <br/> |<span data-ttu-id="1ac80-125">已标记完成</span><span class="sxs-lookup"><span data-stu-id="1ac80-125">Flagged complete</span></span>  <br/> |
|<span data-ttu-id="1ac80-126">0x00000002</span><span class="sxs-lookup"><span data-stu-id="1ac80-126">0x00000002</span></span>  <br/> |<span data-ttu-id="1ac80-127">followupFlagged</span><span class="sxs-lookup"><span data-stu-id="1ac80-127">followupFlagged</span></span>  <br/> |<span data-ttu-id="1ac80-128">已标记</span><span class="sxs-lookup"><span data-stu-id="1ac80-128">Flagged</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="1ac80-129">相关资源</span><span class="sxs-lookup"><span data-stu-id="1ac80-129">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1ac80-130">协议规范</span><span class="sxs-lookup"><span data-stu-id="1ac80-130">Protocol specifications</span></span>

<span data-ttu-id="1ac80-131">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1ac80-131">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1ac80-132">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="1ac80-132">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1ac80-133">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1ac80-133">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1ac80-134">指定与标记相关的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="1ac80-134">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1ac80-135">头文件</span><span class="sxs-lookup"><span data-stu-id="1ac80-135">Header files</span></span>

<span data-ttu-id="1ac80-136">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1ac80-136">Mapidefs.h</span></span>
  
> <span data-ttu-id="1ac80-137">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1ac80-137">Provides data type definitions.</span></span>
    
<span data-ttu-id="1ac80-138">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="1ac80-138">Mapitags.h</span></span>
  
> <span data-ttu-id="1ac80-139">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1ac80-139">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1ac80-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ac80-140">See also</span></span>



[<span data-ttu-id="1ac80-141">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1ac80-141">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1ac80-142">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1ac80-142">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1ac80-143">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1ac80-143">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1ac80-144">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1ac80-144">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

