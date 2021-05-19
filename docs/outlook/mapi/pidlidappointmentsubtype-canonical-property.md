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
ms.openlocfilehash: 921d7d8defbdae66bc48072d757f4f58b7d656f0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345414"
---
# <a name="pidlidappointmentsubtype-canonical-property"></a><span data-ttu-id="d1b9e-103">PidLidAppointmentSubType 规范属性</span><span class="sxs-lookup"><span data-stu-id="d1b9e-103">PidLidAppointmentSubType Canonical Property</span></span>

  
  
<span data-ttu-id="d1b9e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d1b9e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d1b9e-105">指定事件是否全天发生。</span><span class="sxs-lookup"><span data-stu-id="d1b9e-105">Specifies whether or not the event is all day.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d1b9e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d1b9e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d1b9e-107">dispidApptSubType</span><span class="sxs-lookup"><span data-stu-id="d1b9e-107">dispidApptSubType</span></span>  <br/> |
|<span data-ttu-id="d1b9e-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="d1b9e-108">Property set:</span></span>  <br/> |<span data-ttu-id="d1b9e-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="d1b9e-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="d1b9e-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="d1b9e-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="d1b9e-111">0x00008215</span><span class="sxs-lookup"><span data-stu-id="d1b9e-111">0x00008215</span></span>  <br/> |
|<span data-ttu-id="d1b9e-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d1b9e-112">Data type:</span></span>  <br/> |<span data-ttu-id="d1b9e-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="d1b9e-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="d1b9e-114">区域：</span><span class="sxs-lookup"><span data-stu-id="d1b9e-114">Area:</span></span>  <br/> |<span data-ttu-id="d1b9e-115">日历</span><span class="sxs-lookup"><span data-stu-id="d1b9e-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d1b9e-116">备注</span><span class="sxs-lookup"><span data-stu-id="d1b9e-116">Remarks</span></span>

<span data-ttu-id="d1b9e-117">此属性指定事件是否是由用户指定的全天事件。</span><span class="sxs-lookup"><span data-stu-id="d1b9e-117">This property specifies whether or not the event is an all-day event, as specified by the user.</span></span> <span data-ttu-id="d1b9e-118">TRUE 值表示事件是全天事件，在这种情况下，开始时间和结束时间必须为午夜，以便持续时间为 24 小时，并且至少为 24 小时。</span><span class="sxs-lookup"><span data-stu-id="d1b9e-118">A value of TRUE indicates that the event is an all-day event, in which case the start time and end time must be midnight so that the duration is a multiple of 24 hours and is at least 24 hours.</span></span> <span data-ttu-id="d1b9e-119">FALSE 值或缺少此属性指示事件不是全天事件。</span><span class="sxs-lookup"><span data-stu-id="d1b9e-119">A value of FALSE or the absence of this property indicates the event is not an all-day event.</span></span> <span data-ttu-id="d1b9e-120">当用户恰好创建 24 小时的事件时，客户端或服务器不得将该值推断为 TRUE，即使该事件在午夜开始和结束也是如此。</span><span class="sxs-lookup"><span data-stu-id="d1b9e-120">The client or server must not infer the value as TRUE when a user happens to create an event that is 24 hours, even if the event starts and ends at midnight.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d1b9e-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="d1b9e-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d1b9e-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="d1b9e-122">Protocol specifications</span></span>

<span data-ttu-id="d1b9e-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d1b9e-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d1b9e-124">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="d1b9e-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d1b9e-125">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d1b9e-125">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d1b9e-126">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="d1b9e-126">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d1b9e-127">头文件</span><span class="sxs-lookup"><span data-stu-id="d1b9e-127">Header files</span></span>

<span data-ttu-id="d1b9e-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d1b9e-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="d1b9e-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d1b9e-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d1b9e-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1b9e-130">See also</span></span>



[<span data-ttu-id="d1b9e-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d1b9e-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d1b9e-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d1b9e-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d1b9e-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d1b9e-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d1b9e-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d1b9e-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

