---
title: SPropTagArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SPropTagArray
api_type:
- COM
ms.assetid: 4a9e1579-bebe-4a51-8ced-6dba9c3bcb63
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9a5be98298ab1f9333ac1c223a6ef594e60dd86a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344434"
---
# <a name="sproptagarray"></a><span data-ttu-id="6b71d-103">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="6b71d-103">SPropTagArray</span></span>

  
  
<span data-ttu-id="6b71d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6b71d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6b71d-105">包含一个属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="6b71d-105">Contains an array of property tags.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6b71d-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="6b71d-106">Header file:</span></span>  <br/> |<span data-ttu-id="6b71d-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="6b71d-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="6b71d-108">相关宏:</span><span class="sxs-lookup"><span data-stu-id="6b71d-108">Related macros:</span></span>  <br/> |<span data-ttu-id="6b71d-109">[CbNewSPropTagArray](cbnewsproptagarray.md)、 [CbSPropTagArray](cbsproptagarray.md)、 [SizedSPropTagArray](sizedsproptagarray.md)</span><span class="sxs-lookup"><span data-stu-id="6b71d-109">[CbNewSPropTagArray](cbnewsproptagarray.md), [CbSPropTagArray](cbsproptagarray.md), [SizedSPropTagArray](sizedsproptagarray.md)</span></span> <br/> |
   
```cpp
typedef struct _SPropTagArray
{
  ULONG cValues;
  ULONG aulPropTag[MAPI_DIM];
} SPropTagArray, FAR *LPSPropTagArray;

```

## <a name="members"></a><span data-ttu-id="6b71d-110">Members</span><span class="sxs-lookup"><span data-stu-id="6b71d-110">Members</span></span>

 <span data-ttu-id="6b71d-111">**cValues**</span><span class="sxs-lookup"><span data-stu-id="6b71d-111">**cValues**</span></span>
  
> <span data-ttu-id="6b71d-112">由**aulPropTag**成员指示的数组中的属性标记的计数。</span><span class="sxs-lookup"><span data-stu-id="6b71d-112">Count of property tags in the array indicated by the **aulPropTag** member.</span></span> 
    
 <span data-ttu-id="6b71d-113">**aulPropTag**</span><span class="sxs-lookup"><span data-stu-id="6b71d-113">**aulPropTag**</span></span>
  
> <span data-ttu-id="6b71d-114">属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="6b71d-114">Array of property tags.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6b71d-115">注解</span><span class="sxs-lookup"><span data-stu-id="6b71d-115">Remarks</span></span>

<span data-ttu-id="6b71d-116">属性标记是一个32位无符号整数, 由两部分组成:</span><span class="sxs-lookup"><span data-stu-id="6b71d-116">A property tag is a 32-bit unsigned integer that consists of two parts:</span></span> 
  
- <span data-ttu-id="6b71d-117">高顺序16位中的标识符。</span><span class="sxs-lookup"><span data-stu-id="6b71d-117">An identifier in the high-order 16 bits.</span></span>
    
- <span data-ttu-id="6b71d-118">一个低序位16位的类型。</span><span class="sxs-lookup"><span data-stu-id="6b71d-118">A type in the low-order 16 bits.</span></span>
    
<span data-ttu-id="6b71d-119">标识符是特定区域中的一个数值。</span><span class="sxs-lookup"><span data-stu-id="6b71d-119">The identifier is a numeric value in a particular range.</span></span> <span data-ttu-id="6b71d-120">MAPI 为标识符定义范围, 以描述该属性的用途, 以及负责维护该属性的参与者。</span><span class="sxs-lookup"><span data-stu-id="6b71d-120">MAPI defines ranges for identifiers to describe what the property is used for and who is responsible for maintaining it.</span></span> <span data-ttu-id="6b71d-121">MAPI 为在 Mapitags 头文件中支持的每个属性标记定义约束。</span><span class="sxs-lookup"><span data-stu-id="6b71d-121">MAPI defines constraints for each of the property tags that it supports in the Mapitags.h header file.</span></span>
  
<span data-ttu-id="6b71d-122">类型指示属性值的格式。</span><span class="sxs-lookup"><span data-stu-id="6b71d-122">The type indicates the format for the property's value.</span></span> <span data-ttu-id="6b71d-123">MAPI 为它在 mapidefs.h 头文件中支持的每个属性类型定义常量。</span><span class="sxs-lookup"><span data-stu-id="6b71d-123">MAPI defines constants for each of the property types that it supports in the Mapidefs.h header file.</span></span> 
  
<span data-ttu-id="6b71d-124">有关属性标记及其组件的详细信息, 请参阅下列主题之一:</span><span class="sxs-lookup"><span data-stu-id="6b71d-124">For more information about property tags and their components, see one of the following topics:</span></span> 
  
[<span data-ttu-id="6b71d-125">MAPI 属性标记</span><span class="sxs-lookup"><span data-stu-id="6b71d-125">MAPI Property Tags</span></span>](mapi-property-tags.md)
  
[<span data-ttu-id="6b71d-126">MAPI 属性标识符概述</span><span class="sxs-lookup"><span data-stu-id="6b71d-126">MAPI Property Identifier Overview</span></span>](mapi-property-identifier-overview.md)
  
[<span data-ttu-id="6b71d-127">MAPI 属性类型概述</span><span class="sxs-lookup"><span data-stu-id="6b71d-127">MAPI Property Type Overview</span></span>](mapi-property-type-overview.md)
  
<span data-ttu-id="6b71d-128">有关单值和多值属性类型的完整列表, 请参阅附录、[属性标识符和类型](property-identifiers-and-types.md)。</span><span class="sxs-lookup"><span data-stu-id="6b71d-128">For a complete list of the single-valued and multi-valued property types, see the appendix, [Property Identifiers and Types](property-identifiers-and-types.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6b71d-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b71d-129">See also</span></span>



[<span data-ttu-id="6b71d-130">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="6b71d-130">MAPI Structures</span></span>](mapi-structures.md)

