---
title: PidTagScheduleInfoAppointmentTombstone 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoAppointmentTombstone
api_type:
- COM
ms.assetid: 6b82e2ee-992f-4cbe-bdcb-e7465e556640
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7a7134a037aa4845ae22ab18899d27f1e50d6b7e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321320"
---
# <a name="pidtagscheduleinfoappointmenttombstone-canonical-property"></a><span data-ttu-id="b7938-103">PidTagScheduleInfoAppointmentTombstone 规范属性</span><span class="sxs-lookup"><span data-stu-id="b7938-103">PidTagScheduleInfoAppointmentTombstone Canonical Property</span></span>

  
  
<span data-ttu-id="b7938-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b7938-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b7938-105">包含表示已被谢绝的会议的数据块的列表。</span><span class="sxs-lookup"><span data-stu-id="b7938-105">Contains a list of data blocks that represent meetings that have been declined.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b7938-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b7938-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b7938-107">PR_SCHDINFO_APPT_TOMBSTONE</span><span class="sxs-lookup"><span data-stu-id="b7938-107">PR_SCHDINFO_APPT_TOMBSTONE</span></span>  <br/> |
|<span data-ttu-id="b7938-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="b7938-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b7938-109">0x686A</span><span class="sxs-lookup"><span data-stu-id="b7938-109">0x686A</span></span>  <br/> |
|<span data-ttu-id="b7938-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b7938-110">Data type:</span></span>  <br/> |<span data-ttu-id="b7938-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="b7938-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="b7938-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b7938-112">Area:</span></span>  <br/> |<span data-ttu-id="b7938-113">闲/忙</span><span class="sxs-lookup"><span data-stu-id="b7938-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b7938-114">注解</span><span class="sxs-lookup"><span data-stu-id="b7938-114">Remarks</span></span>

<span data-ttu-id="b7938-115">数据块开头的标头为32位值, 其定义为:</span><span class="sxs-lookup"><span data-stu-id="b7938-115">The data blocks begin with a header of 32 bit values defined as:</span></span>
  
|<span data-ttu-id="b7938-116">**Value**</span><span class="sxs-lookup"><span data-stu-id="b7938-116">**Value**</span></span>|<span data-ttu-id="b7938-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="b7938-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b7938-118">标示符</span><span class="sxs-lookup"><span data-stu-id="b7938-118">Identifier</span></span>  <br/> |<span data-ttu-id="b7938-119">此字段必须为0xBEDEAFCD 值。</span><span class="sxs-lookup"><span data-stu-id="b7938-119">This field must be the value 0xBEDEAFCD.</span></span>  <br/> |
|<span data-ttu-id="b7938-120">HeaderSize</span><span class="sxs-lookup"><span data-stu-id="b7938-120">HeaderSize</span></span>  <br/> |<span data-ttu-id="b7938-121">此字段的值必须为0x00000014。</span><span class="sxs-lookup"><span data-stu-id="b7938-121">This field must have the value 0x00000014.</span></span>  <br/> |
|<span data-ttu-id="b7938-122">Version</span><span class="sxs-lookup"><span data-stu-id="b7938-122">Version</span></span>  <br/> |<span data-ttu-id="b7938-123">此字段的值必须为3。</span><span class="sxs-lookup"><span data-stu-id="b7938-123">This field must have the value 3.</span></span>  <br/> |
|<span data-ttu-id="b7938-124">RecordsCount</span><span class="sxs-lookup"><span data-stu-id="b7938-124">RecordsCount</span></span>  <br/> |<span data-ttu-id="b7938-125">追随的记录数。</span><span class="sxs-lookup"><span data-stu-id="b7938-125">The count of records that follow.</span></span>  <br/> |
|<span data-ttu-id="b7938-126">RecordsSize</span><span class="sxs-lookup"><span data-stu-id="b7938-126">RecordsSize</span></span>  <br/> |<span data-ttu-id="b7938-127">此字段的值必须为0x00000014。</span><span class="sxs-lookup"><span data-stu-id="b7938-127">This field must have the value 0x00000014.</span></span>  <br/> |
   
<span data-ttu-id="b7938-128">头的后面是32位值的**RecordsCount**项定义为:</span><span class="sxs-lookup"><span data-stu-id="b7938-128">The header is followed by **RecordsCount** entries of 32 bit values defined as:</span></span> 
  
|<span data-ttu-id="b7938-129">**Value**</span><span class="sxs-lookup"><span data-stu-id="b7938-129">**Value**</span></span>|<span data-ttu-id="b7938-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="b7938-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b7938-131">StartTime</span><span class="sxs-lookup"><span data-stu-id="b7938-131">StartTime</span></span>  <br/> |<span data-ttu-id="b7938-132">自午夜年1月1日 (UTC) 起, 会议对象的开始时间 (以分钟为单位)。</span><span class="sxs-lookup"><span data-stu-id="b7938-132">The meeting object's start time in minutes since midnight, January 1, 1601, UTC.</span></span>  <br/> |
|<span data-ttu-id="b7938-133">EndTime</span><span class="sxs-lookup"><span data-stu-id="b7938-133">EndTime</span></span>  <br/> |<span data-ttu-id="b7938-134">自午夜、1601年1月1日午夜起, 会议对象的结束时间 (以分钟为单位)。</span><span class="sxs-lookup"><span data-stu-id="b7938-134">The meeting object's end time in minutes since midnight, January 1, 1601, UTC.</span></span>  <br/> |
|<span data-ttu-id="b7938-135">GlobalObjectIdSize</span><span class="sxs-lookup"><span data-stu-id="b7938-135">GlobalObjectIdSize</span></span>  <br/> |<span data-ttu-id="b7938-136">GlobalObjectId 字段的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="b7938-136">The size, in bytes, of the GlobalObjectId field.</span></span>  <br/> |
|<span data-ttu-id="b7938-137">GlobalObjectId</span><span class="sxs-lookup"><span data-stu-id="b7938-137">GlobalObjectId</span></span>  <br/> |<span data-ttu-id="b7938-138">此记录表示的会议的**LID_GLOBAL_OBJID** ([PidLidGlobalObjectId](pidlidglobalobjectid-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="b7938-138">The value of the **LID_GLOBAL_OBJID** ([PidLidGlobalObjectId](pidlidglobalobjectid-canonical-property.md)) property of the meeting this record represents.</span></span>  <br/> |
|<span data-ttu-id="b7938-139">UserName</span><span class="sxs-lookup"><span data-stu-id="b7938-139">UserName</span></span>  <br/> |<span data-ttu-id="b7938-140">前两个字节是 PT_STRING8 字符串的长度, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="b7938-140">The first two bytes are the length of the PT_STRING8 string that follows.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="b7938-141">相关资源</span><span class="sxs-lookup"><span data-stu-id="b7938-141">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b7938-142">协议规范</span><span class="sxs-lookup"><span data-stu-id="b7938-142">Protocol specifications</span></span>

<span data-ttu-id="b7938-143">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b7938-143">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b7938-144">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b7938-144">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b7938-145">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b7938-145">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b7938-146">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="b7938-146">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b7938-147">头文件</span><span class="sxs-lookup"><span data-stu-id="b7938-147">Header files</span></span>

<span data-ttu-id="b7938-148">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="b7938-148">Mapidefs.h</span></span>
  
> <span data-ttu-id="b7938-149">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b7938-149">Provides data type definitions.</span></span>
    
<span data-ttu-id="b7938-150">Mapitags</span><span class="sxs-lookup"><span data-stu-id="b7938-150">Mapitags.h</span></span>
  
> <span data-ttu-id="b7938-151">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b7938-151">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b7938-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7938-152">See also</span></span>



[<span data-ttu-id="b7938-153">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b7938-153">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b7938-154">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b7938-154">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b7938-155">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b7938-155">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b7938-156">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b7938-156">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

