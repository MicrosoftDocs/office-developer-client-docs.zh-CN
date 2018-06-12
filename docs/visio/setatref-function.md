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
description: 重定向更新中的用户界面 (UI) 或自动化操作产生到另一个单元格的值。
ms.openlocfilehash: 69a9cb93ae3fbd807ef4f306be386f5389a6cfeb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781240"
---
# <a name="setatref-function"></a><span data-ttu-id="ac636-103">SETATREF 函数</span><span class="sxs-lookup"><span data-stu-id="ac636-103">SETATREF Function</span></span>

<span data-ttu-id="ac636-104">重定向更新中的用户界面 (UI) 或自动化操作产生到另一个单元格的值。</span><span class="sxs-lookup"><span data-stu-id="ac636-104">Redirects updated values resulting from actions in the user interface (UI) or Automation to another cell.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="ac636-105">语法</span><span class="sxs-lookup"><span data-stu-id="ac636-105">Syntax</span></span>

<span data-ttu-id="ac636-106">SETATREF (* **参考 （英文）* * * [，* * *set_expression* * * [，* * *ignore_eval* * *]])</span><span class="sxs-lookup"><span data-stu-id="ac636-106">SETATREF(** *reference* ** [, ** *set_expression* ** [, ** *ignore_eval* ** ]])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="ac636-107">参数</span><span class="sxs-lookup"><span data-stu-id="ac636-107">Parameters</span></span>

|<span data-ttu-id="ac636-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="ac636-108">**Name**</span></span>|<span data-ttu-id="ac636-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="ac636-109">**Required/Optional**</span></span>|<span data-ttu-id="ac636-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ac636-110">**Data Type**</span></span>|<span data-ttu-id="ac636-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="ac636-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ac636-112">_参考 （英文）_</span><span class="sxs-lookup"><span data-stu-id="ac636-112">_reference_</span></span> <br/> |<span data-ttu-id="ac636-113">必需</span><span class="sxs-lookup"><span data-stu-id="ac636-113">Required</span></span>  <br/> |<span data-ttu-id="ac636-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="ac636-114">**String**</span></span> <br/> |<span data-ttu-id="ac636-115">表示对重定向更新的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="ac636-115">A reference to the cell where updates are redirected.</span></span>  <br/> |
| <span data-ttu-id="ac636-116">_set_expression_</span><span class="sxs-lookup"><span data-stu-id="ac636-116">_set_expression_</span></span> <br/> |<span data-ttu-id="ac636-117">可选</span><span class="sxs-lookup"><span data-stu-id="ac636-117">Optional</span></span>  <br/> |<span data-ttu-id="ac636-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="ac636-118">**String**</span></span> <br/> |<span data-ttu-id="ac636-119">分配给_引用_一个表达式。</span><span class="sxs-lookup"><span data-stu-id="ac636-119">An expression that is assigned to  _reference_.</span></span>  <br/> |
| <span data-ttu-id="ac636-120">_ignore_eval_</span><span class="sxs-lookup"><span data-stu-id="ac636-120">_ignore_eval_</span></span> <br/> |<span data-ttu-id="ac636-121">可选</span><span class="sxs-lookup"><span data-stu-id="ac636-121">Optional</span></span>  <br/> |<span data-ttu-id="ac636-122">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="ac636-122">**Boolean**</span></span> <br/> |<span data-ttu-id="ac636-123">如果为 TRUE，则 SETATREF 函数计算为 (0) 零;如果为 FALSE （默认值） SETATREF 函数计算为_reference_的值。</span><span class="sxs-lookup"><span data-stu-id="ac636-123">If TRUE, the SETATREF function evaluates to (0) zero; if FALSE (the default) the SETATREF function evaluates to the value of  _reference_.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ac636-124">备注</span><span class="sxs-lookup"><span data-stu-id="ac636-124">Remarks</span></span>

<span data-ttu-id="ac636-125">当用户操作在绘图窗口中或自动化方法，使 Microsoft Visio 更新包含 SETATREF 公式的单元格时，值改为重定向到 SETATREF 公式 （_引用_） 引用的单元格。</span><span class="sxs-lookup"><span data-stu-id="ac636-125">When a user action in the drawing window, or an Automation method, causes Microsoft Visio to update a cell containing a SETATREF formula, the value is instead redirected to the cell referenced by the SETATREF formula ( _reference_).</span></span> <span data-ttu-id="ac636-126">中包含 SETATREF 函数的单元格的公式保持不变。</span><span class="sxs-lookup"><span data-stu-id="ac636-126">The formula in the cell containing the SETATREF function remains intact.</span></span>
  
<span data-ttu-id="ac636-127">如果省略_set_expression_ ，设置在用户界面或通过使用自动化的值分配给引用的单元格;否则， _set_expression_的某一部分的内容分配给引用的单元格。</span><span class="sxs-lookup"><span data-stu-id="ac636-127">If  _set_expression_ is omitted, the value set in the UI or by using Automation is assigned to the referenced cell; otherwise, the contents of  _set_expression_ are assigned to the referenced cell.</span></span> <span data-ttu-id="ac636-128">这样，要修改或转换之前要分配给引用的单元格的新值。</span><span class="sxs-lookup"><span data-stu-id="ac636-128">This allows the new value to be modified or transformed before being assigned to the referenced cell.</span></span> 
  
<span data-ttu-id="ac636-129">SETATREF 函数有两个相关函数：</span><span class="sxs-lookup"><span data-stu-id="ac636-129">The SETATREF function has two related functions:</span></span> 
  
- <span data-ttu-id="ac636-130">SETATREFEXPR 函数，可用来表示_set_expression_中的新值。</span><span class="sxs-lookup"><span data-stu-id="ac636-130">The SETATREFEXPR function, which you can use to represent the new value within  _set_expression_.</span></span> <span data-ttu-id="ac636-131">例如， _set_expression_的 SETATREFEXPR （）-2 中的。</span><span class="sxs-lookup"><span data-stu-id="ac636-131">For example, a  _set_expression_ of SETATREFEXPR()-2 in.</span></span> <span data-ttu-id="ac636-132">无法用于减去从 SETATREFEXPR 结果的 2 英寸。</span><span class="sxs-lookup"><span data-stu-id="ac636-132">could be used to subtract 2 inches from the SETATREFEXPR result.</span></span> 
    
- <span data-ttu-id="ac636-133">SETATREFEVAL 函数，您可以使用它来指示应计算并由其结果替换_set_expression_的。</span><span class="sxs-lookup"><span data-stu-id="ac636-133">The SETATREFEVAL function, which you can use to indicate that some portion of  _set_expression_ should be evaluated and replaced by its result.</span></span> 
    
<span data-ttu-id="ac636-134">SETATREF 函数用于可以更改的绘图窗口中的用户操作的单元格。</span><span class="sxs-lookup"><span data-stu-id="ac636-134">The SETATREF function is designed for use in cells that can be changed by user actions in the drawing window.</span></span> <span data-ttu-id="ac636-135">支持以下单元格：</span><span class="sxs-lookup"><span data-stu-id="ac636-135">The following cells are supported:</span></span>
  
- <span data-ttu-id="ac636-136">“ShapeTransform”内容 — Width、Height、Angle、PinX 和 PinY 单元格</span><span class="sxs-lookup"><span data-stu-id="ac636-136">ShapeTransform section—Width, Height, Angle, PinX, and PinY cells</span></span>
    
- <span data-ttu-id="ac636-137">“Text Transform”内容 — TxtWidth、TxtHeight、TxtAngle、TxtPinX 和 TxtPinY 单元格</span><span class="sxs-lookup"><span data-stu-id="ac636-137">Text Transform section—TxtWidth, TxtHeight, TxtAngle, TxtPinX, and TxtPinY cells</span></span>
    
- <span data-ttu-id="ac636-138">“1-D Endpoints”内容 — BeginX、BeginY、EndX 和 EndY 单元格</span><span class="sxs-lookup"><span data-stu-id="ac636-138">1-D Endpoints section—BeginX, BeginY, EndX, and EndY cells</span></span>
    
- <span data-ttu-id="ac636-139">“Controls”内容 — Controls.X 和 Controls.Y 单元格</span><span class="sxs-lookup"><span data-stu-id="ac636-139">Controls section—Controls.X and Controls.Y cells</span></span>
    
- <span data-ttu-id="ac636-140">“Shape Data”内容</span><span class="sxs-lookup"><span data-stu-id="ac636-140">Shape Data section</span></span>
    
<span data-ttu-id="ac636-141">SETATREF 更改单元格值的变化的位置，因为它会影响事件触发。</span><span class="sxs-lookup"><span data-stu-id="ac636-141">Because SETATREF changes the location where cell values change, it affects event firing.</span></span> <span data-ttu-id="ac636-142">如果单元格包含 SETATREF，则**FormulaChanged**和**CellChanged**事件触发 SETATREF，不包含 SETATREF 的单元格引用单元格。</span><span class="sxs-lookup"><span data-stu-id="ac636-142">If a cell contains SETATREF, the **FormulaChanged** and **CellChanged** events fire for the cell that is referenced by SETATREF, not the cell containing SETATREF.</span></span> <span data-ttu-id="ac636-143">如果还包含 SETATREF 的单元格包含 SETATREFEXPR，还会包含 SETATREF，因为函数参数已更改的单元格的触发**FormulaChanged**事件。</span><span class="sxs-lookup"><span data-stu-id="ac636-143">If a cell containing SETATREF also contains SETATREFEXPR, the **FormulaChanged** event also fires for the cell containing SETATREF because a function parameter is changed.</span></span> 
  
<span data-ttu-id="ac636-144">对于 SETATREF 函数，还请注意以下一些要点：</span><span class="sxs-lookup"><span data-stu-id="ac636-144">Other important points to note about the SETATREF function include the following:</span></span>
  
- <span data-ttu-id="ac636-145">SETATREF 函数最多可链接 10 个对其他 SETATREF 函数的引用。</span><span class="sxs-lookup"><span data-stu-id="ac636-145">SETATREF functions can chain up to 10 references to other SETATREF functions.</span></span> 
    
- <span data-ttu-id="ac636-146">除 SETATREF 函数以外，单元格可包含其他表达式，包括在一个单元格中可多次出现 SETATREF。</span><span class="sxs-lookup"><span data-stu-id="ac636-146">Cells can contain other expressions in addition to the SETATREF function, including multiple occurrences of SETATREF in a single cell.</span></span>
    
- <span data-ttu-id="ac636-147">如果形状被粘附，Visio 将延续同一工作表中的 SETATREF 引用链并将粘附公式放在引用的单元格中。</span><span class="sxs-lookup"><span data-stu-id="ac636-147">If shapes are glued, Visio follows the SETATREF reference chain within the same sheet and places glue formulas in the referenced cell.</span></span> 
    
- <span data-ttu-id="ac636-148">自动化识别 SETATREF 函数并延续引用单元格链。</span><span class="sxs-lookup"><span data-stu-id="ac636-148">Automation recognizes the SETATREF function and follows the chain of referenced cells.</span></span> 
    
- <span data-ttu-id="ac636-149">与 GUARD 类似，SETATREF 不能避免在 ShapeSheet 中使用 SETF 函数时单元格发生更改。</span><span class="sxs-lookup"><span data-stu-id="ac636-149">Like GUARD, SETATREF does not protect cells from changes made by using the SETF function in the ShapeSheet.</span></span>
    
## <a name="example1"></a><span data-ttu-id="ac636-150">示例 1</span><span class="sxs-lookup"><span data-stu-id="ac636-150">Example1</span></span>

<span data-ttu-id="ac636-151">假设某个形状具有自定义属性 Width，且“Shape Transform”内容中的 Width 单元格包含以下公式：</span><span class="sxs-lookup"><span data-stu-id="ac636-151">Let's say that a shape has a custom property called Width, and that the Width cell in the Shape Transform section contains the following formula:</span></span>
  
<span data-ttu-id="ac636-152">=SETATREF(Prop.Width)</span><span class="sxs-lookup"><span data-stu-id="ac636-152">=SETATREF(Prop.Width)</span></span>
  
<span data-ttu-id="ac636-153">如果用户更改在 UI 中的形状的宽度，将新值分配给 Prop.Width 单元格，而不应用于在 ShapeTransform 部分中; Width 单元格Width 单元格中的公式保持不变。</span><span class="sxs-lookup"><span data-stu-id="ac636-153">If a user were to change the shape's width in the UI, the new value is assigned to the Prop.Width cell, not to the Width cell in the ShapeTransform section; the formula in the Width cell remains unchanged.</span></span> <span data-ttu-id="ac636-154">您还可以使用形状数据设置形状的宽度。</span><span class="sxs-lookup"><span data-stu-id="ac636-154">You can also set the shape's width by using shape data.</span></span>
  
## <a name="example2"></a><span data-ttu-id="ac636-155">示例 2</span><span class="sxs-lookup"><span data-stu-id="ac636-155">Example2</span></span>

<span data-ttu-id="ac636-p107">Visio 解决方案通常具有含分级关系的形状，要求子形状随父形状的移动而移动。下面的示例向您演示了如何使用 ShapeSheet 中的 SETATREF 函数管理这种关系。</span><span class="sxs-lookup"><span data-stu-id="ac636-p107">Visio solutions often have shapes that have a hierarchical relationship, requiring child shapes to move when a parent shape is moved. Following is an example of how you might manage this relationship using the SETATREF function in the ShapeSheet.</span></span> 
  
<span data-ttu-id="ac636-p108">以下公式包含在子形状的“Shape Transform”内容中。我们还定义了用户单元格 User.DeltaX 和 User.DeltaY，用来跟踪父形状的偏移尺寸。这样，子形状会随父形状的移动而移动，并且在移动子形状时仍然保持分级关系。</span><span class="sxs-lookup"><span data-stu-id="ac636-p108">The following formulas are contained in the Shape Transform section of the child shape. Also, we define user cells called User.DeltaX and User.DeltaY, which track the offset dimension from ParentShape. This allows the child shape to move when the parent shape is moved, and also to preserve the hierarchical relationship if the child shape is moved.</span></span>
  
<span data-ttu-id="ac636-161">PinX =SETATREF(User.DeltaX, SETATREFEVAL(SETATREFEXPR() - ParentShape!PinX)) + ParentShape!PinX</span><span class="sxs-lookup"><span data-stu-id="ac636-161">PinX =SETATREF(User.DeltaX, SETATREFEVAL(SETATREFEXPR() - ParentShape!PinX)) + ParentShape!PinX</span></span>
  
<span data-ttu-id="ac636-162">PinY =SETATREF(User.DeltaY, SETATREFEVAL(SETATREFEXPR() - ParentShape!PinY)) + ParentShape!PinY</span><span class="sxs-lookup"><span data-stu-id="ac636-162">PinY =SETATREF(User.DeltaY, SETATREFEVAL(SETATREFEXPR() - ParentShape!PinY)) + ParentShape!PinY</span></span>
  
<span data-ttu-id="ac636-163">当使用用户界面移动子形状时，新的 PinX 和 PinY 值设置为 SETATREFEXPR 函数中的参数。</span><span class="sxs-lookup"><span data-stu-id="ac636-163">When the child shape is moved using the UI, the new PinX and PinY values are set as the parameter in the SETATREFEXPR function.</span></span> <span data-ttu-id="ac636-164">SETATREF 函数计算括在 SETATREFEVAL 的公式，并将 PinX 和 PinY 替换为其结果，然后生成公式分配给用户的单元格引用中的 SETATREF function—User.DeltaX 和 User.DeltaY。</span><span class="sxs-lookup"><span data-stu-id="ac636-164">The SETATREF function evaluates the formula enclosed in SETATREFEVAL and replaces PinX and PinY with their results, and then the resulting formula is assigned to the user cells referenced in the SETATREF function—User.DeltaX and User.DeltaY.</span></span> <span data-ttu-id="ac636-165">最后，SETATREF （User.DeltaX 或 User.DeltaY） 返回的值添加到 ParentShape 计算子形状的 pin 位置的 pin 位置。</span><span class="sxs-lookup"><span data-stu-id="ac636-165">Lastly, the values returned by SETATREF (User.DeltaX or User.DeltaY) are added to the pin location of ParentShape to calculate the child shape's pin location.</span></span>
  

