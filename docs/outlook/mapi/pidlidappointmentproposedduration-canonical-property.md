---
title: PidLidAppointmentProposedDuration 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentProposedDuration
api_type:
- COM
ms.assetid: 37806778-a19a-4905-a845-525d3912bf9e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 56a652e630af70d4cfde12995951a352a1aa97e3
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25390616"
---
# <a name="pidlidappointmentproposedduration-canonical-property"></a><span data-ttu-id="f745f-103">PidLidAppointmentProposedDuration 规范属性</span><span class="sxs-lookup"><span data-stu-id="f745f-103">PidLidAppointmentProposedDuration Canonical Property</span></span>

  
  
<span data-ttu-id="f745f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f745f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f745f-105">指示计数器建议的**dispidApptDuration** ([PidLidAppointmentDuration](pidlidappointmentduration-canonical-property.md)) 属性为建议的值。</span><span class="sxs-lookup"><span data-stu-id="f745f-105">Indicates the proposed value for the **dispidApptDuration** ([PidLidAppointmentDuration](pidlidappointmentduration-canonical-property.md)) property for a counter proposal.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f745f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f745f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f745f-107">dispidApptProposedDuration</span><span class="sxs-lookup"><span data-stu-id="f745f-107">dispidApptProposedDuration</span></span>  <br/> |
|<span data-ttu-id="f745f-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="f745f-108">Property set:</span></span>  <br/> |<span data-ttu-id="f745f-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="f745f-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="f745f-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="f745f-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="f745f-111">0x00008256</span><span class="sxs-lookup"><span data-stu-id="f745f-111">0x00008256</span></span>  <br/> |
|<span data-ttu-id="f745f-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f745f-112">Data type:</span></span>  <br/> |<span data-ttu-id="f745f-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="f745f-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="f745f-114">区域：</span><span class="sxs-lookup"><span data-stu-id="f745f-114">Area:</span></span>  <br/> |<span data-ttu-id="f745f-115">会议</span><span class="sxs-lookup"><span data-stu-id="f745f-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f745f-116">说明</span><span class="sxs-lookup"><span data-stu-id="f745f-116">Remarks</span></span>

<span data-ttu-id="f745f-117">如果设置，它必须等于**dispidApptProposedStartWhole** ([PidLidAppointmentProposedStartWhole](pidlidappointmentproposedstartwhole-canonical-property.md)) 和**dispidApptProposedEndWhole** ([PidLidAppointmentProposedEndWhole](pidlidappointmentproposedendwhole-canonical-property.md)) 属性之间的分钟数。</span><span class="sxs-lookup"><span data-stu-id="f745f-117">If set, it must be equal to the number of minutes between the **dispidApptProposedStartWhole** ([PidLidAppointmentProposedStartWhole](pidlidappointmentproposedstartwhole-canonical-property.md)) and **dispidApptProposedEndWhole** ([PidLidAppointmentProposedEndWhole](pidlidappointmentproposedendwhole-canonical-property.md)) properties.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="f745f-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="f745f-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f745f-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="f745f-119">Protocol specifications</span></span>

<span data-ttu-id="f745f-120">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f745f-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f745f-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="f745f-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="f745f-122">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f745f-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f745f-123">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="f745f-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f745f-124">头文件</span><span class="sxs-lookup"><span data-stu-id="f745f-124">Header files</span></span>

<span data-ttu-id="f745f-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f745f-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="f745f-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f745f-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f745f-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f745f-127">See also</span></span>



[<span data-ttu-id="f745f-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f745f-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f745f-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f745f-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f745f-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f745f-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f745f-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f745f-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

