---
title: SplineStart 行（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm3055
localization_priority: Normal
ms.assetid: 8e327e00-0844-efa4-900b-6954d3b009bb
description: 包含样条第二个控制点的 x 坐标和 y 坐标、第二个节点、第一个节点、最后一个节点和样条的角度。
ms.openlocfilehash: 2ec06619770af4e5dbcc1a763595b6e01a39052b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417474"
---
# <a name="splinestart-row-geometry-section"></a><span data-ttu-id="24005-103">SplineStart 行（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="24005-103">SplineStart Row (Geometry Section)</span></span>

<span data-ttu-id="24005-104">包含样条第二个控制点的*x*坐标和*y*坐标、第二个节点、第一个节点、最后一个节点和样条的角度。</span><span class="sxs-lookup"><span data-stu-id="24005-104">Contains  *x*  - and  *y*  -coordinates for a spline's second control point, its second knot, its first knot, the last knot, and the degree of the spline.</span></span> 
  
<span data-ttu-id="24005-105">SplineStart 行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="24005-105">A SplineStart row contains the following cells.</span></span>
  
|<span data-ttu-id="24005-106">**单元格**</span><span class="sxs-lookup"><span data-stu-id="24005-106">**Cell**</span></span>|<span data-ttu-id="24005-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="24005-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="24005-108">X</span><span class="sxs-lookup"><span data-stu-id="24005-108">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="24005-109">样条第二个控制点的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="24005-109">The  *x*  -coordinate of a spline's second control point.</span></span>  <br/> |
|[<span data-ttu-id="24005-110">Y</span><span class="sxs-lookup"><span data-stu-id="24005-110">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="24005-111">样条第二个控制点的*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="24005-111">The  *y*  -coordinate of a spline's second control point.</span></span>  <br/> |
|[<span data-ttu-id="24005-112">A</span><span class="sxs-lookup"><span data-stu-id="24005-112">A</span></span>](a-cell-geometry-section.md) <br/> |<span data-ttu-id="24005-113">样条的第二个节点。</span><span class="sxs-lookup"><span data-stu-id="24005-113">The second knot of the spline.</span></span>  <br/> |
|[<span data-ttu-id="24005-114">黑白</span><span class="sxs-lookup"><span data-stu-id="24005-114">B</span></span>](b-cell-geometry-section.md) <br/> |<span data-ttu-id="24005-115">样条的第一个节点。</span><span class="sxs-lookup"><span data-stu-id="24005-115">The first knot of a spline.</span></span>  <br/> |
|[<span data-ttu-id="24005-116">lc</span><span class="sxs-lookup"><span data-stu-id="24005-116">C</span></span>](c-cell-geometry-section.md) <br/> |<span data-ttu-id="24005-117">样条的最后一个节点。</span><span class="sxs-lookup"><span data-stu-id="24005-117">The last knot of a spline.</span></span>  <br/> |
|[<span data-ttu-id="24005-118">D</span><span class="sxs-lookup"><span data-stu-id="24005-118">D</span></span>](d-cell-geometry-section.md) <br/> |<span data-ttu-id="24005-119">样条的角度（从 1 到 25 的整数）。</span><span class="sxs-lookup"><span data-stu-id="24005-119">The degree of a spline (an integer from 1 to 25).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="24005-120">说明</span><span class="sxs-lookup"><span data-stu-id="24005-120">Remarks</span></span>

<span data-ttu-id="24005-p101">Visio 在“Geometry”内容中显示样条的定义，其中包含 SplineStart 行以及其后的一个或多个 SplineKnot 行。SplineStart 行前面必须有其他类型的行（如 MoveTo 行），以指示样条的第一个控制点。如果样条前有相应类型的线段，则前面的行可以是 LineTo、ArcTo、NURBSTo、PolylineTo 或 EllipticalArcTo 行。</span><span class="sxs-lookup"><span data-stu-id="24005-p101">Visio displays the definition of a spline in a Geometry section that contains a SplineStart row followed by one or more SplineKnot rows. The SplineStart row must be preceded by another kind of row, such as a MoveTo row, to indicate the first control point of the spline. The preceding row can be a LineTo, ArcTo, NURBSTo, PolylineTo, or EllipticalArcTo row if the spline follows a segment of that type.</span></span>
  

