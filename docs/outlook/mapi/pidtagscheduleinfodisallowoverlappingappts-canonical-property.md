---
title: PidTagScheduleInfoDisallowOverlappingAppts 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoDisallowOverlappingAppts
api_type:
- COM
ms.assetid: 27978a09-daf7-4a50-927a-96d9c4a97d02
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5ead258c056ec2204ddab92e9b99e1b17fe98092
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391897"
---
# <a name="pidtagscheduleinfodisallowoverlappingappts-canonical-property"></a><span data-ttu-id="eca64-103">PidTagScheduleInfoDisallowOverlappingAppts 规范属性</span><span class="sxs-lookup"><span data-stu-id="eca64-103">PidTagScheduleInfoDisallowOverlappingAppts Canonical Property</span></span>

  
  
<span data-ttu-id="eca64-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="eca64-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="eca64-105">包含 TRUE，则不允许使用重叠的约会。</span><span class="sxs-lookup"><span data-stu-id="eca64-105">Contains TRUE if overlapping appointments are disallowed.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="eca64-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="eca64-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="eca64-107">PR_SCHDINFO_DISALLOW_OVERLAPPING_APPTS</span><span class="sxs-lookup"><span data-stu-id="eca64-107">PR_SCHDINFO_DISALLOW_OVERLAPPING_APPTS</span></span>  <br/> |
|<span data-ttu-id="eca64-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="eca64-108">Identifier:</span></span>  <br/> |<span data-ttu-id="eca64-109">0x686F</span><span class="sxs-lookup"><span data-stu-id="eca64-109">0x686F</span></span>  <br/> |
|<span data-ttu-id="eca64-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="eca64-110">Data type:</span></span>  <br/> |<span data-ttu-id="eca64-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="eca64-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="eca64-112">区域：</span><span class="sxs-lookup"><span data-stu-id="eca64-112">Area:</span></span>  <br/> |<span data-ttu-id="eca64-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="eca64-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="eca64-114">说明</span><span class="sxs-lookup"><span data-stu-id="eca64-114">Remarks</span></span>

<span data-ttu-id="eca64-115">**PR_SCHDINFO_AUTO_ACCEPT_APPTS** ([PidTagScheduleInfoAutoAcceptAppointments](pidtagscheduleinfoautoacceptappointments-canonical-property.md)) 属性的值为 TRUE 时，此属性才有意义。</span><span class="sxs-lookup"><span data-stu-id="eca64-115">This property is only meaningful when the value of the **PR_SCHDINFO_AUTO_ACCEPT_APPTS** ([PidTagScheduleInfoAutoAcceptAppointments](pidtagscheduleinfoautoacceptappointments-canonical-property.md)) property is TRUE.</span></span> <span data-ttu-id="eca64-116">值为 TRUE 指示的时自动对会议请求的响应，客户端或服务器必须拒绝重叠以前计划的事件的实例。</span><span class="sxs-lookup"><span data-stu-id="eca64-116">A value of TRUE indicates that when automatically responding to meeting requests, a client or server must decline instances that overlap previously scheduled events.</span></span> <span data-ttu-id="eca64-117">值为 FALSE 或不存在此属性表示必须接受重叠的实例。</span><span class="sxs-lookup"><span data-stu-id="eca64-117">A value of FALSE or the absence of this property indicates that overlapping instances must be accepted.</span></span> <span data-ttu-id="eca64-118">这不是必需的属性。</span><span class="sxs-lookup"><span data-stu-id="eca64-118">This is not a required property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="eca64-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="eca64-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="eca64-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="eca64-120">Protocol specifications</span></span>

<span data-ttu-id="eca64-121">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="eca64-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="eca64-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="eca64-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="eca64-123">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="eca64-123">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="eca64-124">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="eca64-124">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="eca64-125">[[MS OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="eca64-125">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="eca64-126">发布的用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="eca64-126">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="eca64-127">头文件</span><span class="sxs-lookup"><span data-stu-id="eca64-127">Header files</span></span>

<span data-ttu-id="eca64-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="eca64-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="eca64-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="eca64-129">Provides data type definitions.</span></span>
    
<span data-ttu-id="eca64-130">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="eca64-130">Mapitags.h</span></span>
  
> <span data-ttu-id="eca64-131">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="eca64-131">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="eca64-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eca64-132">See also</span></span>



[<span data-ttu-id="eca64-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="eca64-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="eca64-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="eca64-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="eca64-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="eca64-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="eca64-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="eca64-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

