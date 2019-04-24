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
description: 包含形状的第一个顶点的 x 坐标和 y 坐标, 或表示路径中的断点后的第一个顶点的 x 坐标和 y 坐标。
ms.openlocfilehash: fc414093348b8da04fa3503053584395976982dd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283856"
---
# <a name="moveto-row-geometry-section"></a><span data-ttu-id="997ed-103">MoveTo 行（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="997ed-103">MoveTo Row (Geometry Section)</span></span>

<span data-ttu-id="997ed-104">包含形状的第一个顶点的*x*坐标和*y*坐标, 或表示路径中的断点后的第一个顶点的*x*坐标和*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="997ed-104">Contains the  *x*  - and  *y*  -coordinates of the first vertex of a shape, or represents the  *x*  - and  *y*  -coordinates of the first vertex after a break in a path.</span></span> 
  
<span data-ttu-id="997ed-105">**MoveTo**行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="997ed-105">A **MoveTo** row contains the following cells.</span></span> 
  
|<span data-ttu-id="997ed-106">**Cell**</span><span class="sxs-lookup"><span data-stu-id="997ed-106">**Cell**</span></span>|<span data-ttu-id="997ed-107">**Description**</span><span class="sxs-lookup"><span data-stu-id="997ed-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="997ed-108">X</span><span class="sxs-lookup"><span data-stu-id="997ed-108">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="997ed-109">如果**MoveTo**行是该内容中的第一行, 则 X 单元格表示形状的第一个顶点的*X*坐标。</span><span class="sxs-lookup"><span data-stu-id="997ed-109">If the **MoveTo** row is the first row in the section, the X cell represents the  *x*  -coordinate of the first vertex of a shape.</span></span> <span data-ttu-id="997ed-110">如果**MoveTo**行出现在两行之间, 则 X 单元格表示路径中断开处后的第一个顶点的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="997ed-110">If the **MoveTo** row appears between two rows, the X cell represents the  *x*  -coordinate of the first vertex after the break in the path.</span></span>  <br/> |
|[<span data-ttu-id="997ed-111">Y</span><span class="sxs-lookup"><span data-stu-id="997ed-111">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="997ed-112">如果**MoveTo**行是该内容中的第一行, 则 Y 单元格表示形状的第一个顶点的*Y*坐标。</span><span class="sxs-lookup"><span data-stu-id="997ed-112">If the **MoveTo** row is the first row in the section, the Y cell represents the  *y*  -coordinate of the first vertex of a shape.</span></span> <span data-ttu-id="997ed-113">如果**MoveTo**行出现在两行之间, 则 Y 单元格表示路径中断开处后的第一个顶点的*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="997ed-113">If the **MoveTo** row appears between two rows, the Y cell represents the  *y*  -coordinate of the first vertex after the break in the path.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="997ed-114">注解</span><span class="sxs-lookup"><span data-stu-id="997ed-114">Remarks</span></span>

<span data-ttu-id="997ed-115">如果**moveto**行是该内容中的第一行, 则**moveto**行包含形状的第一个顶点的*x*坐标和*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="997ed-115">The **MoveTo** row contains the  *x*  - and  *y*  -coordinates of the first vertex for the shape if the **MoveTo** row is the first row in the section.</span></span> <span data-ttu-id="997ed-116">通常，这就是绘制形状时放置的第一个顶点，而且不一定与一维形状的起点相对应。</span><span class="sxs-lookup"><span data-stu-id="997ed-116">Usually this is the first vertex placed when the shape was drawn, and it does not necessarily correspond to the begin point of a 1-D shape.</span></span> 
  
<span data-ttu-id="997ed-117">"geometry" 内容必须以**RelMoveTo**或**MoveTo**行开头, 但也可以使用**moveto**行和**RelMoveTo**行来表示形状路径的描边间隙。</span><span class="sxs-lookup"><span data-stu-id="997ed-117">A geometry section must begin with either a **RelMoveTo** or a **MoveTo** row, but you can also use the **MoveTo** and **RelMoveTo** rows to represent a gap in the stroking of a shape's path.</span></span> <span data-ttu-id="997ed-118">不过，当该路径用于定义填充区域的边界时，此间隙被解释为直线段。</span><span class="sxs-lookup"><span data-stu-id="997ed-118">However, when the path is used to define the boundary of a filled region, this gap is interpreted as a straight line segment.</span></span> <span data-ttu-id="997ed-119">若要插入这样的间隙, 请在两行之间插入一行, 并将行类型更改为**MoveTo**。</span><span class="sxs-lookup"><span data-stu-id="997ed-119">To insert such a gap, insert a row between two rows and change the row type to **MoveTo**.</span></span> <span data-ttu-id="997ed-120">如果**MoveTo**行在两行之间, 则它包含形状路径中的分隔符后面的行的第一个顶点的*x*坐标和*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="997ed-120">If the **MoveTo** row is between two rows, it contains the  *x*  - and  *y*  -coordinates of the first vertex of the line after the break in the shape's path.</span></span> 
  

