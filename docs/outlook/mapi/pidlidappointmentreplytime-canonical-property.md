---
title: PidLidAppointmentReplyTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentReplyTime
api_type:
- COM
ms.assetid: 80a2608b-fc44-455a-86be-d6235caba99e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5bc2af5205e6e07b56212a6cf7077f9ef4bee89c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776686"
---
# <a name="pidlidappointmentreplytime-canonical-property"></a><span data-ttu-id="6f7c4-103">PidLidAppointmentReplyTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="6f7c4-103">PidLidAppointmentReplyTime Canonical Property</span></span>

  
  
<span data-ttu-id="6f7c4-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6f7c4-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6f7c4-105">指定的日期和时间当与会者响应收到会议请求或会议更新。</span><span class="sxs-lookup"><span data-stu-id="6f7c4-105">Specifies the date and time when the attendee responded to a received meeting request or meeting update.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6f7c4-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6f7c4-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6f7c4-107">dispidApptReplyTime</span><span class="sxs-lookup"><span data-stu-id="6f7c4-107">dispidApptReplyTime</span></span>  <br/> |
|<span data-ttu-id="6f7c4-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="6f7c4-108">Property set:</span></span>  <br/> |<span data-ttu-id="6f7c4-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="6f7c4-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="6f7c4-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="6f7c4-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="6f7c4-111">0x00008220</span><span class="sxs-lookup"><span data-stu-id="6f7c4-111">0x00008220</span></span>  <br/> |
|<span data-ttu-id="6f7c4-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6f7c4-112">Data type:</span></span>  <br/> |<span data-ttu-id="6f7c4-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="6f7c4-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="6f7c4-114">区域：</span><span class="sxs-lookup"><span data-stu-id="6f7c4-114">Area:</span></span>  <br/> |<span data-ttu-id="6f7c4-115">会议</span><span class="sxs-lookup"><span data-stu-id="6f7c4-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6f7c4-116">说明</span><span class="sxs-lookup"><span data-stu-id="6f7c4-116">Remarks</span></span>

<span data-ttu-id="6f7c4-117">必须以协调世界时 (UTC) 指定的值。</span><span class="sxs-lookup"><span data-stu-id="6f7c4-117">The value must be specified in Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6f7c4-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="6f7c4-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6f7c4-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="6f7c4-119">Protocol specifications</span></span>

<span data-ttu-id="6f7c4-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6f7c4-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6f7c4-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="6f7c4-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6f7c4-122">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6f7c4-122">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6f7c4-123">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="6f7c4-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6f7c4-124">头文件</span><span class="sxs-lookup"><span data-stu-id="6f7c4-124">Header files</span></span>

<span data-ttu-id="6f7c4-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6f7c4-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="6f7c4-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6f7c4-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6f7c4-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f7c4-127">See also</span></span>



[<span data-ttu-id="6f7c4-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6f7c4-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6f7c4-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6f7c4-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6f7c4-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6f7c4-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6f7c4-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6f7c4-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

