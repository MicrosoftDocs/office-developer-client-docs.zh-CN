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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331512"
---
# <a name="pidtagparentdisplay-canonical-property"></a><span data-ttu-id="bf50d-103">PidTagParentDisplay 规范属性</span><span class="sxs-lookup"><span data-stu-id="bf50d-103">PidTagParentDisplay Canonical Property</span></span>

  
  
<span data-ttu-id="bf50d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bf50d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bf50d-105">包含在搜索过程中找到邮件的文件夹的显示名称。</span><span class="sxs-lookup"><span data-stu-id="bf50d-105">Contains the display name of the folder where a message was found during a search.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="bf50d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="bf50d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="bf50d-107">PR_PARENT_DISPLAY、PR_PARENT_DISPLAY_A、PR_PARENT_DISPLAY_W</span><span class="sxs-lookup"><span data-stu-id="bf50d-107">PR_PARENT_DISPLAY, PR_PARENT_DISPLAY_A, PR_PARENT_DISPLAY_W</span></span>  <br/> |
|<span data-ttu-id="bf50d-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="bf50d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="bf50d-109">0x0E05</span><span class="sxs-lookup"><span data-stu-id="bf50d-109">0x0E05</span></span>  <br/> |
|<span data-ttu-id="bf50d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="bf50d-110">Data type:</span></span>  <br/> |<span data-ttu-id="bf50d-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="bf50d-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="bf50d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="bf50d-112">Area:</span></span>  <br/> |<span data-ttu-id="bf50d-113">MAPI 非传输</span><span class="sxs-lookup"><span data-stu-id="bf50d-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bf50d-114">注解</span><span class="sxs-lookup"><span data-stu-id="bf50d-114">Remarks</span></span>

<span data-ttu-id="bf50d-115">这些属性不在任何对象上。</span><span class="sxs-lookup"><span data-stu-id="bf50d-115">These properties is not on any object.</span></span> <span data-ttu-id="bf50d-116">它们只能出现在搜索结果文件夹的内容表中。</span><span class="sxs-lookup"><span data-stu-id="bf50d-116">They can only appear in the contents table of a search-results folder.</span></span>
  
<span data-ttu-id="bf50d-117">这些属性和**PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md)) 属性不相互关联。</span><span class="sxs-lookup"><span data-stu-id="bf50d-117">These properties and **PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md)) properties are not related to each other.</span></span> <span data-ttu-id="bf50d-118">它们属于完全不同的上下文。</span><span class="sxs-lookup"><span data-stu-id="bf50d-118">They belong to entirely different contexts.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="bf50d-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="bf50d-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="bf50d-120">头文件</span><span class="sxs-lookup"><span data-stu-id="bf50d-120">Header files</span></span>

<span data-ttu-id="bf50d-121">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="bf50d-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="bf50d-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="bf50d-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="bf50d-123">Mapitags</span><span class="sxs-lookup"><span data-stu-id="bf50d-123">Mapitags.h</span></span>
  
> <span data-ttu-id="bf50d-124">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="bf50d-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bf50d-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf50d-125">See also</span></span>



[<span data-ttu-id="bf50d-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="bf50d-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="bf50d-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="bf50d-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="bf50d-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="bf50d-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="bf50d-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="bf50d-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

