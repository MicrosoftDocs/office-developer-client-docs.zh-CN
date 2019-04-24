---
title: PidTagReportTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReportTime
api_type:
- COM
ms.assetid: b3646505-a9f0-4a72-8277-b238c909f66f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 298c53e537819f800a3acc5cf07c01a7b9f978ec
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330147"
---
# <a name="pidtagreporttime-canonical-property"></a><span data-ttu-id="8dc56-103">PidTagReportTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="8dc56-103">PidTagReportTime Canonical Property</span></span>

  
  
<span data-ttu-id="8dc56-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8dc56-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8dc56-105">包含邮件系统生成报告的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="8dc56-105">Contains the date and time when the messaging system generated a report.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8dc56-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8dc56-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8dc56-107">PR_REPORT_TIME</span><span class="sxs-lookup"><span data-stu-id="8dc56-107">PR_REPORT_TIME</span></span>  <br/> |
|<span data-ttu-id="8dc56-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="8dc56-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8dc56-109">0x0032</span><span class="sxs-lookup"><span data-stu-id="8dc56-109">0x0032</span></span>  <br/> |
|<span data-ttu-id="8dc56-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8dc56-110">Data type:</span></span>  <br/> |<span data-ttu-id="8dc56-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="8dc56-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="8dc56-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8dc56-112">Area:</span></span>  <br/> |<span data-ttu-id="8dc56-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="8dc56-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8dc56-114">注解</span><span class="sxs-lookup"><span data-stu-id="8dc56-114">Remarks</span></span>

<span data-ttu-id="8dc56-115">此属性表示传递和 nondelivery 报告上的每个收件人的属性, 以及 read 和未读报告上的每个邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="8dc56-115">This property represents a per-recipient property on delivery and nondelivery reports and a per-message property on read and nonread reports.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="8dc56-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="8dc56-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="8dc56-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="8dc56-117">Protocol specifications</span></span>

<span data-ttu-id="8dc56-118">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8dc56-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8dc56-119">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="8dc56-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="8dc56-120">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8dc56-120">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8dc56-121">指定在电子邮件中允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="8dc56-121">Specifies the properties and operations that are permissible on email messages.</span></span>
    
<span data-ttu-id="8dc56-122">[[毫秒-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8dc56-122">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8dc56-123">启用对允许/阻止列表的处理以及确定垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="8dc56-123">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="8dc56-124">头文件</span><span class="sxs-lookup"><span data-stu-id="8dc56-124">Header files</span></span>

<span data-ttu-id="8dc56-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="8dc56-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="8dc56-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8dc56-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="8dc56-127">Mapitags</span><span class="sxs-lookup"><span data-stu-id="8dc56-127">Mapitags.h</span></span>
  
> <span data-ttu-id="8dc56-128">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8dc56-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8dc56-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8dc56-129">See also</span></span>



[<span data-ttu-id="8dc56-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8dc56-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8dc56-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8dc56-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8dc56-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8dc56-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8dc56-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8dc56-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

