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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7417ddeb814cafb954d5ab80a6dae771fd0f7a79
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414611"
---
# <a name="lpropcompareprop"></a><span data-ttu-id="a2d36-103">LPropCompareProp</span><span class="sxs-lookup"><span data-stu-id="a2d36-103">LPropCompareProp</span></span>

  
  
<span data-ttu-id="a2d36-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a2d36-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a2d36-105">对两个属性值进行比较, 以确定它们是否相等。</span><span class="sxs-lookup"><span data-stu-id="a2d36-105">Compares two property values to determine whether they are equal.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a2d36-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="a2d36-106">Header file:</span></span>  <br/> |<span data-ttu-id="a2d36-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="a2d36-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="a2d36-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="a2d36-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="a2d36-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="a2d36-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="a2d36-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="a2d36-110">Called by:</span></span>  <br/> |<span data-ttu-id="a2d36-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="a2d36-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
LONG LPropCompareProp(
  LPSPropValue lpSPropValueA,
  LPSPropValue lpSPropValueB
);
```

## <a name="parameters"></a><span data-ttu-id="a2d36-112">参数</span><span class="sxs-lookup"><span data-stu-id="a2d36-112">Parameters</span></span>

 <span data-ttu-id="a2d36-113">_lpSPropValueA_</span><span class="sxs-lookup"><span data-stu-id="a2d36-113">_lpSPropValueA_</span></span>
  
> <span data-ttu-id="a2d36-114">实时指向一个[SPropValue](spropvalue.md)结构的指针, 该结构定义要比较的第一个属性值。</span><span class="sxs-lookup"><span data-stu-id="a2d36-114">[in] Pointer to an [SPropValue](spropvalue.md) structure defining the first property value to be compared.</span></span> 
    
 <span data-ttu-id="a2d36-115">_lpSPropValueB_</span><span class="sxs-lookup"><span data-stu-id="a2d36-115">_lpSPropValueB_</span></span>
  
> <span data-ttu-id="a2d36-116">实时指向一个**SPropValue**结构的指针, 该结构定义要比较的第二个属性值。</span><span class="sxs-lookup"><span data-stu-id="a2d36-116">[in] Pointer to an **SPropValue** structure defining the second property value to be compared.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a2d36-117">返回值</span><span class="sxs-lookup"><span data-stu-id="a2d36-117">Return value</span></span>

 <span data-ttu-id="a2d36-118">对于大多数属性类型, **LPropCompareProp**返回以下值之一:</span><span class="sxs-lookup"><span data-stu-id="a2d36-118">**LPropCompareProp** returns one of the following values for most property types:</span></span> 
  
- <span data-ttu-id="a2d36-119">如果_lpSPropValueA_参数指示的值小于_lpSPropValueB_参数所指定的值, 则小于零。</span><span class="sxs-lookup"><span data-stu-id="a2d36-119">Less than zero if the value indicated by the  _lpSPropValueA_ parameter is less than that indicated by the  _lpSPropValueB_ parameter.</span></span> 
    
- <span data-ttu-id="a2d36-120">如果_lpSPropValueA_指示的值大于_lpSPropValueB_所指示的值, 则大于零。</span><span class="sxs-lookup"><span data-stu-id="a2d36-120">Greater than zero if the value indicated by  _lpSPropValueA_ is greater than that indicated by  _lpSPropValueB_.</span></span>
    
- <span data-ttu-id="a2d36-121">如果_lpSPropValueA_指示的值等于_lpSPropValueB_指示的值, 则为零。</span><span class="sxs-lookup"><span data-stu-id="a2d36-121">Zero if the value indicated by  _lpSPropValueA_ equals the value indicated by  _lpSPropValueB_.</span></span> 
    
<span data-ttu-id="a2d36-122">对于没有内在排序的属性类型 (如 Boolean 或错误类型), 如果两个属性值不相等, **LPropCompareProp**函数将返回一个未定义的值。</span><span class="sxs-lookup"><span data-stu-id="a2d36-122">For property types that have no intrinsic ordering, such as Boolean or error types, the **LPropCompareProp** function returns an undefined value if the two property values are not equal.</span></span> <span data-ttu-id="a2d36-123">此未定义的值在各个调用中是非零和一致的。</span><span class="sxs-lookup"><span data-stu-id="a2d36-123">This undefined value is nonzero and consistent across calls.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="a2d36-124">说明</span><span class="sxs-lookup"><span data-stu-id="a2d36-124">Remarks</span></span>

<span data-ttu-id="a2d36-125">仅当要比较的两个属性的类型相同时, 才使用**LPropCompareProp**函数。</span><span class="sxs-lookup"><span data-stu-id="a2d36-125">Use the **LPropCompareProp** function only if the types of the two properties to be compared are the same.</span></span> 
  
<span data-ttu-id="a2d36-126">在调用**LPropCompareProp**之前, 客户端应用程序或服务提供程序必须先检索属性以与对[IMAPIProp:: GetProps](imapiprop-getprops.md)方法的调用进行比较。</span><span class="sxs-lookup"><span data-stu-id="a2d36-126">Before calling **LPropCompareProp**, a client application or service provider must first retrieve the properties for comparison with a call to the [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> <span data-ttu-id="a2d36-127">当客户端或提供程序调用**LPropCompareProp**时, 该函数将首先检查属性标记, 以确保属性值的比较有效。</span><span class="sxs-lookup"><span data-stu-id="a2d36-127">When a client or provider calls **LPropCompareProp**, the function first examines the property tags to make sure that the comparison of property values is valid.</span></span> <span data-ttu-id="a2d36-128">然后, 该函数将比较属性值, 并返回适当的值。</span><span class="sxs-lookup"><span data-stu-id="a2d36-128">The function then compares the property values, returning an appropriate value.</span></span> 
  
<span data-ttu-id="a2d36-129">如果属性值不相等, **LPropCompareProp**将确定哪一个是较大的值。</span><span class="sxs-lookup"><span data-stu-id="a2d36-129">If the property values are unequal, **LPropCompareProp** determines which one is the greater.</span></span> <span data-ttu-id="a2d36-130">**LPropCompareProp**比较的属性不必属于同一个对象。</span><span class="sxs-lookup"><span data-stu-id="a2d36-130">The properties that **LPropCompareProp** compares do not have to belong to the same object.</span></span> 
  

