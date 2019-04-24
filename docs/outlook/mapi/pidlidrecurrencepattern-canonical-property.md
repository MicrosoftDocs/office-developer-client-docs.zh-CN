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
ms.openlocfilehash: d94ac430df54fc03d96ac761c53ca20201d899c2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315930"
---
# <a name="pidlidrecurrencepattern-canonical-property"></a><span data-ttu-id="9f4c1-103">PidLidRecurrencePattern 规范属性</span><span class="sxs-lookup"><span data-stu-id="9f4c1-103">PidLidRecurrencePattern Canonical Property</span></span>

  
  
<span data-ttu-id="9f4c1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9f4c1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9f4c1-105">指定日历对象的定期模式的说明。</span><span class="sxs-lookup"><span data-stu-id="9f4c1-105">Specifies a description of the recurrence pattern of the calendar object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9f4c1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9f4c1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9f4c1-107">dispidRecurPattern</span><span class="sxs-lookup"><span data-stu-id="9f4c1-107">dispidRecurPattern</span></span>  <br/> |
|<span data-ttu-id="9f4c1-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="9f4c1-108">Property set:</span></span>  <br/> |<span data-ttu-id="9f4c1-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="9f4c1-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="9f4c1-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="9f4c1-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="9f4c1-111">0x00008232</span><span class="sxs-lookup"><span data-stu-id="9f4c1-111">0x00008232</span></span>  <br/> |
|<span data-ttu-id="9f4c1-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9f4c1-112">Data type:</span></span>  <br/> |<span data-ttu-id="9f4c1-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="9f4c1-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="9f4c1-114">区域：</span><span class="sxs-lookup"><span data-stu-id="9f4c1-114">Area:</span></span>  <br/> |<span data-ttu-id="9f4c1-115">日历</span><span class="sxs-lookup"><span data-stu-id="9f4c1-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9f4c1-116">注解</span><span class="sxs-lookup"><span data-stu-id="9f4c1-116">Remarks</span></span>

<span data-ttu-id="9f4c1-117">如果设置了此属性, 则必须将其设置为**dispidApptRecur** ([PidLidAppointmentRecur](pidlidappointmentrecur-canonical-property.md)) 属性所指定的定期的说明。</span><span class="sxs-lookup"><span data-stu-id="9f4c1-117">If this property is set, it must be set to a description of the recurrence that is specified by the **dispidApptRecur** ([PidLidAppointmentRecur](pidlidappointmentrecur-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="9f4c1-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="9f4c1-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="9f4c1-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="9f4c1-119">Protocol specifications</span></span>

<span data-ttu-id="9f4c1-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9f4c1-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9f4c1-121">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="9f4c1-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="9f4c1-122">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9f4c1-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9f4c1-123">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="9f4c1-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="9f4c1-124">头文件</span><span class="sxs-lookup"><span data-stu-id="9f4c1-124">Header files</span></span>

<span data-ttu-id="9f4c1-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="9f4c1-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="9f4c1-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9f4c1-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9f4c1-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f4c1-127">See also</span></span>



[<span data-ttu-id="9f4c1-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9f4c1-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9f4c1-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9f4c1-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9f4c1-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9f4c1-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9f4c1-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9f4c1-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

