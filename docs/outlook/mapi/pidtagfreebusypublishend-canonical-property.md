---
title: PidTagFreeBusyPublishEnd 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFreeBusyPublishEnd
api_type:
- HeaderDef
ms.assetid: df239741-6a63-4cd4-9bbb-42c0f5c668a5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3b4a8cb7136eee914dc697d24e0374ccb4b6f8b1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316182"
---
# <a name="pidtagfreebusypublishend-canonical-property"></a><span data-ttu-id="d6147-103">PidTagFreeBusyPublishEnd 规范属性</span><span class="sxs-lookup"><span data-stu-id="d6147-103">PidTagFreeBusyPublishEnd Canonical Property</span></span>

  
  
<span data-ttu-id="d6147-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d6147-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d6147-105">包含发布区域的结束时间。</span><span class="sxs-lookup"><span data-stu-id="d6147-105">Contains the end time of the publishing range.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d6147-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d6147-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d6147-107">PR_FREEBUSY_PUBLISH_END</span><span class="sxs-lookup"><span data-stu-id="d6147-107">PR_FREEBUSY_PUBLISH_END</span></span>  <br/> |
|<span data-ttu-id="d6147-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d6147-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d6147-109">0x6848</span><span class="sxs-lookup"><span data-stu-id="d6147-109">0x6848</span></span>  <br/> |
|<span data-ttu-id="d6147-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d6147-110">Data type:</span></span>  <br/> |<span data-ttu-id="d6147-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="d6147-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="d6147-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d6147-112">Area:</span></span>  <br/> |<span data-ttu-id="d6147-113">闲/忙</span><span class="sxs-lookup"><span data-stu-id="d6147-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d6147-114">注解</span><span class="sxs-lookup"><span data-stu-id="d6147-114">Remarks</span></span>

<span data-ttu-id="d6147-115">此属性的值是通过将**PR_FREEBUSY_COUNT_MONTHS** ([PidTagFreeBusyCountMonths](pidtagfreebusycountmonths-canonical-property.md)) 的值添加到发布区域的开始日期计算出的。</span><span class="sxs-lookup"><span data-stu-id="d6147-115">The value for this property is computed by adding the value of **PR_FREEBUSY_COUNT_MONTHS** ([PidTagFreeBusyCountMonths](pidtagfreebusycountmonths-canonical-property.md)) to the start date of the publishing range.</span></span> <span data-ttu-id="d6147-116">此值以协调世界时 (UTC) 自1601年1月1日午夜开始的分钟数表示。</span><span class="sxs-lookup"><span data-stu-id="d6147-116">This value is expressed as the number of minutes since midnight, January 1, 1601 in Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d6147-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="d6147-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d6147-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="d6147-118">Protocol specifications</span></span>

<span data-ttu-id="d6147-119">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d6147-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d6147-120">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="d6147-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d6147-121">[[毫秒-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d6147-121">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d6147-122">发布用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="d6147-122">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d6147-123">头文件</span><span class="sxs-lookup"><span data-stu-id="d6147-123">Header files</span></span>

<span data-ttu-id="d6147-124">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="d6147-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="d6147-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d6147-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="d6147-126">Mapitags</span><span class="sxs-lookup"><span data-stu-id="d6147-126">Mapitags.h</span></span>
  
> <span data-ttu-id="d6147-127">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d6147-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d6147-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6147-128">See also</span></span>



[<span data-ttu-id="d6147-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d6147-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d6147-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d6147-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d6147-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d6147-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d6147-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d6147-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

