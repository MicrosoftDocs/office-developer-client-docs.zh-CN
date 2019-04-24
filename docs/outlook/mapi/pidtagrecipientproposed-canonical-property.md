---
title: PidTagRecipientProposed 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientProposed
api_type:
- COM
ms.assetid: 8cb0e46c-0937-482f-be78-1f2e5261b210
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1b09d8d7621121b3652ceb9824f6d36b53844206
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283133"
---
# <a name="pidtagrecipientproposed-canonical-property"></a><span data-ttu-id="f846f-103">PidTagRecipientProposed 规范属性</span><span class="sxs-lookup"><span data-stu-id="f846f-103">PidTagRecipientProposed Canonical Property</span></span>

  
  
<span data-ttu-id="f846f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f846f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f846f-105">指示会议与会者是否已响应。</span><span class="sxs-lookup"><span data-stu-id="f846f-105">Indicates whether a meeting attendee has responded.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f846f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f846f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f846f-107">PR_RECIPIENT_PROPOSED</span><span class="sxs-lookup"><span data-stu-id="f846f-107">PR_RECIPIENT_PROPOSED</span></span>  <br/> |
|<span data-ttu-id="f846f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="f846f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f846f-109">0x5FE1</span><span class="sxs-lookup"><span data-stu-id="f846f-109">0x5FE1</span></span>  <br/> |
|<span data-ttu-id="f846f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f846f-110">Data type:</span></span>  <br/> |<span data-ttu-id="f846f-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="f846f-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="f846f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f846f-112">Area:</span></span>  <br/> |<span data-ttu-id="f846f-113">传输收件人</span><span class="sxs-lookup"><span data-stu-id="f846f-113">Transport recipient</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f846f-114">注解</span><span class="sxs-lookup"><span data-stu-id="f846f-114">Remarks</span></span>

<span data-ttu-id="f846f-115">如果此属性的值为 TRUE, 则表示与会者建议了新的日期和/或时间。</span><span class="sxs-lookup"><span data-stu-id="f846f-115">A value of TRUE for this property indicates that the attendee proposed a new date and/or time.</span></span> <span data-ttu-id="f846f-116">如果值为 FALSE 或缺少此属性, 则表示与会者尚未响应, 或者与会者的最近响应不包含新的日期/时间建议。</span><span class="sxs-lookup"><span data-stu-id="f846f-116">A value of FALSE, or the absence of this property, means either that the attendee has not yet responded, or the most recent response from the attendee did not include a new date/ time proposal.</span></span> <span data-ttu-id="f846f-117">对于定期系列中的与会者, 此值不得为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="f846f-117">This value must not be TRUE for attendees in a recurring series.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="f846f-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="f846f-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f846f-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="f846f-119">Protocol specifications</span></span>

<span data-ttu-id="f846f-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f846f-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f846f-121">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="f846f-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="f846f-122">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f846f-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f846f-123">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="f846f-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f846f-124">头文件</span><span class="sxs-lookup"><span data-stu-id="f846f-124">Header files</span></span>

<span data-ttu-id="f846f-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="f846f-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="f846f-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f846f-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="f846f-127">Mapitags</span><span class="sxs-lookup"><span data-stu-id="f846f-127">Mapitags.h</span></span>
  
> <span data-ttu-id="f846f-128">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f846f-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f846f-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f846f-129">See also</span></span>



[<span data-ttu-id="f846f-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f846f-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f846f-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f846f-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f846f-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f846f-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f846f-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f846f-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

