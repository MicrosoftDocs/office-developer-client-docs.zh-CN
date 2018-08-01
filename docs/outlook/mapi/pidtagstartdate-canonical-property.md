---
title: PidTagStartDate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStartDate
api_type:
- COM
ms.assetid: 908c2d9f-53f4-4aa8-b309-2f3ac2dca5b5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 14a077dfdb0f0781ab0d9f085c758c7a7d6285af
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778447"
---
# <a name="pidtagstartdate-canonical-property"></a><span data-ttu-id="47ce6-103">PidTagStartDate 规范属性</span><span class="sxs-lookup"><span data-stu-id="47ce6-103">PidTagStartDate Canonical Property</span></span>

  
  
<span data-ttu-id="47ce6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="47ce6-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="47ce6-105">包含的开始日期和时间的约会计划应用程序管理。</span><span class="sxs-lookup"><span data-stu-id="47ce6-105">Contains the starting date and time of an appointment as managed by a scheduling application.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="47ce6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="47ce6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="47ce6-107">PR_START_DATE</span><span class="sxs-lookup"><span data-stu-id="47ce6-107">PR_START_DATE</span></span>  <br/> |
|<span data-ttu-id="47ce6-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="47ce6-108">Identifier:</span></span>  <br/> |<span data-ttu-id="47ce6-109">0x0060</span><span class="sxs-lookup"><span data-stu-id="47ce6-109">0x0060</span></span>  <br/> |
|<span data-ttu-id="47ce6-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="47ce6-110">Data type:</span></span>  <br/> |<span data-ttu-id="47ce6-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="47ce6-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="47ce6-112">区域：</span><span class="sxs-lookup"><span data-stu-id="47ce6-112">Area:</span></span>  <br/> |<span data-ttu-id="47ce6-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="47ce6-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="47ce6-114">说明</span><span class="sxs-lookup"><span data-stu-id="47ce6-114">Remarks</span></span>

<span data-ttu-id="47ce6-115">计划应用程序应设置此属性和**PR_END_DATE** ([PidTagEndDate](pidtagenddate-canonical-property.md)) 属性时发送会议请求。</span><span class="sxs-lookup"><span data-stu-id="47ce6-115">Scheduling applications should set both this property and **PR_END_DATE** ([PidTagEndDate](pidtagenddate-canonical-property.md)) properties when sending meeting requests.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="47ce6-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="47ce6-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="47ce6-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="47ce6-117">Protocol specifications</span></span>

<span data-ttu-id="47ce6-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="47ce6-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="47ce6-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="47ce6-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="47ce6-120">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="47ce6-120">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="47ce6-121">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="47ce6-121">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="47ce6-122">头文件</span><span class="sxs-lookup"><span data-stu-id="47ce6-122">Header files</span></span>

<span data-ttu-id="47ce6-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="47ce6-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="47ce6-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="47ce6-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="47ce6-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="47ce6-125">Mapitags.h</span></span>
  
> <span data-ttu-id="47ce6-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="47ce6-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="47ce6-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47ce6-127">See also</span></span>



[<span data-ttu-id="47ce6-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="47ce6-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="47ce6-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="47ce6-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="47ce6-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="47ce6-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="47ce6-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="47ce6-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

