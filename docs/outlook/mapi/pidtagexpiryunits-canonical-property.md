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
ms.openlocfilehash: 8e8deb67990ce25b10a3b0fc1d373f635f958013
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316406"
---
# <a name="pidtagexpiryunits-canonical-property"></a><span data-ttu-id="ef69e-103">PidTagExpiryUnits 规范属性</span><span class="sxs-lookup"><span data-stu-id="ef69e-103">PidTagExpiryUnits Canonical Property</span></span>

  
  
<span data-ttu-id="ef69e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ef69e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ef69e-105">描述**PR_EXPIRY_NUMBER** ([PidTagExpiryNumber](pidtagexpirynumber-canonical-property.md)) 属性相乘的时间单位。</span><span class="sxs-lookup"><span data-stu-id="ef69e-105">Describes the unit of time when the **PR_EXPIRY_NUMBER** ([PidTagExpiryNumber](pidtagexpirynumber-canonical-property.md)) property multiplies.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ef69e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ef69e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ef69e-107">PR_EXPIRY_UNITS</span><span class="sxs-lookup"><span data-stu-id="ef69e-107">PR_EXPIRY_UNITS</span></span>  <br/> |
|<span data-ttu-id="ef69e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ef69e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ef69e-109">0x3FEE</span><span class="sxs-lookup"><span data-stu-id="ef69e-109">0x3FEE</span></span>  <br/> |
|<span data-ttu-id="ef69e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ef69e-110">Data type:</span></span>  <br/> |<span data-ttu-id="ef69e-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="ef69e-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="ef69e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ef69e-112">Area:</span></span>  <br/> |<span data-ttu-id="ef69e-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="ef69e-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ef69e-114">注解</span><span class="sxs-lookup"><span data-stu-id="ef69e-114">Remarks</span></span>

<span data-ttu-id="ef69e-115">如果设置此属性, 则必须为下列值之一:</span><span class="sxs-lookup"><span data-stu-id="ef69e-115">This property, if set, must be one of the following values:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ef69e-116">PidTagExpiryUnits</span><span class="sxs-lookup"><span data-stu-id="ef69e-116">PidTagExpiryUnits</span></span>  <br/> |<span data-ttu-id="ef69e-117">Description (TimeOf)</span><span class="sxs-lookup"><span data-stu-id="ef69e-117">Description (TimeOf)</span></span>  <br/> |
|<span data-ttu-id="ef69e-118">0x00000000</span><span class="sxs-lookup"><span data-stu-id="ef69e-118">0x00000000</span></span>  <br/> |<span data-ttu-id="ef69e-119">分钟, 例如, 60 秒</span><span class="sxs-lookup"><span data-stu-id="ef69e-119">Minutes, for example 60 seconds</span></span>  <br/> |
|<span data-ttu-id="ef69e-120">0x00000001</span><span class="sxs-lookup"><span data-stu-id="ef69e-120">0x00000001</span></span>  <br/> |<span data-ttu-id="ef69e-121">小时数, 例如60x60 秒</span><span class="sxs-lookup"><span data-stu-id="ef69e-121">Hours, for example 60x60 seconds</span></span>  <br/> |
|<span data-ttu-id="ef69e-122">0x00000002</span><span class="sxs-lookup"><span data-stu-id="ef69e-122">0x00000002</span></span>  <br/> |<span data-ttu-id="ef69e-123">天, 例如24x60x60 秒</span><span class="sxs-lookup"><span data-stu-id="ef69e-123">Day, for example 24x60x60 seconds</span></span>  <br/> |
|<span data-ttu-id="ef69e-124">0x00000003</span><span class="sxs-lookup"><span data-stu-id="ef69e-124">0x00000003</span></span>  <br/> |<span data-ttu-id="ef69e-125">周, 例如7x24x60x60 秒</span><span class="sxs-lookup"><span data-stu-id="ef69e-125">Week, for example 7x24x60x60 seconds</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="ef69e-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="ef69e-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ef69e-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="ef69e-127">Protocol specifications</span></span>

<span data-ttu-id="ef69e-128">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ef69e-128">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ef69e-129">指定允许用于电子邮件对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="ef69e-129">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ef69e-130">头文件</span><span class="sxs-lookup"><span data-stu-id="ef69e-130">Header files</span></span>

<span data-ttu-id="ef69e-131">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="ef69e-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="ef69e-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ef69e-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="ef69e-133">Mapitags</span><span class="sxs-lookup"><span data-stu-id="ef69e-133">Mapitags.h</span></span>
  
> <span data-ttu-id="ef69e-134">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ef69e-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ef69e-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef69e-135">See also</span></span>



[<span data-ttu-id="ef69e-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ef69e-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ef69e-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ef69e-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ef69e-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ef69e-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ef69e-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ef69e-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

