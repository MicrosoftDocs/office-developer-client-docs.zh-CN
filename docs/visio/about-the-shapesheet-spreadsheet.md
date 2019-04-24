---
title: 关于 ShapeSheet 电子表格
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm82251822
localization_priority: Normal
ms.assetid: f403890d-4a3a-bacc-53d7-1b9920b23639
description: Microsoft Visio 中的每个元素（每个文档、绘图页、样式、形状、组合、组合中的形状或对象、主控形状、来自其他程序的对象、参考线以及辅助点）都具有用来保存与该对象有关的信息的 ShapeSheet 电子表格。此电子表格包含诸如高度、宽度、角度、颜色以及其他决定形状的外观和行为的属性信息。
ms.openlocfilehash: 37b2ae10b1f511197af5ccf739de91edb74e7819
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345153"
---
# <a name="about-the-shapesheet-spreadsheet"></a><span data-ttu-id="52c21-104">关于 ShapeSheet 电子表格</span><span class="sxs-lookup"><span data-stu-id="52c21-104">About the ShapeSheet Spreadsheet</span></span>

<span data-ttu-id="52c21-p102">Microsoft Visio 中的每个元素（每个文档、绘图页、样式、形状、组合、组合中的形状或对象、主控形状、来自其他程序的对象、参考线以及辅助点）都具有用来保存与该对象有关的信息的 ShapeSheet 电子表格。此电子表格包含诸如高度、宽度、角度、颜色以及其他决定形状的外观和行为的属性信息。</span><span class="sxs-lookup"><span data-stu-id="52c21-p102">Everything in Microsoft Visio, every document, page, style, shape, group, shape or object within a group, master, object from another program, guide, and guide point, has a ShapeSheet spreadsheet where information about that object is stored. This spreadsheet contains information such as height, width, angle, color, and other attributes that determine the shape's appearance and behavior.</span></span>
  
<span data-ttu-id="52c21-p103">作为一名形状开发人员，您需要精确控制所创建的形状的外观和行为。您可以通过在形状的 ShapeSheet 中编辑它来改变其默认行为并增强其功能，可通过 ShapeSheet 窗口或以编程的方式访问该电子表格。</span><span class="sxs-lookup"><span data-stu-id="52c21-p103">As a shape developer, you need precise control over the appearance and behavior of the shapes you create. You can change a shape's default behavior and enhance what it can do by editing it in its ShapeSheet, which you can access in a ShapeSheet window or programmatically.</span></span>
  
## <a name="viewing-an-object-in-a-shapesheet-window"></a><span data-ttu-id="52c21-109">在 ShapeSheet 窗口中查看对象</span><span class="sxs-lookup"><span data-stu-id="52c21-109">Viewing an object in a ShapeSheet window</span></span>

<span data-ttu-id="52c21-110">Visio 绘图窗口和 ShapeSheet 窗口只不过是同一形状的不同视图。</span><span class="sxs-lookup"><span data-stu-id="52c21-110">The Visio drawing window and ShapeSheet window are simply different views of the same shape.</span></span>
  
- <span data-ttu-id="52c21-111">当您在绘图窗口中查看一个形状时，您看到的是根据其 ShapeSheet 中的公式显示的图形外观和行为。</span><span class="sxs-lookup"><span data-stu-id="52c21-111">When you view a shape in a drawing window, you see it rendered graphically and behaving according to the formulas in its ShapeSheet.</span></span>
    
- <span data-ttu-id="52c21-112">当您在 ShapeSheet 窗口中查看一个形状时，您将看到决定其在绘图页上的外观和行为的基本公式。</span><span class="sxs-lookup"><span data-stu-id="52c21-112">When you view a shape in a ShapeSheet window, you see the underlying formulas that determine how it looks and behaves on the drawing page.</span></span>
    
<span data-ttu-id="52c21-p104">您可以同时查看 ShapeSheet 窗口和绘图窗口，并且当您在 ShapeSheet 窗口中操作单元格时，可以看到绘图窗口中的形状发生相应变化，反之亦然。例如，当您使用指针移动形状时，“Shape Transform”内容中形状的 PinX 和 PinY 公式会发生改变，以反映形状在绘图页上的新位置。</span><span class="sxs-lookup"><span data-stu-id="52c21-p104">You can view a ShapeSheet window and a drawing window simultaneously and see the shape change in the drawing window as you manipulate cells in its ShapeSheet window or vice versa. For example, when you move the shape with the pointer, the shape's PinX and PinY formulas in the Shape Transform section change to reflect its new position on the drawing page.</span></span>
  
## <a name="structure-of-the-shapesheet-window"></a><span data-ttu-id="52c21-115">ShapeSheet 窗口的结构</span><span class="sxs-lookup"><span data-stu-id="52c21-115">Structure of the ShapeSheet window</span></span>

<span data-ttu-id="52c21-116">ShapeSheet 分为*几个部分*, 这些部分控制形状的行为或外观的特定方面, 例如其几何图形或格式。</span><span class="sxs-lookup"><span data-stu-id="52c21-116">A ShapeSheet is divided into  *sections*  that control a particular aspect of a shape's behavior or appearance, for example, its geometry or its formatting.</span></span> <span data-ttu-id="52c21-117">每个部分都包含一个或多个包含*单元格*的*行*。</span><span class="sxs-lookup"><span data-stu-id="52c21-117">Each section contains one or more  *rows*  that contain  *cells*  .</span></span> <span data-ttu-id="52c21-118">每个单元格可以包含一个公式、公式的结果（通常称为单元格值）和可选的错误信息。</span><span class="sxs-lookup"><span data-stu-id="52c21-118">Each cell can contain a formula, its result (commonly called the cell value), and optional error information.</span></span> <span data-ttu-id="52c21-119">根据特定单元格的需要，公式可能是必选的，也可能是可选的。</span><span class="sxs-lookup"><span data-stu-id="52c21-119">A formula may be required or optional, depending on the particular cell.</span></span> <span data-ttu-id="52c21-120">一个单元格的数据（如其公式或值）可以进行局部定义，也可以从形状的主控形状或样式中的等价单元格继承，而后者更为常见一些。</span><span class="sxs-lookup"><span data-stu-id="52c21-120">A cell's data (for example, its formula or value) may be locally defined or, more often, inherited from the equivalent cell in the shape's master or style.</span></span> 
  
<span data-ttu-id="52c21-121">下面的示例显示了编辑栏</span><span class="sxs-lookup"><span data-stu-id="52c21-121">The following example shows the formula bar</span></span> ![编辑栏](media/callout1_ZA01036259.gif)<span data-ttu-id="52c21-123">、节</span><span class="sxs-lookup"><span data-stu-id="52c21-123">, a section</span></span> ![section](media/callout2_ZA01036260.gif)<span data-ttu-id="52c21-125">、单元格</span><span class="sxs-lookup"><span data-stu-id="52c21-125">, a cell</span></span> ![单元](media/callout3_ZA01036261.gif)<span data-ttu-id="52c21-127">以及行</span><span class="sxs-lookup"><span data-stu-id="52c21-127">, and a row</span></span> ![row](media/callout4_ZA01036262.gif) <span data-ttu-id="52c21-129">在 ShapeSheet 窗口中。</span><span class="sxs-lookup"><span data-stu-id="52c21-129">in the ShapeSheet window.</span></span> 
  
![ShapeSheet 窗口](media/ShpSheetRef_CA_02a_ZA07645861.gif)
  
<span data-ttu-id="52c21-131">当您绘制形状时，Visio 将形状记录为与线段连接的水平位置和垂直位置的集合。</span><span class="sxs-lookup"><span data-stu-id="52c21-131">When you draw a shape, Visio records the shape as a collection of horizontal and vertical locations connected with line segments.</span></span> <span data-ttu-id="52c21-132">这些位置 (称为顶点) 记录在形状的 " **Geometry** " 内容的 X 和 Y 单元格中。</span><span class="sxs-lookup"><span data-stu-id="52c21-132">These locations (called vertices) are recorded in the X and Y cells of the shape's **Geometry** section.</span></span> <span data-ttu-id="52c21-133">如以下示例所示, 当您单击形状的 ShapeSheet 窗口的 "**几何图形**" 部分中的 X 和 Y 单元格时, 您将看到一个黑色的框突出显示绘图窗口中形状上的顶点。</span><span class="sxs-lookup"><span data-stu-id="52c21-133">As shown in the following example, when you click the X and Y cells in the **Geometry** section of a shape's ShapeSheet window, you will see a black-bordered box highlighting the vertex on the shape in the drawing window.</span></span> 
  
![黑色带边框的框突出显示绘图窗口中形状上的顶点](media/ShpSheetRef_CA_01_ZA07645860.gif)
  
## <a name="editing-an-object-in-the-shapesheet-window"></a><span data-ttu-id="52c21-135">在 ShapeSheet 窗口中编辑对象</span><span class="sxs-lookup"><span data-stu-id="52c21-135">Editing an object in the ShapeSheet window</span></span>

<span data-ttu-id="52c21-p107">当 ShapeSheet 窗口处于活动状态时，功能区将改为显示在该窗口中工作时特定的选项。选择一个 ShapeSheet 单元格后，将会出现一个公式栏，您可以用它输入和编辑对象的公式。或者，您可以直接在该单元格中工作。</span><span class="sxs-lookup"><span data-stu-id="52c21-p107">When a ShapeSheet window is active, the ribbon changes to display options specific to working in this window. When you select a ShapeSheet cell, a formula bar appears, which you can use to enter and edit an object's formulas. Or, you can work directly in the cell.</span></span>
  
<span data-ttu-id="52c21-139">在 ShapeSheet 窗口中，您可以向形状的工作表添加内容，以便为绘图页上的形状添加新特征。</span><span class="sxs-lookup"><span data-stu-id="52c21-139">In a ShapeSheet window, you can add sections to a shape's sheet to add new characteristics to the shape on the drawing page.</span></span> <span data-ttu-id="52c21-140">例如, 可以添加 "**连接点**" 部分来创建连接。</span><span class="sxs-lookup"><span data-stu-id="52c21-140">For example, you can add a **Connection Points** section to create a connection.</span></span> <span data-ttu-id="52c21-141">当您不再需要某个内容时，可以删除它。</span><span class="sxs-lookup"><span data-stu-id="52c21-141">When you no longer need a section, you can delete it.</span></span> 
  
<span data-ttu-id="52c21-142">还可以向内容添加行，以便保存附加公式或更改形状的外观。</span><span class="sxs-lookup"><span data-stu-id="52c21-142">You also can add rows to sections to hold additional formulas or to change a shape's appearance.</span></span> <span data-ttu-id="52c21-143">例如, 您可以向 " **Geometry** " 内容中添加行, 以向形状添加线段。</span><span class="sxs-lookup"><span data-stu-id="52c21-143">For example, you can add a row to a **Geometry** section to add a segment to a shape.</span></span> <span data-ttu-id="52c21-144">同样，您也可以删除不再需要的行。</span><span class="sxs-lookup"><span data-stu-id="52c21-144">Similarly, you can delete rows you no longer need.</span></span> 
  
<span data-ttu-id="52c21-p110">您可以在单元格中显示公式或者值。在输入新公式、编辑现有公式或查看单元格中公式的相互关系时，显示公式。值是 Visio 对单元格的公式求值后得到的结果。您可以显示单元格中的值以便查看求值结果。</span><span class="sxs-lookup"><span data-stu-id="52c21-p110">You can display either formulas or values in cells. Display formulas when you are entering new formulas, editing existing formulas, or to see how formulas in cells relate to each other. A value is the result you get when Visio evaluates a cell's formula. You can display values in cells to see the result of an evaluation.</span></span>
  
## <a name="additional-shapesheet-references"></a><span data-ttu-id="52c21-149">其他 ShapeSheet 引用</span><span class="sxs-lookup"><span data-stu-id="52c21-149">Additional ShapeSheet references</span></span>

<span data-ttu-id="52c21-150">有关 shapesheet 中特定的节、行或单元格的详细信息, 请参阅此[ShapeSheet 引用](reference-visio-shapesheet.md)中的相应文章。</span><span class="sxs-lookup"><span data-stu-id="52c21-150">For details on a particular section, row, or cell in the ShapeSheet, view the corresponding article in this [ShapeSheet Reference](reference-visio-shapesheet.md).</span></span>
  
<span data-ttu-id="52c21-151">有关以编程方式访问 ShapeSheet 电子表格的详细信息，请参阅“Microsoft Visio 自动化参考”。</span><span class="sxs-lookup"><span data-stu-id="52c21-151">For details on programmatically accessing the ShapeSheet spreadsheet, see the Microsoft Visio Automation Reference.</span></span>
  

