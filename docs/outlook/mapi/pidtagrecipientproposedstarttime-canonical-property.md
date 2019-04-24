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
ms.openlocfilehash: 8815728adce809641586c4da5beb4c9fad735507
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283140"
---
# <a name="pidtagrecipientproposedstarttime-canonical-property"></a><span data-ttu-id="845be-103">PidTagRecipientProposedStartTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="845be-103">PidTagRecipientProposedStartTime Canonical Property</span></span>

  
  
<span data-ttu-id="845be-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="845be-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="845be-105">指示会议的建议开始时间。</span><span class="sxs-lookup"><span data-stu-id="845be-105">Indicates a proposed starting time of a meeting.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="845be-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="845be-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="845be-107">PR_RECIPIENT_PROPOSEDSTARTTIME</span><span class="sxs-lookup"><span data-stu-id="845be-107">PR_RECIPIENT_PROPOSEDSTARTTIME</span></span>  <br/> |
|<span data-ttu-id="845be-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="845be-108">Identifier:</span></span>  <br/> |<span data-ttu-id="845be-109">0x5FE3</span><span class="sxs-lookup"><span data-stu-id="845be-109">0x5FE3</span></span>  <br/> |
|<span data-ttu-id="845be-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="845be-110">Data type:</span></span>  <br/> |<span data-ttu-id="845be-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="845be-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="845be-112">区域：</span><span class="sxs-lookup"><span data-stu-id="845be-112">Area:</span></span>  <br/> |<span data-ttu-id="845be-113">传输收件人</span><span class="sxs-lookup"><span data-stu-id="845be-113">Transport recipient</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="845be-114">注解</span><span class="sxs-lookup"><span data-stu-id="845be-114">Remarks</span></span>

<span data-ttu-id="845be-115">当**PR_RECIPIENT_PROPOSED** ([PidTagRecipientProposed](pidtagrecipientproposed-canonical-property.md)) 属性的值设置为 TRUE 时, 此属性的值指示与会者请求的值设置为**dispidApptStartWhole**的值 ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) 属性的单一实例会议对象或异常对象。</span><span class="sxs-lookup"><span data-stu-id="845be-115">When the value of the **PR_RECIPIENT_PROPOSED** ([PidTagRecipientProposed](pidtagrecipientproposed-canonical-property.md)) property is set to TRUE, the value of this property indicates the value requested by the attendee to set as the value of the **dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) property for the single instance meeting object or exception object.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="845be-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="845be-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="845be-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="845be-117">Protocol specifications</span></span>

<span data-ttu-id="845be-118">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="845be-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="845be-119">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="845be-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="845be-120">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="845be-120">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="845be-121">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="845be-121">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="845be-122">头文件</span><span class="sxs-lookup"><span data-stu-id="845be-122">Header files</span></span>

<span data-ttu-id="845be-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="845be-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="845be-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="845be-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="845be-125">Mapitags</span><span class="sxs-lookup"><span data-stu-id="845be-125">Mapitags.h</span></span>
  
> <span data-ttu-id="845be-126">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="845be-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="845be-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="845be-127">See also</span></span>



[<span data-ttu-id="845be-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="845be-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="845be-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="845be-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="845be-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="845be-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="845be-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="845be-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

