---
title: PidLidClipEnd 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidClipEnd
api_type:
- COM
ms.assetid: 17c8db96-80dd-4a7a-9a1b-ab1b37ba616c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1353289da2b428fb58adecc6f7830a2eea4b519a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776717"
---
# <a name="pidlidclipend-canonical-property"></a><span data-ttu-id="7a550-103">PidLidClipEnd 规范属性</span><span class="sxs-lookup"><span data-stu-id="7a550-103">PidLidClipEnd Canonical Property</span></span>

  
  
<span data-ttu-id="7a550-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7a550-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7a550-105">单个实例 calendar 对象指定的结束日期和时间事件以协调世界时 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="7a550-105">Specifies the end date and time of the event in Coordinated Universal Time (UTC) for single instance calendar objects.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7a550-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7a550-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7a550-107">dispidClipEnd</span><span class="sxs-lookup"><span data-stu-id="7a550-107">dispidClipEnd</span></span>  <br/> |
|<span data-ttu-id="7a550-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="7a550-108">Property set:</span></span>  <br/> |<span data-ttu-id="7a550-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="7a550-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="7a550-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="7a550-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="7a550-111">0x00008236</span><span class="sxs-lookup"><span data-stu-id="7a550-111">0x00008236</span></span>  <br/> |
|<span data-ttu-id="7a550-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7a550-112">Data type:</span></span>  <br/> |<span data-ttu-id="7a550-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="7a550-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="7a550-114">区域：</span><span class="sxs-lookup"><span data-stu-id="7a550-114">Area:</span></span>  <br/> |<span data-ttu-id="7a550-115">日历</span><span class="sxs-lookup"><span data-stu-id="7a550-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7a550-116">说明</span><span class="sxs-lookup"><span data-stu-id="7a550-116">Remarks</span></span>

<span data-ttu-id="7a550-117">对于单实例 calendar 对象，它采用 UTC 指定的结束日期和时间的事件。</span><span class="sxs-lookup"><span data-stu-id="7a550-117">For single instance calendar objects, it specifies the end date and time of the event in UTC.</span></span> <span data-ttu-id="7a550-118">对于定期系列，此属性指定午夜采用 UTC，定期系列的最后一个实例的日期除非定期系列有无结束时，在其中案例值必须为 31 年 8 月 4500，11:59</span><span class="sxs-lookup"><span data-stu-id="7a550-118">For a recurring series, this property specifies midnight on the date of the last instance of the recurring series in UTC, unless the recurring series has no end, in which case the value must be 31 August 4500, 11:59 p.m.</span></span>
  
<span data-ttu-id="7a550-119">此属性的值必须设置为**dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) 的值。</span><span class="sxs-lookup"><span data-stu-id="7a550-119">The value of this property must be set to the value of the **dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="7a550-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="7a550-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7a550-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="7a550-121">Protocol specifications</span></span>

<span data-ttu-id="7a550-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7a550-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7a550-123">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="7a550-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7a550-124">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7a550-124">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7a550-125">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="7a550-125">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7a550-126">头文件</span><span class="sxs-lookup"><span data-stu-id="7a550-126">Header files</span></span>

<span data-ttu-id="7a550-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7a550-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="7a550-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7a550-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7a550-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a550-129">See also</span></span>



[<span data-ttu-id="7a550-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7a550-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7a550-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7a550-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7a550-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7a550-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7a550-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7a550-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

