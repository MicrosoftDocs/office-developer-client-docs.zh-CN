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
ms.openlocfilehash: 7726811467324242037ec11a69ae0b1b123d7f21
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427155"
---
# <a name="fpropcompareprop"></a><span data-ttu-id="b464f-103">FPropCompareProp</span><span class="sxs-lookup"><span data-stu-id="b464f-103">FPropCompareProp</span></span>

<span data-ttu-id="b464f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b464f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b464f-105">使用指定的关系运算符比较两个属性值。</span><span class="sxs-lookup"><span data-stu-id="b464f-105">Compares two property values using a specified relational operator.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b464f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="b464f-106">Header file:</span></span>  <br/> |<span data-ttu-id="b464f-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="b464f-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="b464f-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="b464f-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="b464f-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="b464f-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="b464f-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="b464f-110">Called by:</span></span>  <br/> |<span data-ttu-id="b464f-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="b464f-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
BOOL FPropCompareProp(
  LPSPropValue lpSPropValue1,
  ULONG ulRelOp,
  LPSPropValue lpSPropValue2
);
```

## <a name="parameters"></a><span data-ttu-id="b464f-112">参数</span><span class="sxs-lookup"><span data-stu-id="b464f-112">Parameters</span></span>

<span data-ttu-id="b464f-113">_lpSPropValue1_</span><span class="sxs-lookup"><span data-stu-id="b464f-113">_lpSPropValue1_</span></span>
  
> <span data-ttu-id="b464f-114">实时指向定义要比较的第一个属性值的[SPropValue](spropvalue.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="b464f-114">[in] Pointer to an [SPropValue](spropvalue.md) structure defining the first property value for comparison.</span></span> 
    
<span data-ttu-id="b464f-115">_ulRelOp_</span><span class="sxs-lookup"><span data-stu-id="b464f-115">_ulRelOp_</span></span>
  
> <span data-ttu-id="b464f-116">实时要在比较中使用的关系运算符。</span><span class="sxs-lookup"><span data-stu-id="b464f-116">[in] The relational operator to use in the comparison.</span></span> <span data-ttu-id="b464f-117">有关允许的值, 请参阅[SComparePropsRestriction](scomparepropsrestriction.md)结构。</span><span class="sxs-lookup"><span data-stu-id="b464f-117">For allowable values, see the [SComparePropsRestriction](scomparepropsrestriction.md) structure.</span></span> 
    
<span data-ttu-id="b464f-118">_lpSPropValue2_</span><span class="sxs-lookup"><span data-stu-id="b464f-118">_lpSPropValue2_</span></span>
  
> <span data-ttu-id="b464f-119">实时指向定义比较的第二个属性值的**SPropValue**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="b464f-119">[in] Pointer to an **SPropValue** structure defining the second property value for comparison.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="b464f-120">返回值</span><span class="sxs-lookup"><span data-stu-id="b464f-120">Return value</span></span>

<span data-ttu-id="b464f-121">TRUE</span><span class="sxs-lookup"><span data-stu-id="b464f-121">TRUE</span></span> 
  
> <span data-ttu-id="b464f-122">属性值满足指定的关系。</span><span class="sxs-lookup"><span data-stu-id="b464f-122">The property values satisfy the specified relation.</span></span> 
    
<span data-ttu-id="b464f-123">FALSE</span><span class="sxs-lookup"><span data-stu-id="b464f-123">FALSE</span></span> 
  
> <span data-ttu-id="b464f-124">属性值不满足指定的关系。</span><span class="sxs-lookup"><span data-stu-id="b464f-124">The property values do not satisfy the specified relation.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b464f-125">说明</span><span class="sxs-lookup"><span data-stu-id="b464f-125">Remarks</span></span>

<span data-ttu-id="b464f-126">比较方法取决于在[SPropValue](spropvalue.md)属性定义中指定的属性类型。</span><span class="sxs-lookup"><span data-stu-id="b464f-126">The comparison method depends on the property types specified in the [SPropValue](spropvalue.md) property definitions.</span></span> <span data-ttu-id="b464f-127">**FPropCompareProp**和[FPropContainsProp](fpropcontainsprop.md)函数可用于准备生成表的限制。</span><span class="sxs-lookup"><span data-stu-id="b464f-127">The **FPropCompareProp** and [FPropContainsProp](fpropcontainsprop.md) functions can be used to prepare restrictions for generating a table.</span></span> 
  
<span data-ttu-id="b464f-128">比较的顺序为_lpSPropValue1_、_ ulRelOp _、_ lpSPropValue2 _。</span><span class="sxs-lookup"><span data-stu-id="b464f-128">The order of comparison is  _lpSPropValue1_, _ ulRelOp _, _ lpSPropValue2 _.</span></span> <span data-ttu-id="b464f-129">如果要比较的属性值的属性类型不匹配, 则**FPropCompareProp**函数将返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="b464f-129">If the property types of the property values to be compared do not match, the **FPropCompareProp** function returns FALSE.</span></span> 
  

