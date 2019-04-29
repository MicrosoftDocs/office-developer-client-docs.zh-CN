---
title: SplineKnot 行（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm3050
localization_priority: Normal
ms.assetid: 9fbae27d-4f1b-c5f7-aacb-16f359331e83
description: 包含样条控件点和样条节点的 x 坐标和 y 坐标。
ms.openlocfilehash: 432b714772d96e0ab0861bbfb62075258404e607
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407415"
---
# <a name="splineknot-row-geometry-section"></a><span data-ttu-id="ce8eb-103">SplineKnot 行（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="ce8eb-103">SplineKnot Row (Geometry Section)</span></span>

<span data-ttu-id="ce8eb-104">包含样条控件点和样条节点的*x*坐标和*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="ce8eb-104">Contains  *x*  - and  *y*  -coordinates for a spline's control point and a spline's knot.</span></span> 
  
<span data-ttu-id="ce8eb-105">SplineKnot 行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="ce8eb-105">A SplineKnot row contains the following cells.</span></span>
  
|<span data-ttu-id="ce8eb-106">**单元格**</span><span class="sxs-lookup"><span data-stu-id="ce8eb-106">**Cell**</span></span>|<span data-ttu-id="ce8eb-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="ce8eb-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="ce8eb-108">X</span><span class="sxs-lookup"><span data-stu-id="ce8eb-108">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="ce8eb-109">控制点的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="ce8eb-109">The  *x*  -coordinate of a control point.</span></span>  <br/> |
|[<span data-ttu-id="ce8eb-110">Y</span><span class="sxs-lookup"><span data-stu-id="ce8eb-110">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="ce8eb-111">控制点的*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="ce8eb-111">The  *y*  -coordinate of a control point.</span></span>  <br/> |
|[<span data-ttu-id="ce8eb-112">A</span><span class="sxs-lookup"><span data-stu-id="ce8eb-112">A</span></span>](a-cell-geometry-section.md) <br/> |<span data-ttu-id="ce8eb-113">样条的节点之一（最后一个节点或前两个节点除外）。</span><span class="sxs-lookup"><span data-stu-id="ce8eb-113">One of the spline's knots (other than the last one or the first two).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ce8eb-114">说明</span><span class="sxs-lookup"><span data-stu-id="ce8eb-114">Remarks</span></span>

<span data-ttu-id="ce8eb-p101">Visio 在“Geometry”内容中显示样条的定义，其中包含 SplineStart 行以及其后的一个或多个 SplineKnot 行。SplineStart 行前面必须有其他类型的行（如 MoveTo 行），以指示样条的第一个控制点。如果样条前有相应类型的线段，则前面的行可以是 LineTo、ArcTo、NURBSTo、PolylineTo 或 EllipticalArcTo 行。</span><span class="sxs-lookup"><span data-stu-id="ce8eb-p101">Visio displays the definition of a spline in a Geometry section that contains a SplineStart row followed by one or more SplineKnot rows. The SplineStart row must be preceded by another kind of row, such as a MoveTo row, to indicate the first control point of the spline. The preceding row can be a LineTo, ArcTo, NURBSTo, PolylineTo, or EllipticalArcTo row if the spline follows a segment of that type.</span></span>
  

