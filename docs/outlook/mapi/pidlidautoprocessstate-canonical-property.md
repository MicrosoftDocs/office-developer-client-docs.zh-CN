---
title: PidLidAutoProcessState 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAutoProcessState
api_type:
- COM
ms.assetid: 9e724af6-5b56-4eb3-a94c-1015ebce197c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 86ef98ac7b4084de3a96210298fe0d5509d12103
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776691"
---
# <a name="pidlidautoprocessstate-canonical-property"></a><span data-ttu-id="73b0f-103">PidLidAutoProcessState 规范属性</span><span class="sxs-lookup"><span data-stu-id="73b0f-103">PidLidAutoProcessState Canonical Property</span></span>

  
  
<span data-ttu-id="73b0f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="73b0f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="73b0f-105">指定的电子邮件的自动处理中所使用的选项。</span><span class="sxs-lookup"><span data-stu-id="73b0f-105">Specifies the options that are used in automatic processing of email messages.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="73b0f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="73b0f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="73b0f-107">dispidSniffState</span><span class="sxs-lookup"><span data-stu-id="73b0f-107">dispidSniffState</span></span>  <br/> |
|<span data-ttu-id="73b0f-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="73b0f-108">Property set:</span></span>  <br/> |<span data-ttu-id="73b0f-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="73b0f-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="73b0f-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="73b0f-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="73b0f-111">0x0000851A</span><span class="sxs-lookup"><span data-stu-id="73b0f-111">0x0000851A</span></span>  <br/> |
|<span data-ttu-id="73b0f-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="73b0f-112">Data type:</span></span>  <br/> |<span data-ttu-id="73b0f-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="73b0f-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="73b0f-114">区域：</span><span class="sxs-lookup"><span data-stu-id="73b0f-114">Area:</span></span>  <br/> |<span data-ttu-id="73b0f-115">常规消息</span><span class="sxs-lookup"><span data-stu-id="73b0f-115">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="73b0f-116">说明</span><span class="sxs-lookup"><span data-stu-id="73b0f-116">Remarks</span></span>

<span data-ttu-id="73b0f-117">该属性可能不存在，在这种情况下使用"0x00000000"的默认值。</span><span class="sxs-lookup"><span data-stu-id="73b0f-117">The property may be absent, in which case the default value of "0x00000000" is used.</span></span> <span data-ttu-id="73b0f-118">如果设置，此属性必须设置为下表中的值之一。</span><span class="sxs-lookup"><span data-stu-id="73b0f-118">If set, this property must be set to one of the values in the following table.</span></span>
  
|<span data-ttu-id="73b0f-119">**值**</span><span class="sxs-lookup"><span data-stu-id="73b0f-119">**Value**</span></span>|<span data-ttu-id="73b0f-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="73b0f-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="73b0f-121">0x00000000</span><span class="sxs-lookup"><span data-stu-id="73b0f-121">0x00000000</span></span>  <br/> |<span data-ttu-id="73b0f-122">不自动处理邮件。</span><span class="sxs-lookup"><span data-stu-id="73b0f-122">Do not automatically process the message.</span></span>  <br/> |
|<span data-ttu-id="73b0f-123">0x00000001</span><span class="sxs-lookup"><span data-stu-id="73b0f-123">0x00000001</span></span>  <br/> |<span data-ttu-id="73b0f-124">自动处理邮件，或打开邮件时。</span><span class="sxs-lookup"><span data-stu-id="73b0f-124">Process the message automatically or when the message is opened.</span></span>  <br/> |
|<span data-ttu-id="73b0f-125">0x00000002</span><span class="sxs-lookup"><span data-stu-id="73b0f-125">0x00000002</span></span>  <br/> |<span data-ttu-id="73b0f-126">仅当打开邮件时处理该消息。</span><span class="sxs-lookup"><span data-stu-id="73b0f-126">Process the message only when the message is opened.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="73b0f-127">相关资源</span><span class="sxs-lookup"><span data-stu-id="73b0f-127">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="73b0f-128">协议规范</span><span class="sxs-lookup"><span data-stu-id="73b0f-128">Protocol specifications</span></span>

<span data-ttu-id="73b0f-129">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="73b0f-129">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="73b0f-130">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="73b0f-130">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="73b0f-131">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="73b0f-131">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="73b0f-132">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="73b0f-132">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="73b0f-133">头文件</span><span class="sxs-lookup"><span data-stu-id="73b0f-133">Header files</span></span>

<span data-ttu-id="73b0f-134">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="73b0f-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="73b0f-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="73b0f-135">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="73b0f-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73b0f-136">See also</span></span>



[<span data-ttu-id="73b0f-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="73b0f-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="73b0f-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="73b0f-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="73b0f-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="73b0f-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="73b0f-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="73b0f-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

