---
title: PidTagRecipientProposedStartTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientProposedStartTime
api_type:
- COM
ms.assetid: 6687ff62-7ac6-409c-8c87-4e09d38e45f1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7500918daed361eac1c20e46e4046f47b6339c89
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580857"
---
# <a name="pidtagrecipientproposedstarttime-canonical-property"></a><span data-ttu-id="bc722-103">PidTagRecipientProposedStartTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="bc722-103">PidTagRecipientProposedStartTime Canonical Property</span></span>

  
  
<span data-ttu-id="bc722-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bc722-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bc722-105">表示会议建议开始时间。</span><span class="sxs-lookup"><span data-stu-id="bc722-105">Indicates a proposed starting time of a meeting.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="bc722-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="bc722-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="bc722-107">PR_RECIPIENT_PROPOSEDSTARTTIME</span><span class="sxs-lookup"><span data-stu-id="bc722-107">PR_RECIPIENT_PROPOSEDSTARTTIME</span></span>  <br/> |
|<span data-ttu-id="bc722-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="bc722-108">Identifier:</span></span>  <br/> |<span data-ttu-id="bc722-109">0x5FE3</span><span class="sxs-lookup"><span data-stu-id="bc722-109">0x5FE3</span></span>  <br/> |
|<span data-ttu-id="bc722-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="bc722-110">Data type:</span></span>  <br/> |<span data-ttu-id="bc722-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="bc722-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="bc722-112">区域：</span><span class="sxs-lookup"><span data-stu-id="bc722-112">Area:</span></span>  <br/> |<span data-ttu-id="bc722-113">传输收件人</span><span class="sxs-lookup"><span data-stu-id="bc722-113">Transport recipient</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bc722-114">注解</span><span class="sxs-lookup"><span data-stu-id="bc722-114">Remarks</span></span>

<span data-ttu-id="bc722-115">此属性的值时**PR_RECIPIENT_PROPOSED** ([PidTagRecipientProposed](pidtagrecipientproposed-canonical-property.md)) 属性的值设置为 TRUE，指示请求参与者设置为**dispidApptStartWhole** ([的值的值PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) 的单个实例会议对象或 exception 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="bc722-115">When the value of the **PR_RECIPIENT_PROPOSED** ([PidTagRecipientProposed](pidtagrecipientproposed-canonical-property.md)) property is set to TRUE, the value of this property indicates the value requested by the attendee to set as the value of the **dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) property for the single instance meeting object or exception object.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="bc722-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="bc722-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="bc722-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="bc722-117">Protocol specifications</span></span>

<span data-ttu-id="bc722-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bc722-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="bc722-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="bc722-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="bc722-120">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bc722-120">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="bc722-121">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="bc722-121">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="bc722-122">头文件</span><span class="sxs-lookup"><span data-stu-id="bc722-122">Header files</span></span>

<span data-ttu-id="bc722-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="bc722-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="bc722-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="bc722-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="bc722-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="bc722-125">Mapitags.h</span></span>
  
> <span data-ttu-id="bc722-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="bc722-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bc722-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc722-127">See also</span></span>



[<span data-ttu-id="bc722-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="bc722-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="bc722-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="bc722-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="bc722-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="bc722-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="bc722-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="bc722-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

