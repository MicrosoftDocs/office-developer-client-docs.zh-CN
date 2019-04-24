---
title: PidLidCalendarType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidCalendarType
api_type:
- COM
ms.assetid: 06e066f1-2b7d-4a6b-b88c-85a9bfa83bd3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6a33559a3e047890153f6a8e0ab40e49c2bf80cb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341991"
---
# <a name="pidlidcalendartype-canonical-property"></a><span data-ttu-id="c67ff-103">PidLidCalendarType 规范属性</span><span class="sxs-lookup"><span data-stu-id="c67ff-103">PidLidCalendarType Canonical Property</span></span>

  
  
<span data-ttu-id="c67ff-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c67ff-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c67ff-105">指定**dispidApptRecur** ([PidLidAppointmentRecur](pidlidappointmentrecur-canonical-property.md)) 属性中的 CalendarType 字段的值。</span><span class="sxs-lookup"><span data-stu-id="c67ff-105">Specifies the value of the CalendarType field from the **dispidApptRecur** ([PidLidAppointmentRecur](pidlidappointmentrecur-canonical-property.md)) property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c67ff-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c67ff-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c67ff-107">LID_CALENDAR_TYPE</span><span class="sxs-lookup"><span data-stu-id="c67ff-107">LID_CALENDAR_TYPE</span></span>  <br/> |
|<span data-ttu-id="c67ff-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="c67ff-108">Property set:</span></span>  <br/> |<span data-ttu-id="c67ff-109">PSETID_Meeting</span><span class="sxs-lookup"><span data-stu-id="c67ff-109">PSETID_Meeting</span></span>  <br/> |
|<span data-ttu-id="c67ff-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="c67ff-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="c67ff-111">0x0000001C</span><span class="sxs-lookup"><span data-stu-id="c67ff-111">0x0000001C</span></span>  <br/> |
|<span data-ttu-id="c67ff-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c67ff-112">Data type:</span></span>  <br/> |<span data-ttu-id="c67ff-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="c67ff-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="c67ff-114">区域：</span><span class="sxs-lookup"><span data-stu-id="c67ff-114">Area:</span></span>  <br/> |<span data-ttu-id="c67ff-115">会议</span><span class="sxs-lookup"><span data-stu-id="c67ff-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c67ff-116">注解</span><span class="sxs-lookup"><span data-stu-id="c67ff-116">Remarks</span></span>

<span data-ttu-id="c67ff-117">当会议请求代表定期系列或异常时, 这是**dispidApptRecur**属性中的 CalendarType 字段的值。</span><span class="sxs-lookup"><span data-stu-id="c67ff-117">When the meeting request represents a recurring series or an exception, this is the value of the CalendarType field from the **dispidApptRecur** property.</span></span> <span data-ttu-id="c67ff-118">否则, 将不设置此属性, 假定其假定为0。</span><span class="sxs-lookup"><span data-stu-id="c67ff-118">Otherwise, this property is not set and assumed to be 0.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="c67ff-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="c67ff-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c67ff-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="c67ff-120">Protocol specifications</span></span>

<span data-ttu-id="c67ff-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c67ff-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c67ff-122">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="c67ff-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="c67ff-123">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c67ff-123">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c67ff-124">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="c67ff-124">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c67ff-125">头文件</span><span class="sxs-lookup"><span data-stu-id="c67ff-125">Header files</span></span>

<span data-ttu-id="c67ff-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="c67ff-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="c67ff-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c67ff-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c67ff-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c67ff-128">See also</span></span>



[<span data-ttu-id="c67ff-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c67ff-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c67ff-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c67ff-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c67ff-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c67ff-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c67ff-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c67ff-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

