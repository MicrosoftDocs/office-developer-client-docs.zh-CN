---
title: PidLidAppointmentTimeZoneDefinitionEndDisplay 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentTimeZoneDefinitionEndDisplay
api_type:
- COM
ms.assetid: 7b6193cb-612b-408e-b9bc-285df313e2cc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 24ccd25a1d799f3146bd230e5156be0051104f47
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382748"
---
# <a name="pidlidappointmenttimezonedefinitionenddisplay-canonical-property"></a><span data-ttu-id="e6bae-103">PidLidAppointmentTimeZoneDefinitionEndDisplay 规范属性</span><span class="sxs-lookup"><span data-stu-id="e6bae-103">PidLidAppointmentTimeZoneDefinitionEndDisplay Canonical Property</span></span>

  
  
<span data-ttu-id="e6bae-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e6bae-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e6bae-105">包含映射到的存储选择单实例约会或会议请求的结束时间时使用的时区的说明[TZDEFINITION](https://msdn.microsoft.com/library/0ae21571-2299-6407-807c-428668bb6798%28Office.15%29.aspx)结构持久化格式的流。</span><span class="sxs-lookup"><span data-stu-id="e6bae-105">Contains a stream that maps to the persisted format of a [TZDEFINITION](https://msdn.microsoft.com/library/0ae21571-2299-6407-807c-428668bb6798%28Office.15%29.aspx) structure, which stores the description for the time zone that is used when the end time of a single-instance appointment or meeting request is selected.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e6bae-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e6bae-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e6bae-107">dispidApptTZDefEndDisplay</span><span class="sxs-lookup"><span data-stu-id="e6bae-107">dispidApptTZDefEndDisplay</span></span>  <br/> |
|<span data-ttu-id="e6bae-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="e6bae-108">Property set:</span></span>  <br/> |<span data-ttu-id="e6bae-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="e6bae-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="e6bae-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="e6bae-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="e6bae-111">0x0000825F</span><span class="sxs-lookup"><span data-stu-id="e6bae-111">0x0000825F</span></span>  <br/> |
|<span data-ttu-id="e6bae-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e6bae-112">Data type:</span></span>  <br/> |<span data-ttu-id="e6bae-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="e6bae-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="e6bae-114">区域：</span><span class="sxs-lookup"><span data-stu-id="e6bae-114">Area:</span></span>  <br/> |<span data-ttu-id="e6bae-115">日历</span><span class="sxs-lookup"><span data-stu-id="e6bae-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e6bae-116">说明</span><span class="sxs-lookup"><span data-stu-id="e6bae-116">Remarks</span></span>

<span data-ttu-id="e6bae-117">Microsoft Office Outlook 2003 或更早版本和解决方案的基于上协作数据对象 (CDO) 1.2.1 （英文) 和 Outlook 或 Microsoft Exchange Server 已不运行日历更新工具存储的开始时间和结束时间的单实例约会和会议请求以协调世界时 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="e6bae-117">Microsoft Office Outlook 2003 or earlier, and solutions that are based on Collaboration Data Objects (CDO) 1.2.1 and that have not run the calendar update tool for Outlook or Microsoft Exchange Server, store the start time and end time of single-instance appointments and meeting requests in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="e6bae-118">这些客户端不存储在其中创建约会或会议请求的时区的任何信息。</span><span class="sxs-lookup"><span data-stu-id="e6bae-118">These clients do not store any information for the time zone where the appointment or meeting request is created.</span></span>
  
<span data-ttu-id="e6bae-119">自 Microsoft Office Outlook 2007，并基于 CDO 1.2.1 （英文) 的解决方案的 Microsoft Outlook 的运行 Outlook 或 Exchange Server 日历版本更新工具使用**dispidApptTZDefEndDisplay**存储的结束时间的时区。</span><span class="sxs-lookup"><span data-stu-id="e6bae-119">Versions of Microsoft Outlook since Microsoft Office Outlook 2007, and solutions based on CDO 1.2.1 that have run the Outlook or Exchange Server calendar update tool use **dispidApptTZDefEndDisplay** to store the time zone for the end time.</span></span> <span data-ttu-id="e6bae-120">**dispidApptTZDefEndDisplay**显示该约会或会议中原始时区，它已安排，并确定是否更改时区的规则是否应调整的结束时间。</span><span class="sxs-lookup"><span data-stu-id="e6bae-120">**dispidApptTZDefEndDisplay** shows the appointment or meeting in the original time zone that it was scheduled, and determines whether the end time should be adjusted if the rules of the time zone change.</span></span> <span data-ttu-id="e6bae-121">如果该属性不存在，则使用**dispidApptTZDefStartDisplay** ([PidLidAppointmentTimeZoneDefinitionStartDisplay](pidlidappointmenttimezonedefinitionstartdisplay-canonical-property.md)) 属性指定的时区。</span><span class="sxs-lookup"><span data-stu-id="e6bae-121">If this property is missing, the time zone specified by the **dispidApptTZDefStartDisplay** ([PidLidAppointmentTimeZoneDefinitionStartDisplay](pidlidappointmenttimezonedefinitionstartdisplay-canonical-property.md)) property is used.</span></span> <span data-ttu-id="e6bae-122">如果**dispidApptTZDefStartDisplay**缺失或无效，则假定当前的本地时区。</span><span class="sxs-lookup"><span data-stu-id="e6bae-122">If **dispidApptTZDefStartDisplay** is missing or invalid, the current local time zone is assumed.</span></span> <span data-ttu-id="e6bae-123">**dispidApptTZDefEndDisplay**用于仅显示目的，并且不使用定期扩展中。</span><span class="sxs-lookup"><span data-stu-id="e6bae-123">**dispidApptTZDefEndDisplay** is used for display purposes only and is not used in recurrence expansion.</span></span> 
  
<span data-ttu-id="e6bae-124">分析程序必须注意，它读取从**dispidApptTZDefEndDisplay**，获得一个流或时它所**TZDEFINITION**持久化到承诺如**dispidApptTZDefEndDisplay**二进制属性的流。</span><span class="sxs-lookup"><span data-stu-id="e6bae-124">A parser must be careful when it reads a stream obtained from **dispidApptTZDefEndDisplay**, or when it persists **TZDEFINITION** to a stream for commitment to a binary property such as **dispidApptTZDefEndDisplay**.</span></span> <span data-ttu-id="e6bae-125">有关详细信息，请参阅[关于保留 TZDEFINITION 到流提交到二进制属性](https://msdn.microsoft.com/library/0dec535d-d48f-39a5-97d5-0bd109134b3b%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e6bae-125">For more information, see [About persisting TZDEFINITION to a stream to commit to a binary property](https://msdn.microsoft.com/library/0dec535d-d48f-39a5-97d5-0bd109134b3b%28Office.15%29.aspx).</span></span>
  
 <span data-ttu-id="e6bae-126">**dispidApptTZDefEndDisplay**指定时区属性的信息的**dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="e6bae-126">**dispidApptTZDefEndDisplay** specifies time zone information for the **dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) property.</span></span> <span data-ttu-id="e6bae-127">格式、 约束和计算**dispidApptTZDefEndDisplay**是**dispidApptTZDefStartDisplay**属性中指定相同的。</span><span class="sxs-lookup"><span data-stu-id="e6bae-127">The format, constraints, and computation of **dispidApptTZDefEndDisplay** are the same as specified in the **dispidApptTZDefStartDisplay** property.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="e6bae-128">相关资源</span><span class="sxs-lookup"><span data-stu-id="e6bae-128">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e6bae-129">协议规范</span><span class="sxs-lookup"><span data-stu-id="e6bae-129">Protocol specifications</span></span>

<span data-ttu-id="e6bae-130">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e6bae-130">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e6bae-131">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="e6bae-131">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e6bae-132">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e6bae-132">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e6bae-133">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="e6bae-133">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e6bae-134">头文件</span><span class="sxs-lookup"><span data-stu-id="e6bae-134">Header files</span></span>

<span data-ttu-id="e6bae-135">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e6bae-135">Mapidefs.h</span></span>
  
> <span data-ttu-id="e6bae-136">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e6bae-136">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e6bae-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6bae-137">See also</span></span>



[<span data-ttu-id="e6bae-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e6bae-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e6bae-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e6bae-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e6bae-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e6bae-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e6bae-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e6bae-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

