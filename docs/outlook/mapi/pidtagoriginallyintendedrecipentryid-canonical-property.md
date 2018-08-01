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
ms.openlocfilehash: 4745318d5666cc3c138f424c94bc2c5e430a61d0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777935"
---
# <a name="pidtagoriginallyintendedrecipentryid-canonical-property"></a><span data-ttu-id="e888e-103">PidTagOriginallyIntendedRecipEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="e888e-103">PidTagOriginallyIntendedRecipEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="e888e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e888e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e888e-105">包含自动转发邮件的最初预期接收人的项标识符。</span><span class="sxs-lookup"><span data-stu-id="e888e-105">Contains the entry identifier of the originally intended recipient of an auto-forwarded message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e888e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e888e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e888e-107">PR_ORIGINALLY_INTENDED_RECIP_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="e888e-107">PR_ORIGINALLY_INTENDED_RECIP_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="e888e-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="e888e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e888e-109">0x1012</span><span class="sxs-lookup"><span data-stu-id="e888e-109">0x1012</span></span>  <br/> |
|<span data-ttu-id="e888e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e888e-110">Data type:</span></span>  <br/> |<span data-ttu-id="e888e-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="e888e-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="e888e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e888e-112">Area:</span></span>  <br/> |<span data-ttu-id="e888e-113">Server</span><span class="sxs-lookup"><span data-stu-id="e888e-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e888e-114">说明</span><span class="sxs-lookup"><span data-stu-id="e888e-114">Remarks</span></span>

<span data-ttu-id="e888e-115">此属性是在最初预期的邮件收件人的地址属性之一。</span><span class="sxs-lookup"><span data-stu-id="e888e-115">This property is one of the address properties for the originally intended message recipient.</span></span> <span data-ttu-id="e888e-116">它必须已转发邮件的自动代理设置。</span><span class="sxs-lookup"><span data-stu-id="e888e-116">It must be set by the automatic agent that has forwarded the message.</span></span>
  
<span data-ttu-id="e888e-117">此属性对应于 X.400 报告每个收件人属性。</span><span class="sxs-lookup"><span data-stu-id="e888e-117">This property corresponds to the X.400 report per-recipient attribute.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e888e-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="e888e-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="e888e-119">头文件</span><span class="sxs-lookup"><span data-stu-id="e888e-119">Header files</span></span>

<span data-ttu-id="e888e-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e888e-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="e888e-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e888e-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="e888e-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e888e-122">Mapitags.h</span></span>
  
> <span data-ttu-id="e888e-123">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e888e-123">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e888e-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e888e-124">See also</span></span>



[<span data-ttu-id="e888e-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e888e-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e888e-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e888e-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e888e-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e888e-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e888e-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e888e-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

