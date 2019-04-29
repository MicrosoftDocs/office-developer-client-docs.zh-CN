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
ms.openlocfilehash: 3b15cd27f6852f28e9dac113f6c45942de40ebbe
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428786"
---
# <a name="pidtagformcategorysub-canonical-property"></a><span data-ttu-id="0ca52-103">PidTagFormCategorySub 规范属性</span><span class="sxs-lookup"><span data-stu-id="0ca52-103">PidTagFormCategorySub Canonical Property</span></span>

  
  
<span data-ttu-id="0ca52-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0ca52-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0ca52-105">包含由客户端应用程序定义的窗体子类别。</span><span class="sxs-lookup"><span data-stu-id="0ca52-105">Contains the subcategory of a form, as defined by a client application.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0ca52-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0ca52-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0ca52-107">PR_FORM_CATEGORY_SUB、PR_FORM_CATEGORY_SUB_A、PR_FORM_CATEGORY_SUB_W</span><span class="sxs-lookup"><span data-stu-id="0ca52-107">PR_FORM_CATEGORY_SUB, PR_FORM_CATEGORY_SUB_A, PR_FORM_CATEGORY_SUB_W</span></span>  <br/> |
|<span data-ttu-id="0ca52-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="0ca52-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0ca52-109">0x3305</span><span class="sxs-lookup"><span data-stu-id="0ca52-109">0x3305</span></span>  <br/> |
|<span data-ttu-id="0ca52-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0ca52-110">Data type:</span></span>  <br/> |<span data-ttu-id="0ca52-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="0ca52-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="0ca52-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0ca52-112">Area:</span></span>  <br/> |<span data-ttu-id="0ca52-113">MAPI 通用</span><span class="sxs-lookup"><span data-stu-id="0ca52-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0ca52-114">说明</span><span class="sxs-lookup"><span data-stu-id="0ca52-114">Remarks</span></span>

<span data-ttu-id="0ca52-115">这些属性从属于在**PR_FORM_CATEGORY** ([PidTagFormCategory](pidtagformcategory-canonical-property.md)) 属性中提供的主窗体类别。</span><span class="sxs-lookup"><span data-stu-id="0ca52-115">These properties are subordinate to the main form category that is provided in the **PR_FORM_CATEGORY** ([PidTagFormCategory](pidtagformcategory-canonical-property.md)) property.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="0ca52-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="0ca52-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="0ca52-117">头文件</span><span class="sxs-lookup"><span data-stu-id="0ca52-117">Header files</span></span>

<span data-ttu-id="0ca52-118">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="0ca52-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="0ca52-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0ca52-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="0ca52-120">Mapitags</span><span class="sxs-lookup"><span data-stu-id="0ca52-120">Mapitags.h</span></span>
  
> <span data-ttu-id="0ca52-121">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0ca52-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0ca52-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ca52-122">See also</span></span>



[<span data-ttu-id="0ca52-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0ca52-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0ca52-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0ca52-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0ca52-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0ca52-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0ca52-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0ca52-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

