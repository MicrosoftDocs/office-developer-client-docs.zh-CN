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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 95972d53f20f432bc8007f8bbc6734889773f938
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778220"
---
# <a name="pidtagreporttime-canonical-property"></a><span data-ttu-id="32a77-103">PidTagReportTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="32a77-103">PidTagReportTime Canonical Property</span></span>

  
  
<span data-ttu-id="32a77-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="32a77-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="32a77-105">包含的日期和时间在邮件系统时生成报表。</span><span class="sxs-lookup"><span data-stu-id="32a77-105">Contains the date and time when the messaging system generated a report.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="32a77-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="32a77-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="32a77-107">PR_REPORT_TIME</span><span class="sxs-lookup"><span data-stu-id="32a77-107">PR_REPORT_TIME</span></span>  <br/> |
|<span data-ttu-id="32a77-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="32a77-108">Identifier:</span></span>  <br/> |<span data-ttu-id="32a77-109">0x0032</span><span class="sxs-lookup"><span data-stu-id="32a77-109">0x0032</span></span>  <br/> |
|<span data-ttu-id="32a77-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="32a77-110">Data type:</span></span>  <br/> |<span data-ttu-id="32a77-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="32a77-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="32a77-112">区域：</span><span class="sxs-lookup"><span data-stu-id="32a77-112">Area:</span></span>  <br/> |<span data-ttu-id="32a77-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="32a77-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="32a77-114">备注</span><span class="sxs-lookup"><span data-stu-id="32a77-114">Remarks</span></span>

<span data-ttu-id="32a77-115">此属性表示上送达和原件报告的每个收件人属性和读取和 nonread 报表上的每封邮件属性。</span><span class="sxs-lookup"><span data-stu-id="32a77-115">This property represents a per-recipient property on delivery and nondelivery reports and a per-message property on read and nonread reports.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="32a77-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="32a77-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="32a77-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="32a77-117">Protocol specifications</span></span>

<span data-ttu-id="32a77-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="32a77-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="32a77-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="32a77-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="32a77-120">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="32a77-120">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="32a77-121">指定的属性和电子邮件中允许的操作。</span><span class="sxs-lookup"><span data-stu-id="32a77-121">Specifies the properties and operations that are permissible on email messages.</span></span>
    
<span data-ttu-id="32a77-122">[[MS OXCSPAM]](http://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="32a77-122">[[MS-OXCSPAM]](http://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="32a77-123">允许处理的允许/阻止列表，并确定的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="32a77-123">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="32a77-124">头文件</span><span class="sxs-lookup"><span data-stu-id="32a77-124">Header files</span></span>

<span data-ttu-id="32a77-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="32a77-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="32a77-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="32a77-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="32a77-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="32a77-127">Mapitags.h</span></span>
  
> <span data-ttu-id="32a77-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="32a77-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="32a77-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32a77-129">See also</span></span>



[<span data-ttu-id="32a77-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="32a77-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="32a77-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="32a77-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="32a77-132">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="32a77-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="32a77-133">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="32a77-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

