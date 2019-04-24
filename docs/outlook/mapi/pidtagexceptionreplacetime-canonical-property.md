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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f255b91cbd428a2ceaa51140519b02d3f8a3b1ff
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316385"
---
# <a name="pidtagexceptionreplacetime-canonical-property"></a><span data-ttu-id="0576b-103">PidTagExceptionReplaceTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="0576b-103">PidTagExceptionReplaceTime Canonical Property</span></span>

  
  
<span data-ttu-id="0576b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0576b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0576b-105">指示定期模式中的实例发生时的原始日期和时间 (如果它不是异常)。</span><span class="sxs-lookup"><span data-stu-id="0576b-105">Indicates the original date and time when the instance in the recurrence pattern would have occurred if it were not an exception.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0576b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0576b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0576b-107">PR_EXCEPTION_REPLACETIME</span><span class="sxs-lookup"><span data-stu-id="0576b-107">PR_EXCEPTION_REPLACETIME</span></span>  <br/> |
|<span data-ttu-id="0576b-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="0576b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0576b-109">0x7FF9</span><span class="sxs-lookup"><span data-stu-id="0576b-109">0x7FF9</span></span>  <br/> |
|<span data-ttu-id="0576b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0576b-110">Data type:</span></span>  <br/> |<span data-ttu-id="0576b-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="0576b-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="0576b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0576b-112">Area:</span></span>  <br/> |<span data-ttu-id="0576b-113">邮件类定义的非传输</span><span class="sxs-lookup"><span data-stu-id="0576b-113">Message class-defined non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0576b-114">注解</span><span class="sxs-lookup"><span data-stu-id="0576b-114">Remarks</span></span>

<span data-ttu-id="0576b-115">此值必须以协调通用时间 (UTC) 指定。</span><span class="sxs-lookup"><span data-stu-id="0576b-115">This value must be specified in Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="0576b-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="0576b-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0576b-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="0576b-117">Protocol specifications</span></span>

<span data-ttu-id="0576b-118">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0576b-118">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0576b-119">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="0576b-119">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0576b-120">头文件</span><span class="sxs-lookup"><span data-stu-id="0576b-120">Header files</span></span>

<span data-ttu-id="0576b-121">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="0576b-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="0576b-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0576b-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="0576b-123">Mapitags</span><span class="sxs-lookup"><span data-stu-id="0576b-123">Mapitags.h</span></span>
  
> <span data-ttu-id="0576b-124">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0576b-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0576b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0576b-125">See also</span></span>



[<span data-ttu-id="0576b-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0576b-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0576b-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0576b-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0576b-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0576b-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0576b-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0576b-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

