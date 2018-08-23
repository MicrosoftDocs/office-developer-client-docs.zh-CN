---
title: PidLidAppointmentRecur 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentRecur
api_type:
- COM
ms.assetid: 56d6240f-d07b-48d1-aef0-bf57078ea6c3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: da38c8f04c0ffe6b4b26551cb23e84275900fcb4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563056"
---
# <a name="pidlidappointmentrecur-canonical-property"></a><span data-ttu-id="b85aa-103">PidLidAppointmentRecur 规范属性</span><span class="sxs-lookup"><span data-stu-id="b85aa-103">PidLidAppointmentRecur Canonical Property</span></span>

  
  
<span data-ttu-id="b85aa-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b85aa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b85aa-105">指定定期系列时使用的定期模式和[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)中指定的区域之一发生的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="b85aa-105">Specifies the dates and times when a recurring series occurs by using one of the recurrence patterns and ranges that are specified in [[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b85aa-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b85aa-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b85aa-107">dispidApptRecur</span><span class="sxs-lookup"><span data-stu-id="b85aa-107">dispidApptRecur</span></span>  <br/> |
|<span data-ttu-id="b85aa-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="b85aa-108">Property set:</span></span>  <br/> |<span data-ttu-id="b85aa-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="b85aa-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="b85aa-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="b85aa-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="b85aa-111">0x00008216</span><span class="sxs-lookup"><span data-stu-id="b85aa-111">0x00008216</span></span>  <br/> |
|<span data-ttu-id="b85aa-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b85aa-112">Data type:</span></span>  <br/> |<span data-ttu-id="b85aa-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="b85aa-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="b85aa-114">区域：</span><span class="sxs-lookup"><span data-stu-id="b85aa-114">Area:</span></span>  <br/> |<span data-ttu-id="b85aa-115">日历</span><span class="sxs-lookup"><span data-stu-id="b85aa-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b85aa-116">注解</span><span class="sxs-lookup"><span data-stu-id="b85aa-116">Remarks</span></span>

<span data-ttu-id="b85aa-117">此属性指定定期系列时使用的定期模式之一，发生此事件和区域中的详细说明[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="b85aa-117">This property specifies the dates and times when a recurring series occurs by using one of the recurrence patterns and ranges detailed in [[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx).</span></span> <span data-ttu-id="b85aa-118">此属性的值还包含有关修改和删除例外; 信息如日期、 主题、 位置和其他几个属性的异常的信息。</span><span class="sxs-lookup"><span data-stu-id="b85aa-118">The value of this property also contains information about both modified and deleted exceptions; information such as dates, subject, location, and several other properties of exceptions.</span></span> <span data-ttu-id="b85aa-119">此属性的定期日历项目中的二进制数据存储为**AppointmentRecurrencePattern**结构。</span><span class="sxs-lookup"><span data-stu-id="b85aa-119">The binary data in this property for recurring calendar items is stored as the **AppointmentRecurrencePattern** structure.</span></span> <span data-ttu-id="b85aa-120">此属性必须存在在单个实例日历项目。</span><span class="sxs-lookup"><span data-stu-id="b85aa-120">This property must not exist on single instance calendar items.</span></span> 
  
<span data-ttu-id="b85aa-121">有一些限制到定期事件：</span><span class="sxs-lookup"><span data-stu-id="b85aa-121">There are some limitations to recurrences:</span></span>
  
- <span data-ttu-id="b85aa-122">在同一天必须启动多个实例。</span><span class="sxs-lookup"><span data-stu-id="b85aa-122">Multiple instances must not start on the same day.</span></span>
    
- <span data-ttu-id="b85aa-123">匹配项必须不重叠。</span><span class="sxs-lookup"><span data-stu-id="b85aa-123">Occurrences must not overlap.</span></span> <span data-ttu-id="b85aa-124">具体而言，之后将前一个实例的末尾和定期系列中的下一个实例的开始日期必须发生异常修改实例定期系列中的开始日期。</span><span class="sxs-lookup"><span data-stu-id="b85aa-124">Specifically, an exception that modifies the start date of an instance in the recurring series must occur on a date that is after the end of the prior instance and the start of the next instance in the recurring series.</span></span> <span data-ttu-id="b85aa-125">True 如果定期系列中的前一个或下一个实例异常相同。</span><span class="sxs-lookup"><span data-stu-id="b85aa-125">The same is true if the prior or next instances in the recurring series are exceptions.</span></span>
    
<span data-ttu-id="b85aa-126">定期系列的计划取决于其定期模式和范围。</span><span class="sxs-lookup"><span data-stu-id="b85aa-126">The schedule of a recurring series is determined by its recurrence pattern and range.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="b85aa-127">相关资源</span><span class="sxs-lookup"><span data-stu-id="b85aa-127">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b85aa-128">协议规范</span><span class="sxs-lookup"><span data-stu-id="b85aa-128">Protocol specifications</span></span>

<span data-ttu-id="b85aa-129">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b85aa-129">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b85aa-130">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b85aa-130">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b85aa-131">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b85aa-131">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b85aa-132">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="b85aa-132">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="b85aa-133">[[MS OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b85aa-133">[[MS-OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b85aa-134">指定属性和电子邮件和其他对象提醒的交互模型。</span><span class="sxs-lookup"><span data-stu-id="b85aa-134">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b85aa-135">头文件</span><span class="sxs-lookup"><span data-stu-id="b85aa-135">Header files</span></span>

<span data-ttu-id="b85aa-136">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b85aa-136">Mapidefs.h</span></span>
  
> <span data-ttu-id="b85aa-137">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b85aa-137">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b85aa-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b85aa-138">See also</span></span>



[<span data-ttu-id="b85aa-139">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b85aa-139">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b85aa-140">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b85aa-140">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b85aa-141">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b85aa-141">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b85aa-142">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b85aa-142">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

