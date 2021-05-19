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
ms.openlocfilehash: e365c78ea6457e7da79e3d1c749baa922a01acbb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345358"
---
# <a name="pidlidappointmentstateflags-canonical-property"></a><span data-ttu-id="7255f-103">PidLidAppointmentStateFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="7255f-103">PidLidAppointmentStateFlags Canonical Property</span></span>

  
  
<span data-ttu-id="7255f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7255f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7255f-105">指定描述对象状态的位字段。</span><span class="sxs-lookup"><span data-stu-id="7255f-105">Specifies a bit field that describes the state of the object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7255f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7255f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7255f-107">dispidApptStateFlags</span><span class="sxs-lookup"><span data-stu-id="7255f-107">dispidApptStateFlags</span></span>  <br/> |
|<span data-ttu-id="7255f-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="7255f-108">Property set:</span></span>  <br/> |<span data-ttu-id="7255f-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="7255f-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="7255f-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="7255f-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="7255f-111">0x00008217</span><span class="sxs-lookup"><span data-stu-id="7255f-111">0x00008217</span></span>  <br/> |
|<span data-ttu-id="7255f-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7255f-112">Data type:</span></span>  <br/> |<span data-ttu-id="7255f-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="7255f-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="7255f-114">区域：</span><span class="sxs-lookup"><span data-stu-id="7255f-114">Area:</span></span>  <br/> |<span data-ttu-id="7255f-115">会议</span><span class="sxs-lookup"><span data-stu-id="7255f-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7255f-116">备注</span><span class="sxs-lookup"><span data-stu-id="7255f-116">Remarks</span></span>

<span data-ttu-id="7255f-117">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="7255f-117">This property is not required.</span></span> <span data-ttu-id="7255f-118">以下是可以设置的个人标志。</span><span class="sxs-lookup"><span data-stu-id="7255f-118">Below are the individual flags that can be set.</span></span>
  
<span data-ttu-id="7255f-119">M (asfMeeting、0x00000001) </span><span class="sxs-lookup"><span data-stu-id="7255f-119">M (asfMeeting, 0x00000001)</span></span>
  
> <span data-ttu-id="7255f-120">此标志指示对象是会议对象或与会议相关的对象。</span><span class="sxs-lookup"><span data-stu-id="7255f-120">This flag indicates that the object is a meeting object or a meeting-related object.</span></span>
    
<span data-ttu-id="7255f-121">R (asfReceived、0x00000002) </span><span class="sxs-lookup"><span data-stu-id="7255f-121">R (asfReceived, 0x00000002)</span></span>
  
> <span data-ttu-id="7255f-122">此标志指示表示的对象从其他人接收。</span><span class="sxs-lookup"><span data-stu-id="7255f-122">This flag indicates that the represented object was received from someone else.</span></span>
    
<span data-ttu-id="7255f-123">C (asfCanceled， 0x00000004) </span><span class="sxs-lookup"><span data-stu-id="7255f-123">C (asfCanceled, 0x00000004)</span></span>
  
> <span data-ttu-id="7255f-124">此标志指示对象所代表的会议对象已取消。</span><span class="sxs-lookup"><span data-stu-id="7255f-124">This flag indicates that the meeting object represented by the object has been canceled.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="7255f-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="7255f-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7255f-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="7255f-126">Protocol specifications</span></span>

<span data-ttu-id="7255f-127">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7255f-127">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7255f-128">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="7255f-128">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7255f-129">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7255f-129">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7255f-130">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="7255f-130">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7255f-131">头文件</span><span class="sxs-lookup"><span data-stu-id="7255f-131">Header files</span></span>

<span data-ttu-id="7255f-132">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7255f-132">Mapidefs.h</span></span>
  
> <span data-ttu-id="7255f-133">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7255f-133">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7255f-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7255f-134">See also</span></span>



[<span data-ttu-id="7255f-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7255f-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7255f-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7255f-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7255f-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7255f-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7255f-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7255f-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

