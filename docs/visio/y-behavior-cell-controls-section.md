---
title: Y Behavior 单元格（“Controls”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1190
localization_priority: Normal
ms.assetid: 6d5062d3-743b-8664-8ec9-5a8f11d5edf9
description: 控制控制手柄的 y 坐标在手柄移动后将呈现的行为类型。 提供以下公式。
ms.openlocfilehash: bf8cbd490884244c92b68784dcbf041093539c94
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413575"
---
# <a name="y-behavior-cell-controls-section"></a><span data-ttu-id="859a5-104">Y Behavior 单元格（“Controls”内容）</span><span class="sxs-lookup"><span data-stu-id="859a5-104">Y Behavior Cell (Controls Section)</span></span>

<span data-ttu-id="859a5-105">控制控制手柄  *的 y*  坐标在手柄移动后将呈现的行为类型。</span><span class="sxs-lookup"><span data-stu-id="859a5-105">Controls the type of behavior the  *y*  -coordinate of the control handle will exhibit after the handle is moved.</span></span> <span data-ttu-id="859a5-106">提供以下公式。</span><span class="sxs-lookup"><span data-stu-id="859a5-106">These formulas are available.</span></span> 
  
|<span data-ttu-id="859a5-107">**值**</span><span class="sxs-lookup"><span data-stu-id="859a5-107">**Value**</span></span>|<span data-ttu-id="859a5-108">**行为**</span><span class="sxs-lookup"><span data-stu-id="859a5-108">**Behavior**</span></span>|<span data-ttu-id="859a5-109">**定义**</span><span class="sxs-lookup"><span data-stu-id="859a5-109">**Definition**</span></span>|<span data-ttu-id="859a5-110">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="859a5-110">**Automation constant**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="859a5-111">0</span><span class="sxs-lookup"><span data-stu-id="859a5-111">0</span></span>  <br/> | <span data-ttu-id="859a5-112">成比例</span><span class="sxs-lookup"><span data-stu-id="859a5-112">Proportional</span></span>  <br/> | <span data-ttu-id="859a5-113">控制手柄可以移动，在伸展时它也随形状按比例移动。</span><span class="sxs-lookup"><span data-stu-id="859a5-113">The control handle can be moved, and it also moves in proportion with the shape when it is stretched.</span></span>  <br/> |<span data-ttu-id="859a5-114">**visCtlProportional**</span><span class="sxs-lookup"><span data-stu-id="859a5-114">**visCtlProportional**</span></span> <br/> |
| <span data-ttu-id="859a5-115">1</span><span class="sxs-lookup"><span data-stu-id="859a5-115">1</span></span>  <br/> | <span data-ttu-id="859a5-116">比例锁定</span><span class="sxs-lookup"><span data-stu-id="859a5-116">Proportional locked</span></span>  <br/> | <span data-ttu-id="859a5-117">控制手柄可按比例与形状一起移动，但控制手柄本身不能移动。</span><span class="sxs-lookup"><span data-stu-id="859a5-117">The control handle moves in proportion with the shape, but the control handle itself cannot be moved.</span></span>  <br/> |<span data-ttu-id="859a5-118">**visCtlLocked**</span><span class="sxs-lookup"><span data-stu-id="859a5-118">**visCtlLocked**</span></span> <br/> |
| <span data-ttu-id="859a5-119">2</span><span class="sxs-lookup"><span data-stu-id="859a5-119">2</span></span>  <br/> | <span data-ttu-id="859a5-120">底边偏移</span><span class="sxs-lookup"><span data-stu-id="859a5-120">Offset from bottom edge</span></span>  <br/> | <span data-ttu-id="859a5-121">控制手柄与形状底边偏移固定距离。</span><span class="sxs-lookup"><span data-stu-id="859a5-121">The control handle is offset a constant distance from the bottom of the shape.</span></span>  <br/> |<span data-ttu-id="859a5-122">**visCtlOffsetMin**</span><span class="sxs-lookup"><span data-stu-id="859a5-122">**visCtlOffsetMin**</span></span> <br/> |
| <span data-ttu-id="859a5-123">3</span><span class="sxs-lookup"><span data-stu-id="859a5-123">3</span></span>  <br/> | <span data-ttu-id="859a5-124">中心偏移</span><span class="sxs-lookup"><span data-stu-id="859a5-124">Offset from center</span></span>  <br/> | <span data-ttu-id="859a5-125">控制手柄与形状中心偏移固定距离。</span><span class="sxs-lookup"><span data-stu-id="859a5-125">The control handle is offset a constant distance from the center of the shape.</span></span>  <br/> |<span data-ttu-id="859a5-126">**visCtlOffsetMid**</span><span class="sxs-lookup"><span data-stu-id="859a5-126">**visCtlOffsetMid**</span></span> <br/> |
| <span data-ttu-id="859a5-127">4 </span><span class="sxs-lookup"><span data-stu-id="859a5-127">4</span></span>  <br/> | <span data-ttu-id="859a5-128">顶边偏移</span><span class="sxs-lookup"><span data-stu-id="859a5-128">Offset from top edge</span></span>  <br/> | <span data-ttu-id="859a5-129">控制手柄与形状顶边偏移固定距离。</span><span class="sxs-lookup"><span data-stu-id="859a5-129">The control handle is offset a constant distance from the top of the shape.</span></span>  <br/> |<span data-ttu-id="859a5-130">**visCtlOffsetMax**</span><span class="sxs-lookup"><span data-stu-id="859a5-130">**visCtlOffsetMax**</span></span> <br/> |
| <span data-ttu-id="859a5-131">5 </span><span class="sxs-lookup"><span data-stu-id="859a5-131">5</span></span>  <br/> | <span data-ttu-id="859a5-132">成比例，隐藏</span><span class="sxs-lookup"><span data-stu-id="859a5-132">Proportional, hidden</span></span>  <br/> | <span data-ttu-id="859a5-133">与值 0 的含义相同，但控制手柄被隐藏起来了。</span><span class="sxs-lookup"><span data-stu-id="859a5-133">Same as 0, but the control handle is not visible.</span></span>  <br/> |<span data-ttu-id="859a5-134">**visCtlProportionalHidden**</span><span class="sxs-lookup"><span data-stu-id="859a5-134">**visCtlProportionalHidden**</span></span> <br/> |
| <span data-ttu-id="859a5-135">6 </span><span class="sxs-lookup"><span data-stu-id="859a5-135">6</span></span>  <br/> | <span data-ttu-id="859a5-136">比例锁定，隐藏</span><span class="sxs-lookup"><span data-stu-id="859a5-136">Proportional locked, hidden</span></span>  <br/> | <span data-ttu-id="859a5-137">与值 1 的含义相同，但控制手柄被隐藏起来了。</span><span class="sxs-lookup"><span data-stu-id="859a5-137">Same as 1, but the control handle is not visible.</span></span>  <br/> |<span data-ttu-id="859a5-138">**visCtlLockedHiddenv**</span><span class="sxs-lookup"><span data-stu-id="859a5-138">**visCtlLockedHiddenv**</span></span> <br/> |
| <span data-ttu-id="859a5-139">7 </span><span class="sxs-lookup"><span data-stu-id="859a5-139">7</span></span>  <br/> | <span data-ttu-id="859a5-140">左侧偏移，隐藏</span><span class="sxs-lookup"><span data-stu-id="859a5-140">Offset from left edge, hidden</span></span>  <br/> | <span data-ttu-id="859a5-141">与值 2 的含义相同，但控制手柄被隐藏起来了。</span><span class="sxs-lookup"><span data-stu-id="859a5-141">Same as 2, but the control handle is not visible.</span></span>  <br/> |<span data-ttu-id="859a5-142">**visCtlOffsetMinHidden**</span><span class="sxs-lookup"><span data-stu-id="859a5-142">**visCtlOffsetMinHidden**</span></span> <br/> |
| <span data-ttu-id="859a5-143">8 </span><span class="sxs-lookup"><span data-stu-id="859a5-143">8</span></span>  <br/> | <span data-ttu-id="859a5-144">中心偏移，隐藏</span><span class="sxs-lookup"><span data-stu-id="859a5-144">Offset from center, hidden</span></span>  <br/> | <span data-ttu-id="859a5-145">与值 3 的含义相同，但控制手柄被隐藏起来了。</span><span class="sxs-lookup"><span data-stu-id="859a5-145">Same as 3, but the control handle is not visible.</span></span>  <br/> |<span data-ttu-id="859a5-146">**visCtlOffsetMidHidden**</span><span class="sxs-lookup"><span data-stu-id="859a5-146">**visCtlOffsetMidHidden**</span></span> <br/> |
| <span data-ttu-id="859a5-147">9 </span><span class="sxs-lookup"><span data-stu-id="859a5-147">9</span></span>  <br/> | <span data-ttu-id="859a5-148">右侧偏移，隐藏</span><span class="sxs-lookup"><span data-stu-id="859a5-148">Offset from right edge, hidden</span></span>  <br/> | <span data-ttu-id="859a5-149">与值 4 的含义相同，但控制手柄被隐藏起来了。</span><span class="sxs-lookup"><span data-stu-id="859a5-149">Same as 4, but the control handle is not visible.</span></span>  <br/> |<span data-ttu-id="859a5-150">**visCtlOffsetMaxHidden**</span><span class="sxs-lookup"><span data-stu-id="859a5-150">**visCtlOffsetMaxHidden**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="859a5-151">备注</span><span class="sxs-lookup"><span data-stu-id="859a5-151">Remarks</span></span>

<span data-ttu-id="859a5-152">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Y Behavior 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="859a5-152">To get a reference to the Y Behavior cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="859a5-153">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="859a5-153">Cell name:</span></span>  <br/> | <span data-ttu-id="859a5-154">控件。</span><span class="sxs-lookup"><span data-stu-id="859a5-154">Controls.</span></span>  <span data-ttu-id="859a5-155">*name*  .YConwhere 控件。</span><span class="sxs-lookup"><span data-stu-id="859a5-155">*name*  .YConwhere Controls.</span></span>  <span data-ttu-id="859a5-156">*name*  是控件行的名称。</span><span class="sxs-lookup"><span data-stu-id="859a5-156">*name*  is the name of the controls row.</span></span>  <br/> |
   
<span data-ttu-id="859a5-157">要从某个程序按索引获取对 Y Behavior 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="859a5-157">To get a reference to the Y Behavior cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="859a5-158">内容索引：</span><span class="sxs-lookup"><span data-stu-id="859a5-158">Section index:</span></span>  <br/> |<span data-ttu-id="859a5-159">**visSectionControls**</span><span class="sxs-lookup"><span data-stu-id="859a5-159">**visSectionControls**</span></span> <br/> |
| <span data-ttu-id="859a5-160">行索引：</span><span class="sxs-lookup"><span data-stu-id="859a5-160">Row index:</span></span>  <br/> |<span data-ttu-id="859a5-161">**visRowControl**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="859a5-161">**visRowControl** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="859a5-162">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="859a5-162">Cell index:</span></span>  <br/> |<span data-ttu-id="859a5-163">**visCtlYCon**</span><span class="sxs-lookup"><span data-stu-id="859a5-163">**visCtlYCon**</span></span> <br/> |
   

