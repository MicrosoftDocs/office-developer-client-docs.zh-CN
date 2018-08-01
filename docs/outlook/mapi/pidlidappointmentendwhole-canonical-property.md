---
title: PidLidAppointmentEndWhole 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentEndWhole
api_type:
- COM
ms.assetid: f6fd33d6-04fb-4801-a004-fb80a14ca79d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 155300d3c3043713ce2197d3b70843c589d777e8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776596"
---
# <a name="pidlidappointmentendwhole-canonical-property"></a><span data-ttu-id="9faba-103">PidLidAppointmentEndWhole 规范属性</span><span class="sxs-lookup"><span data-stu-id="9faba-103">PidLidAppointmentEndWhole Canonical Property</span></span>

  
  
<span data-ttu-id="9faba-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9faba-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9faba-105">表示的日期和约会结束的时间。</span><span class="sxs-lookup"><span data-stu-id="9faba-105">Represents the date and time that an appointment ends.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9faba-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9faba-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9faba-107">dispidApptEndWhole</span><span class="sxs-lookup"><span data-stu-id="9faba-107">dispidApptEndWhole</span></span>  <br/> |
|<span data-ttu-id="9faba-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="9faba-108">Property set:</span></span>  <br/> |<span data-ttu-id="9faba-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="9faba-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="9faba-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="9faba-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="9faba-111">0x0000820E</span><span class="sxs-lookup"><span data-stu-id="9faba-111">0x0000820E</span></span>  <br/> |
|<span data-ttu-id="9faba-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9faba-112">Data type:</span></span>  <br/> |<span data-ttu-id="9faba-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="9faba-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="9faba-114">区域：</span><span class="sxs-lookup"><span data-stu-id="9faba-114">Area:</span></span>  <br/> |<span data-ttu-id="9faba-115">日历</span><span class="sxs-lookup"><span data-stu-id="9faba-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9faba-116">说明</span><span class="sxs-lookup"><span data-stu-id="9faba-116">Remarks</span></span>

<span data-ttu-id="9faba-117">此属性对应于 Microsoft Office Outlook 对象模型中的约会的**dispidApptEndWhole**属性。</span><span class="sxs-lookup"><span data-stu-id="9faba-117">This property corresponds to the **dispidApptEndWhole** property of the appointment in the Microsoft Office Outlook object model.</span></span> 
  
<span data-ttu-id="9faba-118">此选项指定的结束日期和时间事件;它必须是以协调世界时 (UTC)，并且必须大于**dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="9faba-118">This specifies the end date and time for the event; it must be in Coordinated Universal Time (UTC) and must be greater than the value of the **dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) property.</span></span> <span data-ttu-id="9faba-119">对于定期系列， **dispidApptEndWhole**属性是的结束日期和时间根据定期模式的第一个实例。</span><span class="sxs-lookup"><span data-stu-id="9faba-119">For a recurring series, the **dispidApptEndWhole** property is the end date and time of the first instance according to the recurrence pattern.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="9faba-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="9faba-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="9faba-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="9faba-121">Protocol specifications</span></span>

<span data-ttu-id="9faba-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9faba-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9faba-123">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="9faba-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="9faba-124">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9faba-124">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9faba-125">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="9faba-125">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="9faba-126">头文件</span><span class="sxs-lookup"><span data-stu-id="9faba-126">Header files</span></span>

<span data-ttu-id="9faba-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9faba-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="9faba-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9faba-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9faba-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9faba-129">See also</span></span>



[<span data-ttu-id="9faba-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9faba-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9faba-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9faba-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9faba-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9faba-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9faba-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9faba-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

