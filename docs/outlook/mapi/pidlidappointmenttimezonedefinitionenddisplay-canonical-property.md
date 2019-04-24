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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345379"
---
# <a name="pidlidappointmenttimezonedefinitionenddisplay-canonical-property"></a><span data-ttu-id="2f44d-103">PidLidAppointmentTimeZoneDefinitionEndDisplay 规范属性</span><span class="sxs-lookup"><span data-stu-id="2f44d-103">PidLidAppointmentTimeZoneDefinitionEndDisplay Canonical Property</span></span>

  
  
<span data-ttu-id="2f44d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2f44d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2f44d-105">包含映射到[TZDEFINITION](https://msdn.microsoft.com/library/0ae21571-2299-6407-807c-428668bb6798%28Office.15%29.aspx)结构的保留格式的流, 该格式存储在选择单实例约会或会议请求的结束时间时使用的时区的说明。</span><span class="sxs-lookup"><span data-stu-id="2f44d-105">Contains a stream that maps to the persisted format of a [TZDEFINITION](https://msdn.microsoft.com/library/0ae21571-2299-6407-807c-428668bb6798%28Office.15%29.aspx) structure, which stores the description for the time zone that is used when the end time of a single-instance appointment or meeting request is selected.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2f44d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2f44d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2f44d-107">dispidApptTZDefEndDisplay</span><span class="sxs-lookup"><span data-stu-id="2f44d-107">dispidApptTZDefEndDisplay</span></span>  <br/> |
|<span data-ttu-id="2f44d-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="2f44d-108">Property set:</span></span>  <br/> |<span data-ttu-id="2f44d-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="2f44d-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="2f44d-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="2f44d-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="2f44d-111">0x0000825F</span><span class="sxs-lookup"><span data-stu-id="2f44d-111">0x0000825F</span></span>  <br/> |
|<span data-ttu-id="2f44d-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2f44d-112">Data type:</span></span>  <br/> |<span data-ttu-id="2f44d-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="2f44d-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="2f44d-114">区域：</span><span class="sxs-lookup"><span data-stu-id="2f44d-114">Area:</span></span>  <br/> |<span data-ttu-id="2f44d-115">日历</span><span class="sxs-lookup"><span data-stu-id="2f44d-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2f44d-116">注解</span><span class="sxs-lookup"><span data-stu-id="2f44d-116">Remarks</span></span>

<span data-ttu-id="2f44d-117">Microsoft Office Outlook 2003 或更低版本, 基于协作数据对象 (CDO) 1.2.1 的解决方案以及未运行 Outlook 或 Microsoft Exchange Server 的日历更新工具的解决方案, 存储单实例的开始时间和结束时间协调世界时 (UTC) 的约会和会议请求。</span><span class="sxs-lookup"><span data-stu-id="2f44d-117">Microsoft Office Outlook 2003 or earlier, and solutions that are based on Collaboration Data Objects (CDO) 1.2.1 and that have not run the calendar update tool for Outlook or Microsoft Exchange Server, store the start time and end time of single-instance appointments and meeting requests in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="2f44d-118">这些客户端不会存储创建约会或会议请求的时区的任何信息。</span><span class="sxs-lookup"><span data-stu-id="2f44d-118">These clients do not store any information for the time zone where the appointment or meeting request is created.</span></span>
  
<span data-ttu-id="2f44d-119">由于 microsoft Office Outlook 2007 以及基于 CDO 1.2.1 的解决方案 (已运行 Outlook 或 Exchange Server 日历更新工具), microsoft Outlook 的版本将使用**dispidApptTZDefEndDisplay**存储结束时间的时区。</span><span class="sxs-lookup"><span data-stu-id="2f44d-119">Versions of Microsoft Outlook since Microsoft Office Outlook 2007, and solutions based on CDO 1.2.1 that have run the Outlook or Exchange Server calendar update tool use **dispidApptTZDefEndDisplay** to store the time zone for the end time.</span></span> <span data-ttu-id="2f44d-120">**dispidApptTZDefEndDisplay**在原始时区中显示约会或会议计划的时间, 并确定是否应在时区的规则更改时调整结束时间。</span><span class="sxs-lookup"><span data-stu-id="2f44d-120">**dispidApptTZDefEndDisplay** shows the appointment or meeting in the original time zone that it was scheduled, and determines whether the end time should be adjusted if the rules of the time zone change.</span></span> <span data-ttu-id="2f44d-121">如果缺少此属性, 则使用由**dispidApptTZDefStartDisplay** ([PidLidAppointmentTimeZoneDefinitionStartDisplay](pidlidappointmenttimezonedefinitionstartdisplay-canonical-property.md)) 属性指定的时区。</span><span class="sxs-lookup"><span data-stu-id="2f44d-121">If this property is missing, the time zone specified by the **dispidApptTZDefStartDisplay** ([PidLidAppointmentTimeZoneDefinitionStartDisplay](pidlidappointmenttimezonedefinitionstartdisplay-canonical-property.md)) property is used.</span></span> <span data-ttu-id="2f44d-122">如果**dispidApptTZDefStartDisplay**缺失或无效, 则假定为当前本地时区。</span><span class="sxs-lookup"><span data-stu-id="2f44d-122">If **dispidApptTZDefStartDisplay** is missing or invalid, the current local time zone is assumed.</span></span> <span data-ttu-id="2f44d-123">**dispidApptTZDefEndDisplay**仅用于显示目的, 在定期扩展中不使用。</span><span class="sxs-lookup"><span data-stu-id="2f44d-123">**dispidApptTZDefEndDisplay** is used for display purposes only and is not used in recurrence expansion.</span></span> 
  
<span data-ttu-id="2f44d-124">分析器在读取从**dispidApptTZDefEndDisplay**获取的流时, 或者在它保持**TZDEFINITION**为对二进制属性 (如**dispidApptTZDefEndDisplay**) 承诺的流时, 必须小心。</span><span class="sxs-lookup"><span data-stu-id="2f44d-124">A parser must be careful when it reads a stream obtained from **dispidApptTZDefEndDisplay**, or when it persists **TZDEFINITION** to a stream for commitment to a binary property such as **dispidApptTZDefEndDisplay**.</span></span> <span data-ttu-id="2f44d-125">有关详细信息, 请参阅[关于将 TZDEFINITION 保留给 stream 以提交给二进制属性](https://msdn.microsoft.com/library/0dec535d-d48f-39a5-97d5-0bd109134b3b%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2f44d-125">For more information, see [About persisting TZDEFINITION to a stream to commit to a binary property](https://msdn.microsoft.com/library/0dec535d-d48f-39a5-97d5-0bd109134b3b%28Office.15%29.aspx).</span></span>
  
 <span data-ttu-id="2f44d-126">**dispidApptTZDefEndDisplay**指定**dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) 属性的时区信息。</span><span class="sxs-lookup"><span data-stu-id="2f44d-126">**dispidApptTZDefEndDisplay** specifies time zone information for the **dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) property.</span></span> <span data-ttu-id="2f44d-127">**dispidApptTZDefEndDisplay**的格式、约束和计算与在**dispidApptTZDefStartDisplay**属性中指定的格式、约束和计算相同。</span><span class="sxs-lookup"><span data-stu-id="2f44d-127">The format, constraints, and computation of **dispidApptTZDefEndDisplay** are the same as specified in the **dispidApptTZDefStartDisplay** property.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="2f44d-128">相关资源</span><span class="sxs-lookup"><span data-stu-id="2f44d-128">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2f44d-129">协议规范</span><span class="sxs-lookup"><span data-stu-id="2f44d-129">Protocol specifications</span></span>

<span data-ttu-id="2f44d-130">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2f44d-130">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2f44d-131">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="2f44d-131">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2f44d-132">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2f44d-132">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2f44d-133">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="2f44d-133">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2f44d-134">头文件</span><span class="sxs-lookup"><span data-stu-id="2f44d-134">Header files</span></span>

<span data-ttu-id="2f44d-135">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="2f44d-135">Mapidefs.h</span></span>
  
> <span data-ttu-id="2f44d-136">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2f44d-136">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2f44d-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f44d-137">See also</span></span>



[<span data-ttu-id="2f44d-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2f44d-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2f44d-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2f44d-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2f44d-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2f44d-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2f44d-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2f44d-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

