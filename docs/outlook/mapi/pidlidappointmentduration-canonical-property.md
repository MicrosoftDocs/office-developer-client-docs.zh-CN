---
title: PidLidAppointmentDuration 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentDuration
api_type:
- COM
ms.assetid: 92c07a81-9dec-4118-af1f-02ecad340f07
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cfe5ad9a088fb4c02842e8be9d11a3623be749e3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574903"
---
# <a name="pidlidappointmentduration-canonical-property"></a><span data-ttu-id="64d95-103">PidLidAppointmentDuration 规范属性</span><span class="sxs-lookup"><span data-stu-id="64d95-103">PidLidAppointmentDuration Canonical Property</span></span>

  
  
<span data-ttu-id="64d95-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="64d95-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="64d95-105">表示时间，以分钟为单位，当安排约会的长度。</span><span class="sxs-lookup"><span data-stu-id="64d95-105">Represents the length of time, in minutes, when an appointment is scheduled.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="64d95-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="64d95-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="64d95-107">dispidApptDuration</span><span class="sxs-lookup"><span data-stu-id="64d95-107">dispidApptDuration</span></span>  <br/> |
|<span data-ttu-id="64d95-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="64d95-108">Property set:</span></span>  <br/> |<span data-ttu-id="64d95-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="64d95-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="64d95-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="64d95-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="64d95-111">0x00008213</span><span class="sxs-lookup"><span data-stu-id="64d95-111">0x00008213</span></span>  <br/> |
|<span data-ttu-id="64d95-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="64d95-112">Data type:</span></span>  <br/> |<span data-ttu-id="64d95-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="64d95-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="64d95-114">区域：</span><span class="sxs-lookup"><span data-stu-id="64d95-114">Area:</span></span>  <br/> |<span data-ttu-id="64d95-115">日历</span><span class="sxs-lookup"><span data-stu-id="64d95-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="64d95-116">注解</span><span class="sxs-lookup"><span data-stu-id="64d95-116">Remarks</span></span>

<span data-ttu-id="64d95-117">值必须是**dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) 的值和**dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) 属性之间的分钟数。</span><span class="sxs-lookup"><span data-stu-id="64d95-117">The value must be the number of minutes between the value of the **dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) and the **dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) properties.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="64d95-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="64d95-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="64d95-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="64d95-119">Protocol specifications</span></span>

<span data-ttu-id="64d95-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="64d95-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="64d95-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="64d95-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="64d95-122">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="64d95-122">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="64d95-123">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="64d95-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="64d95-124">头文件</span><span class="sxs-lookup"><span data-stu-id="64d95-124">Header files</span></span>

<span data-ttu-id="64d95-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="64d95-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="64d95-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="64d95-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="64d95-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64d95-127">See also</span></span>



[<span data-ttu-id="64d95-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="64d95-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="64d95-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="64d95-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="64d95-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="64d95-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="64d95-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="64d95-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

