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
ms.openlocfilehash: b0e0847a3a9e21f080a852738ec8afbc98a2263f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316231"
---
# <a name="pidtagformdesignerguid-canonical-property"></a><span data-ttu-id="a3bc1-103">PidTagFormDesignerGuid 规范属性</span><span class="sxs-lookup"><span data-stu-id="a3bc1-103">PidTagFormDesignerGuid Canonical Property</span></span>

  
  
<span data-ttu-id="a3bc1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a3bc1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a3bc1-105">包含用于设计表单的对象的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="a3bc1-105">Contains the unique identifier for the object that is used to design a form.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a3bc1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a3bc1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a3bc1-107">PR_FORM_DESIGNER_GUID</span><span class="sxs-lookup"><span data-stu-id="a3bc1-107">PR_FORM_DESIGNER_GUID</span></span>  <br/> |
|<span data-ttu-id="a3bc1-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="a3bc1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a3bc1-109">0x3309</span><span class="sxs-lookup"><span data-stu-id="a3bc1-109">0x3309</span></span>  <br/> |
|<span data-ttu-id="a3bc1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a3bc1-110">Data type:</span></span>  <br/> |<span data-ttu-id="a3bc1-111">PT_GUID</span><span class="sxs-lookup"><span data-stu-id="a3bc1-111">PT_GUID</span></span>  <br/> |
|<span data-ttu-id="a3bc1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a3bc1-112">Area:</span></span>  <br/> |<span data-ttu-id="a3bc1-113">MAPI 通用</span><span class="sxs-lookup"><span data-stu-id="a3bc1-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a3bc1-114">注解</span><span class="sxs-lookup"><span data-stu-id="a3bc1-114">Remarks</span></span>

<span data-ttu-id="a3bc1-115">此属性通常包含用于创建窗体的设计程序的全局唯一标识符 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="a3bc1-115">This property usually contains the globally unique identifier (GUID) of the design program that is used to create the form.</span></span> <span data-ttu-id="a3bc1-116">此属性可以为空。</span><span class="sxs-lookup"><span data-stu-id="a3bc1-116">This property can be empty.</span></span> 
  
<span data-ttu-id="a3bc1-117">[MAPIUID](mapiuid.md)结构包含唯一标识符的定义。</span><span class="sxs-lookup"><span data-stu-id="a3bc1-117">The [MAPIUID](mapiuid.md) structure contains the definition of the unique identifier.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="a3bc1-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="a3bc1-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="a3bc1-119">头文件</span><span class="sxs-lookup"><span data-stu-id="a3bc1-119">Header files</span></span>

<span data-ttu-id="a3bc1-120">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="a3bc1-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="a3bc1-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a3bc1-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="a3bc1-122">Mapitags</span><span class="sxs-lookup"><span data-stu-id="a3bc1-122">Mapitags.h</span></span>
  
> <span data-ttu-id="a3bc1-123">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a3bc1-123">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a3bc1-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3bc1-124">See also</span></span>



[<span data-ttu-id="a3bc1-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a3bc1-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a3bc1-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a3bc1-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a3bc1-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a3bc1-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a3bc1-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a3bc1-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

