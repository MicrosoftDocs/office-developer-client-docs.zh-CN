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
ms.openlocfilehash: 68bb9a25131a07cf482a39cef70eb08a2b5a1756
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777933"
---
# <a name="pidtagoriginaldisplayto-canonical-property"></a><span data-ttu-id="e27df-103">PidTagOriginalDisplayTo 规范属性</span><span class="sxs-lookup"><span data-stu-id="e27df-103">PidTagOriginalDisplayTo Canonical Property</span></span>

  
  
<span data-ttu-id="e27df-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e27df-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e27df-105">包含主 （收件人） 的原始邮件收件人的显示名称。</span><span class="sxs-lookup"><span data-stu-id="e27df-105">Contains the display names of the primary (To) recipients of the original message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e27df-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e27df-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e27df-107">PR_ORIGINAL_DISPLAY_TO，PR_ORIGINAL_DISPLAY_TO_A，PR_ORIGINAL_DISPLAY_TO_W</span><span class="sxs-lookup"><span data-stu-id="e27df-107">PR_ORIGINAL_DISPLAY_TO, PR_ORIGINAL_DISPLAY_TO_A, PR_ORIGINAL_DISPLAY_TO_W</span></span>  <br/> |
|<span data-ttu-id="e27df-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="e27df-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e27df-109">0x0074</span><span class="sxs-lookup"><span data-stu-id="e27df-109">0x0074</span></span>  <br/> |
|<span data-ttu-id="e27df-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e27df-110">Data type:</span></span>  <br/> |<span data-ttu-id="e27df-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="e27df-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="e27df-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e27df-112">Area:</span></span>  <br/> |<span data-ttu-id="e27df-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="e27df-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e27df-114">说明</span><span class="sxs-lookup"><span data-stu-id="e27df-114">Remarks</span></span>

<span data-ttu-id="e27df-115">这些属性包含由分号分隔的 ASCII 列表。</span><span class="sxs-lookup"><span data-stu-id="e27df-115">These properties contain an ASCII list separated by semicolons.</span></span> <span data-ttu-id="e27df-116">它提供的 MAPI，并直接从**仅包含显示名称**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) 时传递复制或生成原件报表或读取或 nonread 的报表。</span><span class="sxs-lookup"><span data-stu-id="e27df-116">It is furnished by MAPI and is copied directly from **PR_DISPLAY_TO** ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) when a delivery or nondelivery report or a read or nonread report is generated.</span></span> <span data-ttu-id="e27df-117">此属性可能会出现在由其邮件类别定义其他消息。</span><span class="sxs-lookup"><span data-stu-id="e27df-117">This property may be present on other messages as defined by their message classes.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e27df-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="e27df-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e27df-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="e27df-119">Protocol specifications</span></span>

<span data-ttu-id="e27df-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e27df-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e27df-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="e27df-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e27df-122">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e27df-122">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e27df-123">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="e27df-123">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e27df-124">头文件</span><span class="sxs-lookup"><span data-stu-id="e27df-124">Header files</span></span>

<span data-ttu-id="e27df-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e27df-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="e27df-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e27df-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="e27df-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e27df-127">Mapitags.h</span></span>
  
> <span data-ttu-id="e27df-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e27df-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e27df-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e27df-129">See also</span></span>



[<span data-ttu-id="e27df-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e27df-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e27df-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e27df-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e27df-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e27df-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e27df-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e27df-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

