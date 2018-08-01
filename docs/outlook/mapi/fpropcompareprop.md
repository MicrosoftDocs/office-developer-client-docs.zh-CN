---
title: FPropCompareProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FPropCompareProp
api_type:
- COM
ms.assetid: 17cb53c4-7154-4a4e-b4ec-de720fa055cb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 69bbed644a8173bf9291ca48a63960f693108318
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774985"
---
# <a name="fpropcompareprop"></a><span data-ttu-id="bb6c2-103">FPropCompareProp</span><span class="sxs-lookup"><span data-stu-id="bb6c2-103">FPropCompareProp</span></span>

<span data-ttu-id="bb6c2-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="bb6c2-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="bb6c2-105">将使用指定的关系运算符的两个属性值进行比较。</span><span class="sxs-lookup"><span data-stu-id="bb6c2-105">Compares two property values using a specified relational operator.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="bb6c2-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="bb6c2-106">Header file:</span></span>  <br/> |<span data-ttu-id="bb6c2-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="bb6c2-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="bb6c2-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="bb6c2-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="bb6c2-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="bb6c2-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="bb6c2-110">调用：</span><span class="sxs-lookup"><span data-stu-id="bb6c2-110">Called by:</span></span>  <br/> |<span data-ttu-id="bb6c2-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="bb6c2-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
BOOL FPropCompareProp(
  LPSPropValue lpSPropValue1,
  ULONG ulRelOp,
  LPSPropValue lpSPropValue2
);
```

## <a name="parameters"></a><span data-ttu-id="bb6c2-112">参数</span><span class="sxs-lookup"><span data-stu-id="bb6c2-112">Parameters</span></span>

<span data-ttu-id="bb6c2-113">_lpSPropValue1_</span><span class="sxs-lookup"><span data-stu-id="bb6c2-113">_lpSPropValue1_</span></span>
  
> <span data-ttu-id="bb6c2-114">[in]定义用于比较的第一个属性值[SPropValue](spropvalue.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="bb6c2-114">[in] Pointer to an [SPropValue](spropvalue.md) structure defining the first property value for comparison.</span></span> 
    
<span data-ttu-id="bb6c2-115">_ulRelOp_</span><span class="sxs-lookup"><span data-stu-id="bb6c2-115">_ulRelOp_</span></span>
  
> <span data-ttu-id="bb6c2-116">[in]用于比较关系运算符。</span><span class="sxs-lookup"><span data-stu-id="bb6c2-116">[in] The relational operator to use in the comparison.</span></span> <span data-ttu-id="bb6c2-117">允许的值，请参阅[SComparePropsRestriction](scomparepropsrestriction.md)结构。</span><span class="sxs-lookup"><span data-stu-id="bb6c2-117">For allowable values, see the [SComparePropsRestriction](scomparepropsrestriction.md) structure.</span></span> 
    
<span data-ttu-id="bb6c2-118">_lpSPropValue2_</span><span class="sxs-lookup"><span data-stu-id="bb6c2-118">_lpSPropValue2_</span></span>
  
> <span data-ttu-id="bb6c2-119">[in]定义用于比较的第二个属性值**SPropValue**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="bb6c2-119">[in] Pointer to an **SPropValue** structure defining the second property value for comparison.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="bb6c2-120">返回值</span><span class="sxs-lookup"><span data-stu-id="bb6c2-120">Return value</span></span>

<span data-ttu-id="bb6c2-121">TRUE</span><span class="sxs-lookup"><span data-stu-id="bb6c2-121">TRUE</span></span> 
  
> <span data-ttu-id="bb6c2-122">属性值满足指定的关系。</span><span class="sxs-lookup"><span data-stu-id="bb6c2-122">The property values satisfy the specified relation.</span></span> 
    
<span data-ttu-id="bb6c2-123">FALSE</span><span class="sxs-lookup"><span data-stu-id="bb6c2-123">FALSE</span></span> 
  
> <span data-ttu-id="bb6c2-124">属性值不满足指定的关系。</span><span class="sxs-lookup"><span data-stu-id="bb6c2-124">The property values do not satisfy the specified relation.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="bb6c2-125">说明</span><span class="sxs-lookup"><span data-stu-id="bb6c2-125">Remarks</span></span>

<span data-ttu-id="bb6c2-126">比较方法取决于[SPropValue](spropvalue.md)属性定义中指定的属性类型。</span><span class="sxs-lookup"><span data-stu-id="bb6c2-126">The comparison method depends on the property types specified in the [SPropValue](spropvalue.md) property definitions.</span></span> <span data-ttu-id="bb6c2-127">**FPropCompareProp**和[FPropContainsProp](fpropcontainsprop.md)函数可以用于准备用于生成表的限制。</span><span class="sxs-lookup"><span data-stu-id="bb6c2-127">The **FPropCompareProp** and [FPropContainsProp](fpropcontainsprop.md) functions can be used to prepare restrictions for generating a table.</span></span> 
  
<span data-ttu-id="bb6c2-128">_LpSPropValue1_、 _ ulRelOp _、 _ lpSPropValue2 _ 的比较的顺序。</span><span class="sxs-lookup"><span data-stu-id="bb6c2-128">The order of comparison is  _lpSPropValue1_, _ ulRelOp _, _ lpSPropValue2 _.</span></span> <span data-ttu-id="bb6c2-129">如果进行比较的属性值的属性类型不匹配，则**FPropCompareProp**函数将返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="bb6c2-129">If the property types of the property values to be compared do not match, the **FPropCompareProp** function returns FALSE.</span></span> 
  

