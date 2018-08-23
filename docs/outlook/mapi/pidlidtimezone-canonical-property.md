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
ms.openlocfilehash: 90dc35e72fc863ab12d9d6df9c54def7af788efd
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568887"
---
# <a name="pidlidtimezone-canonical-property"></a><span data-ttu-id="b89fc-103">PidLidTimeZone 规范属性</span><span class="sxs-lookup"><span data-stu-id="b89fc-103">PidLidTimeZone Canonical Property</span></span>

  
  
<span data-ttu-id="b89fc-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b89fc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b89fc-105">指定定期会议的信息所在的时区。</span><span class="sxs-lookup"><span data-stu-id="b89fc-105">Specifies information about the time zone of a recurring meeting.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b89fc-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b89fc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b89fc-107">LID_TIME_ZONE</span><span class="sxs-lookup"><span data-stu-id="b89fc-107">LID_TIME_ZONE</span></span>  <br/> |
|<span data-ttu-id="b89fc-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="b89fc-108">Property set:</span></span>  <br/> |<span data-ttu-id="b89fc-109">PSETID_Meeting</span><span class="sxs-lookup"><span data-stu-id="b89fc-109">PSETID_Meeting</span></span>  <br/> |
|<span data-ttu-id="b89fc-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="b89fc-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="b89fc-111">0x0000000C</span><span class="sxs-lookup"><span data-stu-id="b89fc-111">0x0000000C</span></span>  <br/> |
|<span data-ttu-id="b89fc-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b89fc-112">Data type:</span></span>  <br/> |<span data-ttu-id="b89fc-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="b89fc-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="b89fc-114">区域：</span><span class="sxs-lookup"><span data-stu-id="b89fc-114">Area:</span></span>  <br/> |<span data-ttu-id="b89fc-115">会议</span><span class="sxs-lookup"><span data-stu-id="b89fc-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b89fc-116">注解</span><span class="sxs-lookup"><span data-stu-id="b89fc-116">Remarks</span></span>

<span data-ttu-id="b89fc-117">如果未设置**dispidApptRecur** ([PidLidAppointmentRecur](pidlidappointmentrecur-canonical-property.md)) 属性，但如果**LID_IS_RECURRING** ([PidLidIsRecurring](pidlidisrecurring-canonical-property.md)) 属性为 TRUE，则**LID_IS_EXCEPTION** ([仅读取此属性PidLidIsException](pidlidisexception-canonical-property.md)) 属性为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="b89fc-117">This property is only read if the **dispidApptRecur** ([PidLidAppointmentRecur](pidlidappointmentrecur-canonical-property.md)) property is not set, but if the **LID_IS_RECURRING** ([PidLidIsRecurring](pidlidisrecurring-canonical-property.md)) property is TRUE and the **LID_IS_EXCEPTION** ([PidLidIsException](pidlidisexception-canonical-property.md)) property is FALSE.</span></span> <span data-ttu-id="b89fc-118">较低的字指定表中包含的信息所在的时区的索引。</span><span class="sxs-lookup"><span data-stu-id="b89fc-118">The lower WORD specifies an index into a table that contains time zone information.</span></span> <span data-ttu-id="b89fc-119">从右上单词，读取仅最高的位。</span><span class="sxs-lookup"><span data-stu-id="b89fc-119">From the upper WORD, only the highest bit is read.</span></span> <span data-ttu-id="b89fc-120">如果设置此位，然后所在的时区引用将不遵循将遵循夏令时 (DST)，否则为 DST 日期[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)中详细介绍。</span><span class="sxs-lookup"><span data-stu-id="b89fc-120">If that bit is set, then the time zone referenced will not observe daylight saving time (DST), otherwise the DST dates detailed in [[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx) will be followed.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="b89fc-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="b89fc-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b89fc-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="b89fc-122">Protocol specifications</span></span>

<span data-ttu-id="b89fc-123">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b89fc-123">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b89fc-124">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b89fc-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b89fc-125">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b89fc-125">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b89fc-126">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="b89fc-126">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b89fc-127">头文件</span><span class="sxs-lookup"><span data-stu-id="b89fc-127">Header files</span></span>

<span data-ttu-id="b89fc-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b89fc-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="b89fc-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b89fc-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b89fc-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b89fc-130">See also</span></span>



[<span data-ttu-id="b89fc-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b89fc-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b89fc-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b89fc-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b89fc-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b89fc-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b89fc-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b89fc-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

