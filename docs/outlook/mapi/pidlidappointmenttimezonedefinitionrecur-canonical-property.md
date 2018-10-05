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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389300"
---
# <a name="pidlidappointmenttimezonedefinitionrecur-canonical-property"></a><span data-ttu-id="12c83-103">PidLidAppointmentTimeZoneDefinitionRecur 规范属性</span><span class="sxs-lookup"><span data-stu-id="12c83-103">PidLidAppointmentTimeZoneDefinitionRecur Canonical Property</span></span>

  
  
<span data-ttu-id="12c83-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="12c83-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="12c83-105">包含映射到的存储的说明创建定期约会或会议请求时使用的时区[TZDEFINITION](https://msdn.microsoft.com/library/0ae21571-2299-6407-807c-428668bb6798%28Office.15%29.aspx)结构持久化格式的流。</span><span class="sxs-lookup"><span data-stu-id="12c83-105">Contains a stream that maps to the persisted format of a [TZDEFINITION](https://msdn.microsoft.com/library/0ae21571-2299-6407-807c-428668bb6798%28Office.15%29.aspx) structure, which stores the description for the time zone that is used when a recurring appointment or meeting request is created.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="12c83-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="12c83-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="12c83-107">dispidApptTZDefRecur</span><span class="sxs-lookup"><span data-stu-id="12c83-107">dispidApptTZDefRecur</span></span>  <br/> |
|<span data-ttu-id="12c83-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="12c83-108">Property set:</span></span>  <br/> |<span data-ttu-id="12c83-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="12c83-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="12c83-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="12c83-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="12c83-111">0x00008260</span><span class="sxs-lookup"><span data-stu-id="12c83-111">0x00008260</span></span>  <br/> |
|<span data-ttu-id="12c83-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="12c83-112">Data type:</span></span>  <br/> |<span data-ttu-id="12c83-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="12c83-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="12c83-114">区域：</span><span class="sxs-lookup"><span data-stu-id="12c83-114">Area:</span></span>  <br/> |<span data-ttu-id="12c83-115">日历</span><span class="sxs-lookup"><span data-stu-id="12c83-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="12c83-116">说明</span><span class="sxs-lookup"><span data-stu-id="12c83-116">Remarks</span></span>

<span data-ttu-id="12c83-117">自 Microsoft Office Outlook 2007 和基于上协作数据对象 (CDO) 1.2.1 （英文) 的解决方案的 Microsoft Outlook 的运行 Outlook 或 Exchange Server 日历版本更新工具使用**dispidApptTZDefRecur**和**dispidTimeZoneStruct** ([PidLidTimeZoneStruct](pidlidtimezonestruct-canonical-property.md)) 属性以确定是否应调整定期会议，是否更改时区的规则。</span><span class="sxs-lookup"><span data-stu-id="12c83-117">Versions of Microsoft Outlook since Microsoft Office Outlook 2007, and solutions based on Collaboration Data Objects (CDO) 1.2.1 that have run the Outlook or Exchange Server calendar update tool use the **dispidApptTZDefRecur** and **dispidTimeZoneStruct** ([PidLidTimeZoneStruct](pidlidtimezonestruct-canonical-property.md)) properties to determine whether the recurring meeting should be adjusted if the rules of the time zone change.</span></span> <span data-ttu-id="12c83-118">这些属性必须保持同步，因为旧客户端可能仍然操作**dispidTimeZoneStruct**属性。</span><span class="sxs-lookup"><span data-stu-id="12c83-118">These properties must be synchronized, because older clients may still manipulate the **dispidTimeZoneStruct** property.</span></span> <span data-ttu-id="12c83-119">若要检测是否同步两个属性，规则相匹配**dispidTimeZoneStruct** **wFlags**成员应具有的 TZRULE_FLAG_RECUR_CURRENT_TZREG 标记设置。</span><span class="sxs-lookup"><span data-stu-id="12c83-119">To detect whether the two properties are synchronized, the **wFlags** member for the rule that matches **dispidTimeZoneStruct** should have the TZRULE_FLAG_RECUR_CURRENT_TZREG flag set.</span></span> <span data-ttu-id="12c83-120">如果未设置此标志，或将其设置**dispidTimeZoneStruct**属性中的规则与标记的规则不匹配时，应丢弃**dispidApptTZDefRecur**属性，并应改用**dispidTimeZoneStruct** 。</span><span class="sxs-lookup"><span data-stu-id="12c83-120">If this flag is not set, or it is set and the rule in the **dispidTimeZoneStruct** property does not match the marked rule, the **dispidApptTZDefRecur** property should be discarded and **dispidTimeZoneStruct** should be used instead.</span></span> 
  
<span data-ttu-id="12c83-121">当您编写的**dispidApptTZDefRecur**和**dispidTimeZoneStruct**属性到新的定期会议，或时使任意选择使用**dispidTimeZoneStruct**属性，所在的时区 （的当前定义应使用根据 Windows 注册表中）。</span><span class="sxs-lookup"><span data-stu-id="12c83-121">When you write both the **dispidApptTZDefRecur** and **dispidTimeZoneStruct** properties to a new recurring meeting, or, when you make an arbitrary choice to use the **dispidTimeZoneStruct** property, the current definition for the time zone (according to the Windows registry) should be used.</span></span> 
  
<span data-ttu-id="12c83-122">分析程序必须注意，它读取从**dispidApptTZDefRecur**，获得一个流或时它所**TZDEFINITION**持久化到承诺如**dispidApptTZDefRecur**二进制属性的流。</span><span class="sxs-lookup"><span data-stu-id="12c83-122">A parser must be careful when it reads a stream that is obtained from **dispidApptTZDefRecur**, or when it persists **TZDEFINITION** to a stream for commitment to a binary property such as **dispidApptTZDefRecur**.</span></span> <span data-ttu-id="12c83-123">有关详细信息，请参阅[关于保留 TZDEFINITION 到流提交到二进制属性](https://msdn.microsoft.com/library/0dec535d-d48f-39a5-97d5-0bd109134b3b%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="12c83-123">For more information, see [About persisting TZDEFINITION to a stream to commit to a binary property](https://msdn.microsoft.com/library/0dec535d-d48f-39a5-97d5-0bd109134b3b%28Office.15%29.aspx).</span></span>
  
 <span data-ttu-id="12c83-124">**dispidApptTZDefRecur**指定介绍如何将收件人和与协调世界时 (UTC) 转换会议日期和时间定期系列的时区信息。</span><span class="sxs-lookup"><span data-stu-id="12c83-124">**dispidApptTZDefRecur** specifies time zone information that describes how to convert the meeting date and time on a recurring series to and from Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="12c83-125">如果设置此属性，但它具有与由**dispidTimeZoneStruct**代表的数据不一致的数据，客户端必须使用**dispidTimeZoneStruct** ，而不是**dispidApptTZDefRecur**。</span><span class="sxs-lookup"><span data-stu-id="12c83-125">If this property is set but it has data that is inconsistent with the data represented by **dispidTimeZoneStruct**, the client must use **dispidTimeZoneStruct** instead of **dispidApptTZDefRecur**.</span></span> <span data-ttu-id="12c83-126">如果未设置**dispidApptTZDefRecur** ，将使用**PidLidTimeZoneStruct**属性。</span><span class="sxs-lookup"><span data-stu-id="12c83-126">If **dispidApptTZDefRecur** is not set, the **PidLidTimeZoneStruct** property will be used instead.</span></span> <span data-ttu-id="12c83-127">此 BLOB 中的字段顺序-little-endian 字节编码。</span><span class="sxs-lookup"><span data-stu-id="12c83-127">The fields in this BLOB are encoded in little-endian byte order.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="12c83-128">相关资源</span><span class="sxs-lookup"><span data-stu-id="12c83-128">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="12c83-129">协议规范</span><span class="sxs-lookup"><span data-stu-id="12c83-129">Protocol specifications</span></span>

<span data-ttu-id="12c83-130">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="12c83-130">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="12c83-131">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="12c83-131">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="12c83-132">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="12c83-132">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="12c83-133">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="12c83-133">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="12c83-134">头文件</span><span class="sxs-lookup"><span data-stu-id="12c83-134">Header files</span></span>

<span data-ttu-id="12c83-135">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="12c83-135">Mapidefs.h</span></span>
  
> <span data-ttu-id="12c83-136">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="12c83-136">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="12c83-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12c83-137">See also</span></span>



[<span data-ttu-id="12c83-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="12c83-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="12c83-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="12c83-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="12c83-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="12c83-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="12c83-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="12c83-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

