---
title: FPropContainsProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FPropContainsProp
api_type:
- COM
ms.assetid: 43da5b59-7691-49aa-b83c-753d43bfd8fd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ea56996ad56bb4ce93d103a75eba2c29e6059a87
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328040"
---
# <a name="fpropcontainsprop"></a><span data-ttu-id="24e6f-103">FPropContainsProp</span><span class="sxs-lookup"><span data-stu-id="24e6f-103">FPropContainsProp</span></span>

<span data-ttu-id="24e6f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="24e6f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="24e6f-105">比较两个属性值 (通常为字符串或二进制数组), 以查看是否有一个属性值包含另一个。</span><span class="sxs-lookup"><span data-stu-id="24e6f-105">Compares two property values, generally strings or binary arrays, to see if one contains the other.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="24e6f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="24e6f-106">Header file:</span></span>  <br/> |<span data-ttu-id="24e6f-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="24e6f-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="24e6f-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="24e6f-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="24e6f-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="24e6f-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="24e6f-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="24e6f-110">Called by:</span></span>  <br/> |<span data-ttu-id="24e6f-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="24e6f-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
BOOL FPropContainsProp(
  LPSPropValue lpSPropValueDst,
  LPSPropValue lpSPropValueSrc,
  ULONG ulFuzzyLevel
);
```

## <a name="parameters"></a><span data-ttu-id="24e6f-112">参数</span><span class="sxs-lookup"><span data-stu-id="24e6f-112">Parameters</span></span>

<span data-ttu-id="24e6f-113">_lpSPropValueDst_</span><span class="sxs-lookup"><span data-stu-id="24e6f-113">_lpSPropValueDst_</span></span>
  
> <span data-ttu-id="24e6f-114">实时指向[SPropValue](spropvalue.md)结构的指针, 该结构定义可能包含由_lpSPropValueSrc_参数指向的搜索字符串的属性值。</span><span class="sxs-lookup"><span data-stu-id="24e6f-114">[in] Pointer to an [SPropValue](spropvalue.md) structure defining the property value that might contain the search string pointed to by the  _lpSPropValueSrc_ parameter.</span></span> 
    
<span data-ttu-id="24e6f-115">_lpSPropValueSrc_</span><span class="sxs-lookup"><span data-stu-id="24e6f-115">_lpSPropValueSrc_</span></span>
  
> <span data-ttu-id="24e6f-116">实时指向**SPropValue**结构的指针, 该结构定义**FPropContainsProp**在由_lpSPropValueDst_参数指向的属性值中查找的搜索字符串。</span><span class="sxs-lookup"><span data-stu-id="24e6f-116">[in] Pointer to an **SPropValue** structure defining the search string that **FPropContainsProp** is seeking in the property value pointed to by the  _lpSPropValueDst_ parameter.</span></span> 
    
<span data-ttu-id="24e6f-117">_ulFuzzyLevel_</span><span class="sxs-lookup"><span data-stu-id="24e6f-117">_ulFuzzyLevel_</span></span>
  
> <span data-ttu-id="24e6f-118">实时用于定义要在比较中使用的 preciseness 级别的选项设置。</span><span class="sxs-lookup"><span data-stu-id="24e6f-118">[in] Option settings defining the level of preciseness to use in the comparison.</span></span> 

  - <span data-ttu-id="24e6f-119">**较低的16位**适用于类型 PT_BINARY 和 PT_STRING8 的属性。</span><span class="sxs-lookup"><span data-stu-id="24e6f-119">The **lower 16 bits** apply to properties of type PT_BINARY and PT_STRING8.</span></span> <span data-ttu-id="24e6f-120">必须将它们完全设置为以下值之一:</span><span class="sxs-lookup"><span data-stu-id="24e6f-120">They must be set to exactly one of the following values:</span></span>
      
    - <span data-ttu-id="24e6f-121">FL_FULLSTRING: _lpSPropValueSrc_搜索字符串必须等于_lpSPropValueDst_标识的属性值。</span><span class="sxs-lookup"><span data-stu-id="24e6f-121">FL_FULLSTRING: The  _lpSPropValueSrc_ search string must be equal to the property value identified by  _lpSPropValueDst_.</span></span>
        
    - <span data-ttu-id="24e6f-122">FL_PREFIX: _lpSPropValueSrc_搜索字符串必须出现在_lpSPropValueDst_标识的属性值的开头。</span><span class="sxs-lookup"><span data-stu-id="24e6f-122">FL_PREFIX: The  _lpSPropValueSrc_ search string must appear at the beginning of the property value identified by  _lpSPropValueDst_.</span></span> <span data-ttu-id="24e6f-123">这两个值只应与_lpSPropValueSrc_指示的搜索字符串的长度进行比较。</span><span class="sxs-lookup"><span data-stu-id="24e6f-123">The two values should be compared only up to the length of the search string indicated by  _lpSPropValueSrc_.</span></span> 
        
    - <span data-ttu-id="24e6f-124">FL_SUBSTRING: _lpSPropValueSrc_搜索字符串必须包含在_lpSPropValueDst_标识的属性值中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="24e6f-124">FL_SUBSTRING: The  _lpSPropValueSrc_ search string must be contained anywhere in the property value identified by  _lpSPropValueDst_.</span></span> 
      
  - <span data-ttu-id="24e6f-125">**较高的16位**仅适用于 PT_STRING8 类型的属性。</span><span class="sxs-lookup"><span data-stu-id="24e6f-125">The **upper 16 bits** apply only to properties of type PT_STRING8.</span></span> <span data-ttu-id="24e6f-126">可以通过任意组合将它们设置为以下值:</span><span class="sxs-lookup"><span data-stu-id="24e6f-126">They can be set to the following values in any combination:</span></span>
    
    - <span data-ttu-id="24e6f-127">FL_IGNORECASE: 应进行比较, 而不考虑区分大小写。</span><span class="sxs-lookup"><span data-stu-id="24e6f-127">FL_IGNORECASE: The comparison should be made without considering case sensitivity.</span></span> 
        
    - <span data-ttu-id="24e6f-128">FL_IGNORENONSPACE: 比较操作应忽略 Unicode 定义的非空格字符, 如变音标记。</span><span class="sxs-lookup"><span data-stu-id="24e6f-128">FL_IGNORENONSPACE: The comparison should ignore Unicode-defined nonspacing characters such as diacritical marks.</span></span> 
        
    - <span data-ttu-id="24e6f-129">FL_LOOSE: 如果可能, 比较应指示匹配项, 忽略区分大小写和非空格字符。</span><span class="sxs-lookup"><span data-stu-id="24e6f-129">FL_LOOSE: The comparison should indicate a match whenever possible, ignoring case sensitivity and nonspacing characters.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="24e6f-130">返回值</span><span class="sxs-lookup"><span data-stu-id="24e6f-130">Return value</span></span>

<span data-ttu-id="24e6f-131">TRUE</span><span class="sxs-lookup"><span data-stu-id="24e6f-131">TRUE</span></span> 
  
> <span data-ttu-id="24e6f-132">参数都是有效的, 并且_lpSPropValueSrc_搜索字符串包含在_lpSPropValueDst_属性值中指定的。</span><span class="sxs-lookup"><span data-stu-id="24e6f-132">The parameters are all valid and the  _lpSPropValueSrc_ search string is contained as specified in the  _lpSPropValueDst_ property value.</span></span> 
    
<span data-ttu-id="24e6f-133">FALSE</span><span class="sxs-lookup"><span data-stu-id="24e6f-133">FALSE</span></span> 
  
> <span data-ttu-id="24e6f-134">要比较的属性值不是类型 PT_STRING8 或 PT_BINARY, 属性值的类型不同, 或者_lpSPropValueSrc_搜索字符串不包含在_lpSPropValueDst_属性值中指定的情况下。</span><span class="sxs-lookup"><span data-stu-id="24e6f-134">The property values being compared are not of type PT_STRING8 or PT_BINARY, the property values are of different types, or the  _lpSPropValueSrc_ search string is not contained as specified in the  _lpSPropValueDst_ property value.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="24e6f-135">注解</span><span class="sxs-lookup"><span data-stu-id="24e6f-135">Remarks</span></span>

<span data-ttu-id="24e6f-136">比较方法取决于在[SPropValue](spropvalue.md)属性定义中指定的属性类型以及_ulFuzzyLevel_参数中提供的模糊级别试探法。</span><span class="sxs-lookup"><span data-stu-id="24e6f-136">The comparison method depends on the property types specified in the [SPropValue](spropvalue.md) property definitions and the fuzzy level heuristic provided in the  _ulFuzzyLevel_ parameter.</span></span> <span data-ttu-id="24e6f-137">[FPropCompareProp](fpropcompareprop.md)和**FPropContainsProp**函数可用于准备生成表的限制。</span><span class="sxs-lookup"><span data-stu-id="24e6f-137">The [FPropCompareProp](fpropcompareprop.md) and **FPropContainsProp** functions can be used to prepare restrictions for generating a table.</span></span> 
  
<span data-ttu-id="24e6f-138">对于属性类型 PT_BINARY, 将忽略_ulFuzzyLevel_的高16位。</span><span class="sxs-lookup"><span data-stu-id="24e6f-138">The upper 16 bits of  _ulFuzzyLevel_ are ignored for property type PT_BINARY.</span></span> <span data-ttu-id="24e6f-139">如果_ulFuzzyLevel_中的设置缺失或无效, 则执行完全字符串完全匹配。</span><span class="sxs-lookup"><span data-stu-id="24e6f-139">If the settings in  _ulFuzzyLevel_ are missing or invalid, a full-string exact match is performed.</span></span> <span data-ttu-id="24e6f-140">有关属性控制的详细信息, 请参阅[SContentRestriction](scontentrestriction.md)结构。</span><span class="sxs-lookup"><span data-stu-id="24e6f-140">For more information about property containment, see the [SContentRestriction](scontentrestriction.md) structure.</span></span> 
  

