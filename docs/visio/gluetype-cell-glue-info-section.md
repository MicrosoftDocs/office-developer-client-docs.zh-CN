---
title: GlueType 单元格（“Glue Info”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm420
localization_priority: Normal
ms.assetid: fffbefd6-8b0b-0023-6b03-026d1c6e885e
description: 确定将一维形状粘附到另一个形状时是使用静态粘附（点到点）还是动态粘附（形状到形状）。
ms.openlocfilehash: 162827521cda6fe4a37d17a8f7d36d7a36718519
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780350"
---
# <a name="gluetype-cell-glue-info-section"></a><span data-ttu-id="28ca6-103">GlueType 单元格（“Glue Info”部分）</span><span class="sxs-lookup"><span data-stu-id="28ca6-103">GlueType Cell (Glue Info Section)</span></span>

<span data-ttu-id="28ca6-104">确定将一维形状粘附到另一个形状时是使用静态粘附（点到点）还是动态粘附（形状到形状）。</span><span class="sxs-lookup"><span data-stu-id="28ca6-104">Determines whether a 1-D shape uses static (point-to-point) or dynamic (shape-to-shape) glue when it is glued to another shape.</span></span>
  
|<span data-ttu-id="28ca6-105">**值**</span><span class="sxs-lookup"><span data-stu-id="28ca6-105">**Value**</span></span>|<span data-ttu-id="28ca6-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="28ca6-106">**Description**</span></span>|<span data-ttu-id="28ca6-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="28ca6-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="28ca6-108">&amp;H0</span><span class="sxs-lookup"><span data-stu-id="28ca6-108">&amp;H0</span></span>  <br/> | <span data-ttu-id="28ca6-p101">默认值。只有动态连接线可使用动态粘附；其他形状均使用静态粘附。</span><span class="sxs-lookup"><span data-stu-id="28ca6-p101">Default. Allow dynamic glue for the dynamic connector only; otherwise, use static glue.</span></span>  <br/> |<span data-ttu-id="28ca6-111">**visGlueTypeDefault**</span><span class="sxs-lookup"><span data-stu-id="28ca6-111">**visGlueTypeDefault**</span></span> <br/> |
| <span data-ttu-id="28ca6-112">&amp;H1</span><span class="sxs-lookup"><span data-stu-id="28ca6-112">&amp;H1</span></span>  <br/> | <span data-ttu-id="28ca6-113">允许动态粘附。</span><span class="sxs-lookup"><span data-stu-id="28ca6-113">Allow dynamic glue.</span></span>  <br/> | <span data-ttu-id="28ca6-114">在 Visio 2002 中已经放弃该功能。</span><span class="sxs-lookup"><span data-stu-id="28ca6-114">Obsolete in Visio 2002</span></span>  <br/> |
| <span data-ttu-id="28ca6-115">&amp;H2</span><span class="sxs-lookup"><span data-stu-id="28ca6-115">&amp;H2</span></span>  <br/> | <span data-ttu-id="28ca6-116">允许动态粘附。</span><span class="sxs-lookup"><span data-stu-id="28ca6-116">Allow dynamic glue.</span></span>  <br/> |<span data-ttu-id="28ca6-117">**首**</span><span class="sxs-lookup"><span data-stu-id="28ca6-117">**visGlueTypeWalking**</span></span> <br/> |
| <span data-ttu-id="28ca6-118">&amp;H4</span><span class="sxs-lookup"><span data-stu-id="28ca6-118">&amp;H4</span></span>  <br/> | <span data-ttu-id="28ca6-119">不允许动态粘附。</span><span class="sxs-lookup"><span data-stu-id="28ca6-119">Do not allow dynamic glue.</span></span>  <br/> |<span data-ttu-id="28ca6-120">**则**</span><span class="sxs-lookup"><span data-stu-id="28ca6-120">**visGlueTypeNoWalking**</span></span> <br/> |
| <span data-ttu-id="28ca6-121">&amp;H8</span><span class="sxs-lookup"><span data-stu-id="28ca6-121">&amp;H8</span></span>  <br/> | <span data-ttu-id="28ca6-122">不允许使用动态粘附连接此二维形状。</span><span class="sxs-lookup"><span data-stu-id="28ca6-122">Do not allow this 2-D shape to be connected to with dynamic glue.</span></span>  <br/> |<span data-ttu-id="28ca6-123">**visGlueTypeNoWalkingTo**</span><span class="sxs-lookup"><span data-stu-id="28ca6-123">**visGlueTypeNoWalkingTo**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="28ca6-124">注释</span><span class="sxs-lookup"><span data-stu-id="28ca6-124">Remarks</span></span>

<span data-ttu-id="28ca6-125">如果此单元格包含值 1、2 或 3，则只要出现以下二者之一就将建立动态粘附：</span><span class="sxs-lookup"><span data-stu-id="28ca6-125">If this cell contains a value of 1, 2 or 3, dynamic glue will be established when either of the following occurs:</span></span>
  
- <span data-ttu-id="28ca6-126">在用户界面中动态粘附形状。</span><span class="sxs-lookup"><span data-stu-id="28ca6-126">Shapes are dynamically glued in the user interface.</span></span>
    
- <span data-ttu-id="28ca6-127">从某个程序中将形状粘附到另一个形状的 PinX 或 PinY 单元格。</span><span class="sxs-lookup"><span data-stu-id="28ca6-127">Shapes are glued to the PinX or PinY cell of another shape from a program.</span></span>
    
<span data-ttu-id="28ca6-128">如果从某个程序将形状粘附到 PinX 或 PinY 之外的其他形状单元格，则使用静态粘附。</span><span class="sxs-lookup"><span data-stu-id="28ca6-128">If shapes are glued to shape cells other than PinX or PinY from a program, then static glue is used.</span></span>
  
<span data-ttu-id="28ca6-p102">将此值由允许动态粘附更改为不允许动态粘附并不会切断或更改现有的动态粘附。即便在 GlueType 单元格中禁用了动态粘附，程序仍然可以建立动态粘附。</span><span class="sxs-lookup"><span data-stu-id="28ca6-p102">Changing this value from allowing to not allowing dynamic glue does not sever or change existing dynamic glue. Programs can establish dynamic glue even if dynamic glue is disabled in the GlueType cell.</span></span>
  
<span data-ttu-id="28ca6-131">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 GlueType 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="28ca6-131">To get a reference to the GlueType cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="28ca6-132">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="28ca6-132">Cell name:</span></span>  <br/> | <span data-ttu-id="28ca6-133">GlueType</span><span class="sxs-lookup"><span data-stu-id="28ca6-133">GlueType</span></span>  <br/> |
   
<span data-ttu-id="28ca6-134">要从某个程序按索引获取对 GlueType 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="28ca6-134">To get a reference to the GlueType cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="28ca6-135">内容索引：</span><span class="sxs-lookup"><span data-stu-id="28ca6-135">Section index:</span></span>  <br/> |<span data-ttu-id="28ca6-136">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="28ca6-136">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="28ca6-137">行索引：</span><span class="sxs-lookup"><span data-stu-id="28ca6-137">Row index:</span></span>  <br/> |<span data-ttu-id="28ca6-138">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="28ca6-138">**visRowMisc**</span></span> <br/> |
| <span data-ttu-id="28ca6-139">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="28ca6-139">Cell index:</span></span>  <br/> |<span data-ttu-id="28ca6-140">**visGlueType**</span><span class="sxs-lookup"><span data-stu-id="28ca6-140">**visGlueType**</span></span> <br/> |
   

