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
ms.openlocfilehash: 316ac219f548b2459ea2d0ad8cece0f693957fcf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779607"
---
# <a name="about-the-formula-tracing-window"></a><span data-ttu-id="a86e3-103">关于公式跟踪窗口</span><span class="sxs-lookup"><span data-stu-id="a86e3-103">About the Formula Tracing Window</span></span>

<span data-ttu-id="a86e3-104">**“公式跟踪”** 窗口用来向形状开发人员提供与单元格之间相互依赖关系有关的信息 — 这些单元格既包括从属单元格（与给定单元格有从属关系的单元格），也包括引用单元格（给定单元格所依赖的单元格）。</span><span class="sxs-lookup"><span data-stu-id="a86e3-104">The **Formula Tracing** window is designed to provide shape developers with information about cell interdependencies—both dependent cells (cells that have a dependency on a given cell), and precedent cells (cells that a given cell depends on).</span></span> 
  
<span data-ttu-id="a86e3-105">Microsoft Visio ShapeSheet 中的单元格包含值和公式。</span><span class="sxs-lookup"><span data-stu-id="a86e3-105">The cells in a Microsoft Visio ShapeSheet contain values and formulas.</span></span> <span data-ttu-id="a86e3-106">公式反过来，可以为您提供的强大功能来计算中基于另一个单元格的值的一个单元格的值，其他单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="a86e3-106">Formulas can, in turn, have references to other cells, giving you the power to calculate a value in one cell based on another cell's value.</span></span> <span data-ttu-id="a86e3-107">在创建或维护复杂的形状，但是，它可能很难确定所有这些依赖关系，因为公式可以引用在绘图中，任何单元格的单元格中相同的 ShapeSheet 或在绘图中，另一个对象所属于的单元格是否例如，页面、 样式、 master 或另一个形状。</span><span class="sxs-lookup"><span data-stu-id="a86e3-107">When creating or maintaining complex shapes, however, it can be difficult to identify all these interdependencies because a formula can reference any cell in the drawing, whether it's a cell in the same ShapeSheet, or a cell belonging to another object in the drawing, for example, a page, style, master, or another shape.</span></span> 
  
<span data-ttu-id="a86e3-108">**公式跟踪**窗口提供信息以帮助您理解对单元格所做的更改的含义。</span><span class="sxs-lookup"><span data-stu-id="a86e3-108">The **Formula Tracing** window provides information to help you understand the implications of changes you make to cells.</span></span> 
  
## <a name="displaying-the-formula-tracing-window"></a><span data-ttu-id="a86e3-109">显示公式跟踪窗口</span><span class="sxs-lookup"><span data-stu-id="a86e3-109">Displaying the Formula Tracing Window</span></span>

<span data-ttu-id="a86e3-110">若要查看**公式跟踪**窗口处于活动状态，在**ShapeSheet 工具**下在 ShapeSheet 窗口 * * 设计 * * 选项卡的**公式跟踪**组中，单击**显示的窗口**。</span><span class="sxs-lookup"><span data-stu-id="a86e3-110">To view the **Formula Tracing** window, with the ShapeSheet window active, under **ShapeSheet Tools** on the ** Design ** tab, in the **Formula Tracing** group, click **Show Window**.</span></span> <span data-ttu-id="a86e3-111">**公式跟踪**窗口停靠在 ShapeSheet 窗口中默认情况下显示，但可停靠、 浮动或合并与其他可用锚定 ShapeSheet 窗口，例如，**样式资源管理器**窗口锚定的窗口。</span><span class="sxs-lookup"><span data-stu-id="a86e3-111">The **Formula Tracing** window appears docked in the ShapeSheet window by default, but is an anchored window that can be docked, floated or merged with other available anchored ShapeSheet windows, for example, the **Style Explorer** window.</span></span> 
  
## <a name="tracing-dependent-cells"></a><span data-ttu-id="a86e3-112">追踪从属单元格</span><span class="sxs-lookup"><span data-stu-id="a86e3-112">Tracing dependent cells</span></span>

<span data-ttu-id="a86e3-p103">要查看从属于某个特定单元格的单元格的列表，请在 ShapeSheet 窗口中选择该单元格。在本例中，选择了 Width 单元格。</span><span class="sxs-lookup"><span data-stu-id="a86e3-p103">To see a list of cells that are dependent on a particular cell, select that cell in the ShapeSheet window. In this example, the Width cell is selected.</span></span> 
  
![](media/ShapeSheetDependents_UI_01_ZA01039814.gif)
  
<span data-ttu-id="a86e3-115">若要查看其从属单元格，在**公式跟踪**组中，单击**追踪从属单元格**。</span><span class="sxs-lookup"><span data-stu-id="a86e3-115">To view its dependent cells, in the **Formula Tracing**group, click **Trace Dependents**.</span></span>
  
<span data-ttu-id="a86e3-p104">从属于 Width 单元格的所有单元格的列表将出现在 **“公式跟踪”** 窗口中。通过双击 **“公式跟踪”** 窗口中的条目，您可以浏览到该列表中的任何单元格。</span><span class="sxs-lookup"><span data-stu-id="a86e3-p104">A list of all the cells with a dependency on the Width cell appears in the **Formula Tracing** window. You can navigate to any cell in the list by double-clicking its entry in the **Formula Tracing** window.</span></span> 
  
![](media/ShapeSheetDependents_UI_02_ZA01039815.gif)
  
## <a name="tracing-precendent-cells"></a><span data-ttu-id="a86e3-118">跟踪 precendent 单元格</span><span class="sxs-lookup"><span data-stu-id="a86e3-118">Tracing precendent cells</span></span>

<span data-ttu-id="a86e3-p105">要查看某个特定单元格所依赖的单元格列表，请在 ShapeSheet 窗口中选择该单元格。在本例中，选择了 Geometry1.X2 单元格。</span><span class="sxs-lookup"><span data-stu-id="a86e3-p105">To see a list of cells that a particular cell is dependent upon, first select the cell in the ShapeSheet window. In this example, the Geometry1.X2 cell is selected.</span></span> 
  
![](media/ShapeSheetPrecedents_UI_01_ZA01039817.gif)
  
<span data-ttu-id="a86e3-121">若要查看其引用单元格，在**公式跟踪**组中，单击**追踪引用单元格**。</span><span class="sxs-lookup"><span data-stu-id="a86e3-121">To view its precedent cells, in the **Formula Tracing**group, click **Trace Precedents**.</span></span>
  
<span data-ttu-id="a86e3-122">在**公式跟踪**窗口中显示的所有单元格 Geometry1.X2 单元格所依赖于列表。</span><span class="sxs-lookup"><span data-stu-id="a86e3-122">A list of all the cells that the Geometry1.X2 cell is dependent upon appears in the **Formula Tracing** window.</span></span> <span data-ttu-id="a86e3-123">通过双击在**公式跟踪**窗口中的条目，您可以导航到列表中的任意单元格。</span><span class="sxs-lookup"><span data-stu-id="a86e3-123">You can navigate to any cell in the list by double-clicking its entry in the **Formula Tracing** window.</span></span> 
  
![](media/ShapeSheetPrecedents_UI_02_ZA01039818.gif)
  

