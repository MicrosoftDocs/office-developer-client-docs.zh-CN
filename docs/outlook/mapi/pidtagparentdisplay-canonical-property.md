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
ms.openlocfilehash: 910a62a660ea17992aa391d7453919d9fbb53c86
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580430"
---
# <a name="pidtagparentdisplay-canonical-property"></a><span data-ttu-id="2002f-103">PidTagParentDisplay 规范属性</span><span class="sxs-lookup"><span data-stu-id="2002f-103">PidTagParentDisplay Canonical Property</span></span>

  
  
<span data-ttu-id="2002f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2002f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2002f-105">包含一条消息，在其中搜索过程中发现的文件夹的显示名称。</span><span class="sxs-lookup"><span data-stu-id="2002f-105">Contains the display name of the folder where a message was found during a search.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2002f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2002f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2002f-107">PR_PARENT_DISPLAY，PR_PARENT_DISPLAY_A，PR_PARENT_DISPLAY_W</span><span class="sxs-lookup"><span data-stu-id="2002f-107">PR_PARENT_DISPLAY, PR_PARENT_DISPLAY_A, PR_PARENT_DISPLAY_W</span></span>  <br/> |
|<span data-ttu-id="2002f-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="2002f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2002f-109">0x0E05</span><span class="sxs-lookup"><span data-stu-id="2002f-109">0x0E05</span></span>  <br/> |
|<span data-ttu-id="2002f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2002f-110">Data type:</span></span>  <br/> |<span data-ttu-id="2002f-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="2002f-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="2002f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2002f-112">Area:</span></span>  <br/> |<span data-ttu-id="2002f-113">MAPI 非可传送</span><span class="sxs-lookup"><span data-stu-id="2002f-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2002f-114">注解</span><span class="sxs-lookup"><span data-stu-id="2002f-114">Remarks</span></span>

<span data-ttu-id="2002f-115">对任何对象，这些属性不是。</span><span class="sxs-lookup"><span data-stu-id="2002f-115">These properties is not on any object.</span></span> <span data-ttu-id="2002f-116">它们仅可以显示搜索结果文件夹的内容表中。</span><span class="sxs-lookup"><span data-stu-id="2002f-116">They can only appear in the contents table of a search-results folder.</span></span>
  
<span data-ttu-id="2002f-117">这些属性和**PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md)) 属性不与每个其他相关。</span><span class="sxs-lookup"><span data-stu-id="2002f-117">These properties and **PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md)) properties are not related to each other.</span></span> <span data-ttu-id="2002f-118">他们所属完全不同的上下文。</span><span class="sxs-lookup"><span data-stu-id="2002f-118">They belong to entirely different contexts.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="2002f-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="2002f-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="2002f-120">头文件</span><span class="sxs-lookup"><span data-stu-id="2002f-120">Header files</span></span>

<span data-ttu-id="2002f-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2002f-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="2002f-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2002f-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="2002f-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="2002f-123">Mapitags.h</span></span>
  
> <span data-ttu-id="2002f-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2002f-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2002f-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2002f-125">See also</span></span>



[<span data-ttu-id="2002f-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2002f-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2002f-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2002f-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2002f-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2002f-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2002f-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2002f-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

