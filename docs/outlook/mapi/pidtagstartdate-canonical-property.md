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
ms.openlocfilehash: fd799a3dc5ba91d388285f649cccfeec188b6143
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395516"
---
# <a name="pidtagstartdate-canonical-property"></a><span data-ttu-id="d57b1-103">PidTagStartDate 规范属性</span><span class="sxs-lookup"><span data-stu-id="d57b1-103">PidTagStartDate Canonical Property</span></span>

  
  
<span data-ttu-id="d57b1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d57b1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d57b1-105">包含的开始日期和时间的约会计划应用程序管理。</span><span class="sxs-lookup"><span data-stu-id="d57b1-105">Contains the starting date and time of an appointment as managed by a scheduling application.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d57b1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d57b1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d57b1-107">PR_START_DATE</span><span class="sxs-lookup"><span data-stu-id="d57b1-107">PR_START_DATE</span></span>  <br/> |
|<span data-ttu-id="d57b1-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="d57b1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d57b1-109">0x0060</span><span class="sxs-lookup"><span data-stu-id="d57b1-109">0x0060</span></span>  <br/> |
|<span data-ttu-id="d57b1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d57b1-110">Data type:</span></span>  <br/> |<span data-ttu-id="d57b1-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="d57b1-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="d57b1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d57b1-112">Area:</span></span>  <br/> |<span data-ttu-id="d57b1-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="d57b1-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d57b1-114">说明</span><span class="sxs-lookup"><span data-stu-id="d57b1-114">Remarks</span></span>

<span data-ttu-id="d57b1-115">计划应用程序应设置此属性和**PR_END_DATE** ([PidTagEndDate](pidtagenddate-canonical-property.md)) 属性时发送会议请求。</span><span class="sxs-lookup"><span data-stu-id="d57b1-115">Scheduling applications should set both this property and **PR_END_DATE** ([PidTagEndDate](pidtagenddate-canonical-property.md)) properties when sending meeting requests.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d57b1-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="d57b1-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d57b1-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="d57b1-117">Protocol specifications</span></span>

<span data-ttu-id="d57b1-118">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d57b1-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d57b1-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="d57b1-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d57b1-120">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d57b1-120">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d57b1-121">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="d57b1-121">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d57b1-122">头文件</span><span class="sxs-lookup"><span data-stu-id="d57b1-122">Header files</span></span>

<span data-ttu-id="d57b1-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d57b1-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="d57b1-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d57b1-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="d57b1-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d57b1-125">Mapitags.h</span></span>
  
> <span data-ttu-id="d57b1-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d57b1-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d57b1-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d57b1-127">See also</span></span>



[<span data-ttu-id="d57b1-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d57b1-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d57b1-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d57b1-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d57b1-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d57b1-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d57b1-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d57b1-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

