---
title: PidLidAppointmentStateFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentStateFlags
api_type:
- COM
ms.assetid: 1e5f0f83-c40b-4b3a-8492-61d1b53b1e3c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c42649b231e691fec8b5a8d7024b87346cd8ce18
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568544"
---
# <a name="pidlidappointmentstateflags-canonical-property"></a><span data-ttu-id="c8825-103">PidLidAppointmentStateFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="c8825-103">PidLidAppointmentStateFlags Canonical Property</span></span>

  
  
<span data-ttu-id="c8825-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c8825-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c8825-105">指定的描述对象的状态位字段。</span><span class="sxs-lookup"><span data-stu-id="c8825-105">Specifies a bit field that describes the state of the object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c8825-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c8825-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c8825-107">dispidApptStateFlags</span><span class="sxs-lookup"><span data-stu-id="c8825-107">dispidApptStateFlags</span></span>  <br/> |
|<span data-ttu-id="c8825-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="c8825-108">Property set:</span></span>  <br/> |<span data-ttu-id="c8825-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="c8825-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="c8825-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="c8825-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="c8825-111">0x00008217</span><span class="sxs-lookup"><span data-stu-id="c8825-111">0x00008217</span></span>  <br/> |
|<span data-ttu-id="c8825-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c8825-112">Data type:</span></span>  <br/> |<span data-ttu-id="c8825-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="c8825-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="c8825-114">区域：</span><span class="sxs-lookup"><span data-stu-id="c8825-114">Area:</span></span>  <br/> |<span data-ttu-id="c8825-115">会议</span><span class="sxs-lookup"><span data-stu-id="c8825-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c8825-116">注解</span><span class="sxs-lookup"><span data-stu-id="c8825-116">Remarks</span></span>

<span data-ttu-id="c8825-117">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="c8825-117">This property is not required.</span></span> <span data-ttu-id="c8825-118">下面是可以设置的单个标记。</span><span class="sxs-lookup"><span data-stu-id="c8825-118">Below are the individual flags that can be set.</span></span>
  
<span data-ttu-id="c8825-119">M (asfMeeting，0x00000001)</span><span class="sxs-lookup"><span data-stu-id="c8825-119">M (asfMeeting, 0x00000001)</span></span>
  
> <span data-ttu-id="c8825-120">此标志指示对象是会议对象或会议相关对象。</span><span class="sxs-lookup"><span data-stu-id="c8825-120">This flag indicates that the object is a meeting object or a meeting-related object.</span></span>
    
<span data-ttu-id="c8825-121">R (asfReceived，0x00000002:uc)</span><span class="sxs-lookup"><span data-stu-id="c8825-121">R (asfReceived, 0x00000002)</span></span>
  
> <span data-ttu-id="c8825-122">此标志指示指定的对象已收到来自其他人。</span><span class="sxs-lookup"><span data-stu-id="c8825-122">This flag indicates that the represented object was received from someone else.</span></span>
    
<span data-ttu-id="c8825-123">C (asfCanceled，0x00000004)</span><span class="sxs-lookup"><span data-stu-id="c8825-123">C (asfCanceled, 0x00000004)</span></span>
  
> <span data-ttu-id="c8825-124">此标志指示对象所代表的会议对象已被取消。</span><span class="sxs-lookup"><span data-stu-id="c8825-124">This flag indicates that the meeting object represented by the object has been canceled.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="c8825-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="c8825-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c8825-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="c8825-126">Protocol specifications</span></span>

<span data-ttu-id="c8825-127">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c8825-127">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c8825-128">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="c8825-128">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="c8825-129">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c8825-129">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c8825-130">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="c8825-130">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c8825-131">头文件</span><span class="sxs-lookup"><span data-stu-id="c8825-131">Header files</span></span>

<span data-ttu-id="c8825-132">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c8825-132">Mapidefs.h</span></span>
  
> <span data-ttu-id="c8825-133">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c8825-133">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c8825-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8825-134">See also</span></span>



[<span data-ttu-id="c8825-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c8825-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c8825-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c8825-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c8825-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c8825-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c8825-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c8825-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

