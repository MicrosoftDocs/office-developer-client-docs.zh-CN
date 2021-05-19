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
# <a name="pidlidappointmenttimezonedefinitionrecur-canonical-property"></a><span data-ttu-id="209a6-103">PidLidAppointmentTimeZoneDefinitionRecur 规范属性</span><span class="sxs-lookup"><span data-stu-id="209a6-103">PidLidAppointmentTimeZoneDefinitionRecur Canonical Property</span></span>

  
  
<span data-ttu-id="209a6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="209a6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="209a6-105">包含映射到 [TZDEFINITION](https://msdn.microsoft.com/library/0ae21571-2299-6407-807c-428668bb6798%28Office.15%29.aspx) 结构的持久格式的流，该流存储创建定期约会或会议请求时所使用的时区的说明。</span><span class="sxs-lookup"><span data-stu-id="209a6-105">Contains a stream that maps to the persisted format of a [TZDEFINITION](https://msdn.microsoft.com/library/0ae21571-2299-6407-807c-428668bb6798%28Office.15%29.aspx) structure, which stores the description for the time zone that is used when a recurring appointment or meeting request is created.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="209a6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="209a6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="209a6-107">dispidApptTZDefRecur</span><span class="sxs-lookup"><span data-stu-id="209a6-107">dispidApptTZDefRecur</span></span>  <br/> |
|<span data-ttu-id="209a6-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="209a6-108">Property set:</span></span>  <br/> |<span data-ttu-id="209a6-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="209a6-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="209a6-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="209a6-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="209a6-111">0x00008260</span><span class="sxs-lookup"><span data-stu-id="209a6-111">0x00008260</span></span>  <br/> |
|<span data-ttu-id="209a6-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="209a6-112">Data type:</span></span>  <br/> |<span data-ttu-id="209a6-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="209a6-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="209a6-114">区域：</span><span class="sxs-lookup"><span data-stu-id="209a6-114">Area:</span></span>  <br/> |<span data-ttu-id="209a6-115">日历</span><span class="sxs-lookup"><span data-stu-id="209a6-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="209a6-116">备注</span><span class="sxs-lookup"><span data-stu-id="209a6-116">Remarks</span></span>

<span data-ttu-id="209a6-117">自 Microsoft Office Outlook 2007 以来的 Microsoft Outlook 版本以及基于协作数据对象 (CDO) 1.2.1 且已运行 Outlook 或 Exchange Server 日历更新工具的解决方案使用 **dispidApptTZDefRecur** 和 **dispidTimeZoneStruct** ([PidLidTimeZoneStruct](pidlidtimezonestruct-canonical-property.md)) 属性来确定在时区规则更改时是否应该调整定期会议。</span><span class="sxs-lookup"><span data-stu-id="209a6-117">Versions of Microsoft Outlook since Microsoft Office Outlook 2007, and solutions based on Collaboration Data Objects (CDO) 1.2.1 that have run the Outlook or Exchange Server calendar update tool use the **dispidApptTZDefRecur** and **dispidTimeZoneStruct** ([PidLidTimeZoneStruct](pidlidtimezonestruct-canonical-property.md)) properties to determine whether the recurring meeting should be adjusted if the rules of the time zone change.</span></span> <span data-ttu-id="209a6-118">这些属性必须同步，因为较旧的客户端仍可操作 **dispidTimeZoneStruct** 属性。</span><span class="sxs-lookup"><span data-stu-id="209a6-118">These properties must be synchronized, because older clients may still manipulate the **dispidTimeZoneStruct** property.</span></span> <span data-ttu-id="209a6-119">若要检测这两个属性是否同步，与 **dispidTimeZoneStruct** 匹配的规则的 **wFlags** 成员应设置TZRULE_FLAG_RECUR_CURRENT_TZREG标志。</span><span class="sxs-lookup"><span data-stu-id="209a6-119">To detect whether the two properties are synchronized, the **wFlags** member for the rule that matches **dispidTimeZoneStruct** should have the TZRULE_FLAG_RECUR_CURRENT_TZREG flag set.</span></span> <span data-ttu-id="209a6-120">如果未设置此标志，或者已设置此标志，**并且 dispidTimeZoneStruct** 属性中的规则与标记的规则不匹配，应放弃 **dispidApptTZDefRecur** 属性，而应改为使用 **dispidTimeZoneStruct。**</span><span class="sxs-lookup"><span data-stu-id="209a6-120">If this flag is not set, or it is set and the rule in the **dispidTimeZoneStruct** property does not match the marked rule, the **dispidApptTZDefRecur** property should be discarded and **dispidTimeZoneStruct** should be used instead.</span></span> 
  
<span data-ttu-id="209a6-121">当您将 **dispidApptTZDefRecur** 和 **dispidTimeZoneStruct** 属性写入新的定期会议时，或者当您任意选择使用 **dispidTimeZoneStruct** 属性时，应该根据 Windows 注册表) 使用时区 (的当前定义。</span><span class="sxs-lookup"><span data-stu-id="209a6-121">When you write both the **dispidApptTZDefRecur** and **dispidTimeZoneStruct** properties to a new recurring meeting, or, when you make an arbitrary choice to use the **dispidTimeZoneStruct** property, the current definition for the time zone (according to the Windows registry) should be used.</span></span> 
  
<span data-ttu-id="209a6-122">分析程序在读取从 **dispidApptTZDefRecur** 获取的流时，或将 **TZDEFINITION** 保留为流以承诺使用二进制属性（如 **dispidApptTZDefRecur）** 时必须小心。</span><span class="sxs-lookup"><span data-stu-id="209a6-122">A parser must be careful when it reads a stream that is obtained from **dispidApptTZDefRecur**, or when it persists **TZDEFINITION** to a stream for commitment to a binary property such as **dispidApptTZDefRecur**.</span></span> <span data-ttu-id="209a6-123">有关详细信息，请参阅关于 [将 TZDEFINITION 持久化到流以提交到二进制属性](https://msdn.microsoft.com/library/0dec535d-d48f-39a5-97d5-0bd109134b3b%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="209a6-123">For more information, see [About persisting TZDEFINITION to a stream to commit to a binary property](https://msdn.microsoft.com/library/0dec535d-d48f-39a5-97d5-0bd109134b3b%28Office.15%29.aspx).</span></span>
  
 <span data-ttu-id="209a6-124">**dispidApptTZDefRecur** 指定时区信息，该信息描述如何将定期系列上的会议日期和时间转换为协调世界时 (UTC) 。</span><span class="sxs-lookup"><span data-stu-id="209a6-124">**dispidApptTZDefRecur** specifies time zone information that describes how to convert the meeting date and time on a recurring series to and from Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="209a6-125">如果设置了此属性，但其数据与 **dispidTimeZoneStruct** 表示的数据不一致，则客户端必须使用 **dispidTimeZoneStruct** 而不是 **dispidApptTZDefRecur**。</span><span class="sxs-lookup"><span data-stu-id="209a6-125">If this property is set but it has data that is inconsistent with the data represented by **dispidTimeZoneStruct**, the client must use **dispidTimeZoneStruct** instead of **dispidApptTZDefRecur**.</span></span> <span data-ttu-id="209a6-126">如果未 **设置 dispidApptTZDefRecur，** 将改为使用 **PidLidTimeZoneStruct** 属性。</span><span class="sxs-lookup"><span data-stu-id="209a6-126">If **dispidApptTZDefRecur** is not set, the **PidLidTimeZoneStruct** property will be used instead.</span></span> <span data-ttu-id="209a6-127">此 BLOB 中的字段按小尾字节顺序进行编码。</span><span class="sxs-lookup"><span data-stu-id="209a6-127">The fields in this BLOB are encoded in little-endian byte order.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="209a6-128">相关资源</span><span class="sxs-lookup"><span data-stu-id="209a6-128">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="209a6-129">协议规范</span><span class="sxs-lookup"><span data-stu-id="209a6-129">Protocol specifications</span></span>

<span data-ttu-id="209a6-130">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="209a6-130">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="209a6-131">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="209a6-131">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="209a6-132">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="209a6-132">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="209a6-133">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="209a6-133">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="209a6-134">头文件</span><span class="sxs-lookup"><span data-stu-id="209a6-134">Header files</span></span>

<span data-ttu-id="209a6-135">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="209a6-135">Mapidefs.h</span></span>
  
> <span data-ttu-id="209a6-136">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="209a6-136">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="209a6-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="209a6-137">See also</span></span>



[<span data-ttu-id="209a6-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="209a6-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="209a6-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="209a6-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="209a6-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="209a6-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="209a6-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="209a6-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

