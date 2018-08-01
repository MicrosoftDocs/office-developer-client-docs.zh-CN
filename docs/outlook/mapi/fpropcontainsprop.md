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
ms.openlocfilehash: abf33e4167d836aeb88fdefb30ba05840e80ce63
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774989"
---
# <a name="fpropcontainsprop"></a><span data-ttu-id="f5068-103">FPropContainsProp</span><span class="sxs-lookup"><span data-stu-id="f5068-103">FPropContainsProp</span></span>

<span data-ttu-id="f5068-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f5068-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f5068-105">比较两个属性值，通常是字符串或二进制数组，如果一个包含其他。</span><span class="sxs-lookup"><span data-stu-id="f5068-105">Compares two property values, generally strings or binary arrays, to see if one contains the other.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f5068-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="f5068-106">Header file:</span></span>  <br/> |<span data-ttu-id="f5068-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="f5068-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="f5068-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="f5068-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="f5068-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="f5068-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="f5068-110">调用：</span><span class="sxs-lookup"><span data-stu-id="f5068-110">Called by:</span></span>  <br/> |<span data-ttu-id="f5068-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="f5068-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
BOOL FPropContainsProp(
  LPSPropValue lpSPropValueDst,
  LPSPropValue lpSPropValueSrc,
  ULONG ulFuzzyLevel
);
```

## <a name="parameters"></a><span data-ttu-id="f5068-112">参数</span><span class="sxs-lookup"><span data-stu-id="f5068-112">Parameters</span></span>

<span data-ttu-id="f5068-113">_lpSPropValueDst_</span><span class="sxs-lookup"><span data-stu-id="f5068-113">_lpSPropValueDst_</span></span>
  
> <span data-ttu-id="f5068-114">[in]指向[SPropValue](spropvalue.md)结构定义可能包含指向由_lpSPropValueSrc_参数的搜索字符串的属性值的指针。</span><span class="sxs-lookup"><span data-stu-id="f5068-114">[in] Pointer to an [SPropValue](spropvalue.md) structure defining the property value that might contain the search string pointed to by the  _lpSPropValueSrc_ parameter.</span></span> 
    
<span data-ttu-id="f5068-115">_lpSPropValueSrc_</span><span class="sxs-lookup"><span data-stu-id="f5068-115">_lpSPropValueSrc_</span></span>
  
> <span data-ttu-id="f5068-116">[in]指向_lpSPropValueDst_参数指向属性值中定义的搜索字符串的查找**FPropContainsProp** **SPropValue**结构。</span><span class="sxs-lookup"><span data-stu-id="f5068-116">[in] Pointer to an **SPropValue** structure defining the search string that **FPropContainsProp** is seeking in the property value pointed to by the  _lpSPropValueDst_ parameter.</span></span> 
    
<span data-ttu-id="f5068-117">_ulFuzzyLevel_</span><span class="sxs-lookup"><span data-stu-id="f5068-117">_ulFuzzyLevel_</span></span>
  
> <span data-ttu-id="f5068-118">[in]选项设置定义的 preciseness 级别比较中使用。</span><span class="sxs-lookup"><span data-stu-id="f5068-118">[in] Option settings defining the level of preciseness to use in the comparison.</span></span> 

  - <span data-ttu-id="f5068-119">**低 16 位**PT_BINARY 和 PT_STRING8 于类型的属性。</span><span class="sxs-lookup"><span data-stu-id="f5068-119">The **lower 16 bits** apply to properties of type PT_BINARY and PT_STRING8.</span></span> <span data-ttu-id="f5068-120">它们必须设置为完全下列值之一：</span><span class="sxs-lookup"><span data-stu-id="f5068-120">They must be set to exactly one of the following values:</span></span>
      
    - <span data-ttu-id="f5068-121">FL_FULLSTRING: _lpSPropValueSrc_搜索字符串必须由_lpSPropValueDst_标识该属性值等于。</span><span class="sxs-lookup"><span data-stu-id="f5068-121">FL_FULLSTRING: The  _lpSPropValueSrc_ search string must be equal to the property value identified by  _lpSPropValueDst_.</span></span>
        
    - <span data-ttu-id="f5068-122">FL_PREFIX: _lpSPropValueSrc_搜索字符串必须由_lpSPropValueDst_标识该属性值的开始处出现。</span><span class="sxs-lookup"><span data-stu-id="f5068-122">FL_PREFIX: The  _lpSPropValueSrc_ search string must appear at the beginning of the property value identified by  _lpSPropValueDst_.</span></span> <span data-ttu-id="f5068-123">应仅最由_lpSPropValueSrc_搜索字符串的长度比较两个值。</span><span class="sxs-lookup"><span data-stu-id="f5068-123">The two values should be compared only up to the length of the search string indicated by  _lpSPropValueSrc_.</span></span> 
        
    - <span data-ttu-id="f5068-124">FL_SUBSTRING: _lpSPropValueSrc_搜索字符串必须包含无处不在由_lpSPropValueDst_标识该属性值。</span><span class="sxs-lookup"><span data-stu-id="f5068-124">FL_SUBSTRING: The  _lpSPropValueSrc_ search string must be contained anywhere in the property value identified by  _lpSPropValueDst_.</span></span> 
      
  - <span data-ttu-id="f5068-125">**高 16 位**仅适用于 PT_STRING8 类型的属性。</span><span class="sxs-lookup"><span data-stu-id="f5068-125">The **upper 16 bits** apply only to properties of type PT_STRING8.</span></span> <span data-ttu-id="f5068-126">它们可以设置为下列值的任意组合：</span><span class="sxs-lookup"><span data-stu-id="f5068-126">They can be set to the following values in any combination:</span></span>
    
    - <span data-ttu-id="f5068-127">FL_IGNORECASE： 无需考虑区分大小写，应进行比较。</span><span class="sxs-lookup"><span data-stu-id="f5068-127">FL_IGNORECASE: The comparison should be made without considering case sensitivity.</span></span> 
        
    - <span data-ttu-id="f5068-128">FL_IGNORENONSPACE： 比较结果应忽略如音符 Unicode 定义无空格字符。</span><span class="sxs-lookup"><span data-stu-id="f5068-128">FL_IGNORENONSPACE: The comparison should ignore Unicode-defined nonspacing characters such as diacritical marks.</span></span> 
        
    - <span data-ttu-id="f5068-129">FL_LOOSE： 比较结果应指示忽略大小写匹配尽可能敏感性和无空格字符。</span><span class="sxs-lookup"><span data-stu-id="f5068-129">FL_LOOSE: The comparison should indicate a match whenever possible, ignoring case sensitivity and nonspacing characters.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f5068-130">返回值</span><span class="sxs-lookup"><span data-stu-id="f5068-130">Return value</span></span>

<span data-ttu-id="f5068-131">TRUE</span><span class="sxs-lookup"><span data-stu-id="f5068-131">TRUE</span></span> 
  
> <span data-ttu-id="f5068-132">参数是否所有有效且包含_lpSPropValueSrc_搜索字符串中的_lpSPropValueDst_属性值指定。</span><span class="sxs-lookup"><span data-stu-id="f5068-132">The parameters are all valid and the  _lpSPropValueSrc_ search string is contained as specified in the  _lpSPropValueDst_ property value.</span></span> 
    
<span data-ttu-id="f5068-133">FALSE</span><span class="sxs-lookup"><span data-stu-id="f5068-133">FALSE</span></span> 
  
> <span data-ttu-id="f5068-134">要比较的属性值不是类型 PT_STRING8 或 PT_BINARY、 的属性值是不同类型的或不包含_lpSPropValueSrc_搜索字符串中的_lpSPropValueDst_属性值指定。</span><span class="sxs-lookup"><span data-stu-id="f5068-134">The property values being compared are not of type PT_STRING8 or PT_BINARY, the property values are of different types, or the  _lpSPropValueSrc_ search string is not contained as specified in the  _lpSPropValueDst_ property value.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="f5068-135">说明</span><span class="sxs-lookup"><span data-stu-id="f5068-135">Remarks</span></span>

<span data-ttu-id="f5068-136">比较方法取决于[SPropValue](spropvalue.md)属性定义中指定的属性类型和_ulFuzzyLevel_参数中提供的级别模糊推断方法。</span><span class="sxs-lookup"><span data-stu-id="f5068-136">The comparison method depends on the property types specified in the [SPropValue](spropvalue.md) property definitions and the fuzzy level heuristic provided in the  _ulFuzzyLevel_ parameter.</span></span> <span data-ttu-id="f5068-137">[FPropCompareProp](fpropcompareprop.md)和**FPropContainsProp**函数可以用于准备用于生成表的限制。</span><span class="sxs-lookup"><span data-stu-id="f5068-137">The [FPropCompareProp](fpropcompareprop.md) and **FPropContainsProp** functions can be used to prepare restrictions for generating a table.</span></span> 
  
<span data-ttu-id="f5068-138">属性类型 PT_BINARY 忽略_ulFuzzyLevel_高 16 位。</span><span class="sxs-lookup"><span data-stu-id="f5068-138">The upper 16 bits of  _ulFuzzyLevel_ are ignored for property type PT_BINARY.</span></span> <span data-ttu-id="f5068-139">缺失或无效_ulFuzzyLevel_中的设置时，执行完全字符串完全匹配。</span><span class="sxs-lookup"><span data-stu-id="f5068-139">If the settings in  _ulFuzzyLevel_ are missing or invalid, a full-string exact match is performed.</span></span> <span data-ttu-id="f5068-140">有关属性包容详细信息，请参阅[SContentRestriction](scontentrestriction.md)结构。</span><span class="sxs-lookup"><span data-stu-id="f5068-140">For more information about property containment, see the [SContentRestriction](scontentrestriction.md) structure.</span></span> 
  

