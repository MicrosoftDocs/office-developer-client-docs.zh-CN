---
title: PidLidAppointmentTimeZoneDefinitionStartDisplay 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentTimeZoneDefinitionStartDispl
api_type:
- COM
ms.assetid: 08239670-3211-420c-99d7-0056ed967cb8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 504dc4b1cecb9798590e4a15968acc3aa98fe4a6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345015"
---
# <a name="pidlidappointmenttimezonedefinitionstartdisplay-canonical-property"></a><span data-ttu-id="9f897-103">PidLidAppointmentTimeZoneDefinitionStartDisplay 规范属性</span><span class="sxs-lookup"><span data-stu-id="9f897-103">PidLidAppointmentTimeZoneDefinitionStartDisplay Canonical Property</span></span>

  
  
<span data-ttu-id="9f897-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9f897-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9f897-105">包含映射到[TZDEFINITION](https://msdn.microsoft.com/library/0ae21571-2299-6407-807c-428668bb6798%28Office.15%29.aspx)结构的保留格式的流, 该格式存储在选择单实例约会或会议请求的开始时间时使用的时区的说明。</span><span class="sxs-lookup"><span data-stu-id="9f897-105">Contains a stream that maps to the persisted format of a [TZDEFINITION](https://msdn.microsoft.com/library/0ae21571-2299-6407-807c-428668bb6798%28Office.15%29.aspx) structure, which stores the description for the time zone that is used when the start time of a single-instance appointment or meeting request is selected.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9f897-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9f897-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9f897-107">dispidApptTZDefStartDisplay</span><span class="sxs-lookup"><span data-stu-id="9f897-107">dispidApptTZDefStartDisplay</span></span>  <br/> |
|<span data-ttu-id="9f897-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="9f897-108">Property set:</span></span>  <br/> |<span data-ttu-id="9f897-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="9f897-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="9f897-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="9f897-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="9f897-111">0x0000825E</span><span class="sxs-lookup"><span data-stu-id="9f897-111">0x0000825E</span></span>  <br/> |
|<span data-ttu-id="9f897-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9f897-112">Data type:</span></span>  <br/> |<span data-ttu-id="9f897-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="9f897-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="9f897-114">区域：</span><span class="sxs-lookup"><span data-stu-id="9f897-114">Area:</span></span>  <br/> |<span data-ttu-id="9f897-115">日历</span><span class="sxs-lookup"><span data-stu-id="9f897-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9f897-116">注解</span><span class="sxs-lookup"><span data-stu-id="9f897-116">Remarks</span></span>

<span data-ttu-id="9f897-117">Microsoft Office Outlook 2003 或更低版本, 基于协作数据对象 (CDO) 1.2.1 的解决方案以及未运行 Outlook 或 Microsoft Exchange Server 的日历更新工具的解决方案, 存储单实例的开始时间和结束时间协调世界时 (UTC) 的约会和会议请求。</span><span class="sxs-lookup"><span data-stu-id="9f897-117">Microsoft Office Outlook 2003 or earlier, and solutions that are based on Collaboration Data Objects (CDO) 1.2.1 and that have not run the calendar update tool for Outlook or Microsoft Exchange Server, store the start time and end time of single-instance appointments and meeting requests in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="9f897-118">这些客户端不会存储创建约会或会议请求的时区的任何信息。</span><span class="sxs-lookup"><span data-stu-id="9f897-118">These clients do not store any information for the time zone in which the appointment or meeting request is created.</span></span>
  
<span data-ttu-id="9f897-119">由于 Microsoft Office Outlook 2007 以及基于 CDO 1.2.1 的解决方案 (已运行 Outlook 或 Exchange Server 日历更新工具), Outlook 版本将使用此属性存储开始时间的时区。</span><span class="sxs-lookup"><span data-stu-id="9f897-119">Versions of Outlook since Microsoft Office Outlook 2007, and solutions based on CDO 1.2.1 that have run the Outlook or Exchange Server calendar update tool use this property to store the time zone for the start time.</span></span> <span data-ttu-id="9f897-120">**dispidApptTZDefStartDisplay**属性显示预定的原始时区中的约会或会议。</span><span class="sxs-lookup"><span data-stu-id="9f897-120">The **dispidApptTZDefStartDisplay** property shows the appointment or meeting in the original time zone that it was scheduled.</span></span> <span data-ttu-id="9f897-121">它确定在时区的规则更改时是否应调整开始时间。</span><span class="sxs-lookup"><span data-stu-id="9f897-121">It determines whether the start time should be adjusted if the rules of the time zone change.</span></span> <span data-ttu-id="9f897-122">如果缺少此属性, 则假定为当前的本地时区。</span><span class="sxs-lookup"><span data-stu-id="9f897-122">If this property is missing, the current local time zone is assumed.</span></span> <span data-ttu-id="9f897-123">此属性仅用于显示目的, 且不在定期扩展中使用。</span><span class="sxs-lookup"><span data-stu-id="9f897-123">This property is used for display purposes only and is not used in recurrence expansion.</span></span> 
  
<span data-ttu-id="9f897-124">分析器在读取从该属性获取的流时, 或者在它将**TZDEFINITION**保持为对二进制属性 (如**dispidApptTZDefStartDisplay**) 承诺的流时, 必须小心。</span><span class="sxs-lookup"><span data-stu-id="9f897-124">A parser must be careful when it reads a stream obtained from this property, or when it persists **TZDEFINITION** to a stream for commitment to a binary property such as **dispidApptTZDefStartDisplay**.</span></span> <span data-ttu-id="9f897-125">有关详细信息, 请参阅[关于将 TZDEFINITION 保留给 stream 以提交给二进制属性](https://msdn.microsoft.com/library/0dec535d-d48f-39a5-97d5-0bd109134b3b%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9f897-125">For more information, see [About persisting TZDEFINITION to a stream to commit to a binary property](https://msdn.microsoft.com/library/0dec535d-d48f-39a5-97d5-0bd109134b3b%28Office.15%29.aspx).</span></span>
  
<span data-ttu-id="9f897-126">此属性指定**dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) 属性的时区信息。</span><span class="sxs-lookup"><span data-stu-id="9f897-126">This property specifies time zone information for the **dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) property.</span></span> <span data-ttu-id="9f897-127">**dispidApptTZDefStartDisplay**的值用于将开始日期和时间从 UTC 转换为本地时区, 以供显示之用。</span><span class="sxs-lookup"><span data-stu-id="9f897-127">The value of **dispidApptTZDefStartDisplay** is used to convert the start date and time from UTC to the local time zone for display purposes.</span></span> <span data-ttu-id="9f897-128">对于此属性指定的每个**TZRULE** , 不得设置 TZRULE_FLAG_RECUR_CURRENT_TZREG 标志。</span><span class="sxs-lookup"><span data-stu-id="9f897-128">For each **TZRULE** specified by this property, the TZRULE_FLAG_RECUR_CURRENT_TZREG flag must not be set.</span></span> <span data-ttu-id="9f897-129">例如, 如果**TZRULE**是有效的规则, 则 field 的值**TZRULE**必须是 "0x0002";否则, 必须为 "0x0000"。</span><span class="sxs-lookup"><span data-stu-id="9f897-129">For example, if the **TZRULE** is the effective rule, the value of the field, **TZRULE** must be "0x0002"; otherwise, it must be "0x0000".</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="9f897-130">相关资源</span><span class="sxs-lookup"><span data-stu-id="9f897-130">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="9f897-131">协议规范</span><span class="sxs-lookup"><span data-stu-id="9f897-131">Protocol specifications</span></span>

<span data-ttu-id="9f897-132">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9f897-132">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9f897-133">提供属性集定义和对相关 Exchange Server 协议规范的引用。。</span><span class="sxs-lookup"><span data-stu-id="9f897-133">Provides property set definitions and references to related Exchange Server protocol specifications..</span></span>
    
<span data-ttu-id="9f897-134">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9f897-134">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9f897-135">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="9f897-135">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="9f897-136">头文件</span><span class="sxs-lookup"><span data-stu-id="9f897-136">Header files</span></span>

<span data-ttu-id="9f897-137">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="9f897-137">Mapidefs.h</span></span>
  
> <span data-ttu-id="9f897-138">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9f897-138">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9f897-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f897-139">See also</span></span>



[<span data-ttu-id="9f897-140">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9f897-140">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9f897-141">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9f897-141">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9f897-142">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9f897-142">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9f897-143">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9f897-143">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

