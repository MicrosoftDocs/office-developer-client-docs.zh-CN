---
title: PidTagOriginalDisplayTo 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalDisplayTo
api_type:
- COM
ms.assetid: 8c1cf14c-0339-4ced-8f68-4bfaa1e4d3e9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5a2f60051e5cb0717926a5c3e2f878a49919b04c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342699"
---
# <a name="pidtagoriginaldisplayto-canonical-property"></a><span data-ttu-id="7948e-103">PidTagOriginalDisplayTo 规范属性</span><span class="sxs-lookup"><span data-stu-id="7948e-103">PidTagOriginalDisplayTo Canonical Property</span></span>

  
  
<span data-ttu-id="7948e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7948e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7948e-105">包含原始邮件的主 (收件人) 收件人的显示名称。</span><span class="sxs-lookup"><span data-stu-id="7948e-105">Contains the display names of the primary (To) recipients of the original message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7948e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7948e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7948e-107">PR_ORIGINAL_DISPLAY_TO、PR_ORIGINAL_DISPLAY_TO_A、PR_ORIGINAL_DISPLAY_TO_W</span><span class="sxs-lookup"><span data-stu-id="7948e-107">PR_ORIGINAL_DISPLAY_TO, PR_ORIGINAL_DISPLAY_TO_A, PR_ORIGINAL_DISPLAY_TO_W</span></span>  <br/> |
|<span data-ttu-id="7948e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="7948e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="7948e-109">0x0074</span><span class="sxs-lookup"><span data-stu-id="7948e-109">0x0074</span></span>  <br/> |
|<span data-ttu-id="7948e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7948e-110">Data type:</span></span>  <br/> |<span data-ttu-id="7948e-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="7948e-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="7948e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="7948e-112">Area:</span></span>  <br/> |<span data-ttu-id="7948e-113">常规邮件</span><span class="sxs-lookup"><span data-stu-id="7948e-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7948e-114">注解</span><span class="sxs-lookup"><span data-stu-id="7948e-114">Remarks</span></span>

<span data-ttu-id="7948e-115">这些属性包含用分号分隔的 ASCII 列表。</span><span class="sxs-lookup"><span data-stu-id="7948e-115">These properties contain an ASCII list separated by semicolons.</span></span> <span data-ttu-id="7948e-116">它由 MAPI 提供, 并在生成传递或 nondelivery 报告或已读或未读报告时直接从**PR_DISPLAY_TO** ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) 进行复制。</span><span class="sxs-lookup"><span data-stu-id="7948e-116">It is furnished by MAPI and is copied directly from **PR_DISPLAY_TO** ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) when a delivery or nondelivery report or a read or nonread report is generated.</span></span> <span data-ttu-id="7948e-117">此属性可能出现在由其邮件类别定义的其他邮件上。</span><span class="sxs-lookup"><span data-stu-id="7948e-117">This property may be present on other messages as defined by their message classes.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="7948e-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="7948e-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7948e-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="7948e-119">Protocol specifications</span></span>

<span data-ttu-id="7948e-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7948e-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7948e-121">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="7948e-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7948e-122">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7948e-122">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7948e-123">指定在电子邮件对象上允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="7948e-123">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7948e-124">头文件</span><span class="sxs-lookup"><span data-stu-id="7948e-124">Header files</span></span>

<span data-ttu-id="7948e-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="7948e-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="7948e-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7948e-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="7948e-127">Mapitags</span><span class="sxs-lookup"><span data-stu-id="7948e-127">Mapitags.h</span></span>
  
> <span data-ttu-id="7948e-128">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="7948e-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7948e-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7948e-129">See also</span></span>



[<span data-ttu-id="7948e-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7948e-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7948e-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7948e-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7948e-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7948e-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7948e-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7948e-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

