---
title: PidTagNull 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagNull
api_type:
- HeaderDef
ms.assetid: 192cdab8-c615-47b9-9f04-a1414eaf0c77
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7e9c3340dfad47a811b56c86e8e6104fb6aac7c2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329265"
---
# <a name="pidtagnull-canonical-property"></a><span data-ttu-id="4442d-103">PidTagNull 规范属性</span><span class="sxs-lookup"><span data-stu-id="4442d-103">PidTagNull Canonical Property</span></span>

  
  
<span data-ttu-id="4442d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4442d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4442d-105">表示一个空值或属性设置或保留数组空间。</span><span class="sxs-lookup"><span data-stu-id="4442d-105">Represents a null value or setting of a property or reserves array space.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4442d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4442d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4442d-107">PR_NULL</span><span class="sxs-lookup"><span data-stu-id="4442d-107">PR_NULL</span></span>  <br/> |
|<span data-ttu-id="4442d-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="4442d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4442d-109">0x0000</span><span class="sxs-lookup"><span data-stu-id="4442d-109">0x0000</span></span>  <br/> |
|<span data-ttu-id="4442d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4442d-110">Data type:</span></span>  <br/> |<span data-ttu-id="4442d-111">PT_NULL</span><span class="sxs-lookup"><span data-stu-id="4442d-111">PT_NULL</span></span>  <br/> |
|<span data-ttu-id="4442d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4442d-112">Area:</span></span>  <br/> |<span data-ttu-id="4442d-113">常见</span><span class="sxs-lookup"><span data-stu-id="4442d-113">Common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4442d-114">备注</span><span class="sxs-lookup"><span data-stu-id="4442d-114">Remarks</span></span>

<span data-ttu-id="4442d-115">此属性用于在 [SPropValue](spropvalue.md) 结构的数组中保留空间。</span><span class="sxs-lookup"><span data-stu-id="4442d-115">This property is used to reserve space in arrays of [SPropValue](spropvalue.md) structures.</span></span> <span data-ttu-id="4442d-116">它在 [SPropTagArray](sproptagarray.md) 结构的数组中用于告诉方法在返回的 **SPropValue** 结构的数组中保留空间。</span><span class="sxs-lookup"><span data-stu-id="4442d-116">It is used in an array of [SPropTagArray](sproptagarray.md) structures to tell the method to reserve space in the returned array of **SPropValue** structures.</span></span> <span data-ttu-id="4442d-117">这允许以经济实惠的方式填充计算属性。</span><span class="sxs-lookup"><span data-stu-id="4442d-117">This allows for computed properties to be filled in an inexpensive way.</span></span> 
  
<span data-ttu-id="4442d-118">有关详细信息，请参阅 [MAPI 属性类型概述](mapi-property-type-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4442d-118">For more information, see [MAPI Property Type Overview](mapi-property-type-overview.md).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="4442d-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="4442d-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4442d-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="4442d-120">Protocol specifications</span></span>

<span data-ttu-id="4442d-121">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4442d-121">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4442d-122">指定对联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="4442d-122">Specifies the properties and operations that are permissible on contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4442d-123">头文件</span><span class="sxs-lookup"><span data-stu-id="4442d-123">Header files</span></span>

<span data-ttu-id="4442d-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4442d-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="4442d-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4442d-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="4442d-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="4442d-126">Mapitags.h</span></span>
  
> <span data-ttu-id="4442d-127">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4442d-127">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4442d-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4442d-128">See also</span></span>



[<span data-ttu-id="4442d-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4442d-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4442d-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4442d-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4442d-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4442d-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4442d-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4442d-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

