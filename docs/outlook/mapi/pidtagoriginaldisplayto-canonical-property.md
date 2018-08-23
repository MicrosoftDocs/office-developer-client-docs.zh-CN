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
ms.openlocfilehash: 5adeec9a8f7092a2a32008a189918892ca50a952
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589194"
---
# <a name="pidtagoriginaldisplayto-canonical-property"></a><span data-ttu-id="54c18-103">PidTagOriginalDisplayTo 规范属性</span><span class="sxs-lookup"><span data-stu-id="54c18-103">PidTagOriginalDisplayTo Canonical Property</span></span>

  
  
<span data-ttu-id="54c18-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="54c18-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="54c18-105">包含主 （收件人） 的原始邮件收件人的显示名称。</span><span class="sxs-lookup"><span data-stu-id="54c18-105">Contains the display names of the primary (To) recipients of the original message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="54c18-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="54c18-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="54c18-107">PR_ORIGINAL_DISPLAY_TO，PR_ORIGINAL_DISPLAY_TO_A，PR_ORIGINAL_DISPLAY_TO_W</span><span class="sxs-lookup"><span data-stu-id="54c18-107">PR_ORIGINAL_DISPLAY_TO, PR_ORIGINAL_DISPLAY_TO_A, PR_ORIGINAL_DISPLAY_TO_W</span></span>  <br/> |
|<span data-ttu-id="54c18-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="54c18-108">Identifier:</span></span>  <br/> |<span data-ttu-id="54c18-109">0x0074</span><span class="sxs-lookup"><span data-stu-id="54c18-109">0x0074</span></span>  <br/> |
|<span data-ttu-id="54c18-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="54c18-110">Data type:</span></span>  <br/> |<span data-ttu-id="54c18-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="54c18-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="54c18-112">区域：</span><span class="sxs-lookup"><span data-stu-id="54c18-112">Area:</span></span>  <br/> |<span data-ttu-id="54c18-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="54c18-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="54c18-114">注解</span><span class="sxs-lookup"><span data-stu-id="54c18-114">Remarks</span></span>

<span data-ttu-id="54c18-115">这些属性包含由分号分隔的 ASCII 列表。</span><span class="sxs-lookup"><span data-stu-id="54c18-115">These properties contain an ASCII list separated by semicolons.</span></span> <span data-ttu-id="54c18-116">它提供的 MAPI，并直接从**仅包含显示名称**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) 时传递复制或生成原件报表或读取或 nonread 的报表。</span><span class="sxs-lookup"><span data-stu-id="54c18-116">It is furnished by MAPI and is copied directly from **PR_DISPLAY_TO** ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) when a delivery or nondelivery report or a read or nonread report is generated.</span></span> <span data-ttu-id="54c18-117">此属性可能会出现在由其邮件类别定义其他消息。</span><span class="sxs-lookup"><span data-stu-id="54c18-117">This property may be present on other messages as defined by their message classes.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="54c18-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="54c18-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="54c18-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="54c18-119">Protocol specifications</span></span>

<span data-ttu-id="54c18-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="54c18-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="54c18-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="54c18-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="54c18-122">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="54c18-122">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="54c18-123">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="54c18-123">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="54c18-124">头文件</span><span class="sxs-lookup"><span data-stu-id="54c18-124">Header files</span></span>

<span data-ttu-id="54c18-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="54c18-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="54c18-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="54c18-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="54c18-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="54c18-127">Mapitags.h</span></span>
  
> <span data-ttu-id="54c18-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="54c18-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="54c18-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54c18-129">See also</span></span>



[<span data-ttu-id="54c18-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="54c18-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="54c18-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="54c18-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="54c18-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="54c18-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="54c18-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="54c18-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

