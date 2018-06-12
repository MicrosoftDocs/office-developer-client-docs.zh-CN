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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 37a6d101f6ee9c04236253e143aff3a51a9208d3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778329"
---
# <a name="pidtagscheduleinfoappointmenttombstone-canonical-property"></a><span data-ttu-id="ec7d0-103">PidTagScheduleInfoAppointmentTombstone 规范属性</span><span class="sxs-lookup"><span data-stu-id="ec7d0-103">PidTagScheduleInfoAppointmentTombstone Canonical Property</span></span>

  
  
<span data-ttu-id="ec7d0-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ec7d0-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ec7d0-105">包含表示已拒绝的会议数据块的列表。</span><span class="sxs-lookup"><span data-stu-id="ec7d0-105">Contains a list of data blocks that represent meetings that have been declined.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ec7d0-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="ec7d0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ec7d0-107">PR_SCHDINFO_APPT_TOMBSTONE</span><span class="sxs-lookup"><span data-stu-id="ec7d0-107">PR_SCHDINFO_APPT_TOMBSTONE</span></span>  <br/> |
|<span data-ttu-id="ec7d0-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ec7d0-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ec7d0-109">0x686A</span><span class="sxs-lookup"><span data-stu-id="ec7d0-109">0x686A</span></span>  <br/> |
|<span data-ttu-id="ec7d0-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ec7d0-110">Data type:</span></span>  <br/> |<span data-ttu-id="ec7d0-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="ec7d0-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="ec7d0-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ec7d0-112">Area:</span></span>  <br/> |<span data-ttu-id="ec7d0-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="ec7d0-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ec7d0-114">备注</span><span class="sxs-lookup"><span data-stu-id="ec7d0-114">Remarks</span></span>

<span data-ttu-id="ec7d0-115">数据块开始使用定义为 32 位值的标头：</span><span class="sxs-lookup"><span data-stu-id="ec7d0-115">The data blocks begin with a header of 32 bit values defined as:</span></span>
  
|<span data-ttu-id="ec7d0-116">**值**</span><span class="sxs-lookup"><span data-stu-id="ec7d0-116">**Value**</span></span>|<span data-ttu-id="ec7d0-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="ec7d0-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ec7d0-118">标示符</span><span class="sxs-lookup"><span data-stu-id="ec7d0-118">Identifier</span></span>  <br/> |<span data-ttu-id="ec7d0-119">此字段必须 0xBEDEAFCD 的值。</span><span class="sxs-lookup"><span data-stu-id="ec7d0-119">This field must be the value 0xBEDEAFCD.</span></span>  <br/> |
|<span data-ttu-id="ec7d0-120">HeaderSize</span><span class="sxs-lookup"><span data-stu-id="ec7d0-120">HeaderSize</span></span>  <br/> |<span data-ttu-id="ec7d0-121">此字段必须具有值 0x00000014。</span><span class="sxs-lookup"><span data-stu-id="ec7d0-121">This field must have the value 0x00000014.</span></span>  <br/> |
|<span data-ttu-id="ec7d0-122">版本</span><span class="sxs-lookup"><span data-stu-id="ec7d0-122">Version</span></span>  <br/> |<span data-ttu-id="ec7d0-123">此字段必须具有值 3。</span><span class="sxs-lookup"><span data-stu-id="ec7d0-123">This field must have the value 3.</span></span>  <br/> |
|<span data-ttu-id="ec7d0-124">RecordsCount</span><span class="sxs-lookup"><span data-stu-id="ec7d0-124">RecordsCount</span></span>  <br/> |<span data-ttu-id="ec7d0-125">按照的记录数。</span><span class="sxs-lookup"><span data-stu-id="ec7d0-125">The count of records that follow.</span></span>  <br/> |
|<span data-ttu-id="ec7d0-126">RecordsSize</span><span class="sxs-lookup"><span data-stu-id="ec7d0-126">RecordsSize</span></span>  <br/> |<span data-ttu-id="ec7d0-127">此字段必须具有值 0x00000014。</span><span class="sxs-lookup"><span data-stu-id="ec7d0-127">This field must have the value 0x00000014.</span></span>  <br/> |
   
<span data-ttu-id="ec7d0-128">标头是后跟的 32 位值定义为**RecordsCount**条目：</span><span class="sxs-lookup"><span data-stu-id="ec7d0-128">The header is followed by **RecordsCount** entries of 32 bit values defined as:</span></span> 
  
|<span data-ttu-id="ec7d0-129">**值**</span><span class="sxs-lookup"><span data-stu-id="ec7d0-129">**Value**</span></span>|<span data-ttu-id="ec7d0-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="ec7d0-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ec7d0-131">StartTime</span><span class="sxs-lookup"><span data-stu-id="ec7d0-131">StartTime</span></span>  <br/> |<span data-ttu-id="ec7d0-132">以分钟为单位，自午夜，1601 年 1 月 1 日，UTC 会议对象的开始时间。</span><span class="sxs-lookup"><span data-stu-id="ec7d0-132">The meeting object's start time in minutes since midnight, January 1, 1601, UTC.</span></span>  <br/> |
|<span data-ttu-id="ec7d0-133">结束时间</span><span class="sxs-lookup"><span data-stu-id="ec7d0-133">EndTime</span></span>  <br/> |<span data-ttu-id="ec7d0-134">以分钟为单位，自午夜，1601 年 1 月 1 日，UTC 会议对象的结束时间。</span><span class="sxs-lookup"><span data-stu-id="ec7d0-134">The meeting object's end time in minutes since midnight, January 1, 1601, UTC.</span></span>  <br/> |
|<span data-ttu-id="ec7d0-135">GlobalObjectIdSize</span><span class="sxs-lookup"><span data-stu-id="ec7d0-135">GlobalObjectIdSize</span></span>  <br/> |<span data-ttu-id="ec7d0-136">以字节为单位 GlobalObjectId 字段的大小。</span><span class="sxs-lookup"><span data-stu-id="ec7d0-136">The size, in bytes, of the GlobalObjectId field.</span></span>  <br/> |
|<span data-ttu-id="ec7d0-137">GlobalObjectId</span><span class="sxs-lookup"><span data-stu-id="ec7d0-137">GlobalObjectId</span></span>  <br/> |<span data-ttu-id="ec7d0-138">这记录会议的**LID_GLOBAL_OBJID** ([PidLidGlobalObjectId](pidlidglobalobjectid-canonical-property.md)) 属性的值表示。</span><span class="sxs-lookup"><span data-stu-id="ec7d0-138">The value of the **LID_GLOBAL_OBJID** ([PidLidGlobalObjectId](pidlidglobalobjectid-canonical-property.md)) property of the meeting this record represents.</span></span>  <br/> |
|<span data-ttu-id="ec7d0-139">UserName</span><span class="sxs-lookup"><span data-stu-id="ec7d0-139">UserName</span></span>  <br/> |<span data-ttu-id="ec7d0-140">前两个字节是遵循 PT_STRING8 字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="ec7d0-140">The first two bytes are the length of the PT_STRING8 string that follows.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="ec7d0-141">相关资源</span><span class="sxs-lookup"><span data-stu-id="ec7d0-141">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ec7d0-142">协议规范</span><span class="sxs-lookup"><span data-stu-id="ec7d0-142">Protocol specifications</span></span>

<span data-ttu-id="ec7d0-143">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ec7d0-143">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ec7d0-144">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="ec7d0-144">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ec7d0-145">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ec7d0-145">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ec7d0-146">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="ec7d0-146">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ec7d0-147">头文件</span><span class="sxs-lookup"><span data-stu-id="ec7d0-147">Header files</span></span>

<span data-ttu-id="ec7d0-148">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ec7d0-148">Mapidefs.h</span></span>
  
> <span data-ttu-id="ec7d0-149">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ec7d0-149">Provides data type definitions.</span></span>
    
<span data-ttu-id="ec7d0-150">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ec7d0-150">Mapitags.h</span></span>
  
> <span data-ttu-id="ec7d0-151">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ec7d0-151">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ec7d0-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec7d0-152">See also</span></span>



[<span data-ttu-id="ec7d0-153">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ec7d0-153">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ec7d0-154">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ec7d0-154">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ec7d0-155">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ec7d0-155">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ec7d0-156">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ec7d0-156">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

