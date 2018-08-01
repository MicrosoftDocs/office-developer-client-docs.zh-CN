---
title: PidTagFormCategorySub 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFormCategorySub
api_type:
- HeaderDef
ms.assetid: 0e654152-c850-417a-8877-29d47cf85db5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 30c52ca50ed3d04c570bf0a25f98bdd027e411af
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777648"
---
# <a name="pidtagformcategorysub-canonical-property"></a><span data-ttu-id="51e01-103">PidTagFormCategorySub 规范属性</span><span class="sxs-lookup"><span data-stu-id="51e01-103">PidTagFormCategorySub Canonical Property</span></span>

  
  
<span data-ttu-id="51e01-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="51e01-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="51e01-105">包含由客户端应用程序定义的窗体的子类别。</span><span class="sxs-lookup"><span data-stu-id="51e01-105">Contains the subcategory of a form, as defined by a client application.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="51e01-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="51e01-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="51e01-107">PR_FORM_CATEGORY_SUB，PR_FORM_CATEGORY_SUB_A，PR_FORM_CATEGORY_SUB_W</span><span class="sxs-lookup"><span data-stu-id="51e01-107">PR_FORM_CATEGORY_SUB, PR_FORM_CATEGORY_SUB_A, PR_FORM_CATEGORY_SUB_W</span></span>  <br/> |
|<span data-ttu-id="51e01-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="51e01-108">Identifier:</span></span>  <br/> |<span data-ttu-id="51e01-109">0x3305</span><span class="sxs-lookup"><span data-stu-id="51e01-109">0x3305</span></span>  <br/> |
|<span data-ttu-id="51e01-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="51e01-110">Data type:</span></span>  <br/> |<span data-ttu-id="51e01-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="51e01-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="51e01-112">区域：</span><span class="sxs-lookup"><span data-stu-id="51e01-112">Area:</span></span>  <br/> |<span data-ttu-id="51e01-113">常见的 MAPI</span><span class="sxs-lookup"><span data-stu-id="51e01-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="51e01-114">说明</span><span class="sxs-lookup"><span data-stu-id="51e01-114">Remarks</span></span>

<span data-ttu-id="51e01-115">这些属性是属于**PR_FORM_CATEGORY** ([PidTagFormCategory](pidtagformcategory-canonical-property.md)) 属性中提供的主窗体类别。</span><span class="sxs-lookup"><span data-stu-id="51e01-115">These properties are subordinate to the main form category that is provided in the **PR_FORM_CATEGORY** ([PidTagFormCategory](pidtagformcategory-canonical-property.md)) property.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="51e01-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="51e01-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="51e01-117">头文件</span><span class="sxs-lookup"><span data-stu-id="51e01-117">Header files</span></span>

<span data-ttu-id="51e01-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="51e01-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="51e01-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="51e01-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="51e01-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="51e01-120">Mapitags.h</span></span>
  
> <span data-ttu-id="51e01-121">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="51e01-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="51e01-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51e01-122">See also</span></span>



[<span data-ttu-id="51e01-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="51e01-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="51e01-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="51e01-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="51e01-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="51e01-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="51e01-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="51e01-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

