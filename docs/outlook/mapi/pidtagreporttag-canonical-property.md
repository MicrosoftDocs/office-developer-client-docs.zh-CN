---
title: PidTagReportTag 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReportTag
api_type:
- COM
ms.assetid: 581bf372-8705-4617-aaa4-a1d761eb9b58
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: c832842568ea3d64d50b56d226b66d551402ba6e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778221"
---
# <a name="pidtagreporttag-canonical-property"></a><span data-ttu-id="e0e47-103">PidTagReportTag 规范属性</span><span class="sxs-lookup"><span data-stu-id="e0e47-103">PidTagReportTag Canonical Property</span></span>

  
  
<span data-ttu-id="e0e47-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e0e47-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e0e47-105">包含在邮件系统应将复制到生成的邮件的所有报告的二进制标记值。</span><span class="sxs-lookup"><span data-stu-id="e0e47-105">Contains a binary tag value that the messaging system should copy to any report generated for the message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e0e47-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="e0e47-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e0e47-107">PR_REPORT_TAG</span><span class="sxs-lookup"><span data-stu-id="e0e47-107">PR_REPORT_TAG</span></span>  <br/> |
|<span data-ttu-id="e0e47-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="e0e47-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e0e47-109">0x0031</span><span class="sxs-lookup"><span data-stu-id="e0e47-109">0x0031</span></span>  <br/> |
|<span data-ttu-id="e0e47-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e0e47-110">Data type:</span></span>  <br/> |<span data-ttu-id="e0e47-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="e0e47-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="e0e47-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e0e47-112">Area:</span></span>  <br/> |<span data-ttu-id="e0e47-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="e0e47-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e0e47-114">备注</span><span class="sxs-lookup"><span data-stu-id="e0e47-114">Remarks</span></span>

<span data-ttu-id="e0e47-115">此属性，如**PR_SUBJECT_IPM** ([PidTagSubjectMessageId](pidtagsubjectmessageid-canonical-property.md)) 属性，用于将报告与原始邮件相关联。</span><span class="sxs-lookup"><span data-stu-id="e0e47-115">This property, like the **PR_SUBJECT_IPM** ([PidTagSubjectMessageId](pidtagsubjectmessageid-canonical-property.md)) property, is used to correlate a report with the original message.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="e0e47-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="e0e47-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e0e47-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="e0e47-117">Protocol specifications</span></span>

<span data-ttu-id="e0e47-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e0e47-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e0e47-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="e0e47-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e0e47-120">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e0e47-120">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e0e47-121">指定的属性和电子邮件中允许的操作。</span><span class="sxs-lookup"><span data-stu-id="e0e47-121">Specifies the properties and operations that are permissible on email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e0e47-122">头文件</span><span class="sxs-lookup"><span data-stu-id="e0e47-122">Header files</span></span>

<span data-ttu-id="e0e47-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e0e47-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="e0e47-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e0e47-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="e0e47-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e0e47-125">Mapitags.h</span></span>
  
> <span data-ttu-id="e0e47-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e0e47-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e0e47-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0e47-127">See also</span></span>



[<span data-ttu-id="e0e47-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e0e47-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e0e47-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e0e47-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e0e47-130">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e0e47-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e0e47-131">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e0e47-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

