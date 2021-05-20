---
title: PidTagParentDisplay 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagParentDisplay
api_type:
- COM
ms.assetid: 6a36f4fb-17c0-4271-87d4-a92895f35f23
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7aef4c1d83672033662502ad0950b7bac9f58c52
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429500"
---
# <a name="pidtagparentdisplay-canonical-property"></a><span data-ttu-id="951e1-103">PidTagParentDisplay 规范属性</span><span class="sxs-lookup"><span data-stu-id="951e1-103">PidTagParentDisplay Canonical Property</span></span>

  
  
<span data-ttu-id="951e1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="951e1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="951e1-105">包含显示名称中发现邮件的文件夹的行数。</span><span class="sxs-lookup"><span data-stu-id="951e1-105">Contains the display name of the folder where a message was found during a search.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="951e1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="951e1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="951e1-107">PR_PARENT_DISPLAY、PR_PARENT_DISPLAY_A、PR_PARENT_DISPLAY_W</span><span class="sxs-lookup"><span data-stu-id="951e1-107">PR_PARENT_DISPLAY, PR_PARENT_DISPLAY_A, PR_PARENT_DISPLAY_W</span></span>  <br/> |
|<span data-ttu-id="951e1-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="951e1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="951e1-109">0x0E05</span><span class="sxs-lookup"><span data-stu-id="951e1-109">0x0E05</span></span>  <br/> |
|<span data-ttu-id="951e1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="951e1-110">Data type:</span></span>  <br/> |<span data-ttu-id="951e1-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="951e1-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="951e1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="951e1-112">Area:</span></span>  <br/> |<span data-ttu-id="951e1-113">MAPI 不可传输</span><span class="sxs-lookup"><span data-stu-id="951e1-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="951e1-114">备注</span><span class="sxs-lookup"><span data-stu-id="951e1-114">Remarks</span></span>

<span data-ttu-id="951e1-115">这些属性不在任何对象上。</span><span class="sxs-lookup"><span data-stu-id="951e1-115">These properties is not on any object.</span></span> <span data-ttu-id="951e1-116">它们只能出现在搜索结果文件夹的内容表中。</span><span class="sxs-lookup"><span data-stu-id="951e1-116">They can only appear in the contents table of a search-results folder.</span></span>
  
<span data-ttu-id="951e1-117">这些属性和 **PR_PARENT_ENTRYID (** [PidTagParentEntryId](pidtagparententryid-canonical-property.md)) 属性之间不相关。</span><span class="sxs-lookup"><span data-stu-id="951e1-117">These properties and **PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md)) properties are not related to each other.</span></span> <span data-ttu-id="951e1-118">它们属于完全不同的上下文。</span><span class="sxs-lookup"><span data-stu-id="951e1-118">They belong to entirely different contexts.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="951e1-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="951e1-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="951e1-120">头文件</span><span class="sxs-lookup"><span data-stu-id="951e1-120">Header files</span></span>

<span data-ttu-id="951e1-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="951e1-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="951e1-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="951e1-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="951e1-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="951e1-123">Mapitags.h</span></span>
  
> <span data-ttu-id="951e1-124">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="951e1-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="951e1-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="951e1-125">See also</span></span>



[<span data-ttu-id="951e1-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="951e1-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="951e1-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="951e1-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="951e1-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="951e1-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="951e1-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="951e1-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

