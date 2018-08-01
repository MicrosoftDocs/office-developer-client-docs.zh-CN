---
title: PidTagScheduleInfoAutoAcceptAppointments 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoAutoAcceptAppointments
api_type:
- COM
ms.assetid: 79505b29-2706-472b-b084-ab74be7b3405
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4f2cab31d6eed19a262bd0e667166bc79f428877
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778317"
---
# <a name="pidtagscheduleinfoautoacceptappointments-canonical-property"></a><span data-ttu-id="b813d-103">PidTagScheduleInfoAutoAcceptAppointments 规范属性</span><span class="sxs-lookup"><span data-stu-id="b813d-103">PidTagScheduleInfoAutoAcceptAppointments Canonical Property</span></span>

  
  
<span data-ttu-id="b813d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b813d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b813d-105">包含 TRUE，则客户端或服务器应自动回复所有会议请求的与会者或资源。</span><span class="sxs-lookup"><span data-stu-id="b813d-105">Contains TRUE if a client or server should automatically respond to all meeting requests for the attendee or resource.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b813d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b813d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b813d-107">PR_SCHDINFO_AUTO_ACCEPT_APPTS</span><span class="sxs-lookup"><span data-stu-id="b813d-107">PR_SCHDINFO_AUTO_ACCEPT_APPTS</span></span>  <br/> |
|<span data-ttu-id="b813d-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="b813d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b813d-109">0x686D</span><span class="sxs-lookup"><span data-stu-id="b813d-109">0x686D</span></span>  <br/> |
|<span data-ttu-id="b813d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b813d-110">Data type:</span></span>  <br/> |<span data-ttu-id="b813d-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="b813d-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="b813d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b813d-112">Area:</span></span>  <br/> |<span data-ttu-id="b813d-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="b813d-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b813d-114">说明</span><span class="sxs-lookup"><span data-stu-id="b813d-114">Remarks</span></span>

<span data-ttu-id="b813d-115">当响应响应必须接受，除非另外一个约束条件的指定由**PR_SCHDINFO_DISALLOW_RECURRING_APPTS** ([PidTagScheduleInfoDisallowRecurringAppts](pidtagscheduleinfodisallowrecurringappts-canonical-property.md)) 或**PR_SCHDINFO_DISALLOW_OVERLAPPING_APPTS**满足 ([PidTagScheduleInfoDisallowOverlappingAppts](pidtagscheduleinfodisallowoverlappingappts-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="b813d-115">When responding, the response must be acceptance, unless for an additional constraint that is specified by the **PR_SCHDINFO_DISALLOW_RECURRING_APPTS** ([PidTagScheduleInfoDisallowRecurringAppts](pidtagscheduleinfodisallowrecurringappts-canonical-property.md)) or **PR_SCHDINFO_DISALLOW_OVERLAPPING_APPTS** ([PidTagScheduleInfoDisallowOverlappingAppts](pidtagscheduleinfodisallowoverlappingappts-canonical-property.md)) properties is met.</span></span> <span data-ttu-id="b813d-116">值为 FALSE 或不存在此属性指示客户端或服务器必须不自动接受会议请求。</span><span class="sxs-lookup"><span data-stu-id="b813d-116">A value of FALSE or the absence of this property indicates that a client or server must not automatically accept meeting requests.</span></span> <span data-ttu-id="b813d-117">这不是必需的属性。</span><span class="sxs-lookup"><span data-stu-id="b813d-117">This is not a required property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="b813d-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="b813d-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b813d-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="b813d-119">Protocol specifications</span></span>

<span data-ttu-id="b813d-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b813d-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b813d-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="b813d-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b813d-122">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b813d-122">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b813d-123">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="b813d-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="b813d-124">[[MS OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b813d-124">[[MS-OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b813d-125">发布的用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="b813d-125">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b813d-126">头文件</span><span class="sxs-lookup"><span data-stu-id="b813d-126">Header files</span></span>

<span data-ttu-id="b813d-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b813d-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="b813d-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b813d-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="b813d-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b813d-129">Mapitags.h</span></span>
  
> <span data-ttu-id="b813d-130">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b813d-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b813d-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b813d-131">See also</span></span>



[<span data-ttu-id="b813d-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b813d-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b813d-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b813d-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b813d-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b813d-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b813d-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b813d-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

