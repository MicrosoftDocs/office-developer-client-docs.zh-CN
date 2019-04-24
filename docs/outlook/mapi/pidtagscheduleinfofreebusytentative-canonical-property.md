---
title: PidTagScheduleInfoFreeBusyTentative 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoFreeBusyTentative
api_type:
- COM
ms.assetid: 28453d29-30c5-405b-84d2-5bb5f281756c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 18bc41d9038113b5b813f1cfd02d90b8e982703c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359771"
---
# <a name="pidtagscheduleinfofreebusytentative-canonical-property"></a><span data-ttu-id="22ed1-103">PidTagScheduleInfoFreeBusyTentative 规范属性</span><span class="sxs-lookup"><span data-stu-id="22ed1-103">PidTagScheduleInfoFreeBusyTentative Canonical Property</span></span>

  
  
<span data-ttu-id="22ed1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="22ed1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="22ed1-105">包含忙/闲状态为 "暂定" 的时间段。</span><span class="sxs-lookup"><span data-stu-id="22ed1-105">Contains the blocks of times for which the free/busy status is tentative.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="22ed1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="22ed1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="22ed1-107">PR_SCHDINFO_FREEBUSY_TENTATIVE</span><span class="sxs-lookup"><span data-stu-id="22ed1-107">PR_SCHDINFO_FREEBUSY_TENTATIVE</span></span>  <br/> |
|<span data-ttu-id="22ed1-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="22ed1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="22ed1-109">0x6852</span><span class="sxs-lookup"><span data-stu-id="22ed1-109">0x6852</span></span>  <br/> |
|<span data-ttu-id="22ed1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="22ed1-110">Data type:</span></span>  <br/> |<span data-ttu-id="22ed1-111">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="22ed1-111">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="22ed1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="22ed1-112">Area:</span></span>  <br/> |<span data-ttu-id="22ed1-113">闲/忙</span><span class="sxs-lookup"><span data-stu-id="22ed1-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="22ed1-114">注解</span><span class="sxs-lookup"><span data-stu-id="22ed1-114">Remarks</span></span>

<span data-ttu-id="22ed1-115">此属性的值与**PR_SCHDINFO_MONTHS_TENTATIVE** ([PidTagScheduleInfoMonthsTentative](pidtagscheduleinfomonthstentative-canonical-property.md)) 中的值数相同。</span><span class="sxs-lookup"><span data-stu-id="22ed1-115">This property has as many values as the number of values in **PR_SCHDINFO_MONTHS_TENTATIVE** ([PidTagScheduleInfoMonthsTentative](pidtagscheduleinfomonthstentative-canonical-property.md)).</span></span> <span data-ttu-id="22ed1-116">每个二进制值表示一个月, 并与**PR_SCHDINFO_MONTHS_TENTATIVE**中同一索引处的值相对应。</span><span class="sxs-lookup"><span data-stu-id="22ed1-116">Each binary value represents a month and corresponds to the value at the same index in **PR_SCHDINFO_MONTHS_TENTATIVE**.</span></span> <span data-ttu-id="22ed1-117">二进制值按与**PR_SCHDINFO_MONTHS_TENTATIVE**中的值相同的顺序进行排序。</span><span class="sxs-lookup"><span data-stu-id="22ed1-117">The binary values are sorted in the same order as the values in **PR_SCHDINFO_MONTHS_TENTATIVE**.</span></span>
  
<span data-ttu-id="22ed1-118">每个二进制值具有一个或多个4字节块, 每个块都包含以小字节结尾格式的前两个字节中的开始时间和以秒为单位的前两个字节的结束时间。</span><span class="sxs-lookup"><span data-stu-id="22ed1-118">Each binary value has one or more 4-BYTE blocks and each of them contains the start time in the first two bytes and end time in the second two bytes in little-endian format.</span></span> <span data-ttu-id="22ed1-119">"开始时间" 是一个月的第一天与事件的开始时间之间的协调世界时 (utc) 之间的分钟数和 UTC 的开始时间。</span><span class="sxs-lookup"><span data-stu-id="22ed1-119">The start time is the number of minutes between midnight Coordinated Universal Time (UTC) of the first day of the month and the start time of the event in UTC.</span></span> <span data-ttu-id="22ed1-120">结束时间是一个月的第一天 (utc 时间) 与事件的结束时间之间的午夜 (utc) 之间的分钟数。</span><span class="sxs-lookup"><span data-stu-id="22ed1-120">The end time is the number of minutes between midnight UTC of the first day of the month and the end time of the event in UTC.</span></span> <span data-ttu-id="22ed1-121">4字节块按升序排列。</span><span class="sxs-lookup"><span data-stu-id="22ed1-121">The 4-BYTE blocks are sorted in ascending order.</span></span>
  
<span data-ttu-id="22ed1-122">连续或重叠的时间块合并为一个块, 其开始时间为第一个块的开始时间和结束时间为最后一个块的结束时间。</span><span class="sxs-lookup"><span data-stu-id="22ed1-122">Consecutive or overlapping blocks of time are merged into one block with start time as the start time of the first block and end time as the end time of the last block.</span></span> <span data-ttu-id="22ed1-123">如果一个事件分布在多个月或几年, 则该事件被拆分为多个块, 每个月一个。</span><span class="sxs-lookup"><span data-stu-id="22ed1-123">If an event is spread across multiple months or years, the event is split into multiple blocks, one for each month.</span></span> <span data-ttu-id="22ed1-124">如果发布区域中没有暂定事件, 则不能设置此属性和**PR_SCHDINFO_MONTHS_TENTATIVE** , 如果它们已经存在则必须删除。</span><span class="sxs-lookup"><span data-stu-id="22ed1-124">If there are no tentative events in the publishing range, then this property and **PR_SCHDINFO_MONTHS_TENTATIVE** must not be set or must be deleted if they already exist.</span></span> <span data-ttu-id="22ed1-125">否则, 必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="22ed1-125">Otherwise, this property must be set.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="22ed1-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="22ed1-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="22ed1-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="22ed1-127">Protocol specifications</span></span>

<span data-ttu-id="22ed1-128">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="22ed1-128">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="22ed1-129">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="22ed1-129">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="22ed1-130">[[毫秒-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="22ed1-130">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="22ed1-131">发布用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="22ed1-131">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="22ed1-132">头文件</span><span class="sxs-lookup"><span data-stu-id="22ed1-132">Header files</span></span>

<span data-ttu-id="22ed1-133">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="22ed1-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="22ed1-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="22ed1-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="22ed1-135">Mapitags</span><span class="sxs-lookup"><span data-stu-id="22ed1-135">Mapitags.h</span></span>
  
> <span data-ttu-id="22ed1-136">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="22ed1-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="22ed1-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22ed1-137">See also</span></span>



[<span data-ttu-id="22ed1-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="22ed1-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="22ed1-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="22ed1-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="22ed1-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="22ed1-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="22ed1-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="22ed1-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

