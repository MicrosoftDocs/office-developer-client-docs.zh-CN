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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430698"
---
# <a name="sproptagarray"></a><span data-ttu-id="441cd-103">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="441cd-103">SPropTagArray</span></span>

  
  
<span data-ttu-id="441cd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="441cd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="441cd-105">包含属性标记的数组。</span><span class="sxs-lookup"><span data-stu-id="441cd-105">Contains an array of property tags.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="441cd-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="441cd-106">Header file:</span></span>  <br/> |<span data-ttu-id="441cd-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="441cd-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="441cd-108">相关宏：</span><span class="sxs-lookup"><span data-stu-id="441cd-108">Related macros:</span></span>  <br/> |<span data-ttu-id="441cd-109">[](cbnewsproptagarray.md)CbNewSPropTagArray、CbSPropTagArray、SizedSPropTagArray [](cbsproptagarray.md) [](sizedsproptagarray.md)</span><span class="sxs-lookup"><span data-stu-id="441cd-109">[CbNewSPropTagArray](cbnewsproptagarray.md), [CbSPropTagArray](cbsproptagarray.md), [SizedSPropTagArray](sizedsproptagarray.md)</span></span> <br/> |
   
```cpp
typedef struct _SPropTagArray
{
  ULONG cValues;
  ULONG aulPropTag[MAPI_DIM];
} SPropTagArray, FAR *LPSPropTagArray;

```

## <a name="members"></a><span data-ttu-id="441cd-110">Members</span><span class="sxs-lookup"><span data-stu-id="441cd-110">Members</span></span>

 <span data-ttu-id="441cd-111">**cValues**</span><span class="sxs-lookup"><span data-stu-id="441cd-111">**cValues**</span></span>
  
> <span data-ttu-id="441cd-112">由 **aulPropTag** 成员指示的数组中的属性标记计数。</span><span class="sxs-lookup"><span data-stu-id="441cd-112">Count of property tags in the array indicated by the **aulPropTag** member.</span></span> 
    
 <span data-ttu-id="441cd-113">**aulPropTag**</span><span class="sxs-lookup"><span data-stu-id="441cd-113">**aulPropTag**</span></span>
  
> <span data-ttu-id="441cd-114">属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="441cd-114">Array of property tags.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="441cd-115">备注</span><span class="sxs-lookup"><span data-stu-id="441cd-115">Remarks</span></span>

<span data-ttu-id="441cd-116">属性标记是一个 32 位无符号整数，由两部分组成：</span><span class="sxs-lookup"><span data-stu-id="441cd-116">A property tag is a 32-bit unsigned integer that consists of two parts:</span></span> 
  
- <span data-ttu-id="441cd-117">高顺序 16 位中的标识符。</span><span class="sxs-lookup"><span data-stu-id="441cd-117">An identifier in the high-order 16 bits.</span></span>
    
- <span data-ttu-id="441cd-118">低顺序 16 位中的类型。</span><span class="sxs-lookup"><span data-stu-id="441cd-118">A type in the low-order 16 bits.</span></span>
    
<span data-ttu-id="441cd-119">标识符是特定范围中的数值。</span><span class="sxs-lookup"><span data-stu-id="441cd-119">The identifier is a numeric value in a particular range.</span></span> <span data-ttu-id="441cd-120">MAPI 为标识符定义范围，以描述属性用于什么以及谁负责维护它。</span><span class="sxs-lookup"><span data-stu-id="441cd-120">MAPI defines ranges for identifiers to describe what the property is used for and who is responsible for maintaining it.</span></span> <span data-ttu-id="441cd-121">MAPI 为 Mapitags.h 头文件中支持的每个属性标记定义约束。</span><span class="sxs-lookup"><span data-stu-id="441cd-121">MAPI defines constraints for each of the property tags that it supports in the Mapitags.h header file.</span></span>
  
<span data-ttu-id="441cd-122">类型指示属性值的格式。</span><span class="sxs-lookup"><span data-stu-id="441cd-122">The type indicates the format for the property's value.</span></span> <span data-ttu-id="441cd-123">MAPI 为 Mapidefs.h 头文件中支持的每个属性类型定义常量。</span><span class="sxs-lookup"><span data-stu-id="441cd-123">MAPI defines constants for each of the property types that it supports in the Mapidefs.h header file.</span></span> 
  
<span data-ttu-id="441cd-124">有关属性标记及其组件的信息，请参阅下列主题之一：</span><span class="sxs-lookup"><span data-stu-id="441cd-124">For more information about property tags and their components, see one of the following topics:</span></span> 
  
[<span data-ttu-id="441cd-125">MAPI 属性标记</span><span class="sxs-lookup"><span data-stu-id="441cd-125">MAPI Property Tags</span></span>](mapi-property-tags.md)
  
[<span data-ttu-id="441cd-126">MAPI 属性标识符概述</span><span class="sxs-lookup"><span data-stu-id="441cd-126">MAPI Property Identifier Overview</span></span>](mapi-property-identifier-overview.md)
  
[<span data-ttu-id="441cd-127">MAPI 属性类型概述</span><span class="sxs-lookup"><span data-stu-id="441cd-127">MAPI Property Type Overview</span></span>](mapi-property-type-overview.md)
  
<span data-ttu-id="441cd-128">有关单值和多值属性类型的完整列表，请参阅附录属性 [标识符和类型](property-identifiers-and-types.md)。</span><span class="sxs-lookup"><span data-stu-id="441cd-128">For a complete list of the single-valued and multi-valued property types, see the appendix, [Property Identifiers and Types](property-identifiers-and-types.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="441cd-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="441cd-129">See also</span></span>



[<span data-ttu-id="441cd-130">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="441cd-130">MAPI Structures</span></span>](mapi-structures.md)

