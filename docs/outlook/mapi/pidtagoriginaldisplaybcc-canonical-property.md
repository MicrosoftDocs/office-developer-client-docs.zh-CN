---
title: PidTagOriginalDisplayBcc 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalDisplayBcc
api_type:
- COM
ms.assetid: 7bf66f0c-3095-4b4a-a32e-db278e1adc5a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3fbd7205901616695bcdcd012601afd252ac05f3
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396712"
---
# <a name="pidtagoriginaldisplaybcc-canonical-property"></a><span data-ttu-id="4c230-103">PidTagOriginalDisplayBcc 规范属性</span><span class="sxs-lookup"><span data-stu-id="4c230-103">PidTagOriginalDisplayBcc Canonical Property</span></span>

  
  
<span data-ttu-id="4c230-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4c230-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4c230-105">包含原始邮件的任何密件抄送 (BCC) 收件人的显示名称。</span><span class="sxs-lookup"><span data-stu-id="4c230-105">Contains the display names of any blind carbon copy (BCC) recipients of the original message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4c230-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4c230-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4c230-107">PR_ORIGINAL_DISPLAY_BCC，PR_ORIGINAL_DISPLAY_BCC_A，PR_ORIGINAL_DISPLAY_BCC_W</span><span class="sxs-lookup"><span data-stu-id="4c230-107">PR_ORIGINAL_DISPLAY_BCC, PR_ORIGINAL_DISPLAY_BCC_A, PR_ORIGINAL_DISPLAY_BCC_W</span></span>  <br/> |
|<span data-ttu-id="4c230-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="4c230-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4c230-109">0x0072</span><span class="sxs-lookup"><span data-stu-id="4c230-109">0x0072</span></span>  <br/> |
|<span data-ttu-id="4c230-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4c230-110">Data type:</span></span>  <br/> |<span data-ttu-id="4c230-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="4c230-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="4c230-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4c230-112">Area:</span></span>  <br/> |<span data-ttu-id="4c230-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="4c230-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4c230-114">说明</span><span class="sxs-lookup"><span data-stu-id="4c230-114">Remarks</span></span>

<span data-ttu-id="4c230-115">这些属性包含由分号分隔的列表。</span><span class="sxs-lookup"><span data-stu-id="4c230-115">These properties contain a list separated by semicolons.</span></span> <span data-ttu-id="4c230-116">他们提供的 MAPI，并生成传递或原件报表或读取或 nonread 的报表时直接从**PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) 复制。</span><span class="sxs-lookup"><span data-stu-id="4c230-116">They is furnished by MAPI and are copied directly from **PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) when a delivery or nondelivery report or a read or nonread report is generated.</span></span> <span data-ttu-id="4c230-117">这些属性可能会出现在由其邮件类别定义其他消息。</span><span class="sxs-lookup"><span data-stu-id="4c230-117">These properties may be present on other messages as defined by their message classes.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="4c230-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="4c230-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4c230-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="4c230-119">Protocol specifications</span></span>

<span data-ttu-id="4c230-120">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4c230-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4c230-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="4c230-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4c230-122">[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4c230-122">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4c230-123">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="4c230-123">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4c230-124">头文件</span><span class="sxs-lookup"><span data-stu-id="4c230-124">Header files</span></span>

<span data-ttu-id="4c230-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4c230-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="4c230-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4c230-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="4c230-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="4c230-127">Mapitags.h</span></span>
  
> <span data-ttu-id="4c230-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4c230-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4c230-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c230-129">See also</span></span>



[<span data-ttu-id="4c230-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4c230-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4c230-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4c230-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4c230-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4c230-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4c230-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4c230-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

