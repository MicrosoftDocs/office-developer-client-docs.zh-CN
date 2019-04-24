---
title: PidLidResponseStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidResponseStatus
api_type:
- COM
ms.assetid: e56142fd-204b-497e-83b9-59f9acda6cb4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8c8e284752c6fd47eb7a8f227e2dbfeceebea596
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345757"
---
# <a name="pidlidresponsestatus-canonical-property"></a><span data-ttu-id="9ef3e-103">PidLidResponseStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="9ef3e-103">PidLidResponseStatus Canonical Property</span></span>

  
  
<span data-ttu-id="9ef3e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9ef3e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9ef3e-105">指定与会者的响应状态。</span><span class="sxs-lookup"><span data-stu-id="9ef3e-105">Specifies the response status of an attendee.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9ef3e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9ef3e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9ef3e-107">dispidResponseStatus</span><span class="sxs-lookup"><span data-stu-id="9ef3e-107">dispidResponseStatus</span></span>  <br/> |
|<span data-ttu-id="9ef3e-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="9ef3e-108">Property set:</span></span>  <br/> |<span data-ttu-id="9ef3e-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="9ef3e-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="9ef3e-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="9ef3e-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="9ef3e-111">0x00008218</span><span class="sxs-lookup"><span data-stu-id="9ef3e-111">0x00008218</span></span>  <br/> |
|<span data-ttu-id="9ef3e-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9ef3e-112">Data type:</span></span>  <br/> |<span data-ttu-id="9ef3e-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="9ef3e-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="9ef3e-114">区域：</span><span class="sxs-lookup"><span data-stu-id="9ef3e-114">Area:</span></span>  <br/> |<span data-ttu-id="9ef3e-115">会议</span><span class="sxs-lookup"><span data-stu-id="9ef3e-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9ef3e-116">注解</span><span class="sxs-lookup"><span data-stu-id="9ef3e-116">Remarks</span></span>

<span data-ttu-id="9ef3e-117">响应状态必须是下表中的值之一。</span><span class="sxs-lookup"><span data-stu-id="9ef3e-117">The response status must be one of the values in the table below.</span></span>
  
|<span data-ttu-id="9ef3e-118">**响应状态**</span><span class="sxs-lookup"><span data-stu-id="9ef3e-118">**Response status**</span></span>|<span data-ttu-id="9ef3e-119">**Value**</span><span class="sxs-lookup"><span data-stu-id="9ef3e-119">**Value**</span></span>|<span data-ttu-id="9ef3e-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="9ef3e-120">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9ef3e-121">respNone</span><span class="sxs-lookup"><span data-stu-id="9ef3e-121">respNone</span></span>  <br/> |<span data-ttu-id="9ef3e-122">0x00000000</span><span class="sxs-lookup"><span data-stu-id="9ef3e-122">0x00000000</span></span>  <br/> |<span data-ttu-id="9ef3e-123">此对象不需要响应。</span><span class="sxs-lookup"><span data-stu-id="9ef3e-123">No response is required for this object.</span></span> <span data-ttu-id="9ef3e-124">这就是约会对象和会议响应对象的情况。</span><span class="sxs-lookup"><span data-stu-id="9ef3e-124">This is the case for appointment objects and meeting response objects.</span></span>  <br/> |
|<span data-ttu-id="9ef3e-125">respOrganized</span><span class="sxs-lookup"><span data-stu-id="9ef3e-125">respOrganized</span></span>  <br/> |<span data-ttu-id="9ef3e-126">0x00000001</span><span class="sxs-lookup"><span data-stu-id="9ef3e-126">0x00000001</span></span>  <br/> |<span data-ttu-id="9ef3e-127">此会议属于组织者。</span><span class="sxs-lookup"><span data-stu-id="9ef3e-127">This meeting belongs to the organizer.</span></span>  <br/> |
|<span data-ttu-id="9ef3e-128">respTentative</span><span class="sxs-lookup"><span data-stu-id="9ef3e-128">respTentative</span></span>  <br/> |<span data-ttu-id="9ef3e-129">0x00000002</span><span class="sxs-lookup"><span data-stu-id="9ef3e-129">0x00000002</span></span>  <br/> |<span data-ttu-id="9ef3e-130">与会者会议上的此值表示与会者暂时接受了会议请求。</span><span class="sxs-lookup"><span data-stu-id="9ef3e-130">This value on the attendee's meeting indicates that the attendee has tentatively accepted the meeting request.</span></span>  <br/> |
|<span data-ttu-id="9ef3e-131">respAccepted</span><span class="sxs-lookup"><span data-stu-id="9ef3e-131">respAccepted</span></span>  <br/> |<span data-ttu-id="9ef3e-132">0x00000003</span><span class="sxs-lookup"><span data-stu-id="9ef3e-132">0x00000003</span></span>  <br/> |<span data-ttu-id="9ef3e-133">与会者的会议 t 上的此值表示与会者已接受会议请求。</span><span class="sxs-lookup"><span data-stu-id="9ef3e-133">This value on the attendee's meeting t indicates that the attendee has accepted the meeting request.</span></span>  <br/> |
|<span data-ttu-id="9ef3e-134">respDeclined</span><span class="sxs-lookup"><span data-stu-id="9ef3e-134">respDeclined</span></span>  <br/> |<span data-ttu-id="9ef3e-135">0x00000004</span><span class="sxs-lookup"><span data-stu-id="9ef3e-135">0x00000004</span></span>  <br/> |<span data-ttu-id="9ef3e-136">与会者会议上的此值表示与会者已谢绝会议请求。</span><span class="sxs-lookup"><span data-stu-id="9ef3e-136">This value on the attendee's meeting indicates that the attendee has declined the meeting request.</span></span>  <br/> |
|<span data-ttu-id="9ef3e-137">respNotResponded</span><span class="sxs-lookup"><span data-stu-id="9ef3e-137">respNotResponded</span></span>  <br/> |<span data-ttu-id="9ef3e-138">0x00000005</span><span class="sxs-lookup"><span data-stu-id="9ef3e-138">0x00000005</span></span>  <br/> |<span data-ttu-id="9ef3e-139">与会者会议上的此值表示与会者尚未响应。</span><span class="sxs-lookup"><span data-stu-id="9ef3e-139">This value on the attendee's meeting indicates the attendee has not yet responded.</span></span> <span data-ttu-id="9ef3e-140">此值在会议请求、会议更新和会议取消中。</span><span class="sxs-lookup"><span data-stu-id="9ef3e-140">This value is on the meeting request, meeting update, and meeting cancelation.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="9ef3e-141">相关资源</span><span class="sxs-lookup"><span data-stu-id="9ef3e-141">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="9ef3e-142">协议规范</span><span class="sxs-lookup"><span data-stu-id="9ef3e-142">Protocol specifications</span></span>

<span data-ttu-id="9ef3e-143">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9ef3e-143">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9ef3e-144">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="9ef3e-144">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="9ef3e-145">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9ef3e-145">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9ef3e-146">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="9ef3e-146">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="9ef3e-147">头文件</span><span class="sxs-lookup"><span data-stu-id="9ef3e-147">Header files</span></span>

<span data-ttu-id="9ef3e-148">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="9ef3e-148">Mapidefs.h</span></span>
  
> <span data-ttu-id="9ef3e-149">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9ef3e-149">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9ef3e-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ef3e-150">See also</span></span>



[<span data-ttu-id="9ef3e-151">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9ef3e-151">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9ef3e-152">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9ef3e-152">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9ef3e-153">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9ef3e-153">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9ef3e-154">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9ef3e-154">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

