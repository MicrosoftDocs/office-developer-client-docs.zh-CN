---
title: PidTagScheduleInfoFreeBusyMerged 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoFreeBusyMerged
api_type:
- COM
ms.assetid: 3ebfccb6-967a-4f8e-9d94-94c50ba65438
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8d15c6cb256fb1e80e3c94bdfe7e71bd8625aa35
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338715"
---
# <a name="pidtagscheduleinfofreebusymerged-canonical-property"></a><span data-ttu-id="f5ec3-103">PidTagScheduleInfoFreeBusyMerged 规范属性</span><span class="sxs-lookup"><span data-stu-id="f5ec3-103">PidTagScheduleInfoFreeBusyMerged Canonical Property</span></span>

  
  
<span data-ttu-id="f5ec3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f5ec3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f5ec3-105">包含 "闲/忙" 状态设置为 "忙碌" 或 "OOF" 的时间。</span><span class="sxs-lookup"><span data-stu-id="f5ec3-105">Contains the times for which the free/busy status is set to busy or OOF.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f5ec3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f5ec3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f5ec3-107">PR_SCHDINFO_FREEBUSY_MERGED</span><span class="sxs-lookup"><span data-stu-id="f5ec3-107">PR_SCHDINFO_FREEBUSY_MERGED</span></span>  <br/> |
|<span data-ttu-id="f5ec3-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="f5ec3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f5ec3-109">0x6850</span><span class="sxs-lookup"><span data-stu-id="f5ec3-109">0x6850</span></span>  <br/> |
|<span data-ttu-id="f5ec3-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f5ec3-110">Data type:</span></span>  <br/> |<span data-ttu-id="f5ec3-111">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="f5ec3-111">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="f5ec3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f5ec3-112">Area:</span></span>  <br/> |<span data-ttu-id="f5ec3-113">闲/忙</span><span class="sxs-lookup"><span data-stu-id="f5ec3-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f5ec3-114">注解</span><span class="sxs-lookup"><span data-stu-id="f5ec3-114">Remarks</span></span>

<span data-ttu-id="f5ec3-115">此属性中不包含忙/闲类型的 "暂定" 事件。</span><span class="sxs-lookup"><span data-stu-id="f5ec3-115">Events of free/busy type tentative are not included in this property.</span></span> <span data-ttu-id="f5ec3-116">此属性的格式、计算和限制与**PR_SCHDINFO_FREEBUSY_TENTATIVE** ([PidTagScheduleInfoFreeBusyTentative](pidtagscheduleinfofreebusytentative-canonical-property.md)) 的格式相同, 但引用在关联日历上标记为 "OOF" 或 "忙" 的约会。</span><span class="sxs-lookup"><span data-stu-id="f5ec3-116">The format, computation and the restrictions of this property are the same as those of **PR_SCHDINFO_FREEBUSY_TENTATIVE** ([PidTagScheduleInfoFreeBusyTentative](pidtagscheduleinfofreebusytentative-canonical-property.md)) but refer to appointments that are marked OOF or busy on the associated calendar.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="f5ec3-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="f5ec3-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f5ec3-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="f5ec3-118">Protocol specifications</span></span>

<span data-ttu-id="f5ec3-119">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f5ec3-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f5ec3-120">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="f5ec3-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="f5ec3-121">[[毫秒-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f5ec3-121">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f5ec3-122">发布用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="f5ec3-122">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f5ec3-123">头文件</span><span class="sxs-lookup"><span data-stu-id="f5ec3-123">Header files</span></span>

<span data-ttu-id="f5ec3-124">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="f5ec3-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="f5ec3-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f5ec3-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="f5ec3-126">Mapitags</span><span class="sxs-lookup"><span data-stu-id="f5ec3-126">Mapitags.h</span></span>
  
> <span data-ttu-id="f5ec3-127">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f5ec3-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f5ec3-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5ec3-128">See also</span></span>



[<span data-ttu-id="f5ec3-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f5ec3-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f5ec3-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f5ec3-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f5ec3-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f5ec3-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f5ec3-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f5ec3-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

