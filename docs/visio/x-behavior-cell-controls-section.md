---
title: X Behavior 单元格（“Controls”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251285
localization_priority: Normal
ms.assetid: 82423d08-b6ce-0f23-8b61-354c3e5f323e
description: 控制控制手柄的 x 坐标在手柄移动后将表现的行为的类型。
ms.openlocfilehash: 50b08664deec69659ff70a0bf9a17a148ed0e110
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413946"
---
# <a name="x-behavior-cell-controls-section"></a><span data-ttu-id="5de06-103">X Behavior 单元格（“Controls”内容）</span><span class="sxs-lookup"><span data-stu-id="5de06-103">X Behavior Cell (Controls Section)</span></span>

<span data-ttu-id="5de06-104">控制控制手柄的*x*坐标在手柄移动后将表现的行为的类型。</span><span class="sxs-lookup"><span data-stu-id="5de06-104">Controls the type of behavior the  *x*  -coordinate of the control handle will exhibit after the handle is moved.</span></span> 
  
|<span data-ttu-id="5de06-105">**值**</span><span class="sxs-lookup"><span data-stu-id="5de06-105">**Value**</span></span>|<span data-ttu-id="5de06-106">**行为**</span><span class="sxs-lookup"><span data-stu-id="5de06-106">**Behavior**</span></span>|<span data-ttu-id="5de06-107">**定义**</span><span class="sxs-lookup"><span data-stu-id="5de06-107">**Definition**</span></span>|<span data-ttu-id="5de06-108">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="5de06-108">**Automation constant**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="5de06-109">0</span><span class="sxs-lookup"><span data-stu-id="5de06-109">0</span></span>  <br/> | <span data-ttu-id="5de06-110">非</span><span class="sxs-lookup"><span data-stu-id="5de06-110">Proportional</span></span>  <br/> | <span data-ttu-id="5de06-111">控制手柄可以移动，在伸展时它也随形状按比例移动。</span><span class="sxs-lookup"><span data-stu-id="5de06-111">The control handle can be moved, and it also moves in proportion with the shape when it is stretched.</span></span>  <br/> |<span data-ttu-id="5de06-112">**visCtlProportional**</span><span class="sxs-lookup"><span data-stu-id="5de06-112">**visCtlProportional**</span></span> <br/> |
| <span data-ttu-id="5de06-113">1</span><span class="sxs-lookup"><span data-stu-id="5de06-113">1</span></span>  <br/> | <span data-ttu-id="5de06-114">比例锁定</span><span class="sxs-lookup"><span data-stu-id="5de06-114">Proportional locked</span></span>  <br/> | <span data-ttu-id="5de06-115">控制手柄可按比例与形状一起移动，但控制手柄本身不能移动。</span><span class="sxs-lookup"><span data-stu-id="5de06-115">The control handle moves in proportion with the shape but the control handle itself cannot be moved.</span></span>  <br/> |<span data-ttu-id="5de06-116">**visCtlLocked**</span><span class="sxs-lookup"><span data-stu-id="5de06-116">**visCtlLocked**</span></span> <br/> |
| <span data-ttu-id="5de06-117">双面</span><span class="sxs-lookup"><span data-stu-id="5de06-117">2</span></span>  <br/> | <span data-ttu-id="5de06-118">左侧偏移</span><span class="sxs-lookup"><span data-stu-id="5de06-118">Offset from left edge</span></span>  <br/> | <span data-ttu-id="5de06-119">控制手柄与形状左侧偏移固定距离。</span><span class="sxs-lookup"><span data-stu-id="5de06-119">The control handle is offset a constant distance from the left side of the shape.</span></span>  <br/> |<span data-ttu-id="5de06-120">**visCtlOffsetMin**</span><span class="sxs-lookup"><span data-stu-id="5de06-120">**visCtlOffsetMin**</span></span> <br/> |
| <span data-ttu-id="5de06-121">第三章</span><span class="sxs-lookup"><span data-stu-id="5de06-121">3</span></span>  <br/> | <span data-ttu-id="5de06-122">中心偏移</span><span class="sxs-lookup"><span data-stu-id="5de06-122">Offset from center</span></span>  <br/> | <span data-ttu-id="5de06-123">控制手柄与形状中心偏移固定距离。</span><span class="sxs-lookup"><span data-stu-id="5de06-123">The control handle is offset a constant distance from the center of the shape.</span></span>  <br/> |<span data-ttu-id="5de06-124">**visCtlOffsetMid**</span><span class="sxs-lookup"><span data-stu-id="5de06-124">**visCtlOffsetMid**</span></span> <br/> |
| <span data-ttu-id="5de06-125">4</span><span class="sxs-lookup"><span data-stu-id="5de06-125">4</span></span>  <br/> | <span data-ttu-id="5de06-126">右侧偏移</span><span class="sxs-lookup"><span data-stu-id="5de06-126">Offset from right edge</span></span>  <br/> | <span data-ttu-id="5de06-127">控制手柄与形状右侧偏移固定距离。</span><span class="sxs-lookup"><span data-stu-id="5de06-127">The control handle is offset a constant distance from the right side of the shape.</span></span>  <br/> |<span data-ttu-id="5de06-128">**visCtlOffsetMax**</span><span class="sxs-lookup"><span data-stu-id="5de06-128">**visCtlOffsetMax**</span></span> <br/> |
| <span data-ttu-id="5de06-129">5</span><span class="sxs-lookup"><span data-stu-id="5de06-129">5</span></span>  <br/> | <span data-ttu-id="5de06-130">成比例，隐藏</span><span class="sxs-lookup"><span data-stu-id="5de06-130">Proportional, hidden</span></span>  <br/> | <span data-ttu-id="5de06-131">与值 0 的含义相同，但控制手柄被隐藏起来了。</span><span class="sxs-lookup"><span data-stu-id="5de06-131">Same as 0, but the control handle is not visible.</span></span>  <br/> |<span data-ttu-id="5de06-132">**visCtlProportionalHidden**</span><span class="sxs-lookup"><span data-stu-id="5de06-132">**visCtlProportionalHidden**</span></span> <br/> |
| <span data-ttu-id="5de06-133">型</span><span class="sxs-lookup"><span data-stu-id="5de06-133">6</span></span>  <br/> | <span data-ttu-id="5de06-134">比例锁定，隐藏</span><span class="sxs-lookup"><span data-stu-id="5de06-134">Proportional locked, hidden</span></span>  <br/> | <span data-ttu-id="5de06-135">与值 1 的含义相同，但控制手柄被隐藏起来了。</span><span class="sxs-lookup"><span data-stu-id="5de06-135">Same as 1, but the control handle is not visible.</span></span>  <br/> |<span data-ttu-id="5de06-136">**visCtlLockedHiddenv**</span><span class="sxs-lookup"><span data-stu-id="5de06-136">**visCtlLockedHiddenv**</span></span> <br/> |
| <span data-ttu-id="5de06-137">步</span><span class="sxs-lookup"><span data-stu-id="5de06-137">7</span></span>  <br/> | <span data-ttu-id="5de06-138">左侧偏移，隐藏</span><span class="sxs-lookup"><span data-stu-id="5de06-138">Offset from left edge, hidden</span></span>  <br/> | <span data-ttu-id="5de06-139">与值 2 的含义相同，但控制手柄被隐藏起来了。</span><span class="sxs-lookup"><span data-stu-id="5de06-139">Same as 2, but the control handle is not visible.</span></span>  <br/> |<span data-ttu-id="5de06-140">**visCtlOffsetMinHidden**</span><span class="sxs-lookup"><span data-stu-id="5de06-140">**visCtlOffsetMinHidden**</span></span> <br/> |
| <span data-ttu-id="5de06-141">utf-8</span><span class="sxs-lookup"><span data-stu-id="5de06-141">8</span></span>  <br/> | <span data-ttu-id="5de06-142">中心偏移，隐藏</span><span class="sxs-lookup"><span data-stu-id="5de06-142">Offset from center, hidden</span></span>  <br/> | <span data-ttu-id="5de06-143">与值 3 的含义相同，但控制手柄被隐藏起来了。</span><span class="sxs-lookup"><span data-stu-id="5de06-143">Same as 3, but the control handle is not visible.</span></span>  <br/> |<span data-ttu-id="5de06-144">**visCtlOffsetMidHidden**</span><span class="sxs-lookup"><span data-stu-id="5de06-144">**visCtlOffsetMidHidden**</span></span> <br/> |
| <span data-ttu-id="5de06-145">第</span><span class="sxs-lookup"><span data-stu-id="5de06-145">9</span></span>  <br/> | <span data-ttu-id="5de06-146">右侧偏移，隐藏</span><span class="sxs-lookup"><span data-stu-id="5de06-146">Offset from right edge, hidden</span></span>  <br/> | <span data-ttu-id="5de06-147">与值 4 的含义相同，但控制手柄被隐藏起来了。</span><span class="sxs-lookup"><span data-stu-id="5de06-147">Same as 4, but the control handle is not visible.</span></span>  <br/> |<span data-ttu-id="5de06-148">**visCtlOffsetMaxHidden**</span><span class="sxs-lookup"><span data-stu-id="5de06-148">**visCtlOffsetMaxHidden**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5de06-149">说明</span><span class="sxs-lookup"><span data-stu-id="5de06-149">Remarks</span></span>

<span data-ttu-id="5de06-150">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 X Behavior 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="5de06-150">To get a reference to the X Behavior cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="5de06-151">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="5de06-151">Cell name:</span></span>  <br/> | <span data-ttu-id="5de06-152">措施.</span><span class="sxs-lookup"><span data-stu-id="5de06-152">Controls.</span></span>  <span data-ttu-id="5de06-153">*名称*。XConwhere 控件。</span><span class="sxs-lookup"><span data-stu-id="5de06-153">*name*  .XConwhere Controls.</span></span>  <span data-ttu-id="5de06-154">*名称*是控件行的名称。</span><span class="sxs-lookup"><span data-stu-id="5de06-154">*name*  is the name of the controls row.</span></span>  <br/> |
   
<span data-ttu-id="5de06-155">要从某个程序按索引获取对 X Behavior 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="5de06-155">To get a reference to the X Behavior cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="5de06-156">内容索引：</span><span class="sxs-lookup"><span data-stu-id="5de06-156">Section index:</span></span>  <br/> |<span data-ttu-id="5de06-157">**visSectionControls**</span><span class="sxs-lookup"><span data-stu-id="5de06-157">**visSectionControls**</span></span> <br/> |
| <span data-ttu-id="5de06-158">行索引：</span><span class="sxs-lookup"><span data-stu-id="5de06-158">Row index:</span></span>  <br/> |<span data-ttu-id="5de06-159">**visRowControl** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="5de06-159">**visRowControl** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="5de06-160">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="5de06-160">Cell index:</span></span>  <br/> |<span data-ttu-id="5de06-161">**visCtlXCon**</span><span class="sxs-lookup"><span data-stu-id="5de06-161">**visCtlXCon**</span></span> <br/> |
   

