---
title: PidLidAppointmentProposedStartWhole 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentProposedStartWhole
api_type:
- COM
ms.assetid: acc96b0a-bffb-46ef-8c46-b831d165a346
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 064e57310223de2bcaaf084f7c79d2295fc5bf5b
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391638"
---
# <a name="pidlidappointmentproposedstartwhole-canonical-property"></a><span data-ttu-id="f835a-103">PidLidAppointmentProposedStartWhole 规范属性</span><span class="sxs-lookup"><span data-stu-id="f835a-103">PidLidAppointmentProposedStartWhole Canonical Property</span></span>

  
  
<span data-ttu-id="f835a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f835a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f835a-105">指定为**dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) 计数器建议的值。</span><span class="sxs-lookup"><span data-stu-id="f835a-105">Specifies the proposed value for **dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) for a counter proposal.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f835a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f835a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f835a-107">dispidApptProposedStartWhole</span><span class="sxs-lookup"><span data-stu-id="f835a-107">dispidApptProposedStartWhole</span></span>  <br/> |
|<span data-ttu-id="f835a-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="f835a-108">Property set:</span></span>  <br/> |<span data-ttu-id="f835a-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="f835a-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="f835a-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="f835a-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="f835a-111">0x00008250</span><span class="sxs-lookup"><span data-stu-id="f835a-111">0x00008250</span></span>  <br/> |
|<span data-ttu-id="f835a-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f835a-112">Data type:</span></span>  <br/> |<span data-ttu-id="f835a-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="f835a-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="f835a-114">区域：</span><span class="sxs-lookup"><span data-stu-id="f835a-114">Area:</span></span>  <br/> |<span data-ttu-id="f835a-115">会议</span><span class="sxs-lookup"><span data-stu-id="f835a-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f835a-116">说明</span><span class="sxs-lookup"><span data-stu-id="f835a-116">Remarks</span></span>

<span data-ttu-id="f835a-117">以协调世界时 (UTC)，必须指定此值。</span><span class="sxs-lookup"><span data-stu-id="f835a-117">This value must be specified in Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="f835a-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="f835a-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f835a-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="f835a-119">Protocol specifications</span></span>

<span data-ttu-id="f835a-120">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f835a-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f835a-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="f835a-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="f835a-122">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f835a-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f835a-123">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="f835a-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f835a-124">头文件</span><span class="sxs-lookup"><span data-stu-id="f835a-124">Header files</span></span>

<span data-ttu-id="f835a-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f835a-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="f835a-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f835a-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f835a-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f835a-127">See also</span></span>



[<span data-ttu-id="f835a-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f835a-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f835a-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f835a-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f835a-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f835a-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f835a-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f835a-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

