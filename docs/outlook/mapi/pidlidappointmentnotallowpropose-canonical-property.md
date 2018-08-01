---
title: PidLidAppointmentNotAllowPropose 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentNotAllowPropose
api_type:
- COM
ms.assetid: 8be9e2aa-2dc1-406d-8864-7f556de22809
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 183c8eb5112fc35f088bc5c6ac11748e3449f15a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776594"
---
# <a name="pidlidappointmentnotallowpropose-canonical-property"></a><span data-ttu-id="29605-103">PidLidAppointmentNotAllowPropose 规范属性</span><span class="sxs-lookup"><span data-stu-id="29605-103">PidLidAppointmentNotAllowPropose Canonical Property</span></span>

  
  
<span data-ttu-id="29605-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="29605-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="29605-105">指示是否与会者不允许建议新会议的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="29605-105">Indicates whether attendees are not allowed to propose a new date/time for the meeting.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="29605-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="29605-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="29605-107">dispidApptNotAllowPropose</span><span class="sxs-lookup"><span data-stu-id="29605-107">dispidApptNotAllowPropose</span></span>  <br/> |
|<span data-ttu-id="29605-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="29605-108">Property set:</span></span>  <br/> |<span data-ttu-id="29605-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="29605-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="29605-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="29605-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="29605-111">0x0000825A</span><span class="sxs-lookup"><span data-stu-id="29605-111">0x0000825A</span></span>  <br/> |
|<span data-ttu-id="29605-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="29605-112">Data type:</span></span>  <br/> |<span data-ttu-id="29605-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="29605-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="29605-114">区域：</span><span class="sxs-lookup"><span data-stu-id="29605-114">Area:</span></span>  <br/> |<span data-ttu-id="29605-115">会议</span><span class="sxs-lookup"><span data-stu-id="29605-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="29605-116">说明</span><span class="sxs-lookup"><span data-stu-id="29605-116">Remarks</span></span>

<span data-ttu-id="29605-117">值为 FALSE 或不存在此属性指示允许与会者建议新的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="29605-117">A value of FALSE, or the absence of this property indicates that the attendees are allowed to propose a new date/time.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="29605-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="29605-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="29605-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="29605-119">Protocol specifications</span></span>

<span data-ttu-id="29605-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="29605-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="29605-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="29605-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="29605-122">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="29605-122">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="29605-123">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="29605-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="29605-124">头文件</span><span class="sxs-lookup"><span data-stu-id="29605-124">Header files</span></span>

<span data-ttu-id="29605-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="29605-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="29605-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="29605-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="29605-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29605-127">See also</span></span>



[<span data-ttu-id="29605-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="29605-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="29605-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="29605-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="29605-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="29605-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="29605-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="29605-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

