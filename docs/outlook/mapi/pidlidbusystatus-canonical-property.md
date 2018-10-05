---
title: PidLidBusyStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidBusyStatus
api_type:
- COM
ms.assetid: 50c91fe6-2a61-4348-a16d-fd5c501b0715
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cb73a0e09436177b8b53a05588508886ee28a0a5
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383301"
---
# <a name="pidlidbusystatus-canonical-property"></a><span data-ttu-id="13946-103">PidLidBusyStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="13946-103">PidLidBusyStatus Canonical Property</span></span>

  
  
<span data-ttu-id="13946-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="13946-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="13946-105">代表约会的用户的可用性。</span><span class="sxs-lookup"><span data-stu-id="13946-105">Represents the user's availability for an appointment.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="13946-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="13946-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="13946-107">dispidBusyStatus</span><span class="sxs-lookup"><span data-stu-id="13946-107">dispidBusyStatus</span></span>  <br/> |
|<span data-ttu-id="13946-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="13946-108">Property set:</span></span>  <br/> |<span data-ttu-id="13946-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="13946-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="13946-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="13946-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="13946-111">0x00008205</span><span class="sxs-lookup"><span data-stu-id="13946-111">0x00008205</span></span>  <br/> |
|<span data-ttu-id="13946-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="13946-112">Data type:</span></span>  <br/> |<span data-ttu-id="13946-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="13946-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="13946-114">区域：</span><span class="sxs-lookup"><span data-stu-id="13946-114">Area:</span></span>  <br/> |<span data-ttu-id="13946-115">日历</span><span class="sxs-lookup"><span data-stu-id="13946-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="13946-116">说明</span><span class="sxs-lookup"><span data-stu-id="13946-116">Remarks</span></span>

<span data-ttu-id="13946-117">此属性指定对象所述的事件的用户的可用性，并且必须为下面指定的值之一。</span><span class="sxs-lookup"><span data-stu-id="13946-117">This property specifies the availability of a user for the event described by the object and must be one of the values specified below.</span></span>
  
|<span data-ttu-id="13946-118">**值**</span><span class="sxs-lookup"><span data-stu-id="13946-118">**Value**</span></span>|<span data-ttu-id="13946-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="13946-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="13946-120">0x00000000</span><span class="sxs-lookup"><span data-stu-id="13946-120">0x00000000</span></span>  <br/> |<span data-ttu-id="13946-121">用户可用。</span><span class="sxs-lookup"><span data-stu-id="13946-121">The user is available.</span></span>  <br/> |
|<span data-ttu-id="13946-122">0x00000001</span><span class="sxs-lookup"><span data-stu-id="13946-122">0x00000001</span></span>  <br/> |<span data-ttu-id="13946-123">用户可以安排一个暂定事件。</span><span class="sxs-lookup"><span data-stu-id="13946-123">The user has a tentative event scheduled.</span></span>  <br/> |
|<span data-ttu-id="13946-124">0x00000002</span><span class="sxs-lookup"><span data-stu-id="13946-124">0x00000002</span></span>  <br/> |<span data-ttu-id="13946-125">用户正忙。</span><span class="sxs-lookup"><span data-stu-id="13946-125">The user is busy.</span></span>  <br/> |
|<span data-ttu-id="13946-126">0x00000003</span><span class="sxs-lookup"><span data-stu-id="13946-126">0x00000003</span></span>  <br/> |<span data-ttu-id="13946-127">用户不在办公室。</span><span class="sxs-lookup"><span data-stu-id="13946-127">The user is out of office.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="13946-128">相关资源</span><span class="sxs-lookup"><span data-stu-id="13946-128">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="13946-129">协议规范</span><span class="sxs-lookup"><span data-stu-id="13946-129">Protocol specifications</span></span>

<span data-ttu-id="13946-130">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="13946-130">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="13946-131">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="13946-131">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="13946-132">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="13946-132">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="13946-133">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="13946-133">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="13946-134">头文件</span><span class="sxs-lookup"><span data-stu-id="13946-134">Header files</span></span>

<span data-ttu-id="13946-135">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="13946-135">Mapidefs.h</span></span>
  
> <span data-ttu-id="13946-136">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="13946-136">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="13946-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13946-137">See also</span></span>



[<span data-ttu-id="13946-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="13946-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="13946-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="13946-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="13946-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="13946-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="13946-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="13946-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

