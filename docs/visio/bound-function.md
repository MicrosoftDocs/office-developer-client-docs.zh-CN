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
ms.openlocfilehash: 2f6228828fee8fa1831bb0d3a714fca068808652
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779818"
---
# <a name="bound-function"></a><span data-ttu-id="fb14d-103">BOUND 函数</span><span class="sxs-lookup"><span data-stu-id="fb14d-103">BOUND Function</span></span>

<span data-ttu-id="fb14d-104">将某个单元格的值约束在某一范围或一组范围内。</span><span class="sxs-lookup"><span data-stu-id="fb14d-104">Constrains the value of a cell to a range or set of ranges.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="fb14d-105">语法</span><span class="sxs-lookup"><span data-stu-id="fb14d-105">Syntax</span></span>

<span data-ttu-id="fb14d-106">绑定 (* **值** *，* **类型** *，* **忽略** *，* * *value1* * *，* * *value2* * * * * * [，ignore(n) value1(n)、 value2(n)，...] * * *)</span><span class="sxs-lookup"><span data-stu-id="fb14d-106">BOUND (** *value* **, ** *type* **, ** *ignore* **, ** *value1* **, ** *value2* ** ** * [,ignore(n), value1(n), value2(n),...] * ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="fb14d-107">参数</span><span class="sxs-lookup"><span data-stu-id="fb14d-107">Parameters</span></span>

|<span data-ttu-id="fb14d-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="fb14d-108">**Name**</span></span>|<span data-ttu-id="fb14d-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="fb14d-109">**Required/Optional**</span></span>|<span data-ttu-id="fb14d-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="fb14d-110">**Data Type**</span></span>|<span data-ttu-id="fb14d-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="fb14d-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="fb14d-112">_value_</span><span class="sxs-lookup"><span data-stu-id="fb14d-112">_value_</span></span> <br/> |<span data-ttu-id="fb14d-113">必需</span><span class="sxs-lookup"><span data-stu-id="fb14d-113">Required</span></span>  <br/> |<span data-ttu-id="fb14d-114">**数字**</span><span class="sxs-lookup"><span data-stu-id="fb14d-114">**Numeric**</span></span> <br/> |<span data-ttu-id="fb14d-115">受到约束的当前值。</span><span class="sxs-lookup"><span data-stu-id="fb14d-115">The current value being constrained.</span></span>  <br/> |
| <span data-ttu-id="fb14d-116">_type_</span><span class="sxs-lookup"><span data-stu-id="fb14d-116">_type_</span></span> <br/> |<span data-ttu-id="fb14d-117">必需</span><span class="sxs-lookup"><span data-stu-id="fb14d-117">Required</span></span>  <br/> |<span data-ttu-id="fb14d-118">**数字**</span><span class="sxs-lookup"><span data-stu-id="fb14d-118">**Numeric**</span></span> <br/> |<span data-ttu-id="fb14d-119">约束是否包含 (0)，不包含 (1) 还是禁用 (2)。</span><span class="sxs-lookup"><span data-stu-id="fb14d-119">Whether the constraint is inclusive (0), exclusive (1), or disabled (2).</span></span>  <br/> |
| <span data-ttu-id="fb14d-120">_忽略_</span><span class="sxs-lookup"><span data-stu-id="fb14d-120">_ignore_</span></span> <br/> |<span data-ttu-id="fb14d-121">必需</span><span class="sxs-lookup"><span data-stu-id="fb14d-121">Required</span></span>  <br/> |<span data-ttu-id="fb14d-122">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="fb14d-122">**Boolean**</span></span> <br/> | <span data-ttu-id="fb14d-123">为 true，则忽略该范围;若要将限制到区域单元格的值，则为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="fb14d-123">TRUE to ignore the range; FALSE to constrain the value of the cell to the range.</span></span>  <br/> |
| <span data-ttu-id="fb14d-124">_value1_</span><span class="sxs-lookup"><span data-stu-id="fb14d-124">_value1_</span></span> <br/> |<span data-ttu-id="fb14d-125">必需</span><span class="sxs-lookup"><span data-stu-id="fb14d-125">Required</span></span>  <br/> |<span data-ttu-id="fb14d-126">**数字**</span><span class="sxs-lookup"><span data-stu-id="fb14d-126">**Numeric**</span></span> <br/> |<span data-ttu-id="fb14d-127">范围中的第一个值。</span><span class="sxs-lookup"><span data-stu-id="fb14d-127">First value in a range.</span></span>  <br/> |
| <span data-ttu-id="fb14d-128">_value2_</span><span class="sxs-lookup"><span data-stu-id="fb14d-128">_value2_</span></span> <br/> |<span data-ttu-id="fb14d-129">必需</span><span class="sxs-lookup"><span data-stu-id="fb14d-129">Required</span></span>  <br/> |<span data-ttu-id="fb14d-130">**数字**</span><span class="sxs-lookup"><span data-stu-id="fb14d-130">**Numeric**</span></span> <br/> |<span data-ttu-id="fb14d-131">范围内的第二个值。</span><span class="sxs-lookup"><span data-stu-id="fb14d-131">Second value in a range.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fb14d-132">注解</span><span class="sxs-lookup"><span data-stu-id="fb14d-132">Remarks</span></span>

<span data-ttu-id="fb14d-133">使用 BOUND 的函数来限制单元格的值在上限和下限，例如，来控制上方或下方最小值或最大高度不应拉伸的对象。</span><span class="sxs-lookup"><span data-stu-id="fb14d-133">Use the BOUND function to restrict a cell's value to an upper and lower bound, for example, to control objects that should not be stretched above or below a minimum or maximum height.</span></span> <span data-ttu-id="fb14d-134">该约束可以包含或排除相对于范围或范围。</span><span class="sxs-lookup"><span data-stu-id="fb14d-134">The constraint can be inclusive or exclusive with respect to the range or ranges.</span></span> <span data-ttu-id="fb14d-135">如果不应约束的当前值，设置_type_参数为 2 （禁用）。</span><span class="sxs-lookup"><span data-stu-id="fb14d-135">If the current value should not be constrained, set the  _type_ parameter to 2 (disabled).</span></span> 
  
<span data-ttu-id="fb14d-136">通过提供的_忽略_、 _value1_，和_value2_参数的多个匹配项，您可以定义多个区域。</span><span class="sxs-lookup"><span data-stu-id="fb14d-136">You can define multiple ranges by supplying multiple occurrences of the  _ignore_,  _value1_, and  _value2_ parameters.</span></span> <span data-ttu-id="fb14d-137">使用_忽略_参数禁用特定范围约束。</span><span class="sxs-lookup"><span data-stu-id="fb14d-137">Use the  _ignore_ parameter to disable constraints by a particular range.</span></span> 
  
<span data-ttu-id="fb14d-138">包含 BOUND 的函数的公式不会被覆盖时更改其值;而是保留公式和新值放入_value_参数。</span><span class="sxs-lookup"><span data-stu-id="fb14d-138">The formula containing the BOUND function does not get overwritten when its value changes; instead, the formula is preserved and the new value is placed into the  _value_ parameter.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="fb14d-139">示例 1</span><span class="sxs-lookup"><span data-stu-id="fb14d-139">Example 1</span></span>

<span data-ttu-id="fb14d-140">本示例使用 BOUND 函数强制控制手柄始终处于形状的边框内。</span><span class="sxs-lookup"><span data-stu-id="fb14d-140">This example uses the BOUND function to force a control handle to stay within the bounding box of a shape.</span></span> 
  
<span data-ttu-id="fb14d-141">Controls.X1 = 绑定 (宽度\*0.5，0，FALSE、 宽度\*0，宽度\*1)</span><span class="sxs-lookup"><span data-stu-id="fb14d-141">Controls.X1 = BOUND(Width\*0.5, 0, FALSE, Width\*0, Width\*1)</span></span>
  
<span data-ttu-id="fb14d-142">Controls.Y1 = 绑定 (高度\*0.5，0，FALSE、 高度\*0，高度\*1)</span><span class="sxs-lookup"><span data-stu-id="fb14d-142">Controls.Y1 = BOUND(Height\*0.5, 0, FALSE, Height\*0, Height\*1)</span></span>
  
## <a name="example-2"></a><span data-ttu-id="fb14d-143">示例 2</span><span class="sxs-lookup"><span data-stu-id="fb14d-143">Example 2</span></span>

<span data-ttu-id="fb14d-144">本示例使用 BOUND 函数将形状的宽度限制为 2 英寸、4 英寸或 6 英寸。</span><span class="sxs-lookup"><span data-stu-id="fb14d-144">This example uses the BOUND function to constrain a shape's width to 2 inches, 4 inches, or 6 inches.</span></span> 
  
<span data-ttu-id="fb14d-145">Width = BOUND(, 0, FALSE, 2 in, 2 in, FALSE, 4 in, 4 in, FALSE, 6 in, 6 in)</span><span class="sxs-lookup"><span data-stu-id="fb14d-145">Width = BOUND(, 0, FALSE, 2 in, 2 in, FALSE, 4 in, 4 in, FALSE, 6 in, 6 in)</span></span>
  

