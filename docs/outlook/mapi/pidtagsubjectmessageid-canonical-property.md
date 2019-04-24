---
title: PidTagSubjectMessageId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSubjectMessageId
api_type:
- COM
ms.assetid: d4b1a087-0986-467a-aaa9-fc643f7c56fc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7bd5a030d11577c2afabb8a2253cf4f6129814cc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339233"
---
# <a name="pidtagsubjectmessageid-canonical-property"></a><span data-ttu-id="1d477-103">PidTagSubjectMessageId 规范属性</span><span class="sxs-lookup"><span data-stu-id="1d477-103">PidTagSubjectMessageId Canonical Property</span></span>

  
  
<span data-ttu-id="1d477-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1d477-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1d477-105">包含从要为其生成报告的邮件中复制的二进制值。</span><span class="sxs-lookup"><span data-stu-id="1d477-105">Contains a binary value that is copied from the message for which a report is being generated.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1d477-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1d477-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1d477-107">PR_SUBJECT_IPM</span><span class="sxs-lookup"><span data-stu-id="1d477-107">PR_SUBJECT_IPM</span></span>  <br/> |
|<span data-ttu-id="1d477-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="1d477-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1d477-109">0x0038</span><span class="sxs-lookup"><span data-stu-id="1d477-109">0x0038</span></span>  <br/> |
|<span data-ttu-id="1d477-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1d477-110">Data type:</span></span>  <br/> |<span data-ttu-id="1d477-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="1d477-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="1d477-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1d477-112">Area:</span></span>  <br/> |<span data-ttu-id="1d477-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="1d477-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1d477-114">注解</span><span class="sxs-lookup"><span data-stu-id="1d477-114">Remarks</span></span>

<span data-ttu-id="1d477-115">此属性 (如**PR_REPORT_TAG** ([PidTagReportTag](pidtagreporttag-canonical-property.md)) 属性) 可用于将报告与原始邮件关联。</span><span class="sxs-lookup"><span data-stu-id="1d477-115">This property, like the **PR_REPORT_TAG** ([PidTagReportTag](pidtagreporttag-canonical-property.md)) property, can be used to correlate a report with the original message.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="1d477-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="1d477-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="1d477-117">头文件</span><span class="sxs-lookup"><span data-stu-id="1d477-117">Header files</span></span>

<span data-ttu-id="1d477-118">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="1d477-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="1d477-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1d477-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="1d477-120">Mapitags</span><span class="sxs-lookup"><span data-stu-id="1d477-120">Mapitags.h</span></span>
  
> <span data-ttu-id="1d477-121">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1d477-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1d477-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d477-122">See also</span></span>



[<span data-ttu-id="1d477-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1d477-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1d477-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1d477-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1d477-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1d477-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1d477-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1d477-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

