---
title: MoveTo 行（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm3030
localization_priority: Normal
ms.assetid: c5b20257-676c-279d-f730-1b6fbbe98305
description: 包含 x 和 y-第一个形状的顶点坐标或代表 x-和 y-路径中中断后的第一个顶点的坐标。
ms.openlocfilehash: cee62701074269350ae52c6fa7f7aee5cb612f49
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780778"
---
# <a name="moveto-row-geometry-section"></a><span data-ttu-id="683cb-103">MoveTo 行（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="683cb-103">MoveTo Row (Geometry Section)</span></span>

<span data-ttu-id="683cb-104">包含*x*和*y* -第一个形状的顶点坐标或代表*x* -和*y* -路径中中断后的第一个顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="683cb-104">Contains the  *x*  - and  *y*  -coordinates of the first vertex of a shape, or represents the  *x*  - and  *y*  -coordinates of the first vertex after a break in a path.</span></span> 
  
<span data-ttu-id="683cb-105">**MoveTo**行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="683cb-105">A **MoveTo** row contains the following cells.</span></span> 
  
|<span data-ttu-id="683cb-106">**Cell**</span><span class="sxs-lookup"><span data-stu-id="683cb-106">**Cell**</span></span>|<span data-ttu-id="683cb-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="683cb-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="683cb-108">X</span><span class="sxs-lookup"><span data-stu-id="683cb-108">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="683cb-109">如果**MoveTo**行是部分中的第一行，则 X 单元格表示*x*的形状的第一个顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="683cb-109">If the **MoveTo** row is the first row in the section, the X cell represents the  *x*  -coordinate of the first vertex of a shape.</span></span> <span data-ttu-id="683cb-110">如果**MoveTo**行出现在两行之间，则 X 单元格表示*x* -路径中断开后的第一个顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="683cb-110">If the **MoveTo** row appears between two rows, the X cell represents the  *x*  -coordinate of the first vertex after the break in the path.</span></span>  <br/> |
|[<span data-ttu-id="683cb-111">Y</span><span class="sxs-lookup"><span data-stu-id="683cb-111">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="683cb-112">如果**MoveTo**行是部分中的第一行，则 Y 单元格表示*y* -形状的第一个顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="683cb-112">If the **MoveTo** row is the first row in the section, the Y cell represents the  *y*  -coordinate of the first vertex of a shape.</span></span> <span data-ttu-id="683cb-113">如果**MoveTo**行出现在两行之间，则 Y 单元格表示*y* -路径中断开后的第一个顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="683cb-113">If the **MoveTo** row appears between two rows, the Y cell represents the  *y*  -coordinate of the first vertex after the break in the path.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="683cb-114">说明</span><span class="sxs-lookup"><span data-stu-id="683cb-114">Remarks</span></span>

<span data-ttu-id="683cb-115">**MoveTo**行包含*x*和*y* -如果**MoveTo**行是部分中的第一行的形状的第一个顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="683cb-115">The **MoveTo** row contains the  *x*  - and  *y*  -coordinates of the first vertex for the shape if the **MoveTo** row is the first row in the section.</span></span> <span data-ttu-id="683cb-116">通常，这是放置时绘制形状，并且它不一定是对应于一维形状的起点的第一个顶点。</span><span class="sxs-lookup"><span data-stu-id="683cb-116">Usually this is the first vertex placed when the shape was drawn, and it does not necessarily correspond to the begin point of a 1-D shape.</span></span> 
  
<span data-ttu-id="683cb-117">Geometry 内容必须开头**RelMoveTo**或某一**MoveTo**行，但您也可以使用**MoveTo**和**RelMoveTo**行表示中的形状的路径描间隙。</span><span class="sxs-lookup"><span data-stu-id="683cb-117">A geometry section must begin with either a **RelMoveTo** or a **MoveTo** row, but you can also use the **MoveTo** and **RelMoveTo** rows to represent a gap in the stroking of a shape's path.</span></span> <span data-ttu-id="683cb-118">但是，当路径用于定义填充区域的边界，此间隙被解释为直线段。</span><span class="sxs-lookup"><span data-stu-id="683cb-118">However, when the path is used to define the boundary of a filled region, this gap is interpreted as a straight line segment.</span></span> <span data-ttu-id="683cb-119">若要插入此类间隙，两行之间插入一行，并为**MoveTo**更改行类型。</span><span class="sxs-lookup"><span data-stu-id="683cb-119">To insert such a gap, insert a row between two rows and change the row type to **MoveTo**.</span></span> <span data-ttu-id="683cb-120">如果**MoveTo**行是两行之间，它包含*x*和*y* -形状的路径中断开后面的行的第一个顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="683cb-120">If the **MoveTo** row is between two rows, it contains the  *x*  - and  *y*  -coordinates of the first vertex of the line after the break in the shape's path.</span></span> 
  

