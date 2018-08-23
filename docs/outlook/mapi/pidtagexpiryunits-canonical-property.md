---
title: PidTagExpiryUnits 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagExpiryUnits
api_type:
- HeaderDef
ms.assetid: f6a1ca22-cf4c-4e59-8846-6bd937fa8f6e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c6aab4228af0f584d96a2a8cc02c5f36e05a01e8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569601"
---
# <a name="pidtagexpiryunits-canonical-property"></a><span data-ttu-id="dde0d-103">PidTagExpiryUnits 规范属性</span><span class="sxs-lookup"><span data-stu-id="dde0d-103">PidTagExpiryUnits Canonical Property</span></span>

  
  
<span data-ttu-id="dde0d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dde0d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dde0d-105">介绍当**PR_EXPIRY_NUMBER** ([PidTagExpiryNumber](pidtagexpirynumber-canonical-property.md)) 属性相乘的时间单位。</span><span class="sxs-lookup"><span data-stu-id="dde0d-105">Describes the unit of time when the **PR_EXPIRY_NUMBER** ([PidTagExpiryNumber](pidtagexpirynumber-canonical-property.md)) property multiplies.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dde0d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="dde0d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="dde0d-107">PR_EXPIRY_UNITS</span><span class="sxs-lookup"><span data-stu-id="dde0d-107">PR_EXPIRY_UNITS</span></span>  <br/> |
|<span data-ttu-id="dde0d-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="dde0d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="dde0d-109">0x3FEE</span><span class="sxs-lookup"><span data-stu-id="dde0d-109">0x3FEE</span></span>  <br/> |
|<span data-ttu-id="dde0d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="dde0d-110">Data type:</span></span>  <br/> |<span data-ttu-id="dde0d-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="dde0d-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="dde0d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="dde0d-112">Area:</span></span>  <br/> |<span data-ttu-id="dde0d-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="dde0d-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dde0d-114">注解</span><span class="sxs-lookup"><span data-stu-id="dde0d-114">Remarks</span></span>

<span data-ttu-id="dde0d-115">此属性，如果设置，必须是下列值之一：</span><span class="sxs-lookup"><span data-stu-id="dde0d-115">This property, if set, must be one of the following values:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dde0d-116">PidTagExpiryUnits</span><span class="sxs-lookup"><span data-stu-id="dde0d-116">PidTagExpiryUnits</span></span>  <br/> |<span data-ttu-id="dde0d-117">说明 （时间）</span><span class="sxs-lookup"><span data-stu-id="dde0d-117">Description (TimeOf)</span></span>  <br/> |
|<span data-ttu-id="dde0d-118">0x00000000</span><span class="sxs-lookup"><span data-stu-id="dde0d-118">0x00000000</span></span>  <br/> |<span data-ttu-id="dde0d-119">分钟时间，例如 60 秒</span><span class="sxs-lookup"><span data-stu-id="dde0d-119">Minutes, for example 60 seconds</span></span>  <br/> |
|<span data-ttu-id="dde0d-120">0x00000001</span><span class="sxs-lookup"><span data-stu-id="dde0d-120">0x00000001</span></span>  <br/> |<span data-ttu-id="dde0d-121">小时，例如 60 x 60 秒</span><span class="sxs-lookup"><span data-stu-id="dde0d-121">Hours, for example 60x60 seconds</span></span>  <br/> |
|<span data-ttu-id="dde0d-122">0x00000002</span><span class="sxs-lookup"><span data-stu-id="dde0d-122">0x00000002</span></span>  <br/> |<span data-ttu-id="dde0d-123">天，例如 24 x 60 x 60 秒</span><span class="sxs-lookup"><span data-stu-id="dde0d-123">Day, for example 24x60x60 seconds</span></span>  <br/> |
|<span data-ttu-id="dde0d-124">0x00000003</span><span class="sxs-lookup"><span data-stu-id="dde0d-124">0x00000003</span></span>  <br/> |<span data-ttu-id="dde0d-125">周，例如 7x24x60x60 秒</span><span class="sxs-lookup"><span data-stu-id="dde0d-125">Week, for example 7x24x60x60 seconds</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="dde0d-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="dde0d-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="dde0d-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="dde0d-127">Protocol specifications</span></span>

<span data-ttu-id="dde0d-128">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dde0d-128">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dde0d-129">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="dde0d-129">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="dde0d-130">头文件</span><span class="sxs-lookup"><span data-stu-id="dde0d-130">Header files</span></span>

<span data-ttu-id="dde0d-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="dde0d-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="dde0d-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="dde0d-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="dde0d-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="dde0d-133">Mapitags.h</span></span>
  
> <span data-ttu-id="dde0d-134">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="dde0d-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dde0d-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dde0d-135">See also</span></span>



[<span data-ttu-id="dde0d-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="dde0d-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="dde0d-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="dde0d-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="dde0d-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="dde0d-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="dde0d-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="dde0d-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

