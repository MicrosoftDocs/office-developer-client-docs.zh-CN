---
title: PidTagDeferredSendUnits 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDeferredSendUnits
api_type:
- HeaderDef
ms.assetid: 2386be9f-18c9-4949-a2aa-efc8e212801c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: becc076efe0f4f805eb2a8db071b70ad731ee256
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359904"
---
# <a name="pidtagdeferredsendunits-canonical-property"></a><span data-ttu-id="131aa-103">PidTagDeferredSendUnits 规范属性</span><span class="sxs-lookup"><span data-stu-id="131aa-103">PidTagDeferredSendUnits Canonical Property</span></span>

  
  
<span data-ttu-id="131aa-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="131aa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="131aa-105">指定应乘以[PidTagDeferredSendNumber PR_DEFERRED_SEND_NUMBER (PidTagSendNumber](pidtagdeferredsendnumber-canonical-property.md)) 的时间单位。 </span><span class="sxs-lookup"><span data-stu-id="131aa-105">Specifies the unit of time by which the **PR_DEFERRED_SEND_NUMBER** ([PidTagDeferredSendNumber](pidtagdeferredsendnumber-canonical-property.md)) property value should be multiplied.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="131aa-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="131aa-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="131aa-107">PR_DEFERRED_SEND_UNITS</span><span class="sxs-lookup"><span data-stu-id="131aa-107">PR_DEFERRED_SEND_UNITS</span></span>  <br/> |
|<span data-ttu-id="131aa-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="131aa-108">Identifier:</span></span>  <br/> |<span data-ttu-id="131aa-109">0x3FEC</span><span class="sxs-lookup"><span data-stu-id="131aa-109">0x3FEC</span></span>  <br/> |
|<span data-ttu-id="131aa-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="131aa-110">Data type:</span></span>  <br/> |<span data-ttu-id="131aa-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="131aa-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="131aa-112">区域：</span><span class="sxs-lookup"><span data-stu-id="131aa-112">Area:</span></span>  <br/> |<span data-ttu-id="131aa-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="131aa-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="131aa-114">备注</span><span class="sxs-lookup"><span data-stu-id="131aa-114">Remarks</span></span>

<span data-ttu-id="131aa-115">如果设置此属性，则此属性必须具有下列值之一：</span><span class="sxs-lookup"><span data-stu-id="131aa-115">If set, this property must have one of the following values:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="131aa-116">**PidTagDeferredSendUnits**</span><span class="sxs-lookup"><span data-stu-id="131aa-116">**PidTagDeferredSendUnits**</span></span> <br/> |<span data-ttu-id="131aa-117">说明</span><span class="sxs-lookup"><span data-stu-id="131aa-117">Description</span></span>  <br/> |
|<span data-ttu-id="131aa-118">0</span><span class="sxs-lookup"><span data-stu-id="131aa-118">0</span></span>  <br/> |<span data-ttu-id="131aa-119">分钟，例如 60 秒</span><span class="sxs-lookup"><span data-stu-id="131aa-119">Minutes, for example 60 seconds</span></span>  <br/> |
|<span data-ttu-id="131aa-120">1</span><span class="sxs-lookup"><span data-stu-id="131aa-120">1</span></span>  <br/> |<span data-ttu-id="131aa-121">小时，例如 60x60 秒</span><span class="sxs-lookup"><span data-stu-id="131aa-121">Hours, for example 60x60 seconds</span></span>  <br/> |
|<span data-ttu-id="131aa-122">2</span><span class="sxs-lookup"><span data-stu-id="131aa-122">2</span></span>  <br/> |<span data-ttu-id="131aa-123">天，例如 24x60x60 秒</span><span class="sxs-lookup"><span data-stu-id="131aa-123">Day, for example 24x60x60 seconds</span></span>  <br/> |
|<span data-ttu-id="131aa-124">3</span><span class="sxs-lookup"><span data-stu-id="131aa-124">3</span></span>  <br/> |<span data-ttu-id="131aa-125">周，例如 7x24x60x60 秒</span><span class="sxs-lookup"><span data-stu-id="131aa-125">Week, for example 7x24x60x60 seconds</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="131aa-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="131aa-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="131aa-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="131aa-127">Protocol specifications</span></span>

<span data-ttu-id="131aa-128">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="131aa-128">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="131aa-129">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="131aa-129">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="131aa-130">头文件</span><span class="sxs-lookup"><span data-stu-id="131aa-130">Header files</span></span>

<span data-ttu-id="131aa-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="131aa-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="131aa-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="131aa-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="131aa-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="131aa-133">Mapitags.h</span></span>
  
> <span data-ttu-id="131aa-134">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="131aa-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="131aa-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="131aa-135">See also</span></span>



[<span data-ttu-id="131aa-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="131aa-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="131aa-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="131aa-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="131aa-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="131aa-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="131aa-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="131aa-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

