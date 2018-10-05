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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387599"
---
# <a name="pidtagreporttime-canonical-property"></a><span data-ttu-id="1d0d7-103">PidTagReportTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="1d0d7-103">PidTagReportTime Canonical Property</span></span>

  
  
<span data-ttu-id="1d0d7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1d0d7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1d0d7-105">包含的日期和时间在邮件系统时生成报表。</span><span class="sxs-lookup"><span data-stu-id="1d0d7-105">Contains the date and time when the messaging system generated a report.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1d0d7-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1d0d7-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1d0d7-107">PR_REPORT_TIME</span><span class="sxs-lookup"><span data-stu-id="1d0d7-107">PR_REPORT_TIME</span></span>  <br/> |
|<span data-ttu-id="1d0d7-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="1d0d7-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1d0d7-109">0x0032</span><span class="sxs-lookup"><span data-stu-id="1d0d7-109">0x0032</span></span>  <br/> |
|<span data-ttu-id="1d0d7-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1d0d7-110">Data type:</span></span>  <br/> |<span data-ttu-id="1d0d7-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="1d0d7-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="1d0d7-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1d0d7-112">Area:</span></span>  <br/> |<span data-ttu-id="1d0d7-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="1d0d7-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1d0d7-114">说明</span><span class="sxs-lookup"><span data-stu-id="1d0d7-114">Remarks</span></span>

<span data-ttu-id="1d0d7-115">此属性表示上送达和原件报告的每个收件人属性和读取和 nonread 报表上的每封邮件属性。</span><span class="sxs-lookup"><span data-stu-id="1d0d7-115">This property represents a per-recipient property on delivery and nondelivery reports and a per-message property on read and nonread reports.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="1d0d7-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="1d0d7-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1d0d7-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="1d0d7-117">Protocol specifications</span></span>

<span data-ttu-id="1d0d7-118">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1d0d7-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1d0d7-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="1d0d7-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1d0d7-120">[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1d0d7-120">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1d0d7-121">指定的属性和电子邮件中允许的操作。</span><span class="sxs-lookup"><span data-stu-id="1d0d7-121">Specifies the properties and operations that are permissible on email messages.</span></span>
    
<span data-ttu-id="1d0d7-122">[[MS OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1d0d7-122">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1d0d7-123">允许处理的允许/阻止列表，并确定的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="1d0d7-123">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1d0d7-124">头文件</span><span class="sxs-lookup"><span data-stu-id="1d0d7-124">Header files</span></span>

<span data-ttu-id="1d0d7-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1d0d7-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="1d0d7-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1d0d7-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="1d0d7-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="1d0d7-127">Mapitags.h</span></span>
  
> <span data-ttu-id="1d0d7-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1d0d7-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1d0d7-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d0d7-129">See also</span></span>



[<span data-ttu-id="1d0d7-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1d0d7-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1d0d7-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1d0d7-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1d0d7-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1d0d7-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1d0d7-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1d0d7-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

