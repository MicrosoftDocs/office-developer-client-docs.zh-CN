---
title: PidTagScheduleInfoMonthsTentative 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoMonthsTentative
api_type:
- COM
ms.assetid: 3179442c-6499-464a-93af-eb0a7a5b0d30
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6fa0579dcd98a0d819e58e62d8a42cb2972a9d1e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359757"
---
# <a name="pidtagscheduleinfomonthstentative-canonical-property"></a><span data-ttu-id="0008d-103">PidTagScheduleInfoMonthsTentative 规范属性</span><span class="sxs-lookup"><span data-stu-id="0008d-103">PidTagScheduleInfoMonthsTentative Canonical Property</span></span>

  
  
<span data-ttu-id="0008d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0008d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0008d-105">包含忙/闲消息中标记为暂定的月份。</span><span class="sxs-lookup"><span data-stu-id="0008d-105">Contains the months marked tentative in the free/busy message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0008d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0008d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0008d-107">PR_SCHDINFO_MONTHS_TENTATIVE</span><span class="sxs-lookup"><span data-stu-id="0008d-107">PR_SCHDINFO_MONTHS_TENTATIVE</span></span>  <br/> |
|<span data-ttu-id="0008d-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="0008d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0008d-109">0x6851</span><span class="sxs-lookup"><span data-stu-id="0008d-109">0x6851</span></span>  <br/> |
|<span data-ttu-id="0008d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0008d-110">Data type:</span></span>  <br/> |<span data-ttu-id="0008d-111">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="0008d-111">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="0008d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0008d-112">Area:</span></span>  <br/> |<span data-ttu-id="0008d-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="0008d-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0008d-114">备注</span><span class="sxs-lookup"><span data-stu-id="0008d-114">Remarks</span></span>

<span data-ttu-id="0008d-115">此属性中的值数必须介于零和发布范围涵盖的月数之间，即 **PR_FREEBUSY_PUBLISH_START** ([PidTagFreeBusyPublishStart](pidtagfreebusypublishstart-canonical-property.md)) 和 **PR_FREEBUSY_PUBLISH_END** ([PidTagFreeBusyPublishEnd](pidtagfreebusypublishend-canonical-property.md)) 属性之间的时间段。</span><span class="sxs-lookup"><span data-stu-id="0008d-115">The number of values in this property must be between zero and the number of months covered by the publishing range, which is the period between the **PR_FREEBUSY_PUBLISH_START** ([PidTagFreeBusyPublishStart](pidtagfreebusypublishstart-canonical-property.md)) and **PR_FREEBUSY_PUBLISH_END** ([PidTagFreeBusyPublishEnd](pidtagfreebusypublishend-canonical-property.md)) properties.</span></span>
  
<span data-ttu-id="0008d-116">此属性中的每个值都有一个月份和年份编码。</span><span class="sxs-lookup"><span data-stu-id="0008d-116">Each value in this property, has a month and year encoded in it.</span></span> <span data-ttu-id="0008d-117">这是通过使用表达式"year × 16 + month"计算得出的，其中 year 和 month 基于公历。</span><span class="sxs-lookup"><span data-stu-id="0008d-117">This is calculated by using the expression "year × 16 + month" where year and month are based on the Gregorian calendar.</span></span> <span data-ttu-id="0008d-118">值按升序排序，并采用小尾序格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="0008d-118">The values are sorted in ascending order and are encoded in little-endian format.</span></span> <span data-ttu-id="0008d-119">如果事件跨多个月或多个年分布，则每个月份在发布范围内必须有一个值。</span><span class="sxs-lookup"><span data-stu-id="0008d-119">If an event is spread across multiple months, or multiple years, there must be one value for each of the months that fall in the publishing range.</span></span> <span data-ttu-id="0008d-120">如果发布范围中没有任何暂定事件，则此属性和 **PR_SCHDINFO_FREEBUSY_TENTATIVE** ([PidTagScheduleInfoFreeBusyTentative](pidtagscheduleinfofreebusytentative-canonical-property.md)) 不得设置或必须删除（如果它们已存在）。</span><span class="sxs-lookup"><span data-stu-id="0008d-120">If there are no tentative events in the publishing range, then this property and **PR_SCHDINFO_FREEBUSY_TENTATIVE** ([PidTagScheduleInfoFreeBusyTentative](pidtagscheduleinfofreebusytentative-canonical-property.md)) must not be set or must be deleted if they already exist.</span></span> <span data-ttu-id="0008d-121">否则，必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="0008d-121">Otherwise, this property must be set.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="0008d-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="0008d-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0008d-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="0008d-123">Protocol specifications</span></span>

<span data-ttu-id="0008d-124">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0008d-124">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0008d-125">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="0008d-125">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0008d-126">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0008d-126">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0008d-127">发布用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="0008d-127">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0008d-128">头文件</span><span class="sxs-lookup"><span data-stu-id="0008d-128">Header files</span></span>

<span data-ttu-id="0008d-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0008d-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="0008d-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0008d-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="0008d-131">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="0008d-131">Mapitags.h</span></span>
  
> <span data-ttu-id="0008d-132">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0008d-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0008d-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0008d-133">See also</span></span>



[<span data-ttu-id="0008d-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0008d-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0008d-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0008d-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0008d-136">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0008d-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0008d-137">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0008d-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

