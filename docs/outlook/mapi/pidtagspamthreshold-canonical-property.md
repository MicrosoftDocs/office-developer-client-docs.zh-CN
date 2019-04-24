---
title: PidTagSpamThreshold 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 2b2d6b8e-e3dd-4a9b-8bb5-53add675605d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d43a0229f232f9437d1746799534c0f2d6fba83f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346310"
---
# <a name="pidtagspamthreshold-canonical-property"></a><span data-ttu-id="e9435-103">PidTagSpamThreshold 规范属性</span><span class="sxs-lookup"><span data-stu-id="e9435-103">PidTagSpamThreshold Canonical Property</span></span>

  
  
<span data-ttu-id="e9435-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e9435-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e9435-105">long 值, 用于指示垃圾邮件筛选的级别。</span><span class="sxs-lookup"><span data-stu-id="e9435-105">A long value that indicates the level of spam filtering.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e9435-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e9435-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e9435-107">PR_SPAM_THRESHOLD</span><span class="sxs-lookup"><span data-stu-id="e9435-107">PR_SPAM_THRESHOLD</span></span>  <br/> |
|<span data-ttu-id="e9435-108">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="e9435-108">Long ID (LID):</span></span>  <br/> | <span data-ttu-id="e9435-109">0x041B</span><span class="sxs-lookup"><span data-stu-id="e9435-109">0x041B</span></span>  <br/> |
|<span data-ttu-id="e9435-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e9435-110">Data type:</span></span>  <br/> |<span data-ttu-id="e9435-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="e9435-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="e9435-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e9435-112">Area:</span></span>  <br/> |<span data-ttu-id="e9435-113">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="e9435-113">Spam</span></span>  <br/> |
   
## <a name="values"></a><span data-ttu-id="e9435-114">值</span><span class="sxs-lookup"><span data-stu-id="e9435-114">Values</span></span>

<span data-ttu-id="e9435-115">垃圾邮件筛选的值如下所示:</span><span class="sxs-lookup"><span data-stu-id="e9435-115">The values for spam filtering are as follows:</span></span>
  
|<span data-ttu-id="e9435-116">**垃圾邮件级别**</span><span class="sxs-lookup"><span data-stu-id="e9435-116">**Spam Level**</span></span>|<span data-ttu-id="e9435-117">**值**</span><span class="sxs-lookup"><span data-stu-id="e9435-117">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e9435-118">无</span><span class="sxs-lookup"><span data-stu-id="e9435-118">None</span></span>  <br/> |<span data-ttu-id="e9435-119">0xFFFFFFFF</span><span class="sxs-lookup"><span data-stu-id="e9435-119">0xFFFFFFFF</span></span>  <br/> |
|<span data-ttu-id="e9435-120">低</span><span class="sxs-lookup"><span data-stu-id="e9435-120">Low</span></span>  <br/> |<span data-ttu-id="e9435-121">0x00000006</span><span class="sxs-lookup"><span data-stu-id="e9435-121">0x00000006</span></span>  <br/> |
|<span data-ttu-id="e9435-122">中等</span><span class="sxs-lookup"><span data-stu-id="e9435-122">Medium</span></span>  <br/> |<span data-ttu-id="e9435-123">0x00000005</span><span class="sxs-lookup"><span data-stu-id="e9435-123">0x00000005</span></span>  <br/> |
|<span data-ttu-id="e9435-124">高</span><span class="sxs-lookup"><span data-stu-id="e9435-124">High</span></span>  <br/> |<span data-ttu-id="e9435-125">0x00000003</span><span class="sxs-lookup"><span data-stu-id="e9435-125">0x00000003</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="e9435-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="e9435-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e9435-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="e9435-127">Protocol specifications</span></span>

<span data-ttu-id="e9435-128">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e9435-128">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e9435-129">提供属性集定义和对相关 Microsoft Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="e9435-129">Provides property set definitions and references to related Microsoft Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e9435-130">[[毫秒-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e9435-130">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e9435-131">启用对允许/阻止列表的处理以及确定垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="e9435-131">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e9435-132">头文件</span><span class="sxs-lookup"><span data-stu-id="e9435-132">Header files</span></span>

<span data-ttu-id="e9435-133">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="e9435-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="e9435-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e9435-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="e9435-135">Mapitags</span><span class="sxs-lookup"><span data-stu-id="e9435-135">Mapitags.h</span></span>
  
> <span data-ttu-id="e9435-136">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e9435-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e9435-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9435-137">See also</span></span>



[<span data-ttu-id="e9435-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e9435-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e9435-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e9435-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e9435-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e9435-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e9435-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e9435-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

