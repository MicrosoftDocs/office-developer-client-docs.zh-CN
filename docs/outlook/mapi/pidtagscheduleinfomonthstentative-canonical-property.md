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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 20620a5835e627eb7543a03037f9be75db6739ac
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778346"
---
# <a name="pidtagscheduleinfomonthstentative-canonical-property"></a><span data-ttu-id="81d27-103">PidTagScheduleInfoMonthsTentative 规范属性</span><span class="sxs-lookup"><span data-stu-id="81d27-103">PidTagScheduleInfoMonthsTentative Canonical Property</span></span>

  
  
<span data-ttu-id="81d27-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="81d27-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="81d27-105">包含标记暂定忙/闲信息消息中的月份。</span><span class="sxs-lookup"><span data-stu-id="81d27-105">Contains the months marked tentative in the free/busy message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="81d27-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="81d27-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="81d27-107">PR_SCHDINFO_MONTHS_TENTATIVE</span><span class="sxs-lookup"><span data-stu-id="81d27-107">PR_SCHDINFO_MONTHS_TENTATIVE</span></span>  <br/> |
|<span data-ttu-id="81d27-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="81d27-108">Identifier:</span></span>  <br/> |<span data-ttu-id="81d27-109">0x6851</span><span class="sxs-lookup"><span data-stu-id="81d27-109">0x6851</span></span>  <br/> |
|<span data-ttu-id="81d27-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="81d27-110">Data type:</span></span>  <br/> |<span data-ttu-id="81d27-111">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="81d27-111">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="81d27-112">区域：</span><span class="sxs-lookup"><span data-stu-id="81d27-112">Area:</span></span>  <br/> |<span data-ttu-id="81d27-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="81d27-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="81d27-114">备注</span><span class="sxs-lookup"><span data-stu-id="81d27-114">Remarks</span></span>

<span data-ttu-id="81d27-115">此属性中的值数必须介于零和涵盖了发布的范围，这是**PR_FREEBUSY_PUBLISH_START** ([PidTagFreeBusyPublishStart](pidtagfreebusypublishstart-canonical-property.md)) 和**PR_FREEBUSY_PUBLISH_END 之间的时间段的月数之间**([PidTagFreeBusyPublishEnd](pidtagfreebusypublishend-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="81d27-115">The number of values in this property must be between zero and the number of months covered by the publishing range, which is the period between the **PR_FREEBUSY_PUBLISH_START** ([PidTagFreeBusyPublishStart](pidtagfreebusypublishstart-canonical-property.md)) and **PR_FREEBUSY_PUBLISH_END** ([PidTagFreeBusyPublishEnd](pidtagfreebusypublishend-canonical-property.md)) properties.</span></span>
  
<span data-ttu-id="81d27-116">此属性中，每个值都有月份和年份中编码。</span><span class="sxs-lookup"><span data-stu-id="81d27-116">Each value in this property, has a month and year encoded in it.</span></span> <span data-ttu-id="81d27-117">这是通过使用表达式"年 × 16 + 月"年和月基于公历日历上计算得出。</span><span class="sxs-lookup"><span data-stu-id="81d27-117">This is calculated by using the expression "year × 16 + month" where year and month are based on the Gregorian calendar.</span></span> <span data-ttu-id="81d27-118">值以升序排序，并以-little-endian 格式编码。</span><span class="sxs-lookup"><span data-stu-id="81d27-118">The values are sorted in ascending order and are encoded in little-endian format.</span></span> <span data-ttu-id="81d27-119">如果事件跨多个月或多个年，必须有一个月发布的范围中的每个值。</span><span class="sxs-lookup"><span data-stu-id="81d27-119">If an event is spread across multiple months, or multiple years, there must be one value for each of the months that fall in the publishing range.</span></span> <span data-ttu-id="81d27-120">如果发布范围中没有暂定事件，然后此属性和**PR_SCHDINFO_FREEBUSY_TENTATIVE** ([PidTagScheduleInfoFreeBusyTentative](pidtagscheduleinfofreebusytentative-canonical-property.md)) 不能设置或者如果已存在，则必须删除。</span><span class="sxs-lookup"><span data-stu-id="81d27-120">If there are no tentative events in the publishing range, then this property and **PR_SCHDINFO_FREEBUSY_TENTATIVE** ([PidTagScheduleInfoFreeBusyTentative](pidtagscheduleinfofreebusytentative-canonical-property.md)) must not be set or must be deleted if they already exist.</span></span> <span data-ttu-id="81d27-121">否则，必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="81d27-121">Otherwise, this property must be set.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="81d27-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="81d27-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="81d27-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="81d27-123">Protocol specifications</span></span>

<span data-ttu-id="81d27-124">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="81d27-124">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="81d27-125">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="81d27-125">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="81d27-126">[[MS OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="81d27-126">[[MS-OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="81d27-127">发布的用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="81d27-127">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="81d27-128">头文件</span><span class="sxs-lookup"><span data-stu-id="81d27-128">Header files</span></span>

<span data-ttu-id="81d27-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="81d27-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="81d27-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="81d27-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="81d27-131">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="81d27-131">Mapitags.h</span></span>
  
> <span data-ttu-id="81d27-132">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="81d27-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="81d27-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81d27-133">See also</span></span>



[<span data-ttu-id="81d27-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="81d27-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="81d27-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="81d27-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="81d27-136">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="81d27-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="81d27-137">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="81d27-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

