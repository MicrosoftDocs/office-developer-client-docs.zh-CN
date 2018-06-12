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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: ce9fea80a2dfed25002e5500dd4defaf5ff04421
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778030"
---
# <a name="pidtagparentdisplay-canonical-property"></a><span data-ttu-id="52918-103">PidTagParentDisplay 规范属性</span><span class="sxs-lookup"><span data-stu-id="52918-103">PidTagParentDisplay Canonical Property</span></span>

  
  
<span data-ttu-id="52918-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="52918-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="52918-105">包含一条消息，在其中搜索过程中发现的文件夹的显示名称。</span><span class="sxs-lookup"><span data-stu-id="52918-105">Contains the display name of the folder where a message was found during a search.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="52918-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="52918-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="52918-107">PR_PARENT_DISPLAY，PR_PARENT_DISPLAY_A，PR_PARENT_DISPLAY_W</span><span class="sxs-lookup"><span data-stu-id="52918-107">PR_PARENT_DISPLAY, PR_PARENT_DISPLAY_A, PR_PARENT_DISPLAY_W</span></span>  <br/> |
|<span data-ttu-id="52918-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="52918-108">Identifier:</span></span>  <br/> |<span data-ttu-id="52918-109">0x0E05</span><span class="sxs-lookup"><span data-stu-id="52918-109">0x0E05</span></span>  <br/> |
|<span data-ttu-id="52918-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="52918-110">Data type:</span></span>  <br/> |<span data-ttu-id="52918-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="52918-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="52918-112">区域：</span><span class="sxs-lookup"><span data-stu-id="52918-112">Area:</span></span>  <br/> |<span data-ttu-id="52918-113">MAPI 非可传送</span><span class="sxs-lookup"><span data-stu-id="52918-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="52918-114">备注</span><span class="sxs-lookup"><span data-stu-id="52918-114">Remarks</span></span>

<span data-ttu-id="52918-115">对任何对象，这些属性不是。</span><span class="sxs-lookup"><span data-stu-id="52918-115">These properties is not on any object.</span></span> <span data-ttu-id="52918-116">它们仅可以显示搜索结果文件夹的内容表中。</span><span class="sxs-lookup"><span data-stu-id="52918-116">They can only appear in the contents table of a search-results folder.</span></span>
  
<span data-ttu-id="52918-117">这些属性和**PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md)) 属性不与每个其他相关。</span><span class="sxs-lookup"><span data-stu-id="52918-117">These properties and **PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md)) properties are not related to each other.</span></span> <span data-ttu-id="52918-118">他们所属完全不同的上下文。</span><span class="sxs-lookup"><span data-stu-id="52918-118">They belong to entirely different contexts.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="52918-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="52918-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="52918-120">头文件</span><span class="sxs-lookup"><span data-stu-id="52918-120">Header files</span></span>

<span data-ttu-id="52918-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="52918-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="52918-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="52918-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="52918-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="52918-123">Mapitags.h</span></span>
  
> <span data-ttu-id="52918-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="52918-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="52918-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52918-125">See also</span></span>



[<span data-ttu-id="52918-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="52918-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="52918-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="52918-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="52918-128">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="52918-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="52918-129">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="52918-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

