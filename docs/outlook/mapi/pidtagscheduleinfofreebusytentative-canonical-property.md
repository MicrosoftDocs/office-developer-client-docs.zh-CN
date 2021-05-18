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
# <a name="pidtagscheduleinfofreebusytentative-canonical-property"></a><span data-ttu-id="b809c-103">PidTagScheduleInfoFreeBusyTentative 规范属性</span><span class="sxs-lookup"><span data-stu-id="b809c-103">PidTagScheduleInfoFreeBusyTentative Canonical Property</span></span>

  
  
<span data-ttu-id="b809c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b809c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b809c-105">包含忙/闲状态暂定的时间块。</span><span class="sxs-lookup"><span data-stu-id="b809c-105">Contains the blocks of times for which the free/busy status is tentative.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b809c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b809c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b809c-107">PR_SCHDINFO_FREEBUSY_TENTATIVE</span><span class="sxs-lookup"><span data-stu-id="b809c-107">PR_SCHDINFO_FREEBUSY_TENTATIVE</span></span>  <br/> |
|<span data-ttu-id="b809c-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="b809c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b809c-109">0x6852</span><span class="sxs-lookup"><span data-stu-id="b809c-109">0x6852</span></span>  <br/> |
|<span data-ttu-id="b809c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b809c-110">Data type:</span></span>  <br/> |<span data-ttu-id="b809c-111">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="b809c-111">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="b809c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b809c-112">Area:</span></span>  <br/> |<span data-ttu-id="b809c-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="b809c-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b809c-114">备注</span><span class="sxs-lookup"><span data-stu-id="b809c-114">Remarks</span></span>

<span data-ttu-id="b809c-115">此属性具有与[PidTagScheduleInfoMonthsTentative](pidtagscheduleinfomonthstentative-canonical-property.md) PR_SCHDINFO_MONTHS_TENTATIVE (中的值数) 。 </span><span class="sxs-lookup"><span data-stu-id="b809c-115">This property has as many values as the number of values in **PR_SCHDINFO_MONTHS_TENTATIVE** ([PidTagScheduleInfoMonthsTentative](pidtagscheduleinfomonthstentative-canonical-property.md)).</span></span> <span data-ttu-id="b809c-116">每个二进制值表示一个月，对应于中位于同一索引 **PR_SCHDINFO_MONTHS_TENTATIVE。**</span><span class="sxs-lookup"><span data-stu-id="b809c-116">Each binary value represents a month and corresponds to the value at the same index in **PR_SCHDINFO_MONTHS_TENTATIVE**.</span></span> <span data-ttu-id="b809c-117">二进制值按与值相同的顺序进行排序，如 PR_SCHDINFO_MONTHS_TENTATIVE **。**</span><span class="sxs-lookup"><span data-stu-id="b809c-117">The binary values are sorted in the same order as the values in **PR_SCHDINFO_MONTHS_TENTATIVE**.</span></span>
  
<span data-ttu-id="b809c-118">每个二进制值具有一个或多个 4 字节块，每个二进制值包含以小尾数格式表示的两个字节的开始时间和后两个字节的结束时间。</span><span class="sxs-lookup"><span data-stu-id="b809c-118">Each binary value has one or more 4-BYTE blocks and each of them contains the start time in the first two bytes and end time in the second two bytes in little-endian format.</span></span> <span data-ttu-id="b809c-119">开始时间是当月第一天的午夜协调世界时 (UTC) 与事件开始时间之间的分钟数（UTC）。</span><span class="sxs-lookup"><span data-stu-id="b809c-119">The start time is the number of minutes between midnight Coordinated Universal Time (UTC) of the first day of the month and the start time of the event in UTC.</span></span> <span data-ttu-id="b809c-120">结束时间是一个月的第一天的午夜 UTC 与事件结束时间之间的分钟数（UTC）。</span><span class="sxs-lookup"><span data-stu-id="b809c-120">The end time is the number of minutes between midnight UTC of the first day of the month and the end time of the event in UTC.</span></span> <span data-ttu-id="b809c-121">4 字节块按升序排序。</span><span class="sxs-lookup"><span data-stu-id="b809c-121">The 4-BYTE blocks are sorted in ascending order.</span></span>
  
<span data-ttu-id="b809c-122">连续或重叠的时间块合并为一个块，将开始时间作为第一个块的开始时间，将结束时间合并为最后一个块的结束时间。</span><span class="sxs-lookup"><span data-stu-id="b809c-122">Consecutive or overlapping blocks of time are merged into one block with start time as the start time of the first block and end time as the end time of the last block.</span></span> <span data-ttu-id="b809c-123">如果事件跨多个月或年分布，则事件将拆分为多个块，每月一个块。</span><span class="sxs-lookup"><span data-stu-id="b809c-123">If an event is spread across multiple months or years, the event is split into multiple blocks, one for each month.</span></span> <span data-ttu-id="b809c-124">如果发布范围中没有任何暂定事件，则不得设置此属性PR_SCHDINFO_MONTHS_TENTATIVE或必须删除它们（如果它们已经存在）。</span><span class="sxs-lookup"><span data-stu-id="b809c-124">If there are no tentative events in the publishing range, then this property and **PR_SCHDINFO_MONTHS_TENTATIVE** must not be set or must be deleted if they already exist.</span></span> <span data-ttu-id="b809c-125">否则，必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="b809c-125">Otherwise, this property must be set.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="b809c-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="b809c-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b809c-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="b809c-127">Protocol specifications</span></span>

<span data-ttu-id="b809c-128">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b809c-128">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b809c-129">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="b809c-129">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b809c-130">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b809c-130">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b809c-131">发布用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="b809c-131">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b809c-132">头文件</span><span class="sxs-lookup"><span data-stu-id="b809c-132">Header files</span></span>

<span data-ttu-id="b809c-133">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b809c-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="b809c-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b809c-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="b809c-135">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b809c-135">Mapitags.h</span></span>
  
> <span data-ttu-id="b809c-136">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b809c-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b809c-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b809c-137">See also</span></span>



[<span data-ttu-id="b809c-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b809c-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b809c-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b809c-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b809c-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b809c-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b809c-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b809c-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

