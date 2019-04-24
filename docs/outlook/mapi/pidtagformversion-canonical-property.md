---
title: PidTagFormVersion 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFormVersion
api_type:
- HeaderDef
ms.assetid: f2220060-65ea-4969-88d7-8348bd5aa242
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ec806ed3ab871d6a36778b0898b2977628ccdcec
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316203"
---
# <a name="pidtagformversion-canonical-property"></a><span data-ttu-id="db1f2-103">PidTagFormVersion 规范属性</span><span class="sxs-lookup"><span data-stu-id="db1f2-103">PidTagFormVersion Canonical Property</span></span>

  
  
<span data-ttu-id="db1f2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="db1f2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="db1f2-105">包含表单的版本。</span><span class="sxs-lookup"><span data-stu-id="db1f2-105">Contains the version of a form.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="db1f2-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="db1f2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="db1f2-107">PR_FORM_VERSION、PR_FORM_VERSION_A、PR_FORM_VERSION_W</span><span class="sxs-lookup"><span data-stu-id="db1f2-107">PR_FORM_VERSION, PR_FORM_VERSION_A, PR_FORM_VERSION_W</span></span>  <br/> |
|<span data-ttu-id="db1f2-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="db1f2-108">Identifier:</span></span>  <br/> |<span data-ttu-id="db1f2-109">0x3301</span><span class="sxs-lookup"><span data-stu-id="db1f2-109">0x3301</span></span>  <br/> |
|<span data-ttu-id="db1f2-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="db1f2-110">Data type:</span></span>  <br/> |<span data-ttu-id="db1f2-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="db1f2-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="db1f2-112">区域：</span><span class="sxs-lookup"><span data-stu-id="db1f2-112">Area:</span></span>  <br/> |<span data-ttu-id="db1f2-113">MAPI 通用</span><span class="sxs-lookup"><span data-stu-id="db1f2-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="db1f2-114">注解</span><span class="sxs-lookup"><span data-stu-id="db1f2-114">Remarks</span></span>

<span data-ttu-id="db1f2-115">这些属性指示当前对窗体有效的设计版本。</span><span class="sxs-lookup"><span data-stu-id="db1f2-115">These properties indicate what design version is currently in effect for the form.</span></span> <span data-ttu-id="db1f2-116">版本由窗体的设计器定义和维护, 并不一定与任何 MAPI 组件版本相关。</span><span class="sxs-lookup"><span data-stu-id="db1f2-116">The version is defined and maintained by the form's designer and is not necessarily related to any MAPI component version.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="db1f2-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="db1f2-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="db1f2-118">头文件</span><span class="sxs-lookup"><span data-stu-id="db1f2-118">Header files</span></span>

<span data-ttu-id="db1f2-119">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="db1f2-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="db1f2-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="db1f2-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="db1f2-121">Mapitags</span><span class="sxs-lookup"><span data-stu-id="db1f2-121">Mapitags.h</span></span>
  
> <span data-ttu-id="db1f2-122">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="db1f2-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="db1f2-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db1f2-123">See also</span></span>



[<span data-ttu-id="db1f2-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="db1f2-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="db1f2-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="db1f2-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="db1f2-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="db1f2-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="db1f2-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="db1f2-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

