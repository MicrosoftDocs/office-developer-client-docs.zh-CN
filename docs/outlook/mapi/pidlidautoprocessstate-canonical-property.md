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
ms.openlocfilehash: 0918c15d87219c1ee20b177ae21e718e0289cf04
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397616"
---
# <a name="pidlidautoprocessstate-canonical-property"></a><span data-ttu-id="b17d3-103">PidLidAutoProcessState 规范属性</span><span class="sxs-lookup"><span data-stu-id="b17d3-103">PidLidAutoProcessState Canonical Property</span></span>

  
  
<span data-ttu-id="b17d3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b17d3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b17d3-105">指定的电子邮件的自动处理中所使用的选项。</span><span class="sxs-lookup"><span data-stu-id="b17d3-105">Specifies the options that are used in automatic processing of email messages.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b17d3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b17d3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b17d3-107">dispidSniffState</span><span class="sxs-lookup"><span data-stu-id="b17d3-107">dispidSniffState</span></span>  <br/> |
|<span data-ttu-id="b17d3-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="b17d3-108">Property set:</span></span>  <br/> |<span data-ttu-id="b17d3-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="b17d3-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="b17d3-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="b17d3-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="b17d3-111">0x0000851A</span><span class="sxs-lookup"><span data-stu-id="b17d3-111">0x0000851A</span></span>  <br/> |
|<span data-ttu-id="b17d3-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b17d3-112">Data type:</span></span>  <br/> |<span data-ttu-id="b17d3-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="b17d3-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="b17d3-114">区域：</span><span class="sxs-lookup"><span data-stu-id="b17d3-114">Area:</span></span>  <br/> |<span data-ttu-id="b17d3-115">常规消息</span><span class="sxs-lookup"><span data-stu-id="b17d3-115">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b17d3-116">说明</span><span class="sxs-lookup"><span data-stu-id="b17d3-116">Remarks</span></span>

<span data-ttu-id="b17d3-117">该属性可能不存在，在这种情况下使用"0x00000000"的默认值。</span><span class="sxs-lookup"><span data-stu-id="b17d3-117">The property may be absent, in which case the default value of "0x00000000" is used.</span></span> <span data-ttu-id="b17d3-118">如果设置，此属性必须设置为下表中的值之一。</span><span class="sxs-lookup"><span data-stu-id="b17d3-118">If set, this property must be set to one of the values in the following table.</span></span>
  
|<span data-ttu-id="b17d3-119">**值**</span><span class="sxs-lookup"><span data-stu-id="b17d3-119">**Value**</span></span>|<span data-ttu-id="b17d3-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="b17d3-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b17d3-121">0x00000000</span><span class="sxs-lookup"><span data-stu-id="b17d3-121">0x00000000</span></span>  <br/> |<span data-ttu-id="b17d3-122">不自动处理邮件。</span><span class="sxs-lookup"><span data-stu-id="b17d3-122">Do not automatically process the message.</span></span>  <br/> |
|<span data-ttu-id="b17d3-123">0x00000001</span><span class="sxs-lookup"><span data-stu-id="b17d3-123">0x00000001</span></span>  <br/> |<span data-ttu-id="b17d3-124">自动处理邮件，或打开邮件时。</span><span class="sxs-lookup"><span data-stu-id="b17d3-124">Process the message automatically or when the message is opened.</span></span>  <br/> |
|<span data-ttu-id="b17d3-125">0x00000002</span><span class="sxs-lookup"><span data-stu-id="b17d3-125">0x00000002</span></span>  <br/> |<span data-ttu-id="b17d3-126">仅当打开邮件时处理该消息。</span><span class="sxs-lookup"><span data-stu-id="b17d3-126">Process the message only when the message is opened.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="b17d3-127">相关资源</span><span class="sxs-lookup"><span data-stu-id="b17d3-127">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b17d3-128">协议规范</span><span class="sxs-lookup"><span data-stu-id="b17d3-128">Protocol specifications</span></span>

<span data-ttu-id="b17d3-129">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b17d3-129">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b17d3-130">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b17d3-130">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b17d3-131">[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b17d3-131">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b17d3-132">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="b17d3-132">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b17d3-133">头文件</span><span class="sxs-lookup"><span data-stu-id="b17d3-133">Header files</span></span>

<span data-ttu-id="b17d3-134">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b17d3-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="b17d3-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b17d3-135">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b17d3-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b17d3-136">See also</span></span>



[<span data-ttu-id="b17d3-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b17d3-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b17d3-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b17d3-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b17d3-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b17d3-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b17d3-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b17d3-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

