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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25390553"
---
# <a name="pidtagflagstatus-canonical-property"></a><span data-ttu-id="79008-103">PidTagFlagStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="79008-103">PidTagFlagStatus Canonical Property</span></span>

  
  
<span data-ttu-id="79008-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="79008-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="79008-105">指定的消息对象的标志状态。</span><span class="sxs-lookup"><span data-stu-id="79008-105">Specifies the flag state of the message object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="79008-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="79008-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="79008-107">PR_FLAG_STATUS</span><span class="sxs-lookup"><span data-stu-id="79008-107">PR_FLAG_STATUS</span></span>  <br/> |
|<span data-ttu-id="79008-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="79008-108">Identifier:</span></span>  <br/> |<span data-ttu-id="79008-109">0x1090</span><span class="sxs-lookup"><span data-stu-id="79008-109">0x1090</span></span>  <br/> |
|<span data-ttu-id="79008-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="79008-110">Data type:</span></span>  <br/> |<span data-ttu-id="79008-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="79008-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="79008-112">区域：</span><span class="sxs-lookup"><span data-stu-id="79008-112">Area:</span></span>  <br/> |<span data-ttu-id="79008-113">其他</span><span class="sxs-lookup"><span data-stu-id="79008-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="79008-114">说明</span><span class="sxs-lookup"><span data-stu-id="79008-114">Remarks</span></span>

<span data-ttu-id="79008-115">此属性必须存在会议相关对象上,，它应不存在于 task 对象。</span><span class="sxs-lookup"><span data-stu-id="79008-115">This property must not exist on a meeting-related object, and it should not exist on a task object.</span></span> <span data-ttu-id="79008-116">当在其他消息对象上设置时，此属性必须设置为下列值之一：</span><span class="sxs-lookup"><span data-stu-id="79008-116">When set on other message objects, this property must be set to one of the following values:</span></span>
  
|<span data-ttu-id="79008-117">**数值**</span><span class="sxs-lookup"><span data-stu-id="79008-117">**Numeric value**</span></span>|<span data-ttu-id="79008-118">**名称**</span><span class="sxs-lookup"><span data-stu-id="79008-118">**Name**</span></span>|<span data-ttu-id="79008-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="79008-119">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="79008-120">不存在</span><span class="sxs-lookup"><span data-stu-id="79008-120">Not present</span></span>  <br/> |<span data-ttu-id="79008-121">不适用</span><span class="sxs-lookup"><span data-stu-id="79008-121">N/A</span></span>  <br/> |<span data-ttu-id="79008-122">未标记</span><span class="sxs-lookup"><span data-stu-id="79008-122">Unflagged</span></span>  <br/> |
|<span data-ttu-id="79008-123">0x00000001</span><span class="sxs-lookup"><span data-stu-id="79008-123">0x00000001</span></span>  <br/> |<span data-ttu-id="79008-124">followupComplete</span><span class="sxs-lookup"><span data-stu-id="79008-124">followupComplete</span></span>  <br/> |<span data-ttu-id="79008-125">标记完成</span><span class="sxs-lookup"><span data-stu-id="79008-125">Flagged complete</span></span>  <br/> |
|<span data-ttu-id="79008-126">0x00000002</span><span class="sxs-lookup"><span data-stu-id="79008-126">0x00000002</span></span>  <br/> |<span data-ttu-id="79008-127">followupFlagged</span><span class="sxs-lookup"><span data-stu-id="79008-127">followupFlagged</span></span>  <br/> |<span data-ttu-id="79008-128">标记</span><span class="sxs-lookup"><span data-stu-id="79008-128">Flagged</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="79008-129">相关资源</span><span class="sxs-lookup"><span data-stu-id="79008-129">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="79008-130">协议规范</span><span class="sxs-lookup"><span data-stu-id="79008-130">Protocol specifications</span></span>

<span data-ttu-id="79008-131">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="79008-131">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="79008-132">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="79008-132">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="79008-133">[[MS OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="79008-133">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="79008-134">指定的属性和与标记的操作。</span><span class="sxs-lookup"><span data-stu-id="79008-134">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="79008-135">头文件</span><span class="sxs-lookup"><span data-stu-id="79008-135">Header files</span></span>

<span data-ttu-id="79008-136">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="79008-136">Mapidefs.h</span></span>
  
> <span data-ttu-id="79008-137">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="79008-137">Provides data type definitions.</span></span>
    
<span data-ttu-id="79008-138">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="79008-138">Mapitags.h</span></span>
  
> <span data-ttu-id="79008-139">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="79008-139">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="79008-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79008-140">See also</span></span>



[<span data-ttu-id="79008-141">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="79008-141">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="79008-142">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="79008-142">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="79008-143">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="79008-143">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="79008-144">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="79008-144">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

