---
title: PidTagOwnerAppointmentId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOwnerAppointmentId
api_type:
- COM
ms.assetid: b5eea554-6bca-42d1-b943-1327f0d70584
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a6fc194a3ef7d82be656a8d6c3f5fb9ad8326ceb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778006"
---
# <a name="pidtagownerappointmentid-canonical-property"></a><span data-ttu-id="30e82-103">PidTagOwnerAppointmentId 规范属性</span><span class="sxs-lookup"><span data-stu-id="30e82-103">PidTagOwnerAppointmentId Canonical Property</span></span>

  
  
<span data-ttu-id="30e82-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="30e82-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="30e82-105">包含约会的所有者计划中的标识符。</span><span class="sxs-lookup"><span data-stu-id="30e82-105">Contains an identifier for an appointment in the owner's schedule.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="30e82-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="30e82-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="30e82-107">PR_OWNER_APPT_ID</span><span class="sxs-lookup"><span data-stu-id="30e82-107">PR_OWNER_APPT_ID</span></span>  <br/> |
|<span data-ttu-id="30e82-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="30e82-108">Identifier:</span></span>  <br/> |<span data-ttu-id="30e82-109">0x0062</span><span class="sxs-lookup"><span data-stu-id="30e82-109">0x0062</span></span>  <br/> |
|<span data-ttu-id="30e82-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="30e82-110">Data type:</span></span>  <br/> |<span data-ttu-id="30e82-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="30e82-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="30e82-112">区域：</span><span class="sxs-lookup"><span data-stu-id="30e82-112">Area:</span></span>  <br/> |<span data-ttu-id="30e82-113">Appointment</span><span class="sxs-lookup"><span data-stu-id="30e82-113">Appointment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="30e82-114">说明</span><span class="sxs-lookup"><span data-stu-id="30e82-114">Remarks</span></span>

<span data-ttu-id="30e82-115">会议请求中使用此属性。</span><span class="sxs-lookup"><span data-stu-id="30e82-115">This property is used in meeting requests.</span></span> <span data-ttu-id="30e82-116">它不代表条目标识符，但唯一标识中发件人的日程安排约会的长整数。</span><span class="sxs-lookup"><span data-stu-id="30e82-116">It does not represent an entry identifier, but a long integer that uniquely identifies the appointment within the sender's schedule.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="30e82-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="30e82-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="30e82-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="30e82-118">Protocol specifications</span></span>

<span data-ttu-id="30e82-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="30e82-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="30e82-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="30e82-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="30e82-121">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="30e82-121">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="30e82-122">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="30e82-122">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="30e82-123">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="30e82-123">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="30e82-124">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="30e82-124">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="30e82-125">[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="30e82-125">[[MS-OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="30e82-126">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="30e82-126">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="30e82-127">头文件</span><span class="sxs-lookup"><span data-stu-id="30e82-127">Header files</span></span>

<span data-ttu-id="30e82-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="30e82-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="30e82-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="30e82-129">Provides data type definitions.</span></span>
    
<span data-ttu-id="30e82-130">mapitags.h</span><span class="sxs-lookup"><span data-stu-id="30e82-130">mapitags.h</span></span>
  
> <span data-ttu-id="30e82-131">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="30e82-131">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="30e82-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30e82-132">See also</span></span>



[<span data-ttu-id="30e82-133">PidTagOriginalAuthorSearchKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="30e82-133">PidTagOriginalAuthorSearchKey Canonical Property</span></span>](pidtagoriginalauthorsearchkey-canonical-property.md)


[<span data-ttu-id="30e82-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="30e82-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="30e82-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="30e82-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="30e82-136">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="30e82-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="30e82-137">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="30e82-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

