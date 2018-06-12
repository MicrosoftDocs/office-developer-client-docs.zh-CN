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
description: 包含 x 和 y-坐标样条的第二个控制点、 它的第二个节点、 第一个节点、 最后一个节点和样条的度数。
ms.openlocfilehash: 0944da12e6090fde41dc5927b5705e103d29f76d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781428"
---
# <a name="splinestart-row-geometry-section"></a><span data-ttu-id="e89ad-103">SplineStart 行（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="e89ad-103">SplineStart Row (Geometry Section)</span></span>

<span data-ttu-id="e89ad-104">包含*x*和*y* -坐标样条的第二个控制点、 它的第二个节点、 第一个节点、 最后一个节点和样条的度数。</span><span class="sxs-lookup"><span data-stu-id="e89ad-104">Contains  *x*  - and  *y*  -coordinates for a spline's second control point, its second knot, its first knot, the last knot, and the degree of the spline.</span></span> 
  
<span data-ttu-id="e89ad-105">SplineStart 行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="e89ad-105">A SplineStart row contains the following cells.</span></span>
  
|<span data-ttu-id="e89ad-106">**Cell**</span><span class="sxs-lookup"><span data-stu-id="e89ad-106">**Cell**</span></span>|<span data-ttu-id="e89ad-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="e89ad-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e89ad-108">X</span><span class="sxs-lookup"><span data-stu-id="e89ad-108">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="e89ad-109">*X* -样条的第二个控制点的坐标。</span><span class="sxs-lookup"><span data-stu-id="e89ad-109">The  *x*  -coordinate of a spline's second control point.</span></span>  <br/> |
|[<span data-ttu-id="e89ad-110">Y</span><span class="sxs-lookup"><span data-stu-id="e89ad-110">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="e89ad-111">*Y* -样条的第二个控制点的坐标。</span><span class="sxs-lookup"><span data-stu-id="e89ad-111">The  *y*  -coordinate of a spline's second control point.</span></span>  <br/> |
|[<span data-ttu-id="e89ad-112">A</span><span class="sxs-lookup"><span data-stu-id="e89ad-112">A</span></span>](a-cell-geometry-section.md) <br/> |<span data-ttu-id="e89ad-113">样条的第二个节点。</span><span class="sxs-lookup"><span data-stu-id="e89ad-113">The second knot of the spline.</span></span>  <br/> |
|[<span data-ttu-id="e89ad-114">B</span><span class="sxs-lookup"><span data-stu-id="e89ad-114">B</span></span>](b-cell-geometry-section.md) <br/> |<span data-ttu-id="e89ad-115">样条的第一个节点。</span><span class="sxs-lookup"><span data-stu-id="e89ad-115">The first knot of a spline.</span></span>  <br/> |
|[<span data-ttu-id="e89ad-116">C</span><span class="sxs-lookup"><span data-stu-id="e89ad-116">C</span></span>](c-cell-geometry-section.md) <br/> |<span data-ttu-id="e89ad-117">样条的最后一个节点。</span><span class="sxs-lookup"><span data-stu-id="e89ad-117">The last knot of a spline.</span></span>  <br/> |
|[<span data-ttu-id="e89ad-118">D</span><span class="sxs-lookup"><span data-stu-id="e89ad-118">D</span></span>](d-cell-geometry-section.md) <br/> |<span data-ttu-id="e89ad-119">样条的角度（从 1 到 25 的整数）。</span><span class="sxs-lookup"><span data-stu-id="e89ad-119">The degree of a spline (an integer from 1 to 25).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e89ad-120">注解</span><span class="sxs-lookup"><span data-stu-id="e89ad-120">Remarks</span></span>

<span data-ttu-id="e89ad-p101">Visio 在“Geometry”内容中显示样条的定义，其中包含 SplineStart 行以及其后的一个或多个 SplineKnot 行。SplineStart 行前面必须有其他类型的行（如 MoveTo 行），以指示样条的第一个控制点。如果样条前有相应类型的线段，则前面的行可以是 LineTo、ArcTo、NURBSTo、PolylineTo 或 EllipticalArcTo 行。</span><span class="sxs-lookup"><span data-stu-id="e89ad-p101">Visio displays the definition of a spline in a Geometry section that contains a SplineStart row followed by one or more SplineKnot rows. The SplineStart row must be preceded by another kind of row, such as a MoveTo row, to indicate the first control point of the spline. The preceding row can be a LineTo, ArcTo, NURBSTo, PolylineTo, or EllipticalArcTo row if the spline follows a segment of that type.</span></span>
  

