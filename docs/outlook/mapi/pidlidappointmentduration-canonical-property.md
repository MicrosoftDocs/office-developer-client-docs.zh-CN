---
title: PidLidAppointmentDuration 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentDuration
api_type:
- COM
ms.assetid: 92c07a81-9dec-4118-af1f-02ecad340f07
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8ce9df6290fe6e50e52c632f0a14f226c4d715d7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345393"
---
# <a name="pidlidappointmentduration-canonical-property"></a><span data-ttu-id="815ad-103">PidLidAppointmentDuration 规范属性</span><span class="sxs-lookup"><span data-stu-id="815ad-103">PidLidAppointmentDuration Canonical Property</span></span>

  
  
<span data-ttu-id="815ad-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="815ad-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="815ad-105">表示安排约会的时间长度 (以分钟为单位)。</span><span class="sxs-lookup"><span data-stu-id="815ad-105">Represents the length of time, in minutes, when an appointment is scheduled.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="815ad-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="815ad-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="815ad-107">dispidApptDuration</span><span class="sxs-lookup"><span data-stu-id="815ad-107">dispidApptDuration</span></span>  <br/> |
|<span data-ttu-id="815ad-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="815ad-108">Property set:</span></span>  <br/> |<span data-ttu-id="815ad-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="815ad-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="815ad-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="815ad-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="815ad-111">0x00008213</span><span class="sxs-lookup"><span data-stu-id="815ad-111">0x00008213</span></span>  <br/> |
|<span data-ttu-id="815ad-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="815ad-112">Data type:</span></span>  <br/> |<span data-ttu-id="815ad-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="815ad-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="815ad-114">区域：</span><span class="sxs-lookup"><span data-stu-id="815ad-114">Area:</span></span>  <br/> |<span data-ttu-id="815ad-115">日历</span><span class="sxs-lookup"><span data-stu-id="815ad-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="815ad-116">注解</span><span class="sxs-lookup"><span data-stu-id="815ad-116">Remarks</span></span>

<span data-ttu-id="815ad-117">该值必须是**dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) 和**dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) 属性的值之间的分钟数。</span><span class="sxs-lookup"><span data-stu-id="815ad-117">The value must be the number of minutes between the value of the **dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) and the **dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) properties.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="815ad-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="815ad-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="815ad-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="815ad-119">Protocol specifications</span></span>

<span data-ttu-id="815ad-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="815ad-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="815ad-121">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="815ad-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="815ad-122">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="815ad-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="815ad-123">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="815ad-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="815ad-124">头文件</span><span class="sxs-lookup"><span data-stu-id="815ad-124">Header files</span></span>

<span data-ttu-id="815ad-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="815ad-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="815ad-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="815ad-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="815ad-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="815ad-127">See also</span></span>



[<span data-ttu-id="815ad-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="815ad-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="815ad-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="815ad-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="815ad-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="815ad-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="815ad-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="815ad-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

