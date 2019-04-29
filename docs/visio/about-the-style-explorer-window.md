---
title: 关于“样式资源管理器”窗口
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm60119
localization_priority: Normal
ms.assetid: bfdc1a63-c355-c759-bdfa-ce27e3ad10e7
description: 借助“样式资源管理器”窗口，形状开发人员可以迅速判断出哪些形状单元格继承了给定样式，或者给定单元格继承了其值的样式。
ms.openlocfilehash: 55800b692443bae3720b433e5a6178f2709d3675
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431783"
---
# <a name="about-the-style-explorer-window"></a><span data-ttu-id="212d7-103">关于“样式资源管理器”窗口</span><span class="sxs-lookup"><span data-stu-id="212d7-103">About the Style Explorer Window</span></span>

<span data-ttu-id="212d7-104">借助 **“样式资源管理器”** 窗口，形状开发人员可以迅速判断出哪些形状单元格继承了给定样式，或者给定单元格继承了其值的样式。</span><span class="sxs-lookup"><span data-stu-id="212d7-104">The **Style Explorer** window provides shape developers with a quick way to determine which shape cells inherit from a given style, or the style from which a given cell inherits its value.</span></span> 
  
<span data-ttu-id="212d7-p101">可以应用于形状的格式属性的集合称为样式。在 Microsoft Visio 中，作为确保在形状中保持一致性的有效方法，单独的样式可以定义文本、线条和填充属性。此外，还可以为任何一类属性（文本、线条或填充）或任意的属性组合定义样式。</span><span class="sxs-lookup"><span data-stu-id="212d7-p101">Styles are named collections of formatting attributes that you can apply to a shape. In Microsoft Visio, a single style can define text, line, and fill attributes as an efficient way to ensure consistency in your shapes. Additionally, you can also define a style for any one class of attribute (text, line, or fill) or any combination of attributes.</span></span> 
  
<span data-ttu-id="212d7-108">与将格式属性分别应用于形状不同，从样式获取格式的形状不仅可以确保一致性，还能在创建、移动、缩放或旋转时更好地进行响应。</span><span class="sxs-lookup"><span data-stu-id="212d7-108">Unlike shapes to which you've applied formatting attributes individually, shapes that derive their formatting from a style not only ensure consistency but also respond better when they are created, moved, scaled, or rotated.</span></span> 
  
<span data-ttu-id="212d7-109">"**样式资源管理器**" 窗口提供了您需要了解的信息, 以便更好地了解对形状所做更改的影响。</span><span class="sxs-lookup"><span data-stu-id="212d7-109">The **Style Explorer** window provides the information you need to understand better the implications of changes you make to shapes.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="212d7-110">ShapeSheet 窗口中黑色的单元格值是继承而来；而蓝色的值是局部的。</span><span class="sxs-lookup"><span data-stu-id="212d7-110">Cell values that appear black in the ShapeSheet window are inherited; those that appear blue are local.</span></span> 
  
## <a name="using-the-style-explorer-window"></a><span data-ttu-id="212d7-111">使用“样式资源管理器”窗口</span><span class="sxs-lookup"><span data-stu-id="212d7-111">Using the Style Explorer window</span></span>

<span data-ttu-id="212d7-112">若要查看 "**样式资源管理器**" 窗口, 在 shapesheet 窗口处于活动状态时, 在 " **shapesheet 工具设计**" 选项卡上的 "**视图**" 组中选择 "**样式资源管理器**"</span><span class="sxs-lookup"><span data-stu-id="212d7-112">To view the **Style Explorer** window, with the ShapeSheet window active, on the **ShapeSheet Tools Design** tab, in the **View** group, select **Style Explorer**.</span></span> <span data-ttu-id="212d7-113">默认情况下, "**样式资源管理器**" 窗口显示为停靠在 ShapeSheet 窗口中, 但它是一个锚定窗口, 可停靠、浮动或与其他可用的定位 ShapeSheet 窗口合并, 例如, "**公式跟踪**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="212d7-113">The **Style Explorer** window appears docked in the ShapeSheet window by default, but is an anchored window that can be docked, floated, or merged with other available anchored ShapeSheet windows, for example, the **Formula Tracing** window.</span></span> <span data-ttu-id="212d7-114">**“样式资源管理器”** 窗口显示当前绘图中定义的所有样式的树视图。</span><span class="sxs-lookup"><span data-stu-id="212d7-114">The **Style Explorer** window contains a treeview display of all the styles defined in the current drawing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="212d7-115">要获取关于某种样式的信息，您可以在 **“样式资源管理器”** 窗口中右击该样式，以查看其 ShapeSheet。</span><span class="sxs-lookup"><span data-stu-id="212d7-115">To get information about a style, you can right-click the style in the **Style Explorer** window to view its ShapeSheet.</span></span> 
  
<span data-ttu-id="212d7-116">**“样式资源管理器”** 窗口提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="212d7-116">The **Style Explorer** window provides the following information:</span></span> 
  
- <span data-ttu-id="212d7-117">从所选样式继承其值的单元格。在 **“样式资源管理器”** 窗口中选择某一样式后，ShapeSheet 窗口中继承该样式的所有单元格在显示时将不含影线，而未继承该样式的单元格将显示淡淡的影线。</span><span class="sxs-lookup"><span data-stu-id="212d7-117">The cells that inherit their values from a selected style.When you select a style in the **Style Explorer** window, all cells in the ShapeSheet window that inherit from that style appear without hatching, while cells that do not inherit from that style appear lightly hatched.</span></span> 
    
- <span data-ttu-id="212d7-118">选定单元格将继承其值的样式。选择某个 ShapeSheet 单元格后，该单元格从其继承值的样式将显示在 ShapeSheet 窗口下的任务栏上。</span><span class="sxs-lookup"><span data-stu-id="212d7-118">The style from which a selected cell inherits its value.When you select a ShapeSheet cell, the style from which it inherits its value is displayed on the taskbar under the ShapeSheet window.</span></span> 
    

