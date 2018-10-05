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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399163"
---
# <a name="pidtagscheduleinfoappointmenttombstone-canonical-property"></a><span data-ttu-id="d8314-103">PidTagScheduleInfoAppointmentTombstone 规范属性</span><span class="sxs-lookup"><span data-stu-id="d8314-103">PidTagScheduleInfoAppointmentTombstone Canonical Property</span></span>

  
  
<span data-ttu-id="d8314-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d8314-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d8314-105">包含表示已拒绝的会议数据块的列表。</span><span class="sxs-lookup"><span data-stu-id="d8314-105">Contains a list of data blocks that represent meetings that have been declined.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d8314-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d8314-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d8314-107">PR_SCHDINFO_APPT_TOMBSTONE</span><span class="sxs-lookup"><span data-stu-id="d8314-107">PR_SCHDINFO_APPT_TOMBSTONE</span></span>  <br/> |
|<span data-ttu-id="d8314-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="d8314-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d8314-109">0x686A</span><span class="sxs-lookup"><span data-stu-id="d8314-109">0x686A</span></span>  <br/> |
|<span data-ttu-id="d8314-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d8314-110">Data type:</span></span>  <br/> |<span data-ttu-id="d8314-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="d8314-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="d8314-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d8314-112">Area:</span></span>  <br/> |<span data-ttu-id="d8314-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="d8314-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d8314-114">说明</span><span class="sxs-lookup"><span data-stu-id="d8314-114">Remarks</span></span>

<span data-ttu-id="d8314-115">数据块开始使用定义为 32 位值的标头：</span><span class="sxs-lookup"><span data-stu-id="d8314-115">The data blocks begin with a header of 32 bit values defined as:</span></span>
  
|<span data-ttu-id="d8314-116">**值**</span><span class="sxs-lookup"><span data-stu-id="d8314-116">**Value**</span></span>|<span data-ttu-id="d8314-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="d8314-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d8314-118">标示符</span><span class="sxs-lookup"><span data-stu-id="d8314-118">Identifier</span></span>  <br/> |<span data-ttu-id="d8314-119">此字段必须 0xBEDEAFCD 的值。</span><span class="sxs-lookup"><span data-stu-id="d8314-119">This field must be the value 0xBEDEAFCD.</span></span>  <br/> |
|<span data-ttu-id="d8314-120">HeaderSize</span><span class="sxs-lookup"><span data-stu-id="d8314-120">HeaderSize</span></span>  <br/> |<span data-ttu-id="d8314-121">此字段必须具有值 0x00000014。</span><span class="sxs-lookup"><span data-stu-id="d8314-121">This field must have the value 0x00000014.</span></span>  <br/> |
|<span data-ttu-id="d8314-122">版本</span><span class="sxs-lookup"><span data-stu-id="d8314-122">Version</span></span>  <br/> |<span data-ttu-id="d8314-123">此字段必须具有值 3。</span><span class="sxs-lookup"><span data-stu-id="d8314-123">This field must have the value 3.</span></span>  <br/> |
|<span data-ttu-id="d8314-124">RecordsCount</span><span class="sxs-lookup"><span data-stu-id="d8314-124">RecordsCount</span></span>  <br/> |<span data-ttu-id="d8314-125">按照的记录数。</span><span class="sxs-lookup"><span data-stu-id="d8314-125">The count of records that follow.</span></span>  <br/> |
|<span data-ttu-id="d8314-126">RecordsSize</span><span class="sxs-lookup"><span data-stu-id="d8314-126">RecordsSize</span></span>  <br/> |<span data-ttu-id="d8314-127">此字段必须具有值 0x00000014。</span><span class="sxs-lookup"><span data-stu-id="d8314-127">This field must have the value 0x00000014.</span></span>  <br/> |
   
<span data-ttu-id="d8314-128">标头是后跟的 32 位值定义为**RecordsCount**条目：</span><span class="sxs-lookup"><span data-stu-id="d8314-128">The header is followed by **RecordsCount** entries of 32 bit values defined as:</span></span> 
  
|<span data-ttu-id="d8314-129">**值**</span><span class="sxs-lookup"><span data-stu-id="d8314-129">**Value**</span></span>|<span data-ttu-id="d8314-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="d8314-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d8314-131">StartTime</span><span class="sxs-lookup"><span data-stu-id="d8314-131">StartTime</span></span>  <br/> |<span data-ttu-id="d8314-132">以分钟为单位，自午夜，1601 年 1 月 1 日，UTC 会议对象的开始时间。</span><span class="sxs-lookup"><span data-stu-id="d8314-132">The meeting object's start time in minutes since midnight, January 1, 1601, UTC.</span></span>  <br/> |
|<span data-ttu-id="d8314-133">EndTime</span><span class="sxs-lookup"><span data-stu-id="d8314-133">EndTime</span></span>  <br/> |<span data-ttu-id="d8314-134">以分钟为单位，自午夜，1601 年 1 月 1 日，UTC 会议对象的结束时间。</span><span class="sxs-lookup"><span data-stu-id="d8314-134">The meeting object's end time in minutes since midnight, January 1, 1601, UTC.</span></span>  <br/> |
|<span data-ttu-id="d8314-135">GlobalObjectIdSize</span><span class="sxs-lookup"><span data-stu-id="d8314-135">GlobalObjectIdSize</span></span>  <br/> |<span data-ttu-id="d8314-136">以字节为单位 GlobalObjectId 字段的大小。</span><span class="sxs-lookup"><span data-stu-id="d8314-136">The size, in bytes, of the GlobalObjectId field.</span></span>  <br/> |
|<span data-ttu-id="d8314-137">GlobalObjectId</span><span class="sxs-lookup"><span data-stu-id="d8314-137">GlobalObjectId</span></span>  <br/> |<span data-ttu-id="d8314-138">这记录会议的**LID_GLOBAL_OBJID** ([PidLidGlobalObjectId](pidlidglobalobjectid-canonical-property.md)) 属性的值表示。</span><span class="sxs-lookup"><span data-stu-id="d8314-138">The value of the **LID_GLOBAL_OBJID** ([PidLidGlobalObjectId](pidlidglobalobjectid-canonical-property.md)) property of the meeting this record represents.</span></span>  <br/> |
|<span data-ttu-id="d8314-139">UserName</span><span class="sxs-lookup"><span data-stu-id="d8314-139">UserName</span></span>  <br/> |<span data-ttu-id="d8314-140">前两个字节是遵循 PT_STRING8 字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="d8314-140">The first two bytes are the length of the PT_STRING8 string that follows.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="d8314-141">相关资源</span><span class="sxs-lookup"><span data-stu-id="d8314-141">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d8314-142">协议规范</span><span class="sxs-lookup"><span data-stu-id="d8314-142">Protocol specifications</span></span>

<span data-ttu-id="d8314-143">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d8314-143">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d8314-144">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="d8314-144">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d8314-145">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d8314-145">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d8314-146">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="d8314-146">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d8314-147">头文件</span><span class="sxs-lookup"><span data-stu-id="d8314-147">Header files</span></span>

<span data-ttu-id="d8314-148">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d8314-148">Mapidefs.h</span></span>
  
> <span data-ttu-id="d8314-149">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d8314-149">Provides data type definitions.</span></span>
    
<span data-ttu-id="d8314-150">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d8314-150">Mapitags.h</span></span>
  
> <span data-ttu-id="d8314-151">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d8314-151">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d8314-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8314-152">See also</span></span>



[<span data-ttu-id="d8314-153">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d8314-153">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d8314-154">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d8314-154">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d8314-155">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d8314-155">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d8314-156">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d8314-156">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

