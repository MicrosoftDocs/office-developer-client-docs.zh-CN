---
title: PidLidAppointmentTimeZoneDefinitionStartDisplay 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentTimeZoneDefinitionStartDispl
api_type:
- COM
ms.assetid: 08239670-3211-420c-99d7-0056ed967cb8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6ca53633f0c1e5b226f7e03c8ee702d4cda7d115
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586793"
---
# <a name="pidlidappointmenttimezonedefinitionstartdisplay-canonical-property"></a><span data-ttu-id="df494-103">PidLidAppointmentTimeZoneDefinitionStartDisplay 规范属性</span><span class="sxs-lookup"><span data-stu-id="df494-103">PidLidAppointmentTimeZoneDefinitionStartDisplay Canonical Property</span></span>

  
  
<span data-ttu-id="df494-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="df494-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="df494-105">包含映射到的存储选择单实例约会或会议请求的开始时间时使用的时区的说明[TZDEFINITION](http://msdn.microsoft.com/library/0ae21571-2299-6407-807c-428668bb6798%28Office.15%29.aspx)结构持久化格式的流。</span><span class="sxs-lookup"><span data-stu-id="df494-105">Contains a stream that maps to the persisted format of a [TZDEFINITION](http://msdn.microsoft.com/library/0ae21571-2299-6407-807c-428668bb6798%28Office.15%29.aspx) structure, which stores the description for the time zone that is used when the start time of a single-instance appointment or meeting request is selected.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="df494-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="df494-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="df494-107">dispidApptTZDefStartDisplay</span><span class="sxs-lookup"><span data-stu-id="df494-107">dispidApptTZDefStartDisplay</span></span>  <br/> |
|<span data-ttu-id="df494-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="df494-108">Property set:</span></span>  <br/> |<span data-ttu-id="df494-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="df494-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="df494-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="df494-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="df494-111">0x0000825E</span><span class="sxs-lookup"><span data-stu-id="df494-111">0x0000825E</span></span>  <br/> |
|<span data-ttu-id="df494-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="df494-112">Data type:</span></span>  <br/> |<span data-ttu-id="df494-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="df494-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="df494-114">区域：</span><span class="sxs-lookup"><span data-stu-id="df494-114">Area:</span></span>  <br/> |<span data-ttu-id="df494-115">日历</span><span class="sxs-lookup"><span data-stu-id="df494-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="df494-116">注解</span><span class="sxs-lookup"><span data-stu-id="df494-116">Remarks</span></span>

<span data-ttu-id="df494-117">Microsoft Office Outlook 2003 或更早版本和解决方案的基于上协作数据对象 (CDO) 1.2.1 （英文) 和 Outlook 或 Microsoft Exchange Server 已不运行日历更新工具存储的开始时间和结束时间的单实例约会和会议请求以协调世界时 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="df494-117">Microsoft Office Outlook 2003 or earlier, and solutions that are based on Collaboration Data Objects (CDO) 1.2.1 and that have not run the calendar update tool for Outlook or Microsoft Exchange Server, store the start time and end time of single-instance appointments and meeting requests in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="df494-118">这些客户端不存储在其中创建约会或会议请求的时区的任何信息。</span><span class="sxs-lookup"><span data-stu-id="df494-118">These clients do not store any information for the time zone in which the appointment or meeting request is created.</span></span>
  
<span data-ttu-id="df494-119">版本的 Microsoft Office Outlook 2007 和基于 CDO 1.2.1 （英文) 的解决方案运行 Outlook 或 Exchange Server 日历更新工具相 Outlook 使用此属性存储的开始时间的时区。</span><span class="sxs-lookup"><span data-stu-id="df494-119">Versions of Outlook since Microsoft Office Outlook 2007, and solutions based on CDO 1.2.1 that have run the Outlook or Exchange Server calendar update tool use this property to store the time zone for the start time.</span></span> <span data-ttu-id="df494-120">**DispidApptTZDefStartDisplay**属性显示该约会或会议中原始时区安排了它。</span><span class="sxs-lookup"><span data-stu-id="df494-120">The **dispidApptTZDefStartDisplay** property shows the appointment or meeting in the original time zone that it was scheduled.</span></span> <span data-ttu-id="df494-121">如果更改时区的规则是否应调整的开始时间，它确定。</span><span class="sxs-lookup"><span data-stu-id="df494-121">It determines whether the start time should be adjusted if the rules of the time zone change.</span></span> <span data-ttu-id="df494-122">如果该属性不存在，则假定当前的本地时区。</span><span class="sxs-lookup"><span data-stu-id="df494-122">If this property is missing, the current local time zone is assumed.</span></span> <span data-ttu-id="df494-123">此属性用于显示仅并不用于定期扩展。</span><span class="sxs-lookup"><span data-stu-id="df494-123">This property is used for display purposes only and is not used in recurrence expansion.</span></span> 
  
<span data-ttu-id="df494-124">分析程序必须注意，它读取此属性，从获取流或时它所**TZDEFINITION**持久化到承诺如**dispidApptTZDefStartDisplay**二进制属性的流。</span><span class="sxs-lookup"><span data-stu-id="df494-124">A parser must be careful when it reads a stream obtained from this property, or when it persists **TZDEFINITION** to a stream for commitment to a binary property such as **dispidApptTZDefStartDisplay**.</span></span> <span data-ttu-id="df494-125">有关详细信息，请参阅[关于保留 TZDEFINITION 到流提交到二进制属性](http://msdn.microsoft.com/library/0dec535d-d48f-39a5-97d5-0bd109134b3b%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="df494-125">For more information, see [About persisting TZDEFINITION to a stream to commit to a binary property](http://msdn.microsoft.com/library/0dec535d-d48f-39a5-97d5-0bd109134b3b%28Office.15%29.aspx).</span></span>
  
<span data-ttu-id="df494-126">此属性指定时区属性的信息的**dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="df494-126">This property specifies time zone information for the **dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) property.</span></span> <span data-ttu-id="df494-127">**DispidApptTZDefStartDisplay**的值用于将开始日期和时间从 UTC 转换为用于显示本地时区。</span><span class="sxs-lookup"><span data-stu-id="df494-127">The value of **dispidApptTZDefStartDisplay** is used to convert the start date and time from UTC to the local time zone for display purposes.</span></span> <span data-ttu-id="df494-128">为此属性指定每个**TZRULE** ，不得设置 TZRULE_FLAG_RECUR_CURRENT_TZREG 标志。</span><span class="sxs-lookup"><span data-stu-id="df494-128">For each **TZRULE** specified by this property, the TZRULE_FLAG_RECUR_CURRENT_TZREG flag must not be set.</span></span> <span data-ttu-id="df494-129">例如，如果**TZRULE**是有效的规则，字段， **TZRULE**的值必须是"0x0002";否则，它必须是"0x0000"。</span><span class="sxs-lookup"><span data-stu-id="df494-129">For example, if the **TZRULE** is the effective rule, the value of the field, **TZRULE** must be "0x0002"; otherwise, it must be "0x0000".</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="df494-130">相关资源</span><span class="sxs-lookup"><span data-stu-id="df494-130">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="df494-131">协议规范</span><span class="sxs-lookup"><span data-stu-id="df494-131">Protocol specifications</span></span>

<span data-ttu-id="df494-132">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="df494-132">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="df494-133">提供属性集定义和引用相关的 Exchange Server 协议规范正在</span><span class="sxs-lookup"><span data-stu-id="df494-133">Provides property set definitions and references to related Exchange Server protocol specifications..</span></span>
    
<span data-ttu-id="df494-134">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="df494-134">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="df494-135">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="df494-135">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="df494-136">头文件</span><span class="sxs-lookup"><span data-stu-id="df494-136">Header files</span></span>

<span data-ttu-id="df494-137">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="df494-137">Mapidefs.h</span></span>
  
> <span data-ttu-id="df494-138">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="df494-138">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="df494-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df494-139">See also</span></span>



[<span data-ttu-id="df494-140">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="df494-140">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="df494-141">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="df494-141">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="df494-142">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="df494-142">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="df494-143">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="df494-143">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

