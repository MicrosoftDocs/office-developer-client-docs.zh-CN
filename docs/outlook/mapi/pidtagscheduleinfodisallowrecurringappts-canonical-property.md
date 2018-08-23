---
title: PidTagScheduleInfoDisallowRecurringAppts 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoDisallowRecurringAppts
api_type:
- COM
ms.assetid: 61e082dd-f5bc-479b-990a-c9c0360f883e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 19e2cc0b95aaefbca1ec618c55b8d397de4d340e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593688"
---
# <a name="pidtagscheduleinfodisallowrecurringappts-canonical-property"></a><span data-ttu-id="a7117-103">PidTagScheduleInfoDisallowRecurringAppts 规范属性</span><span class="sxs-lookup"><span data-stu-id="a7117-103">PidTagScheduleInfoDisallowRecurringAppts Canonical Property</span></span>

  
  
<span data-ttu-id="a7117-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a7117-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a7117-105">拒绝对定期约会的自动响应时包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="a7117-105">Contains TRUE when the automatic response to recurring appointments is decline.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a7117-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a7117-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a7117-107">PR_SCHDINFO_DISALLOW_RECURRING_APPTS</span><span class="sxs-lookup"><span data-stu-id="a7117-107">PR_SCHDINFO_DISALLOW_RECURRING_APPTS</span></span>  <br/> |
|<span data-ttu-id="a7117-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="a7117-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a7117-109">0x686E</span><span class="sxs-lookup"><span data-stu-id="a7117-109">0x686E</span></span>  <br/> |
|<span data-ttu-id="a7117-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a7117-110">Data type:</span></span>  <br/> |<span data-ttu-id="a7117-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="a7117-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="a7117-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a7117-112">Area:</span></span>  <br/> |<span data-ttu-id="a7117-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="a7117-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a7117-114">注解</span><span class="sxs-lookup"><span data-stu-id="a7117-114">Remarks</span></span>

<span data-ttu-id="a7117-115">**PR_SCHDINFO_AUTO_ACCEPT_APPTS** ([PidTagScheduleInfoAutoAcceptAppointments](pidtagscheduleinfoautoacceptappointments-canonical-property.md)) 属性的值为 TRUE 时，此属性才有意义。</span><span class="sxs-lookup"><span data-stu-id="a7117-115">This property is only meaningful when the value of the **PR_SCHDINFO_AUTO_ACCEPT_APPTS** ([PidTagScheduleInfoAutoAcceptAppointments](pidtagscheduleinfoautoacceptappointments-canonical-property.md)) property is TRUE.</span></span> <span data-ttu-id="a7117-116">此属性不存在指示必须接受定期会议。</span><span class="sxs-lookup"><span data-stu-id="a7117-116">The absence of this property indicates that recurring meetings must be accepted.</span></span> <span data-ttu-id="a7117-117">这不是必需的属性。</span><span class="sxs-lookup"><span data-stu-id="a7117-117">This is not a required property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="a7117-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="a7117-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a7117-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="a7117-119">Protocol specifications</span></span>

<span data-ttu-id="a7117-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a7117-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a7117-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="a7117-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a7117-122">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a7117-122">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a7117-123">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="a7117-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="a7117-124">[[MS OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a7117-124">[[MS-OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a7117-125">发布的用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="a7117-125">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a7117-126">头文件</span><span class="sxs-lookup"><span data-stu-id="a7117-126">Header files</span></span>

<span data-ttu-id="a7117-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a7117-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="a7117-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a7117-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="a7117-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="a7117-129">Mapitags.h</span></span>
  
> <span data-ttu-id="a7117-130">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a7117-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a7117-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7117-131">See also</span></span>



[<span data-ttu-id="a7117-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a7117-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a7117-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a7117-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a7117-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a7117-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a7117-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a7117-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

