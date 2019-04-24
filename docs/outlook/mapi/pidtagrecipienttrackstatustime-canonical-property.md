---
title: PidTagRecipientTrackStatusTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientTrackStatusTime
api_type:
- COM
ms.assetid: f14dfe47-a9f8-4475-bb26-7da3411d8c6f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2dec706252eb6aa1b28f68f6f46473df04f3fbe7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355634"
---
# <a name="pidtagrecipienttrackstatustime-canonical-property"></a><span data-ttu-id="db26d-103">PidTagRecipientTrackStatusTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="db26d-103">PidTagRecipientTrackStatusTime Canonical Property</span></span>

  
  
<span data-ttu-id="db26d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="db26d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="db26d-105">包含与会者响应的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="db26d-105">Contains the date and time when the attendee responded.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="db26d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="db26d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="db26d-107">PR_RECIPIENT_TRACKSTATUS_TIME</span><span class="sxs-lookup"><span data-stu-id="db26d-107">PR_RECIPIENT_TRACKSTATUS_TIME</span></span>  <br/> |
|<span data-ttu-id="db26d-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="db26d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="db26d-109">0x5FFB</span><span class="sxs-lookup"><span data-stu-id="db26d-109">0x5FFB</span></span>  <br/> |
|<span data-ttu-id="db26d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="db26d-110">Data type:</span></span>  <br/> |<span data-ttu-id="db26d-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="db26d-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="db26d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="db26d-112">Area:</span></span>  <br/> |<span data-ttu-id="db26d-113">传输收件人</span><span class="sxs-lookup"><span data-stu-id="db26d-113">Transport recipient</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="db26d-114">注解</span><span class="sxs-lookup"><span data-stu-id="db26d-114">Remarks</span></span>

<span data-ttu-id="db26d-115">必须以协调通用时间 (UTC) 指定该值。</span><span class="sxs-lookup"><span data-stu-id="db26d-115">The value must be specified in Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="db26d-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="db26d-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="db26d-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="db26d-117">Protocol specifications</span></span>

<span data-ttu-id="db26d-118">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="db26d-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="db26d-119">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="db26d-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="db26d-120">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="db26d-120">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="db26d-121">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="db26d-121">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="db26d-122">头文件</span><span class="sxs-lookup"><span data-stu-id="db26d-122">Header files</span></span>

<span data-ttu-id="db26d-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="db26d-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="db26d-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="db26d-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="db26d-125">Mapitags</span><span class="sxs-lookup"><span data-stu-id="db26d-125">Mapitags.h</span></span>
  
> <span data-ttu-id="db26d-126">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="db26d-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="db26d-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db26d-127">See also</span></span>



[<span data-ttu-id="db26d-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="db26d-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="db26d-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="db26d-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="db26d-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="db26d-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="db26d-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="db26d-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

