---
title: PidLidAppointmentSubType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentSubType
api_type:
- COM
ms.assetid: e2e00af3-1fb3-4314-936a-f480674d3d83
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cb9f4e0f58ea27d36ba911ed60527a2e53f23727
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776673"
---
# <a name="pidlidappointmentsubtype-canonical-property"></a><span data-ttu-id="1683e-103">PidLidAppointmentSubType 规范属性</span><span class="sxs-lookup"><span data-stu-id="1683e-103">PidLidAppointmentSubType Canonical Property</span></span>

  
  
<span data-ttu-id="1683e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1683e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1683e-105">指定的事件是全天。</span><span class="sxs-lookup"><span data-stu-id="1683e-105">Specifies whether or not the event is all day.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1683e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1683e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1683e-107">dispidApptSubType</span><span class="sxs-lookup"><span data-stu-id="1683e-107">dispidApptSubType</span></span>  <br/> |
|<span data-ttu-id="1683e-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="1683e-108">Property set:</span></span>  <br/> |<span data-ttu-id="1683e-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="1683e-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="1683e-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="1683e-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="1683e-111">0x00008215</span><span class="sxs-lookup"><span data-stu-id="1683e-111">0x00008215</span></span>  <br/> |
|<span data-ttu-id="1683e-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1683e-112">Data type:</span></span>  <br/> |<span data-ttu-id="1683e-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="1683e-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="1683e-114">区域：</span><span class="sxs-lookup"><span data-stu-id="1683e-114">Area:</span></span>  <br/> |<span data-ttu-id="1683e-115">日历</span><span class="sxs-lookup"><span data-stu-id="1683e-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1683e-116">说明</span><span class="sxs-lookup"><span data-stu-id="1683e-116">Remarks</span></span>

<span data-ttu-id="1683e-117">此属性指定的事件是全天事件，指定的用户。</span><span class="sxs-lookup"><span data-stu-id="1683e-117">This property specifies whether or not the event is an all-day event, as specified by the user.</span></span> <span data-ttu-id="1683e-118">值为 TRUE 指示事件是全天事件，在这种情况下的开始时间和结束时间必须午夜以便持续时间为 24 小时的倍数，并为至少 24 个小时。</span><span class="sxs-lookup"><span data-stu-id="1683e-118">A value of TRUE indicates that the event is an all-day event, in which case the start time and end time must be midnight so that the duration is a multiple of 24 hours and is at least 24 hours.</span></span> <span data-ttu-id="1683e-119">值为 FALSE 或不存在此属性指示该事件不是全天事件。</span><span class="sxs-lookup"><span data-stu-id="1683e-119">A value of FALSE or the absence of this property indicates the event is not an all-day event.</span></span> <span data-ttu-id="1683e-120">在客户端或服务器必须时用户碰巧创建 24 小时的事件，即使事件开始和结束午夜推断的值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="1683e-120">The client or server must not infer the value as TRUE when a user happens to create an event that is 24 hours, even if the event starts and ends at midnight.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="1683e-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="1683e-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1683e-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="1683e-122">Protocol specifications</span></span>

<span data-ttu-id="1683e-123">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1683e-123">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1683e-124">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="1683e-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1683e-125">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1683e-125">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1683e-126">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="1683e-126">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1683e-127">头文件</span><span class="sxs-lookup"><span data-stu-id="1683e-127">Header files</span></span>

<span data-ttu-id="1683e-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1683e-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="1683e-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1683e-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1683e-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1683e-130">See also</span></span>



[<span data-ttu-id="1683e-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1683e-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1683e-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1683e-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1683e-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1683e-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1683e-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1683e-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

