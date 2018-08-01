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
ms.openlocfilehash: 55db507055692c9e929b0125abf719d8c03ac967
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777908"
---
# <a name="pidtagnull-canonical-property"></a><span data-ttu-id="b7cc5-103">PidTagNull 规范属性</span><span class="sxs-lookup"><span data-stu-id="b7cc5-103">PidTagNull Canonical Property</span></span>

  
  
<span data-ttu-id="b7cc5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b7cc5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b7cc5-105">代表一个 null 值或属性的设置，或保留数组空间。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-105">Represents a null value or setting of a property or reserves array space.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b7cc5-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b7cc5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b7cc5-107">PR_NULL</span><span class="sxs-lookup"><span data-stu-id="b7cc5-107">PR_NULL</span></span>  <br/> |
|<span data-ttu-id="b7cc5-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="b7cc5-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b7cc5-109">0x0000</span><span class="sxs-lookup"><span data-stu-id="b7cc5-109">0x0000</span></span>  <br/> |
|<span data-ttu-id="b7cc5-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b7cc5-110">Data type:</span></span>  <br/> |<span data-ttu-id="b7cc5-111">PT_NULL</span><span class="sxs-lookup"><span data-stu-id="b7cc5-111">PT_NULL</span></span>  <br/> |
|<span data-ttu-id="b7cc5-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b7cc5-112">Area:</span></span>  <br/> |<span data-ttu-id="b7cc5-113">Common</span><span class="sxs-lookup"><span data-stu-id="b7cc5-113">Common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b7cc5-114">说明</span><span class="sxs-lookup"><span data-stu-id="b7cc5-114">Remarks</span></span>

<span data-ttu-id="b7cc5-115">此属性用于保留空间数组中的[SPropValue](spropvalue.md)结构。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-115">This property is used to reserve space in arrays of [SPropValue](spropvalue.md) structures.</span></span> <span data-ttu-id="b7cc5-116">使用数组中的[SPropTagArray](sproptagarray.md)结构以告知保留空间返回的数组中的**SPropValue**结构的方法。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-116">It is used in an array of [SPropTagArray](sproptagarray.md) structures to tell the method to reserve space in the returned array of **SPropValue** structures.</span></span> <span data-ttu-id="b7cc5-117">这样，计算属性便宜方式填充。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-117">This allows for computed properties to be filled in an inexpensive way.</span></span> 
  
<span data-ttu-id="b7cc5-118">有关详细信息，请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-118">For more information, see [MAPI Property Type Overview](mapi-property-type-overview.md).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="b7cc5-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="b7cc5-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b7cc5-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="b7cc5-120">Protocol specifications</span></span>

<span data-ttu-id="b7cc5-121">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b7cc5-121">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b7cc5-122">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-122">Specifies the properties and operations that are permissible on contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b7cc5-123">头文件</span><span class="sxs-lookup"><span data-stu-id="b7cc5-123">Header files</span></span>

<span data-ttu-id="b7cc5-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b7cc5-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="b7cc5-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="b7cc5-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b7cc5-126">Mapitags.h</span></span>
  
> <span data-ttu-id="b7cc5-127">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-127">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b7cc5-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7cc5-128">See also</span></span>



[<span data-ttu-id="b7cc5-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b7cc5-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b7cc5-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b7cc5-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b7cc5-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b7cc5-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b7cc5-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b7cc5-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

