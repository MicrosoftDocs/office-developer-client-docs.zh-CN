---
title: BOUND 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60099
localization_priority: Normal
ms.assetid: 36374d78-1028-bd7f-6282-66555ee31306
description: 将某个单元格的值约束在某一范围或一组范围内。
ms.openlocfilehash: 85fbe66d4e458ac4e42c9eb3c65b9a3a1d8211df
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425958"
---
# <a name="bound-function"></a><span data-ttu-id="e361f-103">BOUND 函数</span><span class="sxs-lookup"><span data-stu-id="e361f-103">BOUND Function</span></span>

<span data-ttu-id="e361f-104">将某个单元格的值约束在某一范围或一组范围内。</span><span class="sxs-lookup"><span data-stu-id="e361f-104">Constrains the value of a cell to a range or set of ranges.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="e361f-105">语法</span><span class="sxs-lookup"><span data-stu-id="e361f-105">Syntax</span></span>

<span data-ttu-id="e361f-106">绑定 (\* **值** *、* **类型** *、* **忽略** *、* \* \*\* 、\* *、* \* *value2* \* \* \* \* \* [、ignore (n)、value1 (n)、value2 (n),...] \* \* \*)</span><span class="sxs-lookup"><span data-stu-id="e361f-106">BOUND (\*\* *value* \*\*, \*\* *type* \*\*, \*\* *ignore* \*\*, \*\* *value1* \*\*, \*\* *value2* \*\* \*\* \* [,ignore(n), value1(n), value2(n),...] \* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="e361f-107">参数</span><span class="sxs-lookup"><span data-stu-id="e361f-107">Parameters</span></span>

|<span data-ttu-id="e361f-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="e361f-108">**Name**</span></span>|<span data-ttu-id="e361f-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="e361f-109">**Required/Optional**</span></span>|<span data-ttu-id="e361f-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e361f-110">**Data Type**</span></span>|<span data-ttu-id="e361f-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="e361f-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="e361f-112">_value_</span><span class="sxs-lookup"><span data-stu-id="e361f-112">_value_</span></span> <br/> |<span data-ttu-id="e361f-113">必需</span><span class="sxs-lookup"><span data-stu-id="e361f-113">Required</span></span>  <br/> |<span data-ttu-id="e361f-114">**数值**</span><span class="sxs-lookup"><span data-stu-id="e361f-114">**Numeric**</span></span> <br/> |<span data-ttu-id="e361f-115">受到约束的当前值。</span><span class="sxs-lookup"><span data-stu-id="e361f-115">The current value being constrained.</span></span>  <br/> |
| <span data-ttu-id="e361f-116">_type_</span><span class="sxs-lookup"><span data-stu-id="e361f-116">_type_</span></span> <br/> |<span data-ttu-id="e361f-117">必需</span><span class="sxs-lookup"><span data-stu-id="e361f-117">Required</span></span>  <br/> |<span data-ttu-id="e361f-118">**数值**</span><span class="sxs-lookup"><span data-stu-id="e361f-118">**Numeric**</span></span> <br/> |<span data-ttu-id="e361f-119">约束的类型是包含 (0)、不包含 (1) 还是禁用 (2)。</span><span class="sxs-lookup"><span data-stu-id="e361f-119">Whether the constraint is inclusive (0), exclusive (1), or disabled (2).</span></span>  <br/> |
| <span data-ttu-id="e361f-120">_忽略_</span><span class="sxs-lookup"><span data-stu-id="e361f-120">_ignore_</span></span> <br/> |<span data-ttu-id="e361f-121">必需</span><span class="sxs-lookup"><span data-stu-id="e361f-121">Required</span></span>  <br/> |<span data-ttu-id="e361f-122">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="e361f-122">**Boolean**</span></span> <br/> | <span data-ttu-id="e361f-123">如果为 TRUE, 则忽略区域;如果为 FALSE, 则将单元格的值限定在区域中。</span><span class="sxs-lookup"><span data-stu-id="e361f-123">TRUE to ignore the range; FALSE to constrain the value of the cell to the range.</span></span>  <br/> |
| <span data-ttu-id="e361f-124">_value1_</span><span class="sxs-lookup"><span data-stu-id="e361f-124">_value1_</span></span> <br/> |<span data-ttu-id="e361f-125">必需</span><span class="sxs-lookup"><span data-stu-id="e361f-125">Required</span></span>  <br/> |<span data-ttu-id="e361f-126">**数值**</span><span class="sxs-lookup"><span data-stu-id="e361f-126">**Numeric**</span></span> <br/> |<span data-ttu-id="e361f-127">范围内的第一个值。</span><span class="sxs-lookup"><span data-stu-id="e361f-127">First value in a range.</span></span>  <br/> |
| <span data-ttu-id="e361f-128">_value2_</span><span class="sxs-lookup"><span data-stu-id="e361f-128">_value2_</span></span> <br/> |<span data-ttu-id="e361f-129">必需</span><span class="sxs-lookup"><span data-stu-id="e361f-129">Required</span></span>  <br/> |<span data-ttu-id="e361f-130">**数值**</span><span class="sxs-lookup"><span data-stu-id="e361f-130">**Numeric**</span></span> <br/> |<span data-ttu-id="e361f-131">范围内的第二个值。</span><span class="sxs-lookup"><span data-stu-id="e361f-131">Second value in a range.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e361f-132">说明</span><span class="sxs-lookup"><span data-stu-id="e361f-132">Remarks</span></span>

<span data-ttu-id="e361f-133">使用 BOUND 函数可以将某个单元格的值限制在上限和下限之内，例如，可以控制那些不应拉伸超过最大高度或缩短小于最小高度的对象。</span><span class="sxs-lookup"><span data-stu-id="e361f-133">Use the BOUND function to restrict a cell's value to an upper and lower bound, for example, to control objects that should not be stretched above or below a minimum or maximum height.</span></span> <span data-ttu-id="e361f-134">对于范围，该约束可以包括范围值本身或者不包括范围值本身。</span><span class="sxs-lookup"><span data-stu-id="e361f-134">The constraint can be inclusive or exclusive with respect to the range or ranges.</span></span> <span data-ttu-id="e361f-135">如果当前值不应受约束, 请将_type_参数设置为 2 (已禁用)。</span><span class="sxs-lookup"><span data-stu-id="e361f-135">If the current value should not be constrained, set the  _type_ parameter to 2 (disabled).</span></span> 
  
<span data-ttu-id="e361f-136">您可以通过提供 " _ignore_"、" _value1_" 和 " _value2_ " 参数的多个匹配项来定义多个区域。</span><span class="sxs-lookup"><span data-stu-id="e361f-136">You can define multiple ranges by supplying multiple occurrences of the  _ignore_,  _value1_, and  _value2_ parameters.</span></span> <span data-ttu-id="e361f-137">使用_ignore_参数禁用特定范围的约束。</span><span class="sxs-lookup"><span data-stu-id="e361f-137">Use the  _ignore_ parameter to disable constraints by a particular range.</span></span> 
  
<span data-ttu-id="e361f-138">包含绑定函数的公式在其值发生更改时不会被覆盖;相反, 将保留公式, 并将新值放入_value_参数中。</span><span class="sxs-lookup"><span data-stu-id="e361f-138">The formula containing the BOUND function does not get overwritten when its value changes; instead, the formula is preserved and the new value is placed into the  _value_ parameter.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="e361f-139">示例 1</span><span class="sxs-lookup"><span data-stu-id="e361f-139">Example 1</span></span>

<span data-ttu-id="e361f-140">本示例使用 BOUND 函数强制控制手柄始终处于形状的边框内。</span><span class="sxs-lookup"><span data-stu-id="e361f-140">This example uses the BOUND function to force a control handle to stay within the bounding box of a shape.</span></span> 
  
<span data-ttu-id="e361f-141">控件 X1 = 绑定 (Width\*0.5, 0, FALSE, width\*0, width\*1)</span><span class="sxs-lookup"><span data-stu-id="e361f-141">Controls.X1 = BOUND(Width\*0.5, 0, FALSE, Width\*0, Width\*1)</span></span>
  
<span data-ttu-id="e361f-142">控件。 Y1 = 界限 (Height\*0.5, 0, FALSE, height\*0, height\*1)</span><span class="sxs-lookup"><span data-stu-id="e361f-142">Controls.Y1 = BOUND(Height\*0.5, 0, FALSE, Height\*0, Height\*1)</span></span>
  
## <a name="example-2"></a><span data-ttu-id="e361f-143">示例 2</span><span class="sxs-lookup"><span data-stu-id="e361f-143">Example 2</span></span>

<span data-ttu-id="e361f-144">本示例使用 BOUND 函数将形状的宽度限制为 2 英寸、4 英寸或 6 英寸。</span><span class="sxs-lookup"><span data-stu-id="e361f-144">This example uses the BOUND function to constrain a shape's width to 2 inches, 4 inches, or 6 inches.</span></span> 
  
<span data-ttu-id="e361f-145">Width = BOUND(, 0, FALSE, 2 in, 2 in, FALSE, 4 in, 4 in, FALSE, 6 in, 6 in)</span><span class="sxs-lookup"><span data-stu-id="e361f-145">Width = BOUND(, 0, FALSE, 2 in, 2 in, FALSE, 4 in, 4 in, FALSE, 6 in, 6 in)</span></span>
  

