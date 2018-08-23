---
title: PidLidRecurrencePattern 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidRecurrencePattern
api_type:
- COM
ms.assetid: ac21ba98-f16b-4365-9134-bca7748189ee
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 12a55ec4dfe0fb53a07aef73cb4e96771379e483
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589222"
---
# <a name="pidlidrecurrencepattern-canonical-property"></a><span data-ttu-id="87c2b-103">PidLidRecurrencePattern 规范属性</span><span class="sxs-lookup"><span data-stu-id="87c2b-103">PidLidRecurrencePattern Canonical Property</span></span>

  
  
<span data-ttu-id="87c2b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="87c2b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="87c2b-105">指定定期模式的 calendar 对象的说明。</span><span class="sxs-lookup"><span data-stu-id="87c2b-105">Specifies a description of the recurrence pattern of the calendar object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="87c2b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="87c2b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="87c2b-107">dispidRecurPattern</span><span class="sxs-lookup"><span data-stu-id="87c2b-107">dispidRecurPattern</span></span>  <br/> |
|<span data-ttu-id="87c2b-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="87c2b-108">Property set:</span></span>  <br/> |<span data-ttu-id="87c2b-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="87c2b-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="87c2b-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="87c2b-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="87c2b-111">0x00008232</span><span class="sxs-lookup"><span data-stu-id="87c2b-111">0x00008232</span></span>  <br/> |
|<span data-ttu-id="87c2b-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="87c2b-112">Data type:</span></span>  <br/> |<span data-ttu-id="87c2b-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="87c2b-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="87c2b-114">区域：</span><span class="sxs-lookup"><span data-stu-id="87c2b-114">Area:</span></span>  <br/> |<span data-ttu-id="87c2b-115">日历</span><span class="sxs-lookup"><span data-stu-id="87c2b-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="87c2b-116">注解</span><span class="sxs-lookup"><span data-stu-id="87c2b-116">Remarks</span></span>

<span data-ttu-id="87c2b-117">如果设置此属性，它必须设置为**dispidApptRecur** ([PidLidAppointmentRecur](pidlidappointmentrecur-canonical-property.md)) 属性指定重复的说明。</span><span class="sxs-lookup"><span data-stu-id="87c2b-117">If this property is set, it must be set to a description of the recurrence that is specified by the **dispidApptRecur** ([PidLidAppointmentRecur](pidlidappointmentrecur-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="87c2b-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="87c2b-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="87c2b-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="87c2b-119">Protocol specifications</span></span>

<span data-ttu-id="87c2b-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="87c2b-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="87c2b-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="87c2b-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="87c2b-122">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="87c2b-122">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="87c2b-123">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="87c2b-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="87c2b-124">头文件</span><span class="sxs-lookup"><span data-stu-id="87c2b-124">Header files</span></span>

<span data-ttu-id="87c2b-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="87c2b-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="87c2b-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="87c2b-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="87c2b-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87c2b-127">See also</span></span>



[<span data-ttu-id="87c2b-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="87c2b-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="87c2b-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="87c2b-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="87c2b-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="87c2b-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="87c2b-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="87c2b-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

