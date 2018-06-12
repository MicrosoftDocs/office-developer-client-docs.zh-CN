---
title: PidTagExceptionReplaceTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagExceptionReplaceTime
api_type:
- HeaderDef
ms.assetid: bd4d1311-15e4-4275-a967-c6d11d2e48d2
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 506c4e89bda617ef307a64c266416c0538090ab0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777592"
---
# <a name="pidtagexceptionreplacetime-canonical-property"></a><span data-ttu-id="1f765-103">PidTagExceptionReplaceTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="1f765-103">PidTagExceptionReplaceTime Canonical Property</span></span>

  
  
<span data-ttu-id="1f765-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1f765-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1f765-105">指示原始日期和时间，如果未异常时应出现定期模式中的实例。</span><span class="sxs-lookup"><span data-stu-id="1f765-105">Indicates the original date and time when the instance in the recurrence pattern would have occurred if it were not an exception.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1f765-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="1f765-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1f765-107">PR_EXCEPTION_REPLACETIME</span><span class="sxs-lookup"><span data-stu-id="1f765-107">PR_EXCEPTION_REPLACETIME</span></span>  <br/> |
|<span data-ttu-id="1f765-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="1f765-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1f765-109">0x7FF9</span><span class="sxs-lookup"><span data-stu-id="1f765-109">0x7FF9</span></span>  <br/> |
|<span data-ttu-id="1f765-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1f765-110">Data type:</span></span>  <br/> |<span data-ttu-id="1f765-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="1f765-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="1f765-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1f765-112">Area:</span></span>  <br/> |<span data-ttu-id="1f765-113">类定义消息非可传送</span><span class="sxs-lookup"><span data-stu-id="1f765-113">Message class-defined non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1f765-114">备注</span><span class="sxs-lookup"><span data-stu-id="1f765-114">Remarks</span></span>

<span data-ttu-id="1f765-115">以协调世界时 (UTC)，必须指定此值。</span><span class="sxs-lookup"><span data-stu-id="1f765-115">This value must be specified in Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="1f765-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="1f765-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1f765-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="1f765-117">Protocol specifications</span></span>

<span data-ttu-id="1f765-118">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1f765-118">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1f765-119">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="1f765-119">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1f765-120">头文件</span><span class="sxs-lookup"><span data-stu-id="1f765-120">Header files</span></span>

<span data-ttu-id="1f765-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1f765-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="1f765-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1f765-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="1f765-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="1f765-123">Mapitags.h</span></span>
  
> <span data-ttu-id="1f765-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1f765-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1f765-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f765-125">See also</span></span>



[<span data-ttu-id="1f765-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1f765-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1f765-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1f765-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1f765-128">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1f765-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1f765-129">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1f765-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

