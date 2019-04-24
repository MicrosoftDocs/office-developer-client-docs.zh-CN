---
title: PidLidAppointmentTimeZoneDefinitionRecur 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentTimeZoneDefinitionRecur
api_type:
- COM
ms.assetid: 52fd57a0-9e34-4452-9ecd-2acb454446c9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e5e9b06178a1517fc1c8652b0d667faf1afc77cc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345351"
---
# <a name="pidlidappointmenttimezonedefinitionrecur-canonical-property"></a><span data-ttu-id="e136e-103">PidLidAppointmentTimeZoneDefinitionRecur 规范属性</span><span class="sxs-lookup"><span data-stu-id="e136e-103">PidLidAppointmentTimeZoneDefinitionRecur Canonical Property</span></span>

  
  
<span data-ttu-id="e136e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e136e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e136e-105">包含映射到[TZDEFINITION](https://msdn.microsoft.com/library/0ae21571-2299-6407-807c-428668bb6798%28Office.15%29.aspx)结构的保留格式的流, 该格式存储在创建定期约会或会议请求时所使用的时区的说明。</span><span class="sxs-lookup"><span data-stu-id="e136e-105">Contains a stream that maps to the persisted format of a [TZDEFINITION](https://msdn.microsoft.com/library/0ae21571-2299-6407-807c-428668bb6798%28Office.15%29.aspx) structure, which stores the description for the time zone that is used when a recurring appointment or meeting request is created.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e136e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e136e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e136e-107">dispidApptTZDefRecur</span><span class="sxs-lookup"><span data-stu-id="e136e-107">dispidApptTZDefRecur</span></span>  <br/> |
|<span data-ttu-id="e136e-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="e136e-108">Property set:</span></span>  <br/> |<span data-ttu-id="e136e-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="e136e-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="e136e-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="e136e-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="e136e-111">0x00008260</span><span class="sxs-lookup"><span data-stu-id="e136e-111">0x00008260</span></span>  <br/> |
|<span data-ttu-id="e136e-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e136e-112">Data type:</span></span>  <br/> |<span data-ttu-id="e136e-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="e136e-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="e136e-114">区域：</span><span class="sxs-lookup"><span data-stu-id="e136e-114">Area:</span></span>  <br/> |<span data-ttu-id="e136e-115">日历</span><span class="sxs-lookup"><span data-stu-id="e136e-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e136e-116">注解</span><span class="sxs-lookup"><span data-stu-id="e136e-116">Remarks</span></span>

<span data-ttu-id="e136e-117">microsoft Office outlook 2007 版本的 microsoft Outlook 和基于协作数据对象 (CDO) 1.2.1 的解决方案 (已运行 Outlook 或 Exchange Server 日历更新工具) 使用**dispidApptTZDefRecur**和**dispidTimeZoneStruct** ([PidLidTimeZoneStruct](pidlidtimezonestruct-canonical-property.md)) 属性, 以确定是否应在时区的规则更改时调整定期会议。</span><span class="sxs-lookup"><span data-stu-id="e136e-117">Versions of Microsoft Outlook since Microsoft Office Outlook 2007, and solutions based on Collaboration Data Objects (CDO) 1.2.1 that have run the Outlook or Exchange Server calendar update tool use the **dispidApptTZDefRecur** and **dispidTimeZoneStruct** ([PidLidTimeZoneStruct](pidlidtimezonestruct-canonical-property.md)) properties to determine whether the recurring meeting should be adjusted if the rules of the time zone change.</span></span> <span data-ttu-id="e136e-118">这些属性必须是同步的, 因为旧版客户端仍可能会对**dispidTimeZoneStruct**属性进行操作。</span><span class="sxs-lookup"><span data-stu-id="e136e-118">These properties must be synchronized, because older clients may still manipulate the **dispidTimeZoneStruct** property.</span></span> <span data-ttu-id="e136e-119">若要检测这两个属性是否同步, 匹配**dispidTimeZoneStruct**的规则的**wFlags**成员应设置 TZRULE_FLAG_RECUR_CURRENT_TZREG 标志。</span><span class="sxs-lookup"><span data-stu-id="e136e-119">To detect whether the two properties are synchronized, the **wFlags** member for the rule that matches **dispidTimeZoneStruct** should have the TZRULE_FLAG_RECUR_CURRENT_TZREG flag set.</span></span> <span data-ttu-id="e136e-120">如果未设置此标志, 或者设置了此标志, 并且**dispidTimeZoneStruct**属性中的规则与标记的规则不匹配, 则应丢弃**dispidApptTZDefRecur**属性, 而应改用**dispidTimeZoneStruct** 。</span><span class="sxs-lookup"><span data-stu-id="e136e-120">If this flag is not set, or it is set and the rule in the **dispidTimeZoneStruct** property does not match the marked rule, the **dispidApptTZDefRecur** property should be discarded and **dispidTimeZoneStruct** should be used instead.</span></span> 
  
<span data-ttu-id="e136e-121">当您将**dispidApptTZDefRecur**和**dispidTimeZoneStruct**属性同时写入新的定期会议时, 或者当您使用**dispidTimeZoneStruct**属性进行任意选择时, 时区的当前定义 (应使用 Windows 注册表)。</span><span class="sxs-lookup"><span data-stu-id="e136e-121">When you write both the **dispidApptTZDefRecur** and **dispidTimeZoneStruct** properties to a new recurring meeting, or, when you make an arbitrary choice to use the **dispidTimeZoneStruct** property, the current definition for the time zone (according to the Windows registry) should be used.</span></span> 
  
<span data-ttu-id="e136e-122">分析器在读取从**dispidApptTZDefRecur**获取的流时, 或者在它保持**TZDEFINITION**为对二进制属性 (如**dispidApptTZDefRecur**) 承诺的流时, 必须小心。</span><span class="sxs-lookup"><span data-stu-id="e136e-122">A parser must be careful when it reads a stream that is obtained from **dispidApptTZDefRecur**, or when it persists **TZDEFINITION** to a stream for commitment to a binary property such as **dispidApptTZDefRecur**.</span></span> <span data-ttu-id="e136e-123">有关详细信息, 请参阅[关于将 TZDEFINITION 保留给 stream 以提交给二进制属性](https://msdn.microsoft.com/library/0dec535d-d48f-39a5-97d5-0bd109134b3b%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e136e-123">For more information, see [About persisting TZDEFINITION to a stream to commit to a binary property](https://msdn.microsoft.com/library/0dec535d-d48f-39a5-97d5-0bd109134b3b%28Office.15%29.aspx).</span></span>
  
 <span data-ttu-id="e136e-124">**dispidApptTZDefRecur**指定了描述如何将定期系列上的会议日期和时间转换为协调世界时 (UTC) 的时区信息。</span><span class="sxs-lookup"><span data-stu-id="e136e-124">**dispidApptTZDefRecur** specifies time zone information that describes how to convert the meeting date and time on a recurring series to and from Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="e136e-125">如果设置了此属性, 但它包含的数据与**dispidTimeZoneStruct**所表示的数据不一致, 则客户端必须使用**dispidTimeZoneStruct**而不是**dispidApptTZDefRecur**。</span><span class="sxs-lookup"><span data-stu-id="e136e-125">If this property is set but it has data that is inconsistent with the data represented by **dispidTimeZoneStruct**, the client must use **dispidTimeZoneStruct** instead of **dispidApptTZDefRecur**.</span></span> <span data-ttu-id="e136e-126">如果未设置**dispidApptTZDefRecur** , 则改为使用**PidLidTimeZoneStruct**属性。</span><span class="sxs-lookup"><span data-stu-id="e136e-126">If **dispidApptTZDefRecur** is not set, the **PidLidTimeZoneStruct** property will be used instead.</span></span> <span data-ttu-id="e136e-127">此 BLOB 中的字段以小字节序字节顺序进行编码。</span><span class="sxs-lookup"><span data-stu-id="e136e-127">The fields in this BLOB are encoded in little-endian byte order.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="e136e-128">相关资源</span><span class="sxs-lookup"><span data-stu-id="e136e-128">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e136e-129">协议规范</span><span class="sxs-lookup"><span data-stu-id="e136e-129">Protocol specifications</span></span>

<span data-ttu-id="e136e-130">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e136e-130">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e136e-131">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="e136e-131">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e136e-132">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e136e-132">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e136e-133">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="e136e-133">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e136e-134">头文件</span><span class="sxs-lookup"><span data-stu-id="e136e-134">Header files</span></span>

<span data-ttu-id="e136e-135">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="e136e-135">Mapidefs.h</span></span>
  
> <span data-ttu-id="e136e-136">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e136e-136">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e136e-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e136e-137">See also</span></span>



[<span data-ttu-id="e136e-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e136e-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e136e-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e136e-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e136e-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e136e-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e136e-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e136e-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

