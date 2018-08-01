---
title: 关于公式
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm82251823
localization_priority: Normal
ms.assetid: ec0de3e1-21dc-c5d6-2c2a-d5fef80d89bd
description: 控制形状动作的关键是编写定义所需行为的公式。您可以编辑某个单元格的公式来更改单元格的值，并因此改变某个特定形状的行为。例如，更改“Shape Transform”内容的 Height 单元格所包含的公式可以改变形状的高度。
ms.openlocfilehash: 7df5ffe4d3dc32bcd5209bde353c39a92c7d422b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779597"
---
# <a name="about-formulas"></a><span data-ttu-id="7da36-105">关于公式</span><span class="sxs-lookup"><span data-stu-id="7da36-105">About Formulas</span></span>

<span data-ttu-id="7da36-p102">控制形状动作的关键是编写定义所需行为的公式。您可以编辑某个单元格的公式来更改单元格的值，并因此改变某个特定形状的行为。例如，更改“Shape Transform”内容的 Height 单元格所包含的公式可以改变形状的高度。</span><span class="sxs-lookup"><span data-stu-id="7da36-p102">The key to controlling shape actions is to write formulas that define the behavior you want. You can edit a cell's formula to change the value of the cell and, as a result, change a particular shape's behavior. For example, the Height cell in the Shape Transform section contains a formula that you can change to alter the shape's height.</span></span>
  
<span data-ttu-id="7da36-p103">Microsoft Visio 公式在很多方面都类似于典型的电子表格公式。Visio 将单元格中的所有内容（甚至是数值或简单的单元格引用）都看作公式。</span><span class="sxs-lookup"><span data-stu-id="7da36-p103">Microsoft Visio formulas are similar to typical spreadsheet formulas in many ways. Visio regards anything in a cell, even if it is a numeric value or simple cell reference, as a formula.</span></span>
  
<span data-ttu-id="7da36-p104">单元格中的公式可以从主控形状或样式中的等价单元格继承，也可以进行局部定义。Visio 会对公式求值，然后将结果转化为适合于单元格的值和单位。在 ShapeSheet 窗口中，您可以将单元格内容显示为公式或值。</span><span class="sxs-lookup"><span data-stu-id="7da36-p104">A formula in a cell can be inherited from the equivalent cell of a master or a style or defined locally. Visio evaluates the formula and then converts the results to an appropriate value and appropriate units for the cell. In a ShapeSheet window, you can display cell contents as either formulas or values.</span></span>
  
## <a name="elements-of-a-formula"></a><span data-ttu-id="7da36-114">公式的元素</span><span class="sxs-lookup"><span data-stu-id="7da36-114">Elements of a formula</span></span>

<span data-ttu-id="7da36-p105">公式总是以一个自动插入的等号开始。公式可以包含以下任何元素：</span><span class="sxs-lookup"><span data-stu-id="7da36-p105">A formula always starts with an equal sign, which is inserted automatically. A formula can include any of the following elements:</span></span>
  
- <span data-ttu-id="7da36-117">数字</span><span class="sxs-lookup"><span data-stu-id="7da36-117">Numbers</span></span>
    
- <span data-ttu-id="7da36-118">坐标</span><span class="sxs-lookup"><span data-stu-id="7da36-118">Coordinates</span></span>
    
- <span data-ttu-id="7da36-119">布尔值</span><span class="sxs-lookup"><span data-stu-id="7da36-119">Boolean values</span></span>
    
- <span data-ttu-id="7da36-120">运算符</span><span class="sxs-lookup"><span data-stu-id="7da36-120">Operators</span></span>
    
- <span data-ttu-id="7da36-121">函数</span><span class="sxs-lookup"><span data-stu-id="7da36-121">Functions</span></span>
    
- <span data-ttu-id="7da36-122">字符串</span><span class="sxs-lookup"><span data-stu-id="7da36-122">Strings</span></span>
    
- <span data-ttu-id="7da36-123">单元格引用</span><span class="sxs-lookup"><span data-stu-id="7da36-123">Cell references</span></span>
    
- <span data-ttu-id="7da36-124">度量单位</span><span class="sxs-lookup"><span data-stu-id="7da36-124">Units of measure</span></span>
    
## <a name="default-formulas"></a><span data-ttu-id="7da36-125">默认的公式</span><span class="sxs-lookup"><span data-stu-id="7da36-125">Default formulas</span></span>

<span data-ttu-id="7da36-p106">创建形状时，默认情况下 Visio 会为它创建公式。若要查看这些默认公式，请绘制一个简单的形状（如矩形、椭圆或直线），然后打开它的 ShapeSheet 窗口（在[“开发工具”](run-in-developer-mode-display-the-developer-tab.md)选项卡上单击 **“显示 ShapeSheet”**）。</span><span class="sxs-lookup"><span data-stu-id="7da36-p106">When you create a shape, Visio creates formulas for it by default. To see what the default formulas are, draw a simple shape (such as a rectangle, ellipse, or straight line) and open its ShapeSheet window (on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, click **Show ShapeSheet**).</span></span>
  
## <a name="inherited-formulas"></a><span data-ttu-id="7da36-128">继承的公式</span><span class="sxs-lookup"><span data-stu-id="7da36-128">Inherited formulas</span></span>

<span data-ttu-id="7da36-p107">Visio 将尽可能继承公式。实例总是从其文档模具上的主控形状继承公式并从与绘图一起存储的样式定义继承格式，而不是在实例中制作每个公式的本地副本。这种行为产生多个较小的文件，但仍然允许对主控形状的公式或样式定义所做的更改传播到所有实例。</span><span class="sxs-lookup"><span data-stu-id="7da36-p107">Visio inherits formulas whenever possible. Rather than make a local copy of every formula in the instance, an instance inherits formulas from its master on the document stencil and inherits formatting from the style definition stored with the drawing. This behavior results in smaller files, but also allows changes to the master's formulas or the style definition to be propagated to all instances.</span></span>
  
<span data-ttu-id="7da36-132">单元格中的黑色文本指示继承的公式。</span><span class="sxs-lookup"><span data-stu-id="7da36-132">Black text in a cell indicates an inherited formula.</span></span>
  
## <a name="local-formulas"></a><span data-ttu-id="7da36-133">局部公式</span><span class="sxs-lookup"><span data-stu-id="7da36-133">Local formulas</span></span>

<span data-ttu-id="7da36-p108">当您为实例编写局部公式时，您就用局部替换值替代了单元格中的继承的公式。由于该实例使用局部替换值阻止了单元格继承公式，因此将来在主控形状或样式中对此单元格的更改不会影响该实例。</span><span class="sxs-lookup"><span data-stu-id="7da36-p108">When you write a local formula for an instance, you are replacing the inherited formula in the cell with a local override. Future changes to that cell in the master or style do not affect this instance because it has blocked inheritance for the cell with the local override.</span></span>
  
<span data-ttu-id="7da36-136">应用样式会删除相关单元格中的所有局部公式，除非使用 GUARD 函数进行保护。</span><span class="sxs-lookup"><span data-stu-id="7da36-136">Applying a style deletes all local formulas in the related cells unless you use the GUARD function to protect them.</span></span>
  
<span data-ttu-id="7da36-137">蓝色文本指示局部公式，它或者是 ShapeSheet 窗口中编辑公式的结果，或者是因对形状作出改动而使 Visio 重新设置该单元格的公式的结果。</span><span class="sxs-lookup"><span data-stu-id="7da36-137">Blue text indicates a local formula, either the result of editing the formula in a ShapeSheet window or some change to the shape that caused Visio to reset the formula for that cell.</span></span>
  
## <a name="automatic-updates-to-formulas"></a><span data-ttu-id="7da36-138">自动更新公式</span><span class="sxs-lookup"><span data-stu-id="7da36-138">Automatic updates to formulas</span></span>

 <span data-ttu-id="7da36-p109">Visio 在您改变绘图中的某个形状时会自动更新某些单元格。这意味着在某些情况下您输入的公式可能被替换。例如，如果您拖动角手柄调整形状的大小时，Visio 会重置 PinX、PinY、Width 和 Height 单元格中的公式。</span><span class="sxs-lookup"><span data-stu-id="7da36-p109">Visio automatically updates certain cells whenever you change a shape in a drawing. This means that under some circumstances formulas you enter can be replaced. For example, if you drag a corner handle to resize a shape, Visio resets formulas in the PinX, PinY, Width, and Height cells.</span></span> 
  
<span data-ttu-id="7da36-142">如有必要，可以使用 GUARD 函数防止对公式进行改动。</span><span class="sxs-lookup"><span data-stu-id="7da36-142">If necessary, you can protect formulas against changes by using the GUARD function.</span></span>
  

