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
# <a name="pidtagrecipientproposed-canonical-property"></a><span data-ttu-id="2719a-103">PidTagRecipientProposed 规范属性</span><span class="sxs-lookup"><span data-stu-id="2719a-103">PidTagRecipientProposed Canonical Property</span></span>

  
  
<span data-ttu-id="2719a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2719a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2719a-105">指示与会者是否已响应。</span><span class="sxs-lookup"><span data-stu-id="2719a-105">Indicates whether a meeting attendee has responded.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2719a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2719a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2719a-107">PR_RECIPIENT_PROPOSED</span><span class="sxs-lookup"><span data-stu-id="2719a-107">PR_RECIPIENT_PROPOSED</span></span>  <br/> |
|<span data-ttu-id="2719a-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="2719a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2719a-109">0x5FE1</span><span class="sxs-lookup"><span data-stu-id="2719a-109">0x5FE1</span></span>  <br/> |
|<span data-ttu-id="2719a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2719a-110">Data type:</span></span>  <br/> |<span data-ttu-id="2719a-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="2719a-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="2719a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2719a-112">Area:</span></span>  <br/> |<span data-ttu-id="2719a-113">传输收件人</span><span class="sxs-lookup"><span data-stu-id="2719a-113">Transport recipient</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2719a-114">备注</span><span class="sxs-lookup"><span data-stu-id="2719a-114">Remarks</span></span>

<span data-ttu-id="2719a-115">此属性的 TRUE 值指示与会者建议了新的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="2719a-115">A value of TRUE for this property indicates that the attendee proposed a new date and/or time.</span></span> <span data-ttu-id="2719a-116">FALSE 值或缺少此属性意味着与会者尚未响应，或者与会者的最新响应不包括新的日期/时间建议。</span><span class="sxs-lookup"><span data-stu-id="2719a-116">A value of FALSE, or the absence of this property, means either that the attendee has not yet responded, or the most recent response from the attendee did not include a new date/ time proposal.</span></span> <span data-ttu-id="2719a-117">对于定期系列中的与会者，此值不能为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="2719a-117">This value must not be TRUE for attendees in a recurring series.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="2719a-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="2719a-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2719a-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="2719a-119">Protocol specifications</span></span>

<span data-ttu-id="2719a-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2719a-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2719a-121">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="2719a-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2719a-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2719a-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2719a-123">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="2719a-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2719a-124">头文件</span><span class="sxs-lookup"><span data-stu-id="2719a-124">Header files</span></span>

<span data-ttu-id="2719a-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2719a-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="2719a-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2719a-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="2719a-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="2719a-127">Mapitags.h</span></span>
  
> <span data-ttu-id="2719a-128">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2719a-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2719a-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2719a-129">See also</span></span>



[<span data-ttu-id="2719a-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2719a-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2719a-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2719a-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2719a-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2719a-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2719a-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2719a-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

