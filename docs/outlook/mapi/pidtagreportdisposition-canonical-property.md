---
title: PidTagReportDisposition 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: 56b9e7bd-eece-4264-8ee5-a1bcbec4f35c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dae31959cddad7ad61ea32f2372ea34bdbff658e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346352"
---
# <a name="pidtagreportdisposition-canonical-property"></a><span data-ttu-id="65086-103">PidTagReportDisposition 规范属性</span><span class="sxs-lookup"><span data-stu-id="65086-103">PidTagReportDisposition Canonical Property</span></span>

  
  
<span data-ttu-id="65086-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="65086-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="65086-105">指示请求回执的邮件的回执状态。</span><span class="sxs-lookup"><span data-stu-id="65086-105">Indicates the receipt status for messages that request receipts.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="65086-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="65086-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="65086-107">PR_REPORT_DISPOSITION、PR_REPORT_DISPOSITION_A、PR_REPORT_DISPOSITION_W</span><span class="sxs-lookup"><span data-stu-id="65086-107">PR_REPORT_DISPOSITION, PR_REPORT_DISPOSITION_A, PR_REPORT_DISPOSITION_W</span></span>  <br/> |
|<span data-ttu-id="65086-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="65086-108">Identifier:</span></span>  <br/> |<span data-ttu-id="65086-109">0x0080</span><span class="sxs-lookup"><span data-stu-id="65086-109">0x0080</span></span>  <br/> |
|<span data-ttu-id="65086-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="65086-110">Data type:</span></span>  <br/> |<span data-ttu-id="65086-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="65086-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="65086-112">区域：</span><span class="sxs-lookup"><span data-stu-id="65086-112">Area:</span></span>  <br/> |<span data-ttu-id="65086-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="65086-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="65086-114">注解</span><span class="sxs-lookup"><span data-stu-id="65086-114">Remarks</span></span>

<span data-ttu-id="65086-115">下面是有效值：</span><span class="sxs-lookup"><span data-stu-id="65086-115">The following are valid values:</span></span>
  
- <span data-ttu-id="65086-116">已</span><span class="sxs-lookup"><span data-stu-id="65086-116">"deleted"</span></span>
    
- <span data-ttu-id="65086-117">处理</span><span class="sxs-lookup"><span data-stu-id="65086-117">"processed"</span></span>
    
- <span data-ttu-id="65086-118">分派</span><span class="sxs-lookup"><span data-stu-id="65086-118">"dispatched"</span></span>
    
- <span data-ttu-id="65086-119">否决</span><span class="sxs-lookup"><span data-stu-id="65086-119">"denied"</span></span>
    
- <span data-ttu-id="65086-120">"failed"</span><span class="sxs-lookup"><span data-stu-id="65086-120">"failed"</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="65086-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="65086-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="65086-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="65086-122">Protocol specifications</span></span>

<span data-ttu-id="65086-123">[[毫秒-OXPROPS]]</span><span class="sxs-lookup"><span data-stu-id="65086-123">[[MS-OXPROPS]]</span></span> 
  
> <span data-ttu-id="65086-124">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="65086-124">Provides references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="65086-125">头文件</span><span class="sxs-lookup"><span data-stu-id="65086-125">Header files</span></span>

<span data-ttu-id="65086-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="65086-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="65086-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="65086-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="65086-128">Mapitags</span><span class="sxs-lookup"><span data-stu-id="65086-128">Mapitags.h</span></span>
  
> <span data-ttu-id="65086-129">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="65086-129">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="65086-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65086-130">See also</span></span>



[<span data-ttu-id="65086-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="65086-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="65086-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="65086-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="65086-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="65086-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="65086-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="65086-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

