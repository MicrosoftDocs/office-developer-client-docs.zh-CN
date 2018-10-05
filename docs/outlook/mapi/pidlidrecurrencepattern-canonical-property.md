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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386297"
---
# <a name="pidlidrecurrencepattern-canonical-property"></a><span data-ttu-id="43d81-103">PidLidRecurrencePattern 规范属性</span><span class="sxs-lookup"><span data-stu-id="43d81-103">PidLidRecurrencePattern Canonical Property</span></span>

  
  
<span data-ttu-id="43d81-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="43d81-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="43d81-105">指定定期模式的 calendar 对象的说明。</span><span class="sxs-lookup"><span data-stu-id="43d81-105">Specifies a description of the recurrence pattern of the calendar object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="43d81-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="43d81-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="43d81-107">dispidRecurPattern</span><span class="sxs-lookup"><span data-stu-id="43d81-107">dispidRecurPattern</span></span>  <br/> |
|<span data-ttu-id="43d81-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="43d81-108">Property set:</span></span>  <br/> |<span data-ttu-id="43d81-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="43d81-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="43d81-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="43d81-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="43d81-111">0x00008232</span><span class="sxs-lookup"><span data-stu-id="43d81-111">0x00008232</span></span>  <br/> |
|<span data-ttu-id="43d81-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="43d81-112">Data type:</span></span>  <br/> |<span data-ttu-id="43d81-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="43d81-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="43d81-114">区域：</span><span class="sxs-lookup"><span data-stu-id="43d81-114">Area:</span></span>  <br/> |<span data-ttu-id="43d81-115">日历</span><span class="sxs-lookup"><span data-stu-id="43d81-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="43d81-116">说明</span><span class="sxs-lookup"><span data-stu-id="43d81-116">Remarks</span></span>

<span data-ttu-id="43d81-117">如果设置此属性，它必须设置为**dispidApptRecur** ([PidLidAppointmentRecur](pidlidappointmentrecur-canonical-property.md)) 属性指定重复的说明。</span><span class="sxs-lookup"><span data-stu-id="43d81-117">If this property is set, it must be set to a description of the recurrence that is specified by the **dispidApptRecur** ([PidLidAppointmentRecur](pidlidappointmentrecur-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="43d81-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="43d81-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="43d81-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="43d81-119">Protocol specifications</span></span>

<span data-ttu-id="43d81-120">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="43d81-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="43d81-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="43d81-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="43d81-122">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="43d81-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="43d81-123">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="43d81-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="43d81-124">头文件</span><span class="sxs-lookup"><span data-stu-id="43d81-124">Header files</span></span>

<span data-ttu-id="43d81-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="43d81-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="43d81-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="43d81-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="43d81-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43d81-127">See also</span></span>



[<span data-ttu-id="43d81-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="43d81-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="43d81-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="43d81-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="43d81-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="43d81-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="43d81-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="43d81-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

