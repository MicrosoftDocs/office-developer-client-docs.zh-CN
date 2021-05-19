---
title: 关于“公式跟踪”窗口
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm60118
localization_priority: Normal
ms.assetid: 0cdacd4e-74dc-32c3-2eb2-219bf7fcb532
description: “公式跟踪”窗口用来向形状开发人员提供与单元格之间相互依赖关系有关的信息 — 这些单元格既包括从属单元格（与给定单元格有从属关系的单元格），也包括引用单元格（给定单元格所依赖的单元格）。
ms.openlocfilehash: f5f9d6a7ba3ab7049715d31342cfe7aa68ea053f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345310"
---
# <a name="about-the-formula-tracing-window"></a><span data-ttu-id="ffdef-103">关于“公式跟踪”窗口</span><span class="sxs-lookup"><span data-stu-id="ffdef-103">About the Formula Tracing Window</span></span>

<span data-ttu-id="ffdef-104">**“公式跟踪”** 窗口用来向形状开发人员提供与单元格之间相互依赖关系有关的信息 — 这些单元格既包括从属单元格（与给定单元格有从属关系的单元格），也包括引用单元格（给定单元格所依赖的单元格）。</span><span class="sxs-lookup"><span data-stu-id="ffdef-104">The **Formula Tracing** window is designed to provide shape developers with information about cell interdependencies—both dependent cells (cells that have a dependency on a given cell), and precedent cells (cells that a given cell depends on).</span></span> 
  
<span data-ttu-id="ffdef-105">Microsoft Visio ShapeSheet 中的单元格含有值和公式。</span><span class="sxs-lookup"><span data-stu-id="ffdef-105">The cells in a Microsoft Visio ShapeSheet contain values and formulas.</span></span> <span data-ttu-id="ffdef-106">公式又可以引用其他单元格，从而让你能够基于另一个单元格的值计算一个单元格中的值。</span><span class="sxs-lookup"><span data-stu-id="ffdef-106">Formulas can, in turn, have references to other cells, giving you the power to calculate a value in one cell based on another cell's value.</span></span> <span data-ttu-id="ffdef-107">但是，在创建或维护复杂形状时，可能很难确定所有这些相互依赖关系，因为公式可以引用绘图中的任何单元格，无论是同一 ShapeSheet 中的单元格，还是属于绘图中的其他对象（例如，页面、样式、主控形状或其他形状）的单元格。</span><span class="sxs-lookup"><span data-stu-id="ffdef-107">When creating or maintaining complex shapes, however, it can be difficult to identify all these interdependencies because a formula can reference any cell in the drawing, whether it's a cell in the same ShapeSheet, or a cell belonging to another object in the drawing, for example, a page, style, master, or another shape.</span></span> 
  
<span data-ttu-id="ffdef-108">" **公式跟踪** "窗口提供可帮助您了解对单元格所做的更改的含义的信息。</span><span class="sxs-lookup"><span data-stu-id="ffdef-108">The **Formula Tracing** window provides information to help you understand the implications of changes you make to cells.</span></span> 
  
## <a name="displaying-the-formula-tracing-window"></a><span data-ttu-id="ffdef-109">显示公式跟踪窗口</span><span class="sxs-lookup"><span data-stu-id="ffdef-109">Displaying the Formula Tracing Window</span></span>

<span data-ttu-id="ffdef-110">若要查看"**公式跟踪**"窗口，并且 ShapeSheet 窗口处于活动状态，请在\*\* Design \*\* 选项卡上的 **"ShapeSheet 工具**"下的"公式跟踪"组中，单击"**显示窗口"。** </span><span class="sxs-lookup"><span data-stu-id="ffdef-110">To view the **Formula Tracing** window, with the ShapeSheet window active, under **ShapeSheet Tools** on the \*\* Design \*\* tab, in the **Formula Tracing** group, click **Show Window**.</span></span> <span data-ttu-id="ffdef-111">默认情况下，"公式跟踪"窗口停靠在 ShapeSheet 窗口中，但该窗口是一个锚定窗口，可以停靠、浮动或与其他可用的锚定 ShapeSheet 窗口（例如，"样式资源管理器"窗口）合并。</span><span class="sxs-lookup"><span data-stu-id="ffdef-111">The **Formula Tracing** window appears docked in the ShapeSheet window by default, but is an anchored window that can be docked, floated or merged with other available anchored ShapeSheet windows, for example, the **Style Explorer** window.</span></span> 
  
## <a name="tracing-dependent-cells"></a><span data-ttu-id="ffdef-112">追踪从属单元格</span><span class="sxs-lookup"><span data-stu-id="ffdef-112">Tracing dependent cells</span></span>

<span data-ttu-id="ffdef-p103">要查看从属于某个特定单元格的单元格的列表，请在 ShapeSheet 窗口中选择该单元格。在本例中，选择了 Width 单元格。</span><span class="sxs-lookup"><span data-stu-id="ffdef-p103">To see a list of cells that are dependent on a particular cell, select that cell in the ShapeSheet window. In this example, the Width cell is selected.</span></span> 
  
![已选择 Width 单元格](media/ShapeSheetDependents_UI_01_ZA01039814.gif)
  
<span data-ttu-id="ffdef-116">若要查看其从属单元格，请在"**公式** 跟踪"组中，单击"**追踪从属单元格"。**</span><span class="sxs-lookup"><span data-stu-id="ffdef-116">To view its dependent cells, in the **Formula Tracing** group, click **Trace Dependents**.</span></span>
  
<span data-ttu-id="ffdef-p104">从属于 Width 单元格的所有单元格的列表将出现在 **“公式跟踪”** 窗口中。通过双击 **“公式跟踪”** 窗口中的条目，您可以浏览到该列表中的任何单元格。</span><span class="sxs-lookup"><span data-stu-id="ffdef-p104">A list of all the cells with a dependency on the Width cell appears in the **Formula Tracing** window. You can navigate to any cell in the list by double-clicking its entry in the **Formula Tracing** window.</span></span> 
  
![Width 单元格上具有依赖项的所有单元格都显示在"公式跟踪"窗口中](media/ShapeSheetDependents_UI_02_ZA01039815.gif)
  
## <a name="tracing-precendent-cells"></a><span data-ttu-id="ffdef-120">跟踪预先审查的单元格</span><span class="sxs-lookup"><span data-stu-id="ffdef-120">Tracing precendent cells</span></span>

<span data-ttu-id="ffdef-p105">要查看某个特定单元格所依赖的单元格列表，请在 ShapeSheet 窗口中选择该单元格。在本例中，选择了 Geometry1.X2 单元格。</span><span class="sxs-lookup"><span data-stu-id="ffdef-p105">To see a list of cells that a particular cell is dependent upon, first select the cell in the ShapeSheet window. In this example, the Geometry1.X2 cell is selected.</span></span> 
  
![选择 Geometry1.X2 单元格](media/ShapeSheetPrecedents_UI_01_ZA01039817.gif)
  
<span data-ttu-id="ffdef-124">若要查看其引用单元格，请在"**公式** 跟踪"组中，单击"**追踪引用单元格"。**</span><span class="sxs-lookup"><span data-stu-id="ffdef-124">To view its precedent cells, in the **Formula Tracing** group, click **Trace Precedents**.</span></span>
  
<span data-ttu-id="ffdef-125">Geometry1.X2 单元格所依赖的所有单元格的列表将显示在" **公式** 跟踪"窗口中。</span><span class="sxs-lookup"><span data-stu-id="ffdef-125">A list of all the cells that the Geometry1.X2 cell is dependent upon appears in the **Formula Tracing** window.</span></span> <span data-ttu-id="ffdef-126">通过双击 **“公式跟踪”** 窗口中的条目，您可以浏览到该列表中的任何单元格。</span><span class="sxs-lookup"><span data-stu-id="ffdef-126">You can navigate to any cell in the list by double-clicking its entry in the **Formula Tracing** window.</span></span> 
  
![Geometry1.X2 单元格所依赖的所有单元格都显示在"公式跟踪"窗口中](media/ShapeSheetPrecedents_UI_02_ZA01039818.gif)
  

