---
title: PidTagRecipientTrackStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientTrackStatus
api_type:
- COM
ms.assetid: d619b5e7-2867-44fc-9b42-123bb1bf7bde
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 074bcf7c051b78bc32caf66502747e7fb1ab6b79
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355284"
---
# <a name="pidtagrecipienttrackstatus-canonical-property"></a><span data-ttu-id="a6d4c-103">PidTagRecipientTrackStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="a6d4c-103">PidTagRecipientTrackStatus Canonical Property</span></span>

  
  
<span data-ttu-id="a6d4c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a6d4c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a6d4c-105">指示与会者返回的响应状态。</span><span class="sxs-lookup"><span data-stu-id="a6d4c-105">Indicates the response status returned by the attendee.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a6d4c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a6d4c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a6d4c-107">PR_RECIPIENT_TRACKSTATUS</span><span class="sxs-lookup"><span data-stu-id="a6d4c-107">PR_RECIPIENT_TRACKSTATUS</span></span>  <br/> |
|<span data-ttu-id="a6d4c-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="a6d4c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a6d4c-109">0x5FFF</span><span class="sxs-lookup"><span data-stu-id="a6d4c-109">0x5FFF</span></span>  <br/> |
|<span data-ttu-id="a6d4c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a6d4c-110">Data type:</span></span>  <br/> |<span data-ttu-id="a6d4c-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="a6d4c-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="a6d4c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a6d4c-112">Area:</span></span>  <br/> |<span data-ttu-id="a6d4c-113">传输收件人</span><span class="sxs-lookup"><span data-stu-id="a6d4c-113">Transport recipient</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a6d4c-114">备注</span><span class="sxs-lookup"><span data-stu-id="a6d4c-114">Remarks</span></span>

<span data-ttu-id="a6d4c-115">如果未设置此值，则必须假定为 respNone。</span><span class="sxs-lookup"><span data-stu-id="a6d4c-115">If this value is not set, it must be assumed to be respNone.</span></span> <span data-ttu-id="a6d4c-116">否则，它必须是以下项之一：</span><span class="sxs-lookup"><span data-stu-id="a6d4c-116">Otherwise, it must be one of the following:</span></span>
  
|<span data-ttu-id="a6d4c-117">**响应状态**</span><span class="sxs-lookup"><span data-stu-id="a6d4c-117">**Response status**</span></span>|<span data-ttu-id="a6d4c-118">**值**</span><span class="sxs-lookup"><span data-stu-id="a6d4c-118">**Value**</span></span>|<span data-ttu-id="a6d4c-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="a6d4c-119">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a6d4c-120">respNone</span><span class="sxs-lookup"><span data-stu-id="a6d4c-120">respNone</span></span>  <br/> |<span data-ttu-id="a6d4c-121">0x00000000</span><span class="sxs-lookup"><span data-stu-id="a6d4c-121">0x00000000</span></span>  <br/> |<span data-ttu-id="a6d4c-122">此对象不需要任何响应。</span><span class="sxs-lookup"><span data-stu-id="a6d4c-122">No response is required for this object.</span></span> <span data-ttu-id="a6d4c-123">约会对象和会议响应对象就是这种情况。</span><span class="sxs-lookup"><span data-stu-id="a6d4c-123">This is the case for appointment objects and meeting response objects.</span></span>  <br/> |
|<span data-ttu-id="a6d4c-124">respTentative</span><span class="sxs-lookup"><span data-stu-id="a6d4c-124">respTentative</span></span>  <br/> |<span data-ttu-id="a6d4c-125">0x00000002</span><span class="sxs-lookup"><span data-stu-id="a6d4c-125">0x00000002</span></span>  <br/> |<span data-ttu-id="a6d4c-126">与会者的会议对象的此值指示与会者已暂时接受会议请求对象。</span><span class="sxs-lookup"><span data-stu-id="a6d4c-126">This value on the attendee's meeting object indicates that the attendee has tentatively accepted the meeting request object.</span></span>  <br/> |
|<span data-ttu-id="a6d4c-127">respAccepted</span><span class="sxs-lookup"><span data-stu-id="a6d4c-127">respAccepted</span></span>  <br/> |<span data-ttu-id="a6d4c-128">0x00000003</span><span class="sxs-lookup"><span data-stu-id="a6d4c-128">0x00000003</span></span>  <br/> |<span data-ttu-id="a6d4c-129">与会者的会议对象的此值指示与会者已接受会议请求对象。</span><span class="sxs-lookup"><span data-stu-id="a6d4c-129">This value on the attendee's meeting object indicates that the attendee has accepted the meeting request object.</span></span>  <br/> |
|<span data-ttu-id="a6d4c-130">respDeclined</span><span class="sxs-lookup"><span data-stu-id="a6d4c-130">respDeclined</span></span>  <br/> |<span data-ttu-id="a6d4c-131">0x00000004</span><span class="sxs-lookup"><span data-stu-id="a6d4c-131">0x00000004</span></span>  <br/> |<span data-ttu-id="a6d4c-132">与会者的会议对象的此值指示与会者已拒绝会议请求对象。</span><span class="sxs-lookup"><span data-stu-id="a6d4c-132">This value on the attendee's meeting object indicates that the attendee has declined the meeting request object.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="a6d4c-133">相关资源</span><span class="sxs-lookup"><span data-stu-id="a6d4c-133">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a6d4c-134">协议规范</span><span class="sxs-lookup"><span data-stu-id="a6d4c-134">Protocol specifications</span></span>

<span data-ttu-id="a6d4c-135">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a6d4c-135">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a6d4c-136">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="a6d4c-136">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a6d4c-137">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a6d4c-137">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a6d4c-138">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="a6d4c-138">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="a6d4c-139">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a6d4c-139">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a6d4c-140">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="a6d4c-140">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a6d4c-141">头文件</span><span class="sxs-lookup"><span data-stu-id="a6d4c-141">Header files</span></span>

<span data-ttu-id="a6d4c-142">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a6d4c-142">Mapidefs.h</span></span>
  
> <span data-ttu-id="a6d4c-143">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a6d4c-143">Provides data type definitions.</span></span>
    
<span data-ttu-id="a6d4c-144">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="a6d4c-144">Mapitags.h</span></span>
  
> <span data-ttu-id="a6d4c-145">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a6d4c-145">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a6d4c-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6d4c-146">See also</span></span>



[<span data-ttu-id="a6d4c-147">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a6d4c-147">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a6d4c-148">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a6d4c-148">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a6d4c-149">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a6d4c-149">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a6d4c-150">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a6d4c-150">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

