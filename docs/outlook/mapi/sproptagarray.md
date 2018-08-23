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
ms.openlocfilehash: 5237a5c2767920bdb604bfe86603cea4fca56b84
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572772"
---
# <a name="sproptagarray"></a><span data-ttu-id="29dbf-103">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="29dbf-103">SPropTagArray</span></span>

  
  
<span data-ttu-id="29dbf-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="29dbf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="29dbf-105">包含数组属性标记。</span><span class="sxs-lookup"><span data-stu-id="29dbf-105">Contains an array of property tags.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="29dbf-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="29dbf-106">Header file:</span></span>  <br/> |<span data-ttu-id="29dbf-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="29dbf-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="29dbf-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="29dbf-108">Related macros:</span></span>  <br/> |<span data-ttu-id="29dbf-109">[CbNewSPropTagArray](cbnewsproptagarray.md)， [CbSPropTagArray](cbsproptagarray.md)， [SizedSPropTagArray](sizedsproptagarray.md)</span><span class="sxs-lookup"><span data-stu-id="29dbf-109">[CbNewSPropTagArray](cbnewsproptagarray.md), [CbSPropTagArray](cbsproptagarray.md), [SizedSPropTagArray](sizedsproptagarray.md)</span></span> <br/> |
   
```cpp
typedef struct _SPropTagArray
{
  ULONG cValues;
  ULONG aulPropTag[MAPI_DIM];
} SPropTagArray, FAR *LPSPropTagArray;

```

## <a name="members"></a><span data-ttu-id="29dbf-110">Members</span><span class="sxs-lookup"><span data-stu-id="29dbf-110">Members</span></span>

 <span data-ttu-id="29dbf-111">**cValues**</span><span class="sxs-lookup"><span data-stu-id="29dbf-111">**cValues**</span></span>
  
> <span data-ttu-id="29dbf-112">属性数组由**aulPropTag**成员中的标记的计数。</span><span class="sxs-lookup"><span data-stu-id="29dbf-112">Count of property tags in the array indicated by the **aulPropTag** member.</span></span> 
    
 <span data-ttu-id="29dbf-113">**aulPropTag**</span><span class="sxs-lookup"><span data-stu-id="29dbf-113">**aulPropTag**</span></span>
  
> <span data-ttu-id="29dbf-114">属性标记的数组。</span><span class="sxs-lookup"><span data-stu-id="29dbf-114">Array of property tags.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="29dbf-115">注解</span><span class="sxs-lookup"><span data-stu-id="29dbf-115">Remarks</span></span>

<span data-ttu-id="29dbf-116">属性标记是一个 32 位无符号的整数，由两部分组成：</span><span class="sxs-lookup"><span data-stu-id="29dbf-116">A property tag is a 32-bit unsigned integer that consists of two parts:</span></span> 
  
- <span data-ttu-id="29dbf-117">中高阶 16 位的标识符。</span><span class="sxs-lookup"><span data-stu-id="29dbf-117">An identifier in the high-order 16 bits.</span></span>
    
- <span data-ttu-id="29dbf-118">低序位 16 位中的类型。</span><span class="sxs-lookup"><span data-stu-id="29dbf-118">A type in the low-order 16 bits.</span></span>
    
<span data-ttu-id="29dbf-119">标识符是一个数值在特定范围内。</span><span class="sxs-lookup"><span data-stu-id="29dbf-119">The identifier is a numeric value in a particular range.</span></span> <span data-ttu-id="29dbf-120">MAPI 定义标识符来描述属性用于和谁负责维护它的区域。</span><span class="sxs-lookup"><span data-stu-id="29dbf-120">MAPI defines ranges for identifiers to describe what the property is used for and who is responsible for maintaining it.</span></span> <span data-ttu-id="29dbf-121">MAPI 属性标记它 Mapitags.h 头文件中所支持的每个定义的约束。</span><span class="sxs-lookup"><span data-stu-id="29dbf-121">MAPI defines constraints for each of the property tags that it supports in the Mapitags.h header file.</span></span>
  
<span data-ttu-id="29dbf-122">该类型指示该属性的值的格式。</span><span class="sxs-lookup"><span data-stu-id="29dbf-122">The type indicates the format for the property's value.</span></span> <span data-ttu-id="29dbf-123">MAPI 的属性类型，它支持 Mapidefs.h 头文件中的每个定义的常数。</span><span class="sxs-lookup"><span data-stu-id="29dbf-123">MAPI defines constants for each of the property types that it supports in the Mapidefs.h header file.</span></span> 
  
<span data-ttu-id="29dbf-124">有关属性标记及其组件的详细信息，请参阅以下主题之一：</span><span class="sxs-lookup"><span data-stu-id="29dbf-124">For more information about property tags and their components, see one of the following topics:</span></span> 
  
[<span data-ttu-id="29dbf-125">MAPI 属性标记</span><span class="sxs-lookup"><span data-stu-id="29dbf-125">MAPI Property Tags</span></span>](mapi-property-tags.md)
  
[<span data-ttu-id="29dbf-126">MAPI 属性标识符概述</span><span class="sxs-lookup"><span data-stu-id="29dbf-126">MAPI Property Identifier Overview</span></span>](mapi-property-identifier-overview.md)
  
[<span data-ttu-id="29dbf-127">MAPI 属性类型概述</span><span class="sxs-lookup"><span data-stu-id="29dbf-127">MAPI Property Type Overview</span></span>](mapi-property-type-overview.md)
  
<span data-ttu-id="29dbf-128">单值和多值属性类型的完整列表，请参阅附录[属性标识符和类型](property-identifiers-and-types.md)。</span><span class="sxs-lookup"><span data-stu-id="29dbf-128">For a complete list of the single-valued and multi-valued property types, see the appendix, [Property Identifiers and Types](property-identifiers-and-types.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="29dbf-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29dbf-129">See also</span></span>



[<span data-ttu-id="29dbf-130">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="29dbf-130">MAPI Structures</span></span>](mapi-structures.md)

