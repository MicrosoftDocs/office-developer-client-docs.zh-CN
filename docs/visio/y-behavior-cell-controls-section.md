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
description: 控件类型的行为 y-控制手柄的坐标在手柄移动后将表现。 提供了这些公式。
ms.openlocfilehash: ee2a5e28748df603635f64c080119e28569f576a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781697"
---
# <a name="y-behavior-cell-controls-section"></a><span data-ttu-id="dfbae-104">Y Behavior 单元格（“Controls”部分）</span><span class="sxs-lookup"><span data-stu-id="dfbae-104">Y Behavior Cell (Controls Section)</span></span>

<span data-ttu-id="dfbae-105">控件类型的行为*y* -控制手柄的坐标在手柄移动后将表现。</span><span class="sxs-lookup"><span data-stu-id="dfbae-105">Controls the type of behavior the  *y*  -coordinate of the control handle will exhibit after the handle is moved.</span></span> <span data-ttu-id="dfbae-106">提供了这些公式。</span><span class="sxs-lookup"><span data-stu-id="dfbae-106">These formulas are available.</span></span> 
  
|<span data-ttu-id="dfbae-107">**值**</span><span class="sxs-lookup"><span data-stu-id="dfbae-107">**Value**</span></span>|<span data-ttu-id="dfbae-108">**行为**</span><span class="sxs-lookup"><span data-stu-id="dfbae-108">**Behavior**</span></span>|<span data-ttu-id="dfbae-109">**定义**</span><span class="sxs-lookup"><span data-stu-id="dfbae-109">**Definition**</span></span>|<span data-ttu-id="dfbae-110">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="dfbae-110">**Automation constant**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="dfbae-111">0</span><span class="sxs-lookup"><span data-stu-id="dfbae-111">0</span></span>  <br/> | <span data-ttu-id="dfbae-112">成比例</span><span class="sxs-lookup"><span data-stu-id="dfbae-112">Proportional</span></span>  <br/> | <span data-ttu-id="dfbae-113">控制手柄可以移动，在伸展时它也随形状按比例移动。</span><span class="sxs-lookup"><span data-stu-id="dfbae-113">The control handle can be moved, and it also moves in proportion with the shape when it is stretched.</span></span>  <br/> |<span data-ttu-id="dfbae-114">**visCtlProportional**</span><span class="sxs-lookup"><span data-stu-id="dfbae-114">**visCtlProportional**</span></span> <br/> |
| <span data-ttu-id="dfbae-115">1</span><span class="sxs-lookup"><span data-stu-id="dfbae-115">1</span></span>  <br/> | <span data-ttu-id="dfbae-116">比例锁定</span><span class="sxs-lookup"><span data-stu-id="dfbae-116">Proportional locked</span></span>  <br/> | <span data-ttu-id="dfbae-117">控制手柄可按比例与形状一起移动，但控制手柄本身不能移动。</span><span class="sxs-lookup"><span data-stu-id="dfbae-117">The control handle moves in proportion with the shape, but the control handle itself cannot be moved.</span></span>  <br/> |<span data-ttu-id="dfbae-118">**visCtlLocked**</span><span class="sxs-lookup"><span data-stu-id="dfbae-118">**visCtlLocked**</span></span> <br/> |
| <span data-ttu-id="dfbae-119">2</span><span class="sxs-lookup"><span data-stu-id="dfbae-119">2</span></span>  <br/> | <span data-ttu-id="dfbae-120">底边偏移</span><span class="sxs-lookup"><span data-stu-id="dfbae-120">Offset from bottom edge</span></span>  <br/> | <span data-ttu-id="dfbae-121">控制手柄与形状底边偏移固定距离。</span><span class="sxs-lookup"><span data-stu-id="dfbae-121">The control handle is offset a constant distance from the bottom of the shape.</span></span>  <br/> |<span data-ttu-id="dfbae-122">**visCtlOffsetMin**</span><span class="sxs-lookup"><span data-stu-id="dfbae-122">**visCtlOffsetMin**</span></span> <br/> |
| <span data-ttu-id="dfbae-123">3</span><span class="sxs-lookup"><span data-stu-id="dfbae-123">3</span></span>  <br/> | <span data-ttu-id="dfbae-124">中心偏移</span><span class="sxs-lookup"><span data-stu-id="dfbae-124">Offset from center</span></span>  <br/> | <span data-ttu-id="dfbae-125">控制手柄与形状中心偏移固定距离。</span><span class="sxs-lookup"><span data-stu-id="dfbae-125">The control handle is offset a constant distance from the center of the shape.</span></span>  <br/> |<span data-ttu-id="dfbae-126">**visCtlOffsetMid**</span><span class="sxs-lookup"><span data-stu-id="dfbae-126">**visCtlOffsetMid**</span></span> <br/> |
| <span data-ttu-id="dfbae-127">4</span><span class="sxs-lookup"><span data-stu-id="dfbae-127">4</span></span>  <br/> | <span data-ttu-id="dfbae-128">顶边偏移</span><span class="sxs-lookup"><span data-stu-id="dfbae-128">Offset from top edge</span></span>  <br/> | <span data-ttu-id="dfbae-129">控制手柄与形状顶边偏移固定距离。</span><span class="sxs-lookup"><span data-stu-id="dfbae-129">The control handle is offset a constant distance from the top of the shape.</span></span>  <br/> |<span data-ttu-id="dfbae-130">**visCtlOffsetMax**</span><span class="sxs-lookup"><span data-stu-id="dfbae-130">**visCtlOffsetMax**</span></span> <br/> |
| <span data-ttu-id="dfbae-131">5</span><span class="sxs-lookup"><span data-stu-id="dfbae-131">5</span></span>  <br/> | <span data-ttu-id="dfbae-132">成比例，隐藏</span><span class="sxs-lookup"><span data-stu-id="dfbae-132">Proportional, hidden</span></span>  <br/> | <span data-ttu-id="dfbae-133">与值 0 的含义相同，但控制手柄被隐藏起来了。</span><span class="sxs-lookup"><span data-stu-id="dfbae-133">Same as 0, but the control handle is not visible.</span></span>  <br/> |<span data-ttu-id="dfbae-134">**visCtlProportionalHidden**</span><span class="sxs-lookup"><span data-stu-id="dfbae-134">**visCtlProportionalHidden**</span></span> <br/> |
| <span data-ttu-id="dfbae-135">6</span><span class="sxs-lookup"><span data-stu-id="dfbae-135">6</span></span>  <br/> | <span data-ttu-id="dfbae-136">比例锁定，隐藏</span><span class="sxs-lookup"><span data-stu-id="dfbae-136">Proportional locked, hidden</span></span>  <br/> | <span data-ttu-id="dfbae-137">与值 1 的含义相同，但控制手柄被隐藏起来了。</span><span class="sxs-lookup"><span data-stu-id="dfbae-137">Same as 1, but the control handle is not visible.</span></span>  <br/> |<span data-ttu-id="dfbae-138">**visCtlLockedHiddenv**</span><span class="sxs-lookup"><span data-stu-id="dfbae-138">**visCtlLockedHiddenv**</span></span> <br/> |
| <span data-ttu-id="dfbae-139">7</span><span class="sxs-lookup"><span data-stu-id="dfbae-139">7</span></span>  <br/> | <span data-ttu-id="dfbae-140">左侧偏移，隐藏</span><span class="sxs-lookup"><span data-stu-id="dfbae-140">Offset from left edge, hidden</span></span>  <br/> | <span data-ttu-id="dfbae-141">与值 2 的含义相同，但控制手柄被隐藏起来了。</span><span class="sxs-lookup"><span data-stu-id="dfbae-141">Same as 2, but the control handle is not visible.</span></span>  <br/> |<span data-ttu-id="dfbae-142">**visCtlOffsetMinHidden**</span><span class="sxs-lookup"><span data-stu-id="dfbae-142">**visCtlOffsetMinHidden**</span></span> <br/> |
| <span data-ttu-id="dfbae-143">8</span><span class="sxs-lookup"><span data-stu-id="dfbae-143">8</span></span>  <br/> | <span data-ttu-id="dfbae-144">中心偏移，隐藏</span><span class="sxs-lookup"><span data-stu-id="dfbae-144">Offset from center, hidden</span></span>  <br/> | <span data-ttu-id="dfbae-145">与值 3 的含义相同，但控制手柄被隐藏起来了。</span><span class="sxs-lookup"><span data-stu-id="dfbae-145">Same as 3, but the control handle is not visible.</span></span>  <br/> |<span data-ttu-id="dfbae-146">**visCtlOffsetMidHidden**</span><span class="sxs-lookup"><span data-stu-id="dfbae-146">**visCtlOffsetMidHidden**</span></span> <br/> |
| <span data-ttu-id="dfbae-147">9</span><span class="sxs-lookup"><span data-stu-id="dfbae-147">9</span></span>  <br/> | <span data-ttu-id="dfbae-148">右侧偏移，隐藏</span><span class="sxs-lookup"><span data-stu-id="dfbae-148">Offset from right edge, hidden</span></span>  <br/> | <span data-ttu-id="dfbae-149">与值 4 的含义相同，但控制手柄被隐藏起来了。</span><span class="sxs-lookup"><span data-stu-id="dfbae-149">Same as 4, but the control handle is not visible.</span></span>  <br/> |<span data-ttu-id="dfbae-150">**visCtlOffsetMaxHidden**</span><span class="sxs-lookup"><span data-stu-id="dfbae-150">**visCtlOffsetMaxHidden**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dfbae-151">说明</span><span class="sxs-lookup"><span data-stu-id="dfbae-151">Remarks</span></span>

<span data-ttu-id="dfbae-152">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Y Behavior 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="dfbae-152">To get a reference to the Y Behavior cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="dfbae-153">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="dfbae-153">Cell name:</span></span>  <br/> | <span data-ttu-id="dfbae-154">控件。</span><span class="sxs-lookup"><span data-stu-id="dfbae-154">Controls.</span></span>  <span data-ttu-id="dfbae-155">*名称*。YConwhere 控件。</span><span class="sxs-lookup"><span data-stu-id="dfbae-155">*name*  .YConwhere Controls.</span></span>  <span data-ttu-id="dfbae-156">*name*是控制行的名称。</span><span class="sxs-lookup"><span data-stu-id="dfbae-156">*name*  is the name of the controls row.</span></span>  <br/> |
   
<span data-ttu-id="dfbae-157">要从某个程序按索引获取对 Y Behavior 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="dfbae-157">To get a reference to the Y Behavior cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="dfbae-158">内容索引：</span><span class="sxs-lookup"><span data-stu-id="dfbae-158">Section index:</span></span>  <br/> |<span data-ttu-id="dfbae-159">**visSectionControls**</span><span class="sxs-lookup"><span data-stu-id="dfbae-159">**visSectionControls**</span></span> <br/> |
| <span data-ttu-id="dfbae-160">行索引：</span><span class="sxs-lookup"><span data-stu-id="dfbae-160">Row index:</span></span>  <br/> |<span data-ttu-id="dfbae-161">**visRowControl** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="dfbae-161">**visRowControl** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="dfbae-162">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="dfbae-162">Cell index:</span></span>  <br/> |<span data-ttu-id="dfbae-163">**visCtlYCon**</span><span class="sxs-lookup"><span data-stu-id="dfbae-163">**visCtlYCon**</span></span> <br/> |
   

