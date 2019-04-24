---
title: PidLidAppointmentStartWhole 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentStartWhole
api_type:
- COM
ms.assetid: e5e8ed98-57af-40d0-85c4-9d9832626e6b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6f9fb9c3f02e66fd01e89742edcfba7391c36e3e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345372"
---
# <a name="pidlidappointmentstartwhole-canonical-property"></a><span data-ttu-id="1136b-103">PidLidAppointmentStartWhole 规范属性</span><span class="sxs-lookup"><span data-stu-id="1136b-103">PidLidAppointmentStartWhole Canonical Property</span></span>

  
  
<span data-ttu-id="1136b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1136b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1136b-105">表示约会开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="1136b-105">Represents the date and time when an appointment begins.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1136b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1136b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1136b-107">dispidApptStartWhole</span><span class="sxs-lookup"><span data-stu-id="1136b-107">dispidApptStartWhole</span></span>  <br/> |
|<span data-ttu-id="1136b-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="1136b-108">Property set:</span></span>  <br/> |<span data-ttu-id="1136b-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="1136b-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="1136b-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="1136b-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="1136b-111">0x0000820D</span><span class="sxs-lookup"><span data-stu-id="1136b-111">0x0000820D</span></span>  <br/> |
|<span data-ttu-id="1136b-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1136b-112">Data type:</span></span>  <br/> |<span data-ttu-id="1136b-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="1136b-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="1136b-114">区域：</span><span class="sxs-lookup"><span data-stu-id="1136b-114">Area:</span></span>  <br/> |<span data-ttu-id="1136b-115">日历</span><span class="sxs-lookup"><span data-stu-id="1136b-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1136b-116">注解</span><span class="sxs-lookup"><span data-stu-id="1136b-116">Remarks</span></span>

<span data-ttu-id="1136b-117">此属性指定事件的开始日期和时间。</span><span class="sxs-lookup"><span data-stu-id="1136b-117">This property specifies the start date and time of the event.</span></span> <span data-ttu-id="1136b-118">此属性必须采用协调通用时间 (UTC), 并且必须小于**dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="1136b-118">This property must be in Coordinated Universal Time (UTC) and must be less than the value of the **dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) property.</span></span> <span data-ttu-id="1136b-119">对于定期系列, 此属性是第一个实例根据定期模式的开始日期和时间。</span><span class="sxs-lookup"><span data-stu-id="1136b-119">For a recurring series, this property is the start date and time of the first instance according to the recurrence pattern.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="1136b-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="1136b-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1136b-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="1136b-121">Protocol specifications</span></span>

<span data-ttu-id="1136b-122">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1136b-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1136b-123">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="1136b-123">Provides property set definition and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1136b-124">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1136b-124">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1136b-125">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="1136b-125">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1136b-126">头文件</span><span class="sxs-lookup"><span data-stu-id="1136b-126">Header files</span></span>

<span data-ttu-id="1136b-127">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="1136b-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="1136b-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1136b-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1136b-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1136b-129">See also</span></span>



[<span data-ttu-id="1136b-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1136b-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1136b-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1136b-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1136b-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1136b-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1136b-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1136b-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

