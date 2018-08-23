---
title: PidTagFormDesignerGuid 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFormDesignerGuid
api_type:
- HeaderDef
ms.assetid: 8d7f5789-610c-47f6-a109-5513d677ef60
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 30c8f31c104be52da2900eb81c7b7c29dfa55015
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586527"
---
# <a name="pidtagformdesignerguid-canonical-property"></a><span data-ttu-id="a2c6e-103">PidTagFormDesignerGuid 规范属性</span><span class="sxs-lookup"><span data-stu-id="a2c6e-103">PidTagFormDesignerGuid Canonical Property</span></span>

  
  
<span data-ttu-id="a2c6e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a2c6e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a2c6e-105">包含用于设计窗体的对象的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="a2c6e-105">Contains the unique identifier for the object that is used to design a form.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a2c6e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a2c6e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a2c6e-107">PR_FORM_DESIGNER_GUID</span><span class="sxs-lookup"><span data-stu-id="a2c6e-107">PR_FORM_DESIGNER_GUID</span></span>  <br/> |
|<span data-ttu-id="a2c6e-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="a2c6e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a2c6e-109">0x3309</span><span class="sxs-lookup"><span data-stu-id="a2c6e-109">0x3309</span></span>  <br/> |
|<span data-ttu-id="a2c6e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a2c6e-110">Data type:</span></span>  <br/> |<span data-ttu-id="a2c6e-111">PT_GUID</span><span class="sxs-lookup"><span data-stu-id="a2c6e-111">PT_GUID</span></span>  <br/> |
|<span data-ttu-id="a2c6e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a2c6e-112">Area:</span></span>  <br/> |<span data-ttu-id="a2c6e-113">常见的 MAPI</span><span class="sxs-lookup"><span data-stu-id="a2c6e-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a2c6e-114">注解</span><span class="sxs-lookup"><span data-stu-id="a2c6e-114">Remarks</span></span>

<span data-ttu-id="a2c6e-115">此属性通常包含用于创建窗体的设计程序的全局唯一标识符 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="a2c6e-115">This property usually contains the globally unique identifier (GUID) of the design program that is used to create the form.</span></span> <span data-ttu-id="a2c6e-116">此属性可以为空。</span><span class="sxs-lookup"><span data-stu-id="a2c6e-116">This property can be empty.</span></span> 
  
<span data-ttu-id="a2c6e-117">[MAPIUID](mapiuid.md)结构包含定义的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="a2c6e-117">The [MAPIUID](mapiuid.md) structure contains the definition of the unique identifier.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="a2c6e-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="a2c6e-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="a2c6e-119">头文件</span><span class="sxs-lookup"><span data-stu-id="a2c6e-119">Header files</span></span>

<span data-ttu-id="a2c6e-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a2c6e-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="a2c6e-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a2c6e-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="a2c6e-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="a2c6e-122">Mapitags.h</span></span>
  
> <span data-ttu-id="a2c6e-123">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a2c6e-123">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a2c6e-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2c6e-124">See also</span></span>



[<span data-ttu-id="a2c6e-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a2c6e-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a2c6e-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a2c6e-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a2c6e-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a2c6e-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a2c6e-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a2c6e-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

