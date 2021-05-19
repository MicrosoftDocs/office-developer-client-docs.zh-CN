---
title: SETATREF 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60113
localization_priority: Normal
ms.assetid: 1ecfdb05-2533-470a-006b-e554026944d8
description: 将用户界面中的操作产生的更新值 (UI) 自动化重定向到另一个单元格。
ms.openlocfilehash: c4f5fe94aba90ce0a69983d6637a5399b6e42707
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416802"
---
# <a name="setatref-function"></a><span data-ttu-id="8c4b6-103">SETATREF 函数</span><span class="sxs-lookup"><span data-stu-id="8c4b6-103">SETATREF Function</span></span>

<span data-ttu-id="8c4b6-104">将用户界面中的操作产生的更新值 (UI) 自动化重定向到另一个单元格。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-104">Redirects updated values resulting from actions in the user interface (UI) or Automation to another cell.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="8c4b6-105">语法</span><span class="sxs-lookup"><span data-stu-id="8c4b6-105">Syntax</span></span>

<span data-ttu-id="8c4b6-106">SETATREF (\*\* *reference* \*\* [， \*\* *set_expression* \*\* [， \*\* *ignore_eval* \*\* ]]]) </span><span class="sxs-lookup"><span data-stu-id="8c4b6-106">SETATREF(\*\* *reference* \*\* [, \*\* *set_expression* \*\* [, \*\* *ignore_eval* \*\* ]])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="8c4b6-107">参数</span><span class="sxs-lookup"><span data-stu-id="8c4b6-107">Parameters</span></span>

|<span data-ttu-id="8c4b6-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="8c4b6-108">**Name**</span></span>|<span data-ttu-id="8c4b6-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="8c4b6-109">**Required/Optional**</span></span>|<span data-ttu-id="8c4b6-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8c4b6-110">**Data Type**</span></span>|<span data-ttu-id="8c4b6-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="8c4b6-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="8c4b6-112">_reference_</span><span class="sxs-lookup"><span data-stu-id="8c4b6-112">_reference_</span></span> <br/> |<span data-ttu-id="8c4b6-113">必需</span><span class="sxs-lookup"><span data-stu-id="8c4b6-113">Required</span></span>  <br/> |<span data-ttu-id="8c4b6-114">**String**</span><span class="sxs-lookup"><span data-stu-id="8c4b6-114">**String**</span></span> <br/> |<span data-ttu-id="8c4b6-115">表示对重定向更新的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-115">A reference to the cell where updates are redirected.</span></span>  <br/> |
| <span data-ttu-id="8c4b6-116">_set_expression_</span><span class="sxs-lookup"><span data-stu-id="8c4b6-116">_set_expression_</span></span> <br/> |<span data-ttu-id="8c4b6-117">可选</span><span class="sxs-lookup"><span data-stu-id="8c4b6-117">Optional</span></span>  <br/> |<span data-ttu-id="8c4b6-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="8c4b6-118">**String**</span></span> <br/> |<span data-ttu-id="8c4b6-119">分配给引用 的  _表达式_。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-119">An expression that is assigned to  _reference_.</span></span>  <br/> |
| <span data-ttu-id="8c4b6-120">_ignore_eval_</span><span class="sxs-lookup"><span data-stu-id="8c4b6-120">_ignore_eval_</span></span> <br/> |<span data-ttu-id="8c4b6-121">可选</span><span class="sxs-lookup"><span data-stu-id="8c4b6-121">Optional</span></span>  <br/> |<span data-ttu-id="8c4b6-122">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="8c4b6-122">**Boolean**</span></span> <br/> |<span data-ttu-id="8c4b6-123">如果为 TRUE，则 SETATREF 函数的 (为 0) 零;如果为 FALSE (SETATREF) 计算结果为引用  _的值的默认值_。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-123">If TRUE, the SETATREF function evaluates to (0) zero; if FALSE (the default) the SETATREF function evaluates to the value of  _reference_.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8c4b6-124">备注</span><span class="sxs-lookup"><span data-stu-id="8c4b6-124">Remarks</span></span>

<span data-ttu-id="8c4b6-125">当绘图窗口中的用户操作或自动化方法导致 Microsoft Visio 更新包含 SETATREF 公式的单元格时，值会重定向到 SETATREF 公式 (引用的单元格) 。 </span><span class="sxs-lookup"><span data-stu-id="8c4b6-125">When a user action in the drawing window, or an Automation method, causes Microsoft Visio to update a cell containing a SETATREF formula, the value is instead redirected to the cell referenced by the SETATREF formula ( _reference_).</span></span> <span data-ttu-id="8c4b6-126">含有 SETATREF 函数的单元格中的公式将保持不变。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-126">The formula in the cell containing the SETATREF function remains intact.</span></span>
  
<span data-ttu-id="8c4b6-127">如果  _set_expression，_ 则 UI 中或通过使用自动化设置的值将分配给引用的单元格;否则，  _将set_expression分配给_ 引用的单元格。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-127">If  _set_expression_ is omitted, the value set in the UI or by using Automation is assigned to the referenced cell; otherwise, the contents of  _set_expression_ are assigned to the referenced cell.</span></span> <span data-ttu-id="8c4b6-128">这样，可以在将新值赋给引用的单元格之前对其进行修改或转换。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-128">This allows the new value to be modified or transformed before being assigned to the referenced cell.</span></span> 
  
<span data-ttu-id="8c4b6-129">SETATREF 函数有两个相关函数：</span><span class="sxs-lookup"><span data-stu-id="8c4b6-129">The SETATREF function has two related functions:</span></span> 
  
- <span data-ttu-id="8c4b6-130">SETATREFEXPR 函数，可用于表示 set_expression _。_</span><span class="sxs-lookup"><span data-stu-id="8c4b6-130">The SETATREFEXPR function, which you can use to represent the new value within  _set_expression_.</span></span> <span data-ttu-id="8c4b6-131">例如，一个  _set_expression_ SETATREFEXPR () -2 in。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-131">For example, a  _set_expression_ of SETATREFEXPR()-2 in.</span></span> <span data-ttu-id="8c4b6-132">可用于从 SETATREFEXPR 结果中减去 2 英寸。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-132">could be used to subtract 2 inches from the SETATREFEXPR result.</span></span> 
    
- <span data-ttu-id="8c4b6-133">SETATREFEVAL 函数，可用于指示应计算set_expression部分内容，并替换为其结果。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-133">The SETATREFEVAL function, which you can use to indicate that some portion of  _set_expression_ should be evaluated and replaced by its result.</span></span> 
    
<span data-ttu-id="8c4b6-134">SETATREF 函数设计用于绘图窗口中用户操作可更改的单元格。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-134">The SETATREF function is designed for use in cells that can be changed by user actions in the drawing window.</span></span> <span data-ttu-id="8c4b6-135">该函数支持以下单元格：</span><span class="sxs-lookup"><span data-stu-id="8c4b6-135">The following cells are supported:</span></span>
  
- <span data-ttu-id="8c4b6-136">“ShapeTransform”内容 — Width、Height、Angle、PinX 和 PinY 单元格</span><span class="sxs-lookup"><span data-stu-id="8c4b6-136">ShapeTransform section—Width, Height, Angle, PinX, and PinY cells</span></span>
    
- <span data-ttu-id="8c4b6-137">“Text Transform”内容 — TxtWidth、TxtHeight、TxtAngle、TxtPinX 和 TxtPinY 单元格</span><span class="sxs-lookup"><span data-stu-id="8c4b6-137">Text Transform section—TxtWidth, TxtHeight, TxtAngle, TxtPinX, and TxtPinY cells</span></span>
    
- <span data-ttu-id="8c4b6-138">“1-D Endpoints”内容 — BeginX、BeginY、EndX 和 EndY 单元格</span><span class="sxs-lookup"><span data-stu-id="8c4b6-138">1-D Endpoints section—BeginX, BeginY, EndX, and EndY cells</span></span>
    
- <span data-ttu-id="8c4b6-139">“Controls”内容 — Controls.X 和 Controls.Y 单元格</span><span class="sxs-lookup"><span data-stu-id="8c4b6-139">Controls section—Controls.X and Controls.Y cells</span></span>
    
- <span data-ttu-id="8c4b6-140">“Shape Data”内容</span><span class="sxs-lookup"><span data-stu-id="8c4b6-140">Shape Data section</span></span>
    
<span data-ttu-id="8c4b6-141">由于 SETATREF 会更改单元格值发生变化的位置，因此它会影响事件触发。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-141">Because SETATREF changes the location where cell values change, it affects event firing.</span></span> <span data-ttu-id="8c4b6-142">如果某个单元格包含 SETATREF，则 **FormulaChanged** 和 **CellChanged** 事件将为 SETATREF 所引用的单元格而触发，而不会为包含 SETATREF 的单元格而触发。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-142">If a cell contains SETATREF, the **FormulaChanged** and **CellChanged** events fire for the cell that is referenced by SETATREF, not the cell containing SETATREF.</span></span> <span data-ttu-id="8c4b6-143">如果包含 SETATREF 的单元格还包含 SETATREFEXPR，FormulaChanged 事件也会为包含 SETATREF 的单元格触发，因为函数参数已更改。 </span><span class="sxs-lookup"><span data-stu-id="8c4b6-143">If a cell containing SETATREF also contains SETATREFEXPR, the **FormulaChanged** event also fires for the cell containing SETATREF because a function parameter is changed.</span></span> 
  
<span data-ttu-id="8c4b6-144">对于 SETATREF 函数，还请注意以下一些要点：</span><span class="sxs-lookup"><span data-stu-id="8c4b6-144">Other important points to note about the SETATREF function include the following:</span></span>
  
- <span data-ttu-id="8c4b6-145">SETATREF 函数最多可链接 10 个对其他 SETATREF 函数的引用。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-145">SETATREF functions can chain up to 10 references to other SETATREF functions.</span></span> 
    
- <span data-ttu-id="8c4b6-146">除 SETATREF 函数以外，单元格可包含其他表达式，包括在一个单元格中可多次出现 SETATREF。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-146">Cells can contain other expressions in addition to the SETATREF function, including multiple occurrences of SETATREF in a single cell.</span></span>
    
- <span data-ttu-id="8c4b6-147">如果形状被粘附，Visio 将延续同一工作表中的 SETATREF 引用链并将粘附公式放在引用的单元格中。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-147">If shapes are glued, Visio follows the SETATREF reference chain within the same sheet and places glue formulas in the referenced cell.</span></span> 
    
- <span data-ttu-id="8c4b6-148">自动化识别 SETATREF 函数并延续引用单元格链。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-148">Automation recognizes the SETATREF function and follows the chain of referenced cells.</span></span> 
    
- <span data-ttu-id="8c4b6-149">与 GUARD 类似，SETATREF 不能避免在 ShapeSheet 中使用 SETF 函数时单元格发生更改。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-149">Like GUARD, SETATREF does not protect cells from changes made by using the SETF function in the ShapeSheet.</span></span>
    
## <a name="example1"></a><span data-ttu-id="8c4b6-150">示例 1</span><span class="sxs-lookup"><span data-stu-id="8c4b6-150">Example1</span></span>

<span data-ttu-id="8c4b6-151">假设某个形状具有自定义属性 Width，且“Shape Transform”内容中的 Width 单元格包含以下公式：</span><span class="sxs-lookup"><span data-stu-id="8c4b6-151">Let's say that a shape has a custom property called Width, and that the Width cell in the Shape Transform section contains the following formula:</span></span>
  
<span data-ttu-id="8c4b6-152">=SETATREF (Prop.Width) </span><span class="sxs-lookup"><span data-stu-id="8c4b6-152">=SETATREF(Prop.Width)</span></span>
  
<span data-ttu-id="8c4b6-153">如果用户在 UI 中更改形状的宽度，则新值将分配给 Prop.Width 单元格，而不是 ShapeTransform 内容中的 Width 单元格;Width 单元格中的公式保持不变。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-153">If a user were to change the shape's width in the UI, the new value is assigned to the Prop.Width cell, not to the Width cell in the ShapeTransform section; the formula in the Width cell remains unchanged.</span></span> <span data-ttu-id="8c4b6-154">您还可以使用形状数据设置形状的宽度。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-154">You can also set the shape's width by using shape data.</span></span>
  
## <a name="example2"></a><span data-ttu-id="8c4b6-155">示例 2</span><span class="sxs-lookup"><span data-stu-id="8c4b6-155">Example2</span></span>

<span data-ttu-id="8c4b6-p107">Visio 解决方案通常具有含分级关系的形状，要求子形状随父形状的移动而移动。下面的示例向您演示了如何使用 ShapeSheet 中的 SETATREF 函数管理这种关系。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-p107">Visio solutions often have shapes that have a hierarchical relationship, requiring child shapes to move when a parent shape is moved. Following is an example of how you might manage this relationship using the SETATREF function in the ShapeSheet.</span></span> 
  
<span data-ttu-id="8c4b6-p108">以下公式包含在子形状的“Shape Transform”内容中。我们还定义了用户单元格 User.DeltaX 和 User.DeltaY，用来跟踪父形状的偏移尺寸。这样，子形状会随父形状的移动而移动，并且在移动子形状时仍然保持分级关系。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-p108">The following formulas are contained in the Shape Transform section of the child shape. Also, we define user cells called User.DeltaX and User.DeltaY, which track the offset dimension from ParentShape. This allows the child shape to move when the parent shape is moved, and also to preserve the hierarchical relationship if the child shape is moved.</span></span>
  
<span data-ttu-id="8c4b6-161">PinX =SETATREF(User.DeltaX, SETATREFEVAL(SETATREFEXPR() - ParentShape!PinX)) + ParentShape!PinX</span><span class="sxs-lookup"><span data-stu-id="8c4b6-161">PinX =SETATREF(User.DeltaX, SETATREFEVAL(SETATREFEXPR() - ParentShape!PinX)) + ParentShape!PinX</span></span>
  
<span data-ttu-id="8c4b6-162">PinY =SETATREF(User.DeltaY, SETATREFEVAL(SETATREFEXPR() - ParentShape!PinY)) + ParentShape!PinY</span><span class="sxs-lookup"><span data-stu-id="8c4b6-162">PinY =SETATREF(User.DeltaY, SETATREFEVAL(SETATREFEXPR() - ParentShape!PinY)) + ParentShape!PinY</span></span>
  
<span data-ttu-id="8c4b6-163">当使用 UI 移动子形状时，新的 PinX 和 PinY 值被设置为 SETATREFEXPR 函数中的参数。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-163">When the child shape is moved using the UI, the new PinX and PinY values are set as the parameter in the SETATREFEXPR function.</span></span> <span data-ttu-id="8c4b6-164">SETATREF 函数计算包含在 SETATREFEVAL 中的公式，并将 PinX 和 PinY 替换为其结果，然后将生成的公式分配给 SETATREF 函数中引用的用户单元格 User.DeltaX 和 User.DeltaY。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-164">The SETATREF function evaluates the formula enclosed in SETATREFEVAL and replaces PinX and PinY with their results, and then the resulting formula is assigned to the user cells referenced in the SETATREF function—User.DeltaX and User.DeltaY.</span></span> <span data-ttu-id="8c4b6-165">最后，SETATREF（User.DeltaX 或 User.DeltaY）所返回的值被添加到父形状的旋转中心点位置，以计算子形状的旋转中心点位置。</span><span class="sxs-lookup"><span data-stu-id="8c4b6-165">Lastly, the values returned by SETATREF (User.DeltaX or User.DeltaY) are added to the pin location of ParentShape to calculate the child shape's pin location.</span></span>
  

