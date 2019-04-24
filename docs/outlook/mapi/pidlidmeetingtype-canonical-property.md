---
title: PidLidMeetingType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidMeetingType
api_type:
- COM
ms.assetid: 290b290c-7836-4a7e-bf1a-8d0225a07e56
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d2b00c67984d090274a17028ee74e46bee482e2b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331575"
---
# <a name="pidlidmeetingtype-canonical-property"></a><span data-ttu-id="48680-103">PidLidMeetingType 规范属性</span><span class="sxs-lookup"><span data-stu-id="48680-103">PidLidMeetingType Canonical Property</span></span>

  
  
<span data-ttu-id="48680-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="48680-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="48680-105">指示会议请求或会议更新的类型。</span><span class="sxs-lookup"><span data-stu-id="48680-105">Indicates the type of meeting request or meeting update.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="48680-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="48680-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="48680-107">dispidMeetingType</span><span class="sxs-lookup"><span data-stu-id="48680-107">dispidMeetingType</span></span>  <br/> |
|<span data-ttu-id="48680-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="48680-108">Property set:</span></span>  <br/> |<span data-ttu-id="48680-109">PSETID_Meeting</span><span class="sxs-lookup"><span data-stu-id="48680-109">PSETID_Meeting</span></span>  <br/> |
|<span data-ttu-id="48680-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="48680-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="48680-111">0x00000026</span><span class="sxs-lookup"><span data-stu-id="48680-111">0x00000026</span></span>  <br/> |
|<span data-ttu-id="48680-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="48680-112">Data type:</span></span>  <br/> |<span data-ttu-id="48680-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="48680-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="48680-114">区域：</span><span class="sxs-lookup"><span data-stu-id="48680-114">Area:</span></span>  <br/> |<span data-ttu-id="48680-115">会议</span><span class="sxs-lookup"><span data-stu-id="48680-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="48680-116">注解</span><span class="sxs-lookup"><span data-stu-id="48680-116">Remarks</span></span>

<span data-ttu-id="48680-117">此属性的值必须设置为以下值之一:</span><span class="sxs-lookup"><span data-stu-id="48680-117">The value of this property must be set to one of the following:</span></span>
  
|<span data-ttu-id="48680-118">**属性**</span><span class="sxs-lookup"><span data-stu-id="48680-118">**Property**</span></span>|<span data-ttu-id="48680-119">**Value**</span><span class="sxs-lookup"><span data-stu-id="48680-119">**Value**</span></span>|<span data-ttu-id="48680-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="48680-120">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="48680-121">mtgEmpty</span><span class="sxs-lookup"><span data-stu-id="48680-121">mtgEmpty</span></span>  <br/> |<span data-ttu-id="48680-122">0x00000000</span><span class="sxs-lookup"><span data-stu-id="48680-122">0x00000000</span></span>  <br/> |<span data-ttu-id="48680-123">发生.</span><span class="sxs-lookup"><span data-stu-id="48680-123">Unspecified.</span></span>  <br/> |
|<span data-ttu-id="48680-124">mtgRequest</span><span class="sxs-lookup"><span data-stu-id="48680-124">mtgRequest</span></span>  <br/> |<span data-ttu-id="48680-125">0x00000001</span><span class="sxs-lookup"><span data-stu-id="48680-125">0x00000001</span></span>  <br/> |<span data-ttu-id="48680-126">初始会议请求。</span><span class="sxs-lookup"><span data-stu-id="48680-126">Initial meeting request.</span></span>  <br/> |
|<span data-ttu-id="48680-127">mtgFull</span><span class="sxs-lookup"><span data-stu-id="48680-127">mtgFull</span></span>  <br/> |<span data-ttu-id="48680-128">0x00010000</span><span class="sxs-lookup"><span data-stu-id="48680-128">0x00010000</span></span>  <br/> |<span data-ttu-id="48680-129">完全更新。</span><span class="sxs-lookup"><span data-stu-id="48680-129">Full update.</span></span>  <br/> |
|<span data-ttu-id="48680-130">mtgInfo</span><span class="sxs-lookup"><span data-stu-id="48680-130">mtgInfo</span></span>  <br/> |<span data-ttu-id="48680-131">0x00020000</span><span class="sxs-lookup"><span data-stu-id="48680-131">0x00020000</span></span>  <br/> |<span data-ttu-id="48680-132">信息更新。</span><span class="sxs-lookup"><span data-stu-id="48680-132">Informational update.</span></span>  <br/> |
|<span data-ttu-id="48680-133">mtgOutOfDate</span><span class="sxs-lookup"><span data-stu-id="48680-133">mtgOutOfDate</span></span>  <br/> |<span data-ttu-id="48680-134">0x00080000</span><span class="sxs-lookup"><span data-stu-id="48680-134">0x00080000</span></span>  <br/> |<span data-ttu-id="48680-135">在此之后收到一个更新的会议请求或会议更新。</span><span class="sxs-lookup"><span data-stu-id="48680-135">A newer meeting request or meeting update was received after this one.</span></span>  <br/> |
|<span data-ttu-id="48680-136">mtgDelegatorCopy</span><span class="sxs-lookup"><span data-stu-id="48680-136">mtgDelegatorCopy</span></span>  <br/> |<span data-ttu-id="48680-137">0x00100000</span><span class="sxs-lookup"><span data-stu-id="48680-137">0x00100000</span></span>  <br/> |<span data-ttu-id="48680-138">这是在代理人处理与会议相关的对象时在代理者的副本上设置的。</span><span class="sxs-lookup"><span data-stu-id="48680-138">This is set on the delegator's copy when a delegate handles meeting-related objects.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="48680-139">相关资源</span><span class="sxs-lookup"><span data-stu-id="48680-139">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="48680-140">协议规范</span><span class="sxs-lookup"><span data-stu-id="48680-140">Protocol specifications</span></span>

<span data-ttu-id="48680-141">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="48680-141">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="48680-142">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="48680-142">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="48680-143">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="48680-143">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="48680-144">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="48680-144">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="48680-145">头文件</span><span class="sxs-lookup"><span data-stu-id="48680-145">Header files</span></span>

<span data-ttu-id="48680-146">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="48680-146">Mapidefs.h</span></span>
  
> <span data-ttu-id="48680-147">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="48680-147">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="48680-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48680-148">See also</span></span>



[<span data-ttu-id="48680-149">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="48680-149">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="48680-150">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="48680-150">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="48680-151">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="48680-151">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="48680-152">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="48680-152">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

