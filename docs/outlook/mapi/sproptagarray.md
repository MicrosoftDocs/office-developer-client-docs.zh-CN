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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 5cfad1c75aaab9afae47de5798f9e6b7ea530940
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778855"
---
# <a name="sproptagarray"></a><span data-ttu-id="240b8-103">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="240b8-103">SPropTagArray</span></span>

  
  
<span data-ttu-id="240b8-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="240b8-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="240b8-105">包含数组属性标记。</span><span class="sxs-lookup"><span data-stu-id="240b8-105">Contains an array of property tags.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="240b8-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="240b8-106">Header file:</span></span>  <br/> |<span data-ttu-id="240b8-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="240b8-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="240b8-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="240b8-108">Related macros:</span></span>  <br/> |<span data-ttu-id="240b8-109">[CbNewSPropTagArray](cbnewsproptagarray.md)， [CbSPropTagArray](cbsproptagarray.md)， [SizedSPropTagArray](sizedsproptagarray.md)</span><span class="sxs-lookup"><span data-stu-id="240b8-109">[CbNewSPropTagArray](cbnewsproptagarray.md), [CbSPropTagArray](cbsproptagarray.md), [SizedSPropTagArray](sizedsproptagarray.md)</span></span> <br/> |
   
```cpp
typedef struct _SPropTagArray
{
  ULONG cValues;
  ULONG aulPropTag[MAPI_DIM];
} SPropTagArray, FAR *LPSPropTagArray;

```

## <a name="members"></a><span data-ttu-id="240b8-110">成员</span><span class="sxs-lookup"><span data-stu-id="240b8-110">Members</span></span>

 <span data-ttu-id="240b8-111">**cValues**</span><span class="sxs-lookup"><span data-stu-id="240b8-111">**cValues**</span></span>
  
> <span data-ttu-id="240b8-112">属性数组由**aulPropTag**成员中的标记的计数。</span><span class="sxs-lookup"><span data-stu-id="240b8-112">Count of property tags in the array indicated by the **aulPropTag** member.</span></span> 
    
 <span data-ttu-id="240b8-113">**aulPropTag**</span><span class="sxs-lookup"><span data-stu-id="240b8-113">**aulPropTag**</span></span>
  
> <span data-ttu-id="240b8-114">属性标记的数组。</span><span class="sxs-lookup"><span data-stu-id="240b8-114">Array of property tags.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="240b8-115">备注</span><span class="sxs-lookup"><span data-stu-id="240b8-115">Remarks</span></span>

<span data-ttu-id="240b8-116">属性标记是一个 32 位无符号的整数，由两部分组成：</span><span class="sxs-lookup"><span data-stu-id="240b8-116">A property tag is a 32-bit unsigned integer that consists of two parts:</span></span> 
  
- <span data-ttu-id="240b8-117">中高阶 16 位的标识符。</span><span class="sxs-lookup"><span data-stu-id="240b8-117">An identifier in the high-order 16 bits.</span></span>
    
- <span data-ttu-id="240b8-118">低序位 16 位中的类型。</span><span class="sxs-lookup"><span data-stu-id="240b8-118">A type in the low-order 16 bits.</span></span>
    
<span data-ttu-id="240b8-119">标识符是一个数值在特定范围内。</span><span class="sxs-lookup"><span data-stu-id="240b8-119">The identifier is a numeric value in a particular range.</span></span> <span data-ttu-id="240b8-120">MAPI 定义标识符来描述属性用于和谁负责维护它的区域。</span><span class="sxs-lookup"><span data-stu-id="240b8-120">MAPI defines ranges for identifiers to describe what the property is used for and who is responsible for maintaining it.</span></span> <span data-ttu-id="240b8-121">MAPI 属性标记它 Mapitags.h 头文件中所支持的每个定义的约束。</span><span class="sxs-lookup"><span data-stu-id="240b8-121">MAPI defines constraints for each of the property tags that it supports in the Mapitags.h header file.</span></span>
  
<span data-ttu-id="240b8-122">该类型指示该属性的值的格式。</span><span class="sxs-lookup"><span data-stu-id="240b8-122">The type indicates the format for the property's value.</span></span> <span data-ttu-id="240b8-123">MAPI 的属性类型，它支持 Mapidefs.h 头文件中的每个定义的常数。</span><span class="sxs-lookup"><span data-stu-id="240b8-123">MAPI defines constants for each of the property types that it supports in the Mapidefs.h header file.</span></span> 
  
<span data-ttu-id="240b8-124">有关属性标记及其组件的详细信息，请参阅以下主题之一：</span><span class="sxs-lookup"><span data-stu-id="240b8-124">For more information about property tags and their components, see one of the following topics:</span></span> 
  
[<span data-ttu-id="240b8-125">MAPI 属性标记</span><span class="sxs-lookup"><span data-stu-id="240b8-125">MAPI Property Tags</span></span>](mapi-property-tags.md)
  
[<span data-ttu-id="240b8-126">MAPI 属性标识符概述</span><span class="sxs-lookup"><span data-stu-id="240b8-126">MAPI Property Identifier Overview</span></span>](mapi-property-identifier-overview.md)
  
[<span data-ttu-id="240b8-127">MAPI 属性类型概述</span><span class="sxs-lookup"><span data-stu-id="240b8-127">MAPI Property Type Overview</span></span>](mapi-property-type-overview.md)
  
<span data-ttu-id="240b8-128">单值和多值属性类型的完整列表，请参阅附录[属性标识符和类型](property-identifiers-and-types.md)。</span><span class="sxs-lookup"><span data-stu-id="240b8-128">For a complete list of the single-valued and multi-valued property types, see the appendix, [Property Identifiers and Types](property-identifiers-and-types.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="240b8-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="240b8-129">See also</span></span>



[<span data-ttu-id="240b8-130">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="240b8-130">MAPI Structures</span></span>](mapi-structures.md)

