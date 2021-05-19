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
ms.openlocfilehash: aa9aacd8a1d75ed4c14a980e162a68c47995a55c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356355"
---
# <a name="pidlidappointmentnotallowpropose-canonical-property"></a><span data-ttu-id="f3039-103">PidLidAppointmentNotAllowPropose 规范属性</span><span class="sxs-lookup"><span data-stu-id="f3039-103">PidLidAppointmentNotAllowPropose Canonical Property</span></span>

  
  
<span data-ttu-id="f3039-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f3039-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f3039-105">指示是否允许与会者为会议建议新的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="f3039-105">Indicates whether attendees are not allowed to propose a new date/time for the meeting.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f3039-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f3039-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f3039-107">dispidApptNotAllowPropose</span><span class="sxs-lookup"><span data-stu-id="f3039-107">dispidApptNotAllowPropose</span></span>  <br/> |
|<span data-ttu-id="f3039-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="f3039-108">Property set:</span></span>  <br/> |<span data-ttu-id="f3039-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="f3039-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="f3039-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="f3039-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="f3039-111">0x0000825A</span><span class="sxs-lookup"><span data-stu-id="f3039-111">0x0000825A</span></span>  <br/> |
|<span data-ttu-id="f3039-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f3039-112">Data type:</span></span>  <br/> |<span data-ttu-id="f3039-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="f3039-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="f3039-114">区域：</span><span class="sxs-lookup"><span data-stu-id="f3039-114">Area:</span></span>  <br/> |<span data-ttu-id="f3039-115">会议</span><span class="sxs-lookup"><span data-stu-id="f3039-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f3039-116">备注</span><span class="sxs-lookup"><span data-stu-id="f3039-116">Remarks</span></span>

<span data-ttu-id="f3039-117">如果值为 FALSE，或者缺少此属性，则表明允许与会者建议新的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="f3039-117">A value of FALSE, or the absence of this property indicates that the attendees are allowed to propose a new date/time.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="f3039-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="f3039-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f3039-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="f3039-119">Protocol specifications</span></span>

<span data-ttu-id="f3039-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f3039-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f3039-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="f3039-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="f3039-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f3039-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f3039-123">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="f3039-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f3039-124">头文件</span><span class="sxs-lookup"><span data-stu-id="f3039-124">Header files</span></span>

<span data-ttu-id="f3039-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f3039-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="f3039-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f3039-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f3039-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3039-127">See also</span></span>



[<span data-ttu-id="f3039-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f3039-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f3039-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f3039-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f3039-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f3039-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f3039-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f3039-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

