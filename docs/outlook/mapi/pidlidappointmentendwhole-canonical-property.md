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
ms.openlocfilehash: eaff90de919c1bdc04983bce32a2aa808ae56013
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358896"
---
# <a name="pidlidappointmentendwhole-canonical-property"></a><span data-ttu-id="3fb97-103">PidLidAppointmentEndWhole 规范属性</span><span class="sxs-lookup"><span data-stu-id="3fb97-103">PidLidAppointmentEndWhole Canonical Property</span></span>

  
  
<span data-ttu-id="3fb97-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3fb97-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3fb97-105">表示约会结束的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="3fb97-105">Represents the date and time that an appointment ends.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3fb97-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3fb97-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3fb97-107">dispidApptEndWhole</span><span class="sxs-lookup"><span data-stu-id="3fb97-107">dispidApptEndWhole</span></span>  <br/> |
|<span data-ttu-id="3fb97-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="3fb97-108">Property set:</span></span>  <br/> |<span data-ttu-id="3fb97-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="3fb97-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="3fb97-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="3fb97-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="3fb97-111">0x0000820E</span><span class="sxs-lookup"><span data-stu-id="3fb97-111">0x0000820E</span></span>  <br/> |
|<span data-ttu-id="3fb97-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3fb97-112">Data type:</span></span>  <br/> |<span data-ttu-id="3fb97-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="3fb97-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="3fb97-114">区域：</span><span class="sxs-lookup"><span data-stu-id="3fb97-114">Area:</span></span>  <br/> |<span data-ttu-id="3fb97-115">日历</span><span class="sxs-lookup"><span data-stu-id="3fb97-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3fb97-116">注解</span><span class="sxs-lookup"><span data-stu-id="3fb97-116">Remarks</span></span>

<span data-ttu-id="3fb97-117">此属性对应于 Microsoft Office Outlook 对象模型中的约会的**dispidApptEndWhole**属性。</span><span class="sxs-lookup"><span data-stu-id="3fb97-117">This property corresponds to the **dispidApptEndWhole** property of the appointment in the Microsoft Office Outlook object model.</span></span> 
  
<span data-ttu-id="3fb97-118">这将指定事件的结束日期和时间;它必须采用协调通用时间 (UTC), 并且必须大于**dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="3fb97-118">This specifies the end date and time for the event; it must be in Coordinated Universal Time (UTC) and must be greater than the value of the **dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) property.</span></span> <span data-ttu-id="3fb97-119">对于定期系列, **dispidApptEndWhole**属性是第一个实例根据定期模式的结束日期和时间。</span><span class="sxs-lookup"><span data-stu-id="3fb97-119">For a recurring series, the **dispidApptEndWhole** property is the end date and time of the first instance according to the recurrence pattern.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="3fb97-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="3fb97-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3fb97-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="3fb97-121">Protocol specifications</span></span>

<span data-ttu-id="3fb97-122">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3fb97-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3fb97-123">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="3fb97-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="3fb97-124">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3fb97-124">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3fb97-125">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="3fb97-125">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3fb97-126">头文件</span><span class="sxs-lookup"><span data-stu-id="3fb97-126">Header files</span></span>

<span data-ttu-id="3fb97-127">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="3fb97-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="3fb97-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3fb97-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3fb97-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3fb97-129">See also</span></span>



[<span data-ttu-id="3fb97-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3fb97-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3fb97-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3fb97-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3fb97-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3fb97-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3fb97-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3fb97-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

