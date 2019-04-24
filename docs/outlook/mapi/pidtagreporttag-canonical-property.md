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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 870fbf2228206253261124907d6bd420f95fb7c1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331428"
---
# <a name="pidtagreporttag-canonical-property"></a><span data-ttu-id="6c045-103">PidTagReportTag 规范属性</span><span class="sxs-lookup"><span data-stu-id="6c045-103">PidTagReportTag Canonical Property</span></span>

  
  
<span data-ttu-id="6c045-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6c045-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6c045-105">包含一个二进制标记值, 邮件系统应将此值复制到为该邮件生成的任何报告。</span><span class="sxs-lookup"><span data-stu-id="6c045-105">Contains a binary tag value that the messaging system should copy to any report generated for the message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6c045-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6c045-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6c045-107">PR_REPORT_TAG</span><span class="sxs-lookup"><span data-stu-id="6c045-107">PR_REPORT_TAG</span></span>  <br/> |
|<span data-ttu-id="6c045-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="6c045-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6c045-109">0x0031</span><span class="sxs-lookup"><span data-stu-id="6c045-109">0x0031</span></span>  <br/> |
|<span data-ttu-id="6c045-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6c045-110">Data type:</span></span>  <br/> |<span data-ttu-id="6c045-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="6c045-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="6c045-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6c045-112">Area:</span></span>  <br/> |<span data-ttu-id="6c045-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="6c045-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6c045-114">注解</span><span class="sxs-lookup"><span data-stu-id="6c045-114">Remarks</span></span>

<span data-ttu-id="6c045-115">此属性 (如**PR_SUBJECT_IPM** ([PidTagSubjectMessageId](pidtagsubjectmessageid-canonical-property.md)) 属性) 用于将报告与原始邮件关联。</span><span class="sxs-lookup"><span data-stu-id="6c045-115">This property, like the **PR_SUBJECT_IPM** ([PidTagSubjectMessageId](pidtagsubjectmessageid-canonical-property.md)) property, is used to correlate a report with the original message.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="6c045-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="6c045-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6c045-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="6c045-117">Protocol specifications</span></span>

<span data-ttu-id="6c045-118">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6c045-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6c045-119">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="6c045-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6c045-120">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6c045-120">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6c045-121">指定在电子邮件中允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="6c045-121">Specifies the properties and operations that are permissible on email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6c045-122">头文件</span><span class="sxs-lookup"><span data-stu-id="6c045-122">Header files</span></span>

<span data-ttu-id="6c045-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="6c045-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="6c045-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6c045-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="6c045-125">Mapitags</span><span class="sxs-lookup"><span data-stu-id="6c045-125">Mapitags.h</span></span>
  
> <span data-ttu-id="6c045-126">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6c045-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6c045-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c045-127">See also</span></span>



[<span data-ttu-id="6c045-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6c045-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6c045-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6c045-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6c045-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6c045-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6c045-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6c045-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

