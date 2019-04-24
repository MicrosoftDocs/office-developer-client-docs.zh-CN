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
# <a name="pidtagflagstatus-canonical-property"></a><span data-ttu-id="13ec1-103">PidTagFlagStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="13ec1-103">PidTagFlagStatus Canonical Property</span></span>

  
  
<span data-ttu-id="13ec1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="13ec1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="13ec1-105">指定邮件对象的标记状态。</span><span class="sxs-lookup"><span data-stu-id="13ec1-105">Specifies the flag state of the message object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="13ec1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="13ec1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="13ec1-107">PR_FLAG_STATUS</span><span class="sxs-lookup"><span data-stu-id="13ec1-107">PR_FLAG_STATUS</span></span>  <br/> |
|<span data-ttu-id="13ec1-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="13ec1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="13ec1-109">0x1090</span><span class="sxs-lookup"><span data-stu-id="13ec1-109">0x1090</span></span>  <br/> |
|<span data-ttu-id="13ec1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="13ec1-110">Data type:</span></span>  <br/> |<span data-ttu-id="13ec1-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="13ec1-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="13ec1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="13ec1-112">Area:</span></span>  <br/> |<span data-ttu-id="13ec1-113">其他</span><span class="sxs-lookup"><span data-stu-id="13ec1-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="13ec1-114">注解</span><span class="sxs-lookup"><span data-stu-id="13ec1-114">Remarks</span></span>

<span data-ttu-id="13ec1-115">此属性不能在与会议相关的对象上存在, 并且不应存在于任务对象上。</span><span class="sxs-lookup"><span data-stu-id="13ec1-115">This property must not exist on a meeting-related object, and it should not exist on a task object.</span></span> <span data-ttu-id="13ec1-116">当对其他 message 对象进行设置时, 此属性必须设置为以下值之一:</span><span class="sxs-lookup"><span data-stu-id="13ec1-116">When set on other message objects, this property must be set to one of the following values:</span></span>
  
|<span data-ttu-id="13ec1-117">**数字值**</span><span class="sxs-lookup"><span data-stu-id="13ec1-117">**Numeric value**</span></span>|<span data-ttu-id="13ec1-118">**名称**</span><span class="sxs-lookup"><span data-stu-id="13ec1-118">**Name**</span></span>|<span data-ttu-id="13ec1-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="13ec1-119">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="13ec1-120">不存在</span><span class="sxs-lookup"><span data-stu-id="13ec1-120">Not present</span></span>  <br/> |<span data-ttu-id="13ec1-121">不适用</span><span class="sxs-lookup"><span data-stu-id="13ec1-121">N/A</span></span>  <br/> |<span data-ttu-id="13ec1-122">标记</span><span class="sxs-lookup"><span data-stu-id="13ec1-122">Unflagged</span></span>  <br/> |
|<span data-ttu-id="13ec1-123">0x00000001</span><span class="sxs-lookup"><span data-stu-id="13ec1-123">0x00000001</span></span>  <br/> |<span data-ttu-id="13ec1-124">followupComplete</span><span class="sxs-lookup"><span data-stu-id="13ec1-124">followupComplete</span></span>  <br/> |<span data-ttu-id="13ec1-125">标记完成</span><span class="sxs-lookup"><span data-stu-id="13ec1-125">Flagged complete</span></span>  <br/> |
|<span data-ttu-id="13ec1-126">0x00000002</span><span class="sxs-lookup"><span data-stu-id="13ec1-126">0x00000002</span></span>  <br/> |<span data-ttu-id="13ec1-127">followupFlagged</span><span class="sxs-lookup"><span data-stu-id="13ec1-127">followupFlagged</span></span>  <br/> |<span data-ttu-id="13ec1-128">带</span><span class="sxs-lookup"><span data-stu-id="13ec1-128">Flagged</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="13ec1-129">相关资源</span><span class="sxs-lookup"><span data-stu-id="13ec1-129">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="13ec1-130">协议规范</span><span class="sxs-lookup"><span data-stu-id="13ec1-130">Protocol specifications</span></span>

<span data-ttu-id="13ec1-131">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="13ec1-131">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="13ec1-132">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="13ec1-132">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="13ec1-133">[[毫秒-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="13ec1-133">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="13ec1-134">指定与标记相关的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="13ec1-134">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="13ec1-135">头文件</span><span class="sxs-lookup"><span data-stu-id="13ec1-135">Header files</span></span>

<span data-ttu-id="13ec1-136">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="13ec1-136">Mapidefs.h</span></span>
  
> <span data-ttu-id="13ec1-137">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="13ec1-137">Provides data type definitions.</span></span>
    
<span data-ttu-id="13ec1-138">Mapitags</span><span class="sxs-lookup"><span data-stu-id="13ec1-138">Mapitags.h</span></span>
  
> <span data-ttu-id="13ec1-139">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="13ec1-139">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="13ec1-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13ec1-140">See also</span></span>



[<span data-ttu-id="13ec1-141">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="13ec1-141">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="13ec1-142">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="13ec1-142">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="13ec1-143">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="13ec1-143">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="13ec1-144">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="13ec1-144">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

