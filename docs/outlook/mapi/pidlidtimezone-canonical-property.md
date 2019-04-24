---
title: PidLidTimeZone 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTimeZone
api_type:
- COM
ms.assetid: ffbab371-1a1d-4aa4-ad31-17549a74513c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b62779567a7dbd298fdd313e90b13fb223e4e47e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319269"
---
# <a name="pidlidtimezone-canonical-property"></a><span data-ttu-id="7d180-103">PidLidTimeZone 规范属性</span><span class="sxs-lookup"><span data-stu-id="7d180-103">PidLidTimeZone Canonical Property</span></span>

  
  
<span data-ttu-id="7d180-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7d180-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7d180-105">指定有关定期会议的时区的信息。</span><span class="sxs-lookup"><span data-stu-id="7d180-105">Specifies information about the time zone of a recurring meeting.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7d180-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7d180-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7d180-107">LID_TIME_ZONE</span><span class="sxs-lookup"><span data-stu-id="7d180-107">LID_TIME_ZONE</span></span>  <br/> |
|<span data-ttu-id="7d180-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="7d180-108">Property set:</span></span>  <br/> |<span data-ttu-id="7d180-109">PSETID_Meeting</span><span class="sxs-lookup"><span data-stu-id="7d180-109">PSETID_Meeting</span></span>  <br/> |
|<span data-ttu-id="7d180-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="7d180-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="7d180-111">0x0000000C</span><span class="sxs-lookup"><span data-stu-id="7d180-111">0x0000000C</span></span>  <br/> |
|<span data-ttu-id="7d180-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7d180-112">Data type:</span></span>  <br/> |<span data-ttu-id="7d180-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="7d180-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="7d180-114">区域：</span><span class="sxs-lookup"><span data-stu-id="7d180-114">Area:</span></span>  <br/> |<span data-ttu-id="7d180-115">会议</span><span class="sxs-lookup"><span data-stu-id="7d180-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7d180-116">注解</span><span class="sxs-lookup"><span data-stu-id="7d180-116">Remarks</span></span>

<span data-ttu-id="7d180-117">仅当未设置**dispidApptRecur** ([PidLidAppointmentRecur](pidlidappointmentrecur-canonical-property.md)) 属性, 但如果**LID_IS_RECURRING** ([PidLidIsRecurring](pidlidisrecurring-canonical-property.md)) 属性为 TRUE 且**LID_IS_EXCEPTION** ([PidLidIsException](pidlidisexception-canonical-property.md)) 属性为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="7d180-117">This property is only read if the **dispidApptRecur** ([PidLidAppointmentRecur](pidlidappointmentrecur-canonical-property.md)) property is not set, but if the **LID_IS_RECURRING** ([PidLidIsRecurring](pidlidisrecurring-canonical-property.md)) property is TRUE and the **LID_IS_EXCEPTION** ([PidLidIsException](pidlidisexception-canonical-property.md)) property is FALSE.</span></span> <span data-ttu-id="7d180-118">下半个字指定包含时区信息的表中的索引。</span><span class="sxs-lookup"><span data-stu-id="7d180-118">The lower WORD specifies an index into a table that contains time zone information.</span></span> <span data-ttu-id="7d180-119">在上面的单词中, 只读取最高位。</span><span class="sxs-lookup"><span data-stu-id="7d180-119">From the upper WORD, only the highest bit is read.</span></span> <span data-ttu-id="7d180-120">如果设置了该位, 则引用的时区将不会遵守夏时制 (DST), 否则将遵循[[OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)中详细介绍的 DST 日期。</span><span class="sxs-lookup"><span data-stu-id="7d180-120">If that bit is set, then the time zone referenced will not observe daylight saving time (DST), otherwise the DST dates detailed in [[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx) will be followed.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="7d180-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="7d180-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7d180-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="7d180-122">Protocol specifications</span></span>

<span data-ttu-id="7d180-123">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7d180-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7d180-124">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="7d180-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7d180-125">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7d180-125">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7d180-126">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="7d180-126">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7d180-127">头文件</span><span class="sxs-lookup"><span data-stu-id="7d180-127">Header files</span></span>

<span data-ttu-id="7d180-128">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="7d180-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="7d180-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7d180-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7d180-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d180-130">See also</span></span>



[<span data-ttu-id="7d180-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7d180-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7d180-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7d180-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7d180-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7d180-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7d180-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7d180-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

