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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 62d5b04086e45b6b3d2cfa960472010827d60d6b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778213"
---
# <a name="pidtagreportdisposition-canonical-property"></a><span data-ttu-id="282fc-103">PidTagReportDisposition 规范属性</span><span class="sxs-lookup"><span data-stu-id="282fc-103">PidTagReportDisposition Canonical Property</span></span>

  
  
<span data-ttu-id="282fc-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="282fc-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="282fc-105">指示请求收款的消息的回执状态。</span><span class="sxs-lookup"><span data-stu-id="282fc-105">Indicates the receipt status for messages that request receipts.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="282fc-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="282fc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="282fc-107">PR_REPORT_DISPOSITION，PR_REPORT_DISPOSITION_A，PR_REPORT_DISPOSITION_W</span><span class="sxs-lookup"><span data-stu-id="282fc-107">PR_REPORT_DISPOSITION, PR_REPORT_DISPOSITION_A, PR_REPORT_DISPOSITION_W</span></span>  <br/> |
|<span data-ttu-id="282fc-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="282fc-108">Identifier:</span></span>  <br/> |<span data-ttu-id="282fc-109">0x0080</span><span class="sxs-lookup"><span data-stu-id="282fc-109">0x0080</span></span>  <br/> |
|<span data-ttu-id="282fc-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="282fc-110">Data type:</span></span>  <br/> |<span data-ttu-id="282fc-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="282fc-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="282fc-112">区域：</span><span class="sxs-lookup"><span data-stu-id="282fc-112">Area:</span></span>  <br/> |<span data-ttu-id="282fc-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="282fc-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="282fc-114">备注</span><span class="sxs-lookup"><span data-stu-id="282fc-114">Remarks</span></span>

<span data-ttu-id="282fc-115">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="282fc-115">The following are valid values:</span></span>
  
- <span data-ttu-id="282fc-116">"已删除"</span><span class="sxs-lookup"><span data-stu-id="282fc-116">"deleted"</span></span>
    
- <span data-ttu-id="282fc-117">"处理"</span><span class="sxs-lookup"><span data-stu-id="282fc-117">"processed"</span></span>
    
- <span data-ttu-id="282fc-118">"发送"</span><span class="sxs-lookup"><span data-stu-id="282fc-118">"dispatched"</span></span>
    
- <span data-ttu-id="282fc-119">"拒绝"</span><span class="sxs-lookup"><span data-stu-id="282fc-119">"denied"</span></span>
    
- <span data-ttu-id="282fc-120">"failed"</span><span class="sxs-lookup"><span data-stu-id="282fc-120">"failed"</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="282fc-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="282fc-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="282fc-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="282fc-122">Protocol specifications</span></span>

<span data-ttu-id="282fc-123">[[MS-OXPROPS]]</span><span class="sxs-lookup"><span data-stu-id="282fc-123">[[MS-OXPROPS]]</span></span> 
  
> <span data-ttu-id="282fc-124">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="282fc-124">Provides references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="282fc-125">头文件</span><span class="sxs-lookup"><span data-stu-id="282fc-125">Header files</span></span>

<span data-ttu-id="282fc-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="282fc-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="282fc-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="282fc-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="282fc-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="282fc-128">Mapitags.h</span></span>
  
> <span data-ttu-id="282fc-129">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="282fc-129">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="282fc-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="282fc-130">See also</span></span>



[<span data-ttu-id="282fc-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="282fc-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="282fc-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="282fc-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="282fc-133">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="282fc-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="282fc-134">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="282fc-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

