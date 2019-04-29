---
title: RelMoveTo 行 ("Geometry" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 04a0ba9f-48dd-488f-9c87-3890a12adf89
description: 包含形状的第一个顶点的 x 坐标和 y 坐标, 或路径中断开点后的第一个顶点的 x 坐标和 y 坐标 (相对于形状的高度和宽度)。
ms.openlocfilehash: 488945dbeeea177514770da57b5f26ac947053a3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414198"
---
# <a name="relmoveto-row-geometry-section"></a><span data-ttu-id="0d5d0-103">RelMoveTo 行 ("Geometry" 部分)</span><span class="sxs-lookup"><span data-stu-id="0d5d0-103">RelMoveTo Row (Geometry Section)</span></span>

<span data-ttu-id="0d5d0-104">包含形状的第一个顶点的*x*坐标和*y*坐标, 或路径中断开点后的第一个顶点的*x*坐标和*y*坐标 (相对于形状的高度和宽度)。</span><span class="sxs-lookup"><span data-stu-id="0d5d0-104">Contains the  *x*  - and  *y*  -coordinates of the first vertex of a shape or the  *x*  - and  *y*  -coordinates of the first vertex after a break in a path, relative to the height and width of the shape.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0d5d0-105">**RelMoveTo**行只能在 .vsdx、.vsdm、.vstx、.vstm、.vssx 和. .vssm 文件格式中持久化。</span><span class="sxs-lookup"><span data-stu-id="0d5d0-105">A **RelMoveTo** row can only be persisted in the .vsdx, .vsdm, .vstx, .vstm, .vssx, and .vssm file formats.</span></span> <span data-ttu-id="0d5d0-106">将文件保存为 Visio 2003-2010 格式时, **RelMoveTo**行将转换为[MoveTo](moveto-row-geometry-section.md)行。</span><span class="sxs-lookup"><span data-stu-id="0d5d0-106">When a file is saved to the Visio 2003-2010 formats, the **RelMoveTo** row is converted to a [MoveTo](moveto-row-geometry-section.md) row.</span></span> 
  
<span data-ttu-id="0d5d0-107">**RelMoveTo**行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="0d5d0-107">A **RelMoveTo** row contains the following cells.</span></span> 
  
|<span data-ttu-id="0d5d0-108">**单元格**</span><span class="sxs-lookup"><span data-stu-id="0d5d0-108">**Cell**</span></span>|<span data-ttu-id="0d5d0-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="0d5d0-109">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="0d5d0-110">X</span><span class="sxs-lookup"><span data-stu-id="0d5d0-110">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="0d5d0-111">如果**RelMoveTo**行是该内容中的第一行, 则 X 单元格表示形状的第一个顶点相对于形状宽度的*X*坐标。</span><span class="sxs-lookup"><span data-stu-id="0d5d0-111">If the **RelMoveTo** row is the first row in the section, the X cell represents the  *x*  -coordinate of the first vertex of a shape relative to the width of the shape.</span></span> <span data-ttu-id="0d5d0-112">如果**RelMoveTo**行出现在两行之间, 则 X 单元格表示路径中断开处后的第一个顶点的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="0d5d0-112">If the **RelMoveTo** row appears between two rows, the X cell represents the  *x*  -coordinate of the first vertex after the break in the path.</span></span>  <br/> |
|[<span data-ttu-id="0d5d0-113">Y</span><span class="sxs-lookup"><span data-stu-id="0d5d0-113">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="0d5d0-114">如果**RelMoveTo**行是该内容中的第一行, 则 Y 单元格表示形状的第一个顶点的*Y*坐标。</span><span class="sxs-lookup"><span data-stu-id="0d5d0-114">If the **RelMoveTo** row is the first row in the section, the Y cell represents the  *y*  -coordinate of the first vertex of a shape.</span></span> <span data-ttu-id="0d5d0-115">如果**RelMoveTo**行出现在两行之间, 则 Y 单元格表示路径中断开处后的第一个顶点的*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="0d5d0-115">If the **RelMoveTo** row appears between two rows, the Y cell represents the  *y*  -coordinate of the first vertex after the break in the path.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0d5d0-116">说明</span><span class="sxs-lookup"><span data-stu-id="0d5d0-116">Remarks</span></span>

<span data-ttu-id="0d5d0-117">**RelMoveTo**行中的值等效于[MoveTo](moveto-row-geometry-section.md)行中与形状的宽度和高度相乘的值。</span><span class="sxs-lookup"><span data-stu-id="0d5d0-117">Values in the **RelMoveTo** row are equivalent to values in a [MoveTo](moveto-row-geometry-section.md) row that are multiplied by the width and height of the shape.</span></span> <span data-ttu-id="0d5d0-118">例如: 一个**RelMoveTo**行, 其中**x**单元格的值为 "0", 而**Y**单元格的值为 "0.5", 则可以替换为**MoveTo**行, 其中**X**单元格的值为公式 "Width*0", 而**y**单元格为公式 "Height*0.5"。</span><span class="sxs-lookup"><span data-stu-id="0d5d0-118">For example: a **RelMoveTo** row where the value of the **X** cell is "0" and the value of the **Y** cell is "0.5" could be replaced with **MoveTo** row where the value of the **X** cell is the formula "Width*0" and the **Y** cell is the formula "Height*0.5."</span></span> 
  
<span data-ttu-id="0d5d0-119">如果 MoveTo 行是该内容中的第一行, 则 " **RelMoveTo** " 行包含形状的第一个顶点的*x*坐标和*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="0d5d0-119">The **RelMoveTo** row contains the  *x*  - and  *y*  -coordinates of the first vertex for the shape if the MoveTo row is the first row in the section.</span></span> <span data-ttu-id="0d5d0-120">通常，这就是绘制形状时放置的第一个顶点，而且不一定与一维形状的起点相对应。</span><span class="sxs-lookup"><span data-stu-id="0d5d0-120">Usually this is the first vertex placed when the shape was drawn, and it does not necessarily correspond to the begin point of a 1-D shape.</span></span> 
  
<span data-ttu-id="0d5d0-121">**Geometry**节必须以**MoveTo**或**RelMoveTo**行开头, 但也可以使用**RelMoveTo**行和**MoveTo**行来表示形状路径相对于形状的宽度和高度的描边之间的间隙。</span><span class="sxs-lookup"><span data-stu-id="0d5d0-121">A **Geometry** section must begin with a **MoveTo** or a **RelMoveTo** row, but you can also use the **RelMoveTo** row and **MoveTo** row to represent a gap in the stroking of a shape's path relative to the shape's width and height.</span></span> <span data-ttu-id="0d5d0-122">不过，当该路径用于定义填充区域的边界时，此间隙被解释为直线段。</span><span class="sxs-lookup"><span data-stu-id="0d5d0-122">However, when the path is used to define the boundary of a filled region, this gap is interpreted as a straight line segment.</span></span> <span data-ttu-id="0d5d0-123">若要插入这样的间隙, 请在两行之间插入一行, 并将行类型更改为**RelMoveTo**。</span><span class="sxs-lookup"><span data-stu-id="0d5d0-123">To insert such a gap, insert a row between two rows and change the row type to **RelMoveTo**.</span></span> <span data-ttu-id="0d5d0-124">如果**RelMoveTo**行在两行之间, 则它包含形状路径中的分隔符后面的行的第一个顶点的*x*坐标和*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="0d5d0-124">If the **RelMoveTo** row is between two rows, it contains the  *x*  - and  *y*  -coordinates of the first vertex of the line after the break in the shape's path.</span></span> 
  

