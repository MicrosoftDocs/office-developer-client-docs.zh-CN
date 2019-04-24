---
title: PidLidAppointmentLastSequence 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentLastSequence
api_type:
- COM
ms.assetid: 52fa57be-746d-4b80-92b6-2ba83f796325
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 82cf630033cde8b5c6859064c86f43eb9fc12091
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358119"
---
# <a name="pidlidappointmentlastsequence-canonical-property"></a><span data-ttu-id="fbeb0-103">PidLidAppointmentLastSequence 规范属性</span><span class="sxs-lookup"><span data-stu-id="fbeb0-103">PidLidAppointmentLastSequence Canonical Property</span></span>

  
  
<span data-ttu-id="fbeb0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fbeb0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fbeb0-105">向组织者指示发送给任何与会者的最后一个序列号。</span><span class="sxs-lookup"><span data-stu-id="fbeb0-105">Indicates to the organizer the last sequence number that was sent to any attendee.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fbeb0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="fbeb0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="fbeb0-107">dispidApptLastSequence</span><span class="sxs-lookup"><span data-stu-id="fbeb0-107">dispidApptLastSequence</span></span>  <br/> |
|<span data-ttu-id="fbeb0-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="fbeb0-108">Property set:</span></span>  <br/> |<span data-ttu-id="fbeb0-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="fbeb0-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="fbeb0-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="fbeb0-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="fbeb0-111">0x00008203</span><span class="sxs-lookup"><span data-stu-id="fbeb0-111">0x00008203</span></span>  <br/> |
|<span data-ttu-id="fbeb0-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fbeb0-112">Data type:</span></span>  <br/> |<span data-ttu-id="fbeb0-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="fbeb0-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="fbeb0-114">区域：</span><span class="sxs-lookup"><span data-stu-id="fbeb0-114">Area:</span></span>  <br/> |<span data-ttu-id="fbeb0-115">会议</span><span class="sxs-lookup"><span data-stu-id="fbeb0-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fbeb0-116">注解</span><span class="sxs-lookup"><span data-stu-id="fbeb0-116">Remarks</span></span>

<span data-ttu-id="fbeb0-117">此属性对与会者没有任何意义。</span><span class="sxs-lookup"><span data-stu-id="fbeb0-117">This property has no meaning for an attendee.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="fbeb0-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="fbeb0-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="fbeb0-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="fbeb0-119">Protocol specifications</span></span>

<span data-ttu-id="fbeb0-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fbeb0-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fbeb0-121">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="fbeb0-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="fbeb0-122">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fbeb0-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fbeb0-123">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="fbeb0-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="fbeb0-124">头文件</span><span class="sxs-lookup"><span data-stu-id="fbeb0-124">Header files</span></span>

<span data-ttu-id="fbeb0-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="fbeb0-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="fbeb0-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fbeb0-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fbeb0-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbeb0-127">See also</span></span>



[<span data-ttu-id="fbeb0-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fbeb0-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fbeb0-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fbeb0-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fbeb0-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="fbeb0-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fbeb0-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fbeb0-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

