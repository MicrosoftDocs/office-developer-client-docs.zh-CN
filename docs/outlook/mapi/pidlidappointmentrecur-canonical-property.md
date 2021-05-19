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
ms.openlocfilehash: de50616664048af6b931a09df7c65461e9ee3399
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331778"
---
# <a name="pidlidappointmentrecur-canonical-property"></a><span data-ttu-id="513aa-103">PidLidAppointmentRecur 规范属性</span><span class="sxs-lookup"><span data-stu-id="513aa-103">PidLidAppointmentRecur Canonical Property</span></span>

  
  
<span data-ttu-id="513aa-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="513aa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="513aa-105">使用 [[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)中指定的定期模式和范围之一指定定期系列的发生日期和时间。</span><span class="sxs-lookup"><span data-stu-id="513aa-105">Specifies the dates and times when a recurring series occurs by using one of the recurrence patterns and ranges that are specified in [[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="513aa-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="513aa-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="513aa-107">dispidApptRecur</span><span class="sxs-lookup"><span data-stu-id="513aa-107">dispidApptRecur</span></span>  <br/> |
|<span data-ttu-id="513aa-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="513aa-108">Property set:</span></span>  <br/> |<span data-ttu-id="513aa-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="513aa-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="513aa-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="513aa-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="513aa-111">0x00008216</span><span class="sxs-lookup"><span data-stu-id="513aa-111">0x00008216</span></span>  <br/> |
|<span data-ttu-id="513aa-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="513aa-112">Data type:</span></span>  <br/> |<span data-ttu-id="513aa-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="513aa-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="513aa-114">区域：</span><span class="sxs-lookup"><span data-stu-id="513aa-114">Area:</span></span>  <br/> |<span data-ttu-id="513aa-115">日历</span><span class="sxs-lookup"><span data-stu-id="513aa-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="513aa-116">备注</span><span class="sxs-lookup"><span data-stu-id="513aa-116">Remarks</span></span>

<span data-ttu-id="513aa-117">此属性通过使用 [[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)中详述的定期模式和范围之一来指定发生定期系列的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="513aa-117">This property specifies the dates and times when a recurring series occurs by using one of the recurrence patterns and ranges detailed in [[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx).</span></span> <span data-ttu-id="513aa-118">此属性的值还包含有关修改和删除的异常的信息;信息，例如日期、主题、位置和例外的其他几个属性。</span><span class="sxs-lookup"><span data-stu-id="513aa-118">The value of this property also contains information about both modified and deleted exceptions; information such as dates, subject, location, and several other properties of exceptions.</span></span> <span data-ttu-id="513aa-119">此属性中定期日历项目的二进制数据存储为 **AppointmentRecurrencePattern** 结构。</span><span class="sxs-lookup"><span data-stu-id="513aa-119">The binary data in this property for recurring calendar items is stored as the **AppointmentRecurrencePattern** structure.</span></span> <span data-ttu-id="513aa-120">此属性不能存在于单个实例日历项目上。</span><span class="sxs-lookup"><span data-stu-id="513aa-120">This property must not exist on single instance calendar items.</span></span> 
  
<span data-ttu-id="513aa-121">定期存在一些限制：</span><span class="sxs-lookup"><span data-stu-id="513aa-121">There are some limitations to recurrences:</span></span>
  
- <span data-ttu-id="513aa-122">多个实例不得在同一天启动。</span><span class="sxs-lookup"><span data-stu-id="513aa-122">Multiple instances must not start on the same day.</span></span>
    
- <span data-ttu-id="513aa-123">事件不得重叠。</span><span class="sxs-lookup"><span data-stu-id="513aa-123">Occurrences must not overlap.</span></span> <span data-ttu-id="513aa-124">具体而言，修改定期系列中实例的开始日期的异常必须在上一实例结束之后和定期系列中下一个实例的开始日期发生。</span><span class="sxs-lookup"><span data-stu-id="513aa-124">Specifically, an exception that modifies the start date of an instance in the recurring series must occur on a date that is after the end of the prior instance and the start of the next instance in the recurring series.</span></span> <span data-ttu-id="513aa-125">如果定期系列中的上一个实例或下一个实例为例外，则同样如此。</span><span class="sxs-lookup"><span data-stu-id="513aa-125">The same is true if the prior or next instances in the recurring series are exceptions.</span></span>
    
<span data-ttu-id="513aa-126">定期系列的日程安排由定期系列的定期模式范围。</span><span class="sxs-lookup"><span data-stu-id="513aa-126">The schedule of a recurring series is determined by its recurrence pattern and range.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="513aa-127">相关资源</span><span class="sxs-lookup"><span data-stu-id="513aa-127">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="513aa-128">协议规范</span><span class="sxs-lookup"><span data-stu-id="513aa-128">Protocol specifications</span></span>

<span data-ttu-id="513aa-129">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="513aa-129">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="513aa-130">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="513aa-130">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="513aa-131">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="513aa-131">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="513aa-132">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="513aa-132">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="513aa-133">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="513aa-133">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="513aa-134">指定电子邮件和其他对象提醒的属性和交互模型。</span><span class="sxs-lookup"><span data-stu-id="513aa-134">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="513aa-135">头文件</span><span class="sxs-lookup"><span data-stu-id="513aa-135">Header files</span></span>

<span data-ttu-id="513aa-136">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="513aa-136">Mapidefs.h</span></span>
  
> <span data-ttu-id="513aa-137">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="513aa-137">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="513aa-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="513aa-138">See also</span></span>



[<span data-ttu-id="513aa-139">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="513aa-139">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="513aa-140">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="513aa-140">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="513aa-141">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="513aa-141">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="513aa-142">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="513aa-142">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

