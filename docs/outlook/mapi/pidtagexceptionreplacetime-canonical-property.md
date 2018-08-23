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
ms.openlocfilehash: 20893f7c3d64698f70ae26c09c2d7ddc64ce3f9d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569930"
---
# <a name="pidtagexceptionreplacetime-canonical-property"></a><span data-ttu-id="5fabe-103">PidTagExceptionReplaceTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="5fabe-103">PidTagExceptionReplaceTime Canonical Property</span></span>

  
  
<span data-ttu-id="5fabe-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5fabe-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5fabe-105">指示原始日期和时间，如果未异常时应出现定期模式中的实例。</span><span class="sxs-lookup"><span data-stu-id="5fabe-105">Indicates the original date and time when the instance in the recurrence pattern would have occurred if it were not an exception.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5fabe-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5fabe-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5fabe-107">PR_EXCEPTION_REPLACETIME</span><span class="sxs-lookup"><span data-stu-id="5fabe-107">PR_EXCEPTION_REPLACETIME</span></span>  <br/> |
|<span data-ttu-id="5fabe-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="5fabe-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5fabe-109">0x7FF9</span><span class="sxs-lookup"><span data-stu-id="5fabe-109">0x7FF9</span></span>  <br/> |
|<span data-ttu-id="5fabe-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5fabe-110">Data type:</span></span>  <br/> |<span data-ttu-id="5fabe-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="5fabe-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="5fabe-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5fabe-112">Area:</span></span>  <br/> |<span data-ttu-id="5fabe-113">类定义消息非可传送</span><span class="sxs-lookup"><span data-stu-id="5fabe-113">Message class-defined non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5fabe-114">注解</span><span class="sxs-lookup"><span data-stu-id="5fabe-114">Remarks</span></span>

<span data-ttu-id="5fabe-115">以协调世界时 (UTC)，必须指定此值。</span><span class="sxs-lookup"><span data-stu-id="5fabe-115">This value must be specified in Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5fabe-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="5fabe-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5fabe-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="5fabe-117">Protocol specifications</span></span>

<span data-ttu-id="5fabe-118">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5fabe-118">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5fabe-119">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="5fabe-119">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5fabe-120">头文件</span><span class="sxs-lookup"><span data-stu-id="5fabe-120">Header files</span></span>

<span data-ttu-id="5fabe-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5fabe-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="5fabe-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5fabe-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="5fabe-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="5fabe-123">Mapitags.h</span></span>
  
> <span data-ttu-id="5fabe-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5fabe-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5fabe-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5fabe-125">See also</span></span>



[<span data-ttu-id="5fabe-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5fabe-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5fabe-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5fabe-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5fabe-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5fabe-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5fabe-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5fabe-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

