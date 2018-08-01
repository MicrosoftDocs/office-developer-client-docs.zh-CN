---
title: RelMoveTo 行（“Geometry”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 04a0ba9f-48dd-488f-9c87-3890a12adf89
description: 包含 x 和 y 坐标的形状或 x 的第一个顶点-和 y-中的高度和宽度的形状的相对路径，中断后的第一个顶点的坐标。
ms.openlocfilehash: 77b3e731bfd1f35abe34ffbf3155b57133e56412
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781067"
---
# <a name="relmoveto-row-geometry-section"></a><span data-ttu-id="cc8fc-103">RelMoveTo 行（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="cc8fc-103">RelMoveTo Row (Geometry Section)</span></span>

<span data-ttu-id="cc8fc-104">包含*x*和*y*坐标的形状或*x*的第一个顶点-和*y* -中的高度和宽度的形状的相对路径，中断后的第一个顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="cc8fc-104">Contains the  *x*  - and  *y*  -coordinates of the first vertex of a shape or the  *x*  - and  *y*  -coordinates of the first vertex after a break in a path, relative to the height and width of the shape.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cc8fc-105">**RelMoveTo**行仅可保持在.vsdx、.vsdm、.vstx、.vstm、.vssx 和.vssm 文件格式。</span><span class="sxs-lookup"><span data-stu-id="cc8fc-105">A **RelMoveTo** row can only be persisted in the .vsdx, .vsdm, .vstx, .vstm, .vssx, and .vssm file formats.</span></span> <span data-ttu-id="cc8fc-106">为 Visio 2003 2010年格式保存文件后， **RelMoveTo**行转换为某一[MoveTo](moveto-row-geometry-section.md)行。</span><span class="sxs-lookup"><span data-stu-id="cc8fc-106">When a file is saved to the Visio 2003-2010 formats, the **RelMoveTo** row is converted to a [MoveTo](moveto-row-geometry-section.md) row.</span></span> 
  
<span data-ttu-id="cc8fc-107">**RelMoveTo**行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="cc8fc-107">A **RelMoveTo** row contains the following cells.</span></span> 
  
|<span data-ttu-id="cc8fc-108">**Cell**</span><span class="sxs-lookup"><span data-stu-id="cc8fc-108">**Cell**</span></span>|<span data-ttu-id="cc8fc-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="cc8fc-109">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="cc8fc-110">X</span><span class="sxs-lookup"><span data-stu-id="cc8fc-110">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="cc8fc-111">如果**RelMoveTo**行是该节中的第一行，则 X 单元格表示*x* -相对于形状的宽度形状的第一个顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="cc8fc-111">If the **RelMoveTo** row is the first row in the section, the X cell represents the  *x*  -coordinate of the first vertex of a shape relative to the width of the shape.</span></span> <span data-ttu-id="cc8fc-112">如果**RelMoveTo**行出现在两行之间，则 X 单元格表示*x* -路径中断开后的第一个顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="cc8fc-112">If the **RelMoveTo** row appears between two rows, the X cell represents the  *x*  -coordinate of the first vertex after the break in the path.</span></span>  <br/> |
|[<span data-ttu-id="cc8fc-113">Y</span><span class="sxs-lookup"><span data-stu-id="cc8fc-113">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="cc8fc-114">Y 单元格**RelMoveTo**行是否部分中的第一行，代表*y* -形状的第一个顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="cc8fc-114">If the **RelMoveTo** row is the first row in the section, the Y cell represents the  *y*  -coordinate of the first vertex of a shape.</span></span> <span data-ttu-id="cc8fc-115">如果**RelMoveTo**行出现在两行之间，则 Y 单元格表示*y* -路径中断开后的第一个顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="cc8fc-115">If the **RelMoveTo** row appears between two rows, the Y cell represents the  *y*  -coordinate of the first vertex after the break in the path.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cc8fc-116">说明</span><span class="sxs-lookup"><span data-stu-id="cc8fc-116">Remarks</span></span>

<span data-ttu-id="cc8fc-117">**RelMoveTo**行中的值为等同于乘以的宽度和高度形状的[MoveTo](moveto-row-geometry-section.md)行中的值。</span><span class="sxs-lookup"><span data-stu-id="cc8fc-117">Values in the **RelMoveTo** row are equivalent to values in a [MoveTo](moveto-row-geometry-section.md) row that are multiplied by the width and height of the shape.</span></span> <span data-ttu-id="cc8fc-118">例如： **RelMoveTo**行其中**X**单元格的值是"0"，则**Y**单元格的值是"0.5"可以替换为**MoveTo**行，其中**X**单元格的值是公式"宽度*0" 和**Y**单元格公式"高度*0.5。"</span><span class="sxs-lookup"><span data-stu-id="cc8fc-118">For example: a **RelMoveTo** row where the value of the **X** cell is "0" and the value of the **Y** cell is "0.5" could be replaced with **MoveTo** row where the value of the **X** cell is the formula "Width*0" and the **Y** cell is the formula "Height*0.5."</span></span> 
  
<span data-ttu-id="cc8fc-119">**RelMoveTo**行包含*x*和*y* -如果 MoveTo 行是部分中的第一行的形状的第一个顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="cc8fc-119">The **RelMoveTo** row contains the  *x*  - and  *y*  -coordinates of the first vertex for the shape if the MoveTo row is the first row in the section.</span></span> <span data-ttu-id="cc8fc-120">通常，这是放置时绘制形状，并且它不一定是对应于一维形状的起点的第一个顶点。</span><span class="sxs-lookup"><span data-stu-id="cc8fc-120">Usually this is the first vertex placed when the shape was drawn, and it does not necessarily correspond to the begin point of a 1-D shape.</span></span> 
  
<span data-ttu-id="cc8fc-121">**Geometry**内容必须**MoveTo**或开头**RelMoveTo**一行，但您也可以使用**RelMoveTo**行和**MoveTo**行表示中的相对于形状的宽度和高度的形状的路径描间隙。</span><span class="sxs-lookup"><span data-stu-id="cc8fc-121">A **Geometry** section must begin with a **MoveTo** or a **RelMoveTo** row, but you can also use the **RelMoveTo** row and **MoveTo** row to represent a gap in the stroking of a shape's path relative to the shape's width and height.</span></span> <span data-ttu-id="cc8fc-122">但是，当路径用于定义填充区域的边界，此间隙被解释为直线段。</span><span class="sxs-lookup"><span data-stu-id="cc8fc-122">However, when the path is used to define the boundary of a filled region, this gap is interpreted as a straight line segment.</span></span> <span data-ttu-id="cc8fc-123">插入此类间隙、 两行之间插入一行和到**RelMoveTo**更改行类型。</span><span class="sxs-lookup"><span data-stu-id="cc8fc-123">To insert such a gap, insert a row between two rows and change the row type to **RelMoveTo**.</span></span> <span data-ttu-id="cc8fc-124">如果两行之间有**RelMoveTo**行，它包含*x*和*y* -形状的路径中断开后面的行的第一个顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="cc8fc-124">If the **RelMoveTo** row is between two rows, it contains the  *x*  - and  *y*  -coordinates of the first vertex of the line after the break in the shape's path.</span></span> 
  

