---
title: LPropCompareProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.LPropCompareProp
api_type:
- COM
ms.assetid: f14ad568-fe45-4875-957d-415d39dc6f28
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: d214cb5d449e2f7e42e7ee72774fdc146495adb4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776168"
---
# <a name="lpropcompareprop"></a><span data-ttu-id="c71e5-103">LPropCompareProp</span><span class="sxs-lookup"><span data-stu-id="c71e5-103">LPropCompareProp</span></span>

  
  
<span data-ttu-id="c71e5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c71e5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c71e5-105">比较两个属性值来确定它们是否相等。</span><span class="sxs-lookup"><span data-stu-id="c71e5-105">Compares two property values to determine whether they are equal.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c71e5-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="c71e5-106">Header file:</span></span>  <br/> |<span data-ttu-id="c71e5-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="c71e5-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="c71e5-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="c71e5-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="c71e5-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="c71e5-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="c71e5-110">调用：</span><span class="sxs-lookup"><span data-stu-id="c71e5-110">Called by:</span></span>  <br/> |<span data-ttu-id="c71e5-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="c71e5-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
LONG LPropCompareProp(
  LPSPropValue lpSPropValueA,
  LPSPropValue lpSPropValueB
);
```

## <a name="parameters"></a><span data-ttu-id="c71e5-112">参数</span><span class="sxs-lookup"><span data-stu-id="c71e5-112">Parameters</span></span>

 <span data-ttu-id="c71e5-113">_lpSPropValueA_</span><span class="sxs-lookup"><span data-stu-id="c71e5-113">_lpSPropValueA_</span></span>
  
> <span data-ttu-id="c71e5-114">[in]指向[SPropValue](spropvalue.md)结构定义要进行比较的第一个属性值的指针。</span><span class="sxs-lookup"><span data-stu-id="c71e5-114">[in] Pointer to an [SPropValue](spropvalue.md) structure defining the first property value to be compared.</span></span> 
    
 <span data-ttu-id="c71e5-115">_lpSPropValueB_</span><span class="sxs-lookup"><span data-stu-id="c71e5-115">_lpSPropValueB_</span></span>
  
> <span data-ttu-id="c71e5-116">[in]指向**SPropValue**结构定义要进行比较的第二个属性值的指针。</span><span class="sxs-lookup"><span data-stu-id="c71e5-116">[in] Pointer to an **SPropValue** structure defining the second property value to be compared.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="c71e5-117">返回值</span><span class="sxs-lookup"><span data-stu-id="c71e5-117">Return value</span></span>

 <span data-ttu-id="c71e5-118">**LPropCompareProp**返回大多数属性类型的下列值之一：</span><span class="sxs-lookup"><span data-stu-id="c71e5-118">**LPropCompareProp** returns one of the following values for most property types:</span></span> 
  
- <span data-ttu-id="c71e5-119">小于零值由_lpSPropValueA_参数小于的_lpSPropValueB_参数指示。</span><span class="sxs-lookup"><span data-stu-id="c71e5-119">Less than zero if the value indicated by the  _lpSPropValueA_ parameter is less than that indicated by the  _lpSPropValueB_ parameter.</span></span> 
    
- <span data-ttu-id="c71e5-120">大于零，如果值由_lpSPropValueA_为大于由_lpSPropValueB_。</span><span class="sxs-lookup"><span data-stu-id="c71e5-120">Greater than zero if the value indicated by  _lpSPropValueA_ is greater than that indicated by  _lpSPropValueB_.</span></span>
    
- <span data-ttu-id="c71e5-121">零，如果值由_lpSPropValueA_等于指示_lpSPropValueB_的值。</span><span class="sxs-lookup"><span data-stu-id="c71e5-121">Zero if the value indicated by  _lpSPropValueA_ equals the value indicated by  _lpSPropValueB_.</span></span> 
    
<span data-ttu-id="c71e5-122">对于具有任何固有排序，如布尔值的属性类型或错误类型， **LPropCompareProp**函数返回未定义的值，如果两个属性值不相等。</span><span class="sxs-lookup"><span data-stu-id="c71e5-122">For property types that have no intrinsic ordering, such as Boolean or error types, the **LPropCompareProp** function returns an undefined value if the two property values are not equal.</span></span> <span data-ttu-id="c71e5-123">未定义的该值是跨呼叫非零值和一致。</span><span class="sxs-lookup"><span data-stu-id="c71e5-123">This undefined value is nonzero and consistent across calls.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="c71e5-124">备注</span><span class="sxs-lookup"><span data-stu-id="c71e5-124">Remarks</span></span>

<span data-ttu-id="c71e5-125">仅当要进行比较的两个属性的类型都是相同，请使用**LPropCompareProp**函数。</span><span class="sxs-lookup"><span data-stu-id="c71e5-125">Use the **LPropCompareProp** function only if the types of the two properties to be compared are the same.</span></span> 
  
<span data-ttu-id="c71e5-126">调用之前**LPropCompareProp**，客户端应用程序或服务提供商必须先检索对[IMAPIProp::GetProps](imapiprop-getprops.md)方法的调用与比较的属性。</span><span class="sxs-lookup"><span data-stu-id="c71e5-126">Before calling **LPropCompareProp**, a client application or service provider must first retrieve the properties for comparison with a call to the [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> <span data-ttu-id="c71e5-127">客户端或提供程序的调用**LPropCompareProp**，该函数首先检查属性标记以确保属性值的比较结果时有效。</span><span class="sxs-lookup"><span data-stu-id="c71e5-127">When a client or provider calls **LPropCompareProp**, the function first examines the property tags to make sure that the comparison of property values is valid.</span></span> <span data-ttu-id="c71e5-128">然后，该函数比较返回相应值的属性值。</span><span class="sxs-lookup"><span data-stu-id="c71e5-128">The function then compares the property values, returning an appropriate value.</span></span> 
  
<span data-ttu-id="c71e5-129">如果属性值不相等， **LPropCompareProp**确定哪一种更高版本。</span><span class="sxs-lookup"><span data-stu-id="c71e5-129">If the property values are unequal, **LPropCompareProp** determines which one is the greater.</span></span> <span data-ttu-id="c71e5-130">**LPropCompareProp**比较的属性没有属于相同的对象。</span><span class="sxs-lookup"><span data-stu-id="c71e5-130">The properties that **LPropCompareProp** compares do not have to belong to the same object.</span></span> 
  

