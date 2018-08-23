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
ms.openlocfilehash: adccbaf65adec2c517c4890f722198e8262092cb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564603"
---
# <a name="fpropcompareprop"></a><span data-ttu-id="ae5b1-103">FPropCompareProp</span><span class="sxs-lookup"><span data-stu-id="ae5b1-103">FPropCompareProp</span></span>

<span data-ttu-id="ae5b1-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ae5b1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ae5b1-105">将使用指定的关系运算符的两个属性值进行比较。</span><span class="sxs-lookup"><span data-stu-id="ae5b1-105">Compares two property values using a specified relational operator.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ae5b1-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="ae5b1-106">Header file:</span></span>  <br/> |<span data-ttu-id="ae5b1-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="ae5b1-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="ae5b1-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="ae5b1-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="ae5b1-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="ae5b1-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="ae5b1-110">调用：</span><span class="sxs-lookup"><span data-stu-id="ae5b1-110">Called by:</span></span>  <br/> |<span data-ttu-id="ae5b1-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="ae5b1-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
BOOL FPropCompareProp(
  LPSPropValue lpSPropValue1,
  ULONG ulRelOp,
  LPSPropValue lpSPropValue2
);
```

## <a name="parameters"></a><span data-ttu-id="ae5b1-112">参数</span><span class="sxs-lookup"><span data-stu-id="ae5b1-112">Parameters</span></span>

<span data-ttu-id="ae5b1-113">_lpSPropValue1_</span><span class="sxs-lookup"><span data-stu-id="ae5b1-113">_lpSPropValue1_</span></span>
  
> <span data-ttu-id="ae5b1-114">[in]定义用于比较的第一个属性值[SPropValue](spropvalue.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="ae5b1-114">[in] Pointer to an [SPropValue](spropvalue.md) structure defining the first property value for comparison.</span></span> 
    
<span data-ttu-id="ae5b1-115">_ulRelOp_</span><span class="sxs-lookup"><span data-stu-id="ae5b1-115">_ulRelOp_</span></span>
  
> <span data-ttu-id="ae5b1-116">[in]用于比较关系运算符。</span><span class="sxs-lookup"><span data-stu-id="ae5b1-116">[in] The relational operator to use in the comparison.</span></span> <span data-ttu-id="ae5b1-117">允许的值，请参阅[SComparePropsRestriction](scomparepropsrestriction.md)结构。</span><span class="sxs-lookup"><span data-stu-id="ae5b1-117">For allowable values, see the [SComparePropsRestriction](scomparepropsrestriction.md) structure.</span></span> 
    
<span data-ttu-id="ae5b1-118">_lpSPropValue2_</span><span class="sxs-lookup"><span data-stu-id="ae5b1-118">_lpSPropValue2_</span></span>
  
> <span data-ttu-id="ae5b1-119">[in]定义用于比较的第二个属性值**SPropValue**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="ae5b1-119">[in] Pointer to an **SPropValue** structure defining the second property value for comparison.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="ae5b1-120">返回值</span><span class="sxs-lookup"><span data-stu-id="ae5b1-120">Return value</span></span>

<span data-ttu-id="ae5b1-121">TRUE</span><span class="sxs-lookup"><span data-stu-id="ae5b1-121">TRUE</span></span> 
  
> <span data-ttu-id="ae5b1-122">属性值满足指定的关系。</span><span class="sxs-lookup"><span data-stu-id="ae5b1-122">The property values satisfy the specified relation.</span></span> 
    
<span data-ttu-id="ae5b1-123">FALSE</span><span class="sxs-lookup"><span data-stu-id="ae5b1-123">FALSE</span></span> 
  
> <span data-ttu-id="ae5b1-124">属性值不满足指定的关系。</span><span class="sxs-lookup"><span data-stu-id="ae5b1-124">The property values do not satisfy the specified relation.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ae5b1-125">注解</span><span class="sxs-lookup"><span data-stu-id="ae5b1-125">Remarks</span></span>

<span data-ttu-id="ae5b1-126">比较方法取决于[SPropValue](spropvalue.md)属性定义中指定的属性类型。</span><span class="sxs-lookup"><span data-stu-id="ae5b1-126">The comparison method depends on the property types specified in the [SPropValue](spropvalue.md) property definitions.</span></span> <span data-ttu-id="ae5b1-127">**FPropCompareProp**和[FPropContainsProp](fpropcontainsprop.md)函数可以用于准备用于生成表的限制。</span><span class="sxs-lookup"><span data-stu-id="ae5b1-127">The **FPropCompareProp** and [FPropContainsProp](fpropcontainsprop.md) functions can be used to prepare restrictions for generating a table.</span></span> 
  
<span data-ttu-id="ae5b1-128">_LpSPropValue1_、 _ ulRelOp _、 _ lpSPropValue2 _ 的比较的顺序。</span><span class="sxs-lookup"><span data-stu-id="ae5b1-128">The order of comparison is  _lpSPropValue1_, _ ulRelOp _, _ lpSPropValue2 _.</span></span> <span data-ttu-id="ae5b1-129">如果进行比较的属性值的属性类型不匹配，则**FPropCompareProp**函数将返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="ae5b1-129">If the property types of the property values to be compared do not match, the **FPropCompareProp** function returns FALSE.</span></span> 
  

