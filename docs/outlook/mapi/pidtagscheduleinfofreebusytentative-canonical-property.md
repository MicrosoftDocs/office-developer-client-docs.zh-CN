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
ms.openlocfilehash: a00505b765abdcb7b8fe9d68052774b30bbdf692
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778349"
---
# <a name="pidtagscheduleinfofreebusytentative-canonical-property"></a><span data-ttu-id="e35a9-103">PidTagScheduleInfoFreeBusyTentative 规范属性</span><span class="sxs-lookup"><span data-stu-id="e35a9-103">PidTagScheduleInfoFreeBusyTentative Canonical Property</span></span>

  
  
<span data-ttu-id="e35a9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e35a9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e35a9-105">包含的基块处于暂定忙/闲状态的时间。</span><span class="sxs-lookup"><span data-stu-id="e35a9-105">Contains the blocks of times for which the free/busy status is tentative.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e35a9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e35a9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e35a9-107">PR_SCHDINFO_FREEBUSY_TENTATIVE</span><span class="sxs-lookup"><span data-stu-id="e35a9-107">PR_SCHDINFO_FREEBUSY_TENTATIVE</span></span>  <br/> |
|<span data-ttu-id="e35a9-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="e35a9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e35a9-109">0x6852</span><span class="sxs-lookup"><span data-stu-id="e35a9-109">0x6852</span></span>  <br/> |
|<span data-ttu-id="e35a9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e35a9-110">Data type:</span></span>  <br/> |<span data-ttu-id="e35a9-111">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="e35a9-111">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="e35a9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e35a9-112">Area:</span></span>  <br/> |<span data-ttu-id="e35a9-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="e35a9-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e35a9-114">说明</span><span class="sxs-lookup"><span data-stu-id="e35a9-114">Remarks</span></span>

<span data-ttu-id="e35a9-115">此属性在**PR_SCHDINFO_MONTHS_TENTATIVE** ([PidTagScheduleInfoMonthsTentative](pidtagscheduleinfomonthstentative-canonical-property.md)) 中具有多个值作为值的数目。</span><span class="sxs-lookup"><span data-stu-id="e35a9-115">This property has as many values as the number of values in **PR_SCHDINFO_MONTHS_TENTATIVE** ([PidTagScheduleInfoMonthsTentative](pidtagscheduleinfomonthstentative-canonical-property.md)).</span></span> <span data-ttu-id="e35a9-116">每个二进制值表示的月和对应于**PR_SCHDINFO_MONTHS_TENTATIVE**中相同的索引处的值。</span><span class="sxs-lookup"><span data-stu-id="e35a9-116">Each binary value represents a month and corresponds to the value at the same index in **PR_SCHDINFO_MONTHS_TENTATIVE**.</span></span> <span data-ttu-id="e35a9-117">**PR_SCHDINFO_MONTHS_TENTATIVE**中的值相同的顺序排序的二进制值。</span><span class="sxs-lookup"><span data-stu-id="e35a9-117">The binary values are sorted in the same order as the values in **PR_SCHDINFO_MONTHS_TENTATIVE**.</span></span>
  
<span data-ttu-id="e35a9-118">每个二进制值都有一个或多个 4 字节块，以及每个包含前两个字节的开始时间和结束时间-little-endian 格式中的第二个两个字节。</span><span class="sxs-lookup"><span data-stu-id="e35a9-118">Each binary value has one or more 4-BYTE blocks and each of them contains the start time in the first two bytes and end time in the second two bytes in little-endian format.</span></span> <span data-ttu-id="e35a9-119">相应月份的第一天的协调世界时 (UTC) 午夜和采用 UTC 的事件的开始时间之间的分钟数的开始时间。</span><span class="sxs-lookup"><span data-stu-id="e35a9-119">The start time is the number of minutes between midnight Coordinated Universal Time (UTC) of the first day of the month and the start time of the event in UTC.</span></span> <span data-ttu-id="e35a9-120">相应月份的第一天的午夜 UTC 和采用 UTC 的事件的结束时间之间的分钟数的结束时间。</span><span class="sxs-lookup"><span data-stu-id="e35a9-120">The end time is the number of minutes between midnight UTC of the first day of the month and the end time of the event in UTC.</span></span> <span data-ttu-id="e35a9-121">4 字节块按升序排序。</span><span class="sxs-lookup"><span data-stu-id="e35a9-121">The 4-BYTE blocks are sorted in ascending order.</span></span>
  
<span data-ttu-id="e35a9-122">连续或重叠的时间段合并到一个块作为的开始时间的开始时间的第一个块和作为的最后一个块的结束时间的结束时间。</span><span class="sxs-lookup"><span data-stu-id="e35a9-122">Consecutive or overlapping blocks of time are merged into one block with start time as the start time of the first block and end time as the end time of the last block.</span></span> <span data-ttu-id="e35a9-123">如果事件跨多个月或年，则事件分为多个块，一个用于每个月。</span><span class="sxs-lookup"><span data-stu-id="e35a9-123">If an event is spread across multiple months or years, the event is split into multiple blocks, one for each month.</span></span> <span data-ttu-id="e35a9-124">如果发布范围中没有暂定事件，然后此属性和**PR_SCHDINFO_MONTHS_TENTATIVE**不得设置或者如果已存在，则必须删除。</span><span class="sxs-lookup"><span data-stu-id="e35a9-124">If there are no tentative events in the publishing range, then this property and **PR_SCHDINFO_MONTHS_TENTATIVE** must not be set or must be deleted if they already exist.</span></span> <span data-ttu-id="e35a9-125">否则，必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="e35a9-125">Otherwise, this property must be set.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="e35a9-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="e35a9-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e35a9-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="e35a9-127">Protocol specifications</span></span>

<span data-ttu-id="e35a9-128">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e35a9-128">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e35a9-129">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="e35a9-129">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e35a9-130">[[MS OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e35a9-130">[[MS-OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e35a9-131">发布的用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="e35a9-131">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e35a9-132">头文件</span><span class="sxs-lookup"><span data-stu-id="e35a9-132">Header files</span></span>

<span data-ttu-id="e35a9-133">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e35a9-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="e35a9-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e35a9-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="e35a9-135">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e35a9-135">Mapitags.h</span></span>
  
> <span data-ttu-id="e35a9-136">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e35a9-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e35a9-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e35a9-137">See also</span></span>



[<span data-ttu-id="e35a9-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e35a9-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e35a9-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e35a9-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e35a9-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e35a9-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e35a9-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e35a9-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

