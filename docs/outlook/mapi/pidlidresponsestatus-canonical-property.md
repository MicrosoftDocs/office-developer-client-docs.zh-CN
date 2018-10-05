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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385009"
---
# <a name="pidlidresponsestatus-canonical-property"></a><span data-ttu-id="cb061-103">PidLidResponseStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="cb061-103">PidLidResponseStatus Canonical Property</span></span>

  
  
<span data-ttu-id="cb061-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cb061-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cb061-105">指定与会者的响应的状态。</span><span class="sxs-lookup"><span data-stu-id="cb061-105">Specifies the response status of an attendee.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cb061-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="cb061-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cb061-107">dispidResponseStatus</span><span class="sxs-lookup"><span data-stu-id="cb061-107">dispidResponseStatus</span></span>  <br/> |
|<span data-ttu-id="cb061-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="cb061-108">Property set:</span></span>  <br/> |<span data-ttu-id="cb061-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="cb061-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="cb061-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="cb061-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="cb061-111">0x00008218</span><span class="sxs-lookup"><span data-stu-id="cb061-111">0x00008218</span></span>  <br/> |
|<span data-ttu-id="cb061-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cb061-112">Data type:</span></span>  <br/> |<span data-ttu-id="cb061-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="cb061-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="cb061-114">区域：</span><span class="sxs-lookup"><span data-stu-id="cb061-114">Area:</span></span>  <br/> |<span data-ttu-id="cb061-115">会议</span><span class="sxs-lookup"><span data-stu-id="cb061-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cb061-116">说明</span><span class="sxs-lookup"><span data-stu-id="cb061-116">Remarks</span></span>

<span data-ttu-id="cb061-117">响应状态必须是下表中的值之一。</span><span class="sxs-lookup"><span data-stu-id="cb061-117">The response status must be one of the values in the table below.</span></span>
  
|<span data-ttu-id="cb061-118">**响应状态**</span><span class="sxs-lookup"><span data-stu-id="cb061-118">**Response status**</span></span>|<span data-ttu-id="cb061-119">**值**</span><span class="sxs-lookup"><span data-stu-id="cb061-119">**Value**</span></span>|<span data-ttu-id="cb061-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="cb061-120">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cb061-121">respNone</span><span class="sxs-lookup"><span data-stu-id="cb061-121">respNone</span></span>  <br/> |<span data-ttu-id="cb061-122">0x00000000</span><span class="sxs-lookup"><span data-stu-id="cb061-122">0x00000000</span></span>  <br/> |<span data-ttu-id="cb061-123">没有响应，则需要此对象。</span><span class="sxs-lookup"><span data-stu-id="cb061-123">No response is required for this object.</span></span> <span data-ttu-id="cb061-124">这是约会对象和会议响应对象的情况。</span><span class="sxs-lookup"><span data-stu-id="cb061-124">This is the case for appointment objects and meeting response objects.</span></span>  <br/> |
|<span data-ttu-id="cb061-125">respOrganized</span><span class="sxs-lookup"><span data-stu-id="cb061-125">respOrganized</span></span>  <br/> |<span data-ttu-id="cb061-126">0x00000001</span><span class="sxs-lookup"><span data-stu-id="cb061-126">0x00000001</span></span>  <br/> |<span data-ttu-id="cb061-127">此会议所属的组织者。</span><span class="sxs-lookup"><span data-stu-id="cb061-127">This meeting belongs to the organizer.</span></span>  <br/> |
|<span data-ttu-id="cb061-128">respTentative</span><span class="sxs-lookup"><span data-stu-id="cb061-128">respTentative</span></span>  <br/> |<span data-ttu-id="cb061-129">0x00000002</span><span class="sxs-lookup"><span data-stu-id="cb061-129">0x00000002</span></span>  <br/> |<span data-ttu-id="cb061-130">在与会者的会议此值指示与会者已暂时接受会议请求。</span><span class="sxs-lookup"><span data-stu-id="cb061-130">This value on the attendee's meeting indicates that the attendee has tentatively accepted the meeting request.</span></span>  <br/> |
|<span data-ttu-id="cb061-131">respAccepted</span><span class="sxs-lookup"><span data-stu-id="cb061-131">respAccepted</span></span>  <br/> |<span data-ttu-id="cb061-132">0x00000003</span><span class="sxs-lookup"><span data-stu-id="cb061-132">0x00000003</span></span>  <br/> |<span data-ttu-id="cb061-133">与会者的会议 t 上此值指示参与者已接受会议请求。</span><span class="sxs-lookup"><span data-stu-id="cb061-133">This value on the attendee's meeting t indicates that the attendee has accepted the meeting request.</span></span>  <br/> |
|<span data-ttu-id="cb061-134">respDeclined</span><span class="sxs-lookup"><span data-stu-id="cb061-134">respDeclined</span></span>  <br/> |<span data-ttu-id="cb061-135">0x00000004</span><span class="sxs-lookup"><span data-stu-id="cb061-135">0x00000004</span></span>  <br/> |<span data-ttu-id="cb061-136">在与会者的会议此值指示参与者已拒绝会议请求。</span><span class="sxs-lookup"><span data-stu-id="cb061-136">This value on the attendee's meeting indicates that the attendee has declined the meeting request.</span></span>  <br/> |
|<span data-ttu-id="cb061-137">respNotResponded</span><span class="sxs-lookup"><span data-stu-id="cb061-137">respNotResponded</span></span>  <br/> |<span data-ttu-id="cb061-138">0x00000005</span><span class="sxs-lookup"><span data-stu-id="cb061-138">0x00000005</span></span>  <br/> |<span data-ttu-id="cb061-139">在与会者的会议此值指示参与者尚未响应。</span><span class="sxs-lookup"><span data-stu-id="cb061-139">This value on the attendee's meeting indicates the attendee has not yet responded.</span></span> <span data-ttu-id="cb061-140">此值是在会议请求、 会议更新和会议取消。</span><span class="sxs-lookup"><span data-stu-id="cb061-140">This value is on the meeting request, meeting update, and meeting cancelation.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="cb061-141">相关资源</span><span class="sxs-lookup"><span data-stu-id="cb061-141">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="cb061-142">协议规范</span><span class="sxs-lookup"><span data-stu-id="cb061-142">Protocol specifications</span></span>

<span data-ttu-id="cb061-143">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cb061-143">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cb061-144">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="cb061-144">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="cb061-145">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cb061-145">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cb061-146">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="cb061-146">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="cb061-147">头文件</span><span class="sxs-lookup"><span data-stu-id="cb061-147">Header files</span></span>

<span data-ttu-id="cb061-148">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cb061-148">Mapidefs.h</span></span>
  
> <span data-ttu-id="cb061-149">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cb061-149">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cb061-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb061-150">See also</span></span>



[<span data-ttu-id="cb061-151">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cb061-151">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cb061-152">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cb061-152">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cb061-153">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="cb061-153">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cb061-154">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cb061-154">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

