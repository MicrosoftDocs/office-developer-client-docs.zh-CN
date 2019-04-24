---
title: PidTagOriginallyIntendedRecipEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginallyIntendedRecipEntryId
api_type:
- COM
ms.assetid: fc288a7a-1927-484e-b860-9cc118672ed2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cf9a070e8f892cb7bd4668b3f92397070e5b2284
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342523"
---
# <a name="pidtagoriginallyintendedrecipentryid-canonical-property"></a><span data-ttu-id="d18ac-103">PidTagOriginallyIntendedRecipEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="d18ac-103">PidTagOriginallyIntendedRecipEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="d18ac-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d18ac-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d18ac-105">包含自动转发邮件最初预期收件人的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="d18ac-105">Contains the entry identifier of the originally intended recipient of an auto-forwarded message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d18ac-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d18ac-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d18ac-107">PR_ORIGINALLY_INTENDED_RECIP_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="d18ac-107">PR_ORIGINALLY_INTENDED_RECIP_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="d18ac-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d18ac-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d18ac-109">0x1012</span><span class="sxs-lookup"><span data-stu-id="d18ac-109">0x1012</span></span>  <br/> |
|<span data-ttu-id="d18ac-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d18ac-110">Data type:</span></span>  <br/> |<span data-ttu-id="d18ac-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="d18ac-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="d18ac-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d18ac-112">Area:</span></span>  <br/> |<span data-ttu-id="d18ac-113">服务器</span><span class="sxs-lookup"><span data-stu-id="d18ac-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d18ac-114">注解</span><span class="sxs-lookup"><span data-stu-id="d18ac-114">Remarks</span></span>

<span data-ttu-id="d18ac-115">此属性是最初预期的邮件收件人的地址属性之一。</span><span class="sxs-lookup"><span data-stu-id="d18ac-115">This property is one of the address properties for the originally intended message recipient.</span></span> <span data-ttu-id="d18ac-116">必须由已转发邮件的自动代理进行设置。</span><span class="sxs-lookup"><span data-stu-id="d18ac-116">It must be set by the automatic agent that has forwarded the message.</span></span>
  
<span data-ttu-id="d18ac-117">此属性对应于每个收件人的400个报告属性。</span><span class="sxs-lookup"><span data-stu-id="d18ac-117">This property corresponds to the X.400 report per-recipient attribute.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d18ac-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="d18ac-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="d18ac-119">头文件</span><span class="sxs-lookup"><span data-stu-id="d18ac-119">Header files</span></span>

<span data-ttu-id="d18ac-120">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="d18ac-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="d18ac-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d18ac-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="d18ac-122">Mapitags</span><span class="sxs-lookup"><span data-stu-id="d18ac-122">Mapitags.h</span></span>
  
> <span data-ttu-id="d18ac-123">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d18ac-123">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d18ac-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d18ac-124">See also</span></span>



[<span data-ttu-id="d18ac-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d18ac-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d18ac-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d18ac-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d18ac-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d18ac-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d18ac-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d18ac-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

