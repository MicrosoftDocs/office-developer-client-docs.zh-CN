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
ms.openlocfilehash: 3790ce243890f1cce4d67352a8fb0b7191588269
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777656"
---
# <a name="pidtagformversion-canonical-property"></a><span data-ttu-id="8e73f-103">PidTagFormVersion 规范属性</span><span class="sxs-lookup"><span data-stu-id="8e73f-103">PidTagFormVersion Canonical Property</span></span>

  
  
<span data-ttu-id="8e73f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8e73f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8e73f-105">包含为表单的版本。</span><span class="sxs-lookup"><span data-stu-id="8e73f-105">Contains the version of a form.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8e73f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8e73f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8e73f-107">PR_FORM_VERSION，PR_FORM_VERSION_A，PR_FORM_VERSION_W</span><span class="sxs-lookup"><span data-stu-id="8e73f-107">PR_FORM_VERSION, PR_FORM_VERSION_A, PR_FORM_VERSION_W</span></span>  <br/> |
|<span data-ttu-id="8e73f-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="8e73f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8e73f-109">0x3301</span><span class="sxs-lookup"><span data-stu-id="8e73f-109">0x3301</span></span>  <br/> |
|<span data-ttu-id="8e73f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8e73f-110">Data type:</span></span>  <br/> |<span data-ttu-id="8e73f-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="8e73f-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="8e73f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8e73f-112">Area:</span></span>  <br/> |<span data-ttu-id="8e73f-113">常见的 MAPI</span><span class="sxs-lookup"><span data-stu-id="8e73f-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8e73f-114">说明</span><span class="sxs-lookup"><span data-stu-id="8e73f-114">Remarks</span></span>

<span data-ttu-id="8e73f-115">这些属性指示哪些设计版本是当前在窗体的效果。</span><span class="sxs-lookup"><span data-stu-id="8e73f-115">These properties indicate what design version is currently in effect for the form.</span></span> <span data-ttu-id="8e73f-116">定义和维护表单版本的设计器，并不一定与任何 MAPI 组件版本。</span><span class="sxs-lookup"><span data-stu-id="8e73f-116">The version is defined and maintained by the form's designer and is not necessarily related to any MAPI component version.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="8e73f-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="8e73f-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="8e73f-118">头文件</span><span class="sxs-lookup"><span data-stu-id="8e73f-118">Header files</span></span>

<span data-ttu-id="8e73f-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8e73f-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="8e73f-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8e73f-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="8e73f-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="8e73f-121">Mapitags.h</span></span>
  
> <span data-ttu-id="8e73f-122">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8e73f-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8e73f-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e73f-123">See also</span></span>



[<span data-ttu-id="8e73f-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8e73f-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8e73f-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8e73f-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8e73f-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8e73f-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8e73f-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8e73f-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

