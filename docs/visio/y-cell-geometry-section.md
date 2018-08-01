---
title: Y 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251750
localization_priority: Normal
ms.assetid: a53b5787-f419-7a36-3c04-c63b3c173ac7
description: 代表 y-坐标在本地坐标系中的形状。 下表描述了基于在它的行的 Y 单元格所在。
ms.openlocfilehash: 461fd0ec41d34132f469c811292550d2f7e094f0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781710"
---
# <a name="y-cell-geometry-section"></a><span data-ttu-id="e15ec-104">Y 单元格（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="e15ec-104">Y Cell (Geometry Section)</span></span>

<span data-ttu-id="e15ec-105">代表*y* -坐标在本地坐标系中的形状。</span><span class="sxs-lookup"><span data-stu-id="e15ec-105">Represents a  *y*  -coordinate on a shape in local coordinates.</span></span> <span data-ttu-id="e15ec-106">下表描述了基于在它的行的 Y 单元格所在。</span><span class="sxs-lookup"><span data-stu-id="e15ec-106">This table describes the Y cell based on the row in which it's located.</span></span> 
  
|<span data-ttu-id="e15ec-107">**Row**</span><span class="sxs-lookup"><span data-stu-id="e15ec-107">**Row**</span></span>|<span data-ttu-id="e15ec-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="e15ec-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e15ec-109">NURBSTo</span><span class="sxs-lookup"><span data-stu-id="e15ec-109">NURBSTo</span></span>](nurbsto-row-geometry-section.md) <br/> | <span data-ttu-id="e15ec-110">如果 MoveTo 行是部分中的第一行，则 Y 单元格表示*y* -路径的第一个顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="e15ec-110">If the MoveTo row is the first row in the section, the Y cell represents the  *y*  -coordinate of the first vertex of a path.</span></span> <span data-ttu-id="e15ec-111">如果 MoveTo 行出现在两行之间，则 Y 单元格表示*y* -路径中断开后的第一个顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="e15ec-111">If the MoveTo row appears between two rows, the Y cell represents the  *y*  -coordinate of the first vertex after the break in the path.</span></span>  <br/> |
|[<span data-ttu-id="e15ec-112">LineTo</span><span class="sxs-lookup"><span data-stu-id="e15ec-112">LineTo</span></span>](lineto-row-geometry-section.md) <br/> | <span data-ttu-id="e15ec-113">*Y* -直线段终顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="e15ec-113">The  *y*  -coordinate of the ending vertex of a straight line segment.</span></span>  <br/> |
|[<span data-ttu-id="e15ec-114">ArcTo</span><span class="sxs-lookup"><span data-stu-id="e15ec-114">ArcTo</span></span>](arcto-row-geometry-section.md) <br/> | <span data-ttu-id="e15ec-115">*Y* -弧形终顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="e15ec-115">The  *y*  -coordinate of the ending vertex of an arc.</span></span>  <br/> |
|[<span data-ttu-id="e15ec-116">EllipticalArcTo</span><span class="sxs-lookup"><span data-stu-id="e15ec-116">EllipticalArcTo</span></span>](ellipticalarcto-row-geometry-section.md) <br/> | <span data-ttu-id="e15ec-117">*Y* -椭圆弧线终顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="e15ec-117">The  *y*  -coordinate of the ending vertex of an elliptical arc.</span></span>  <br/> |
|[<span data-ttu-id="e15ec-118">PolylineTo</span><span class="sxs-lookup"><span data-stu-id="e15ec-118">PolylineTo</span></span>](polylineto-row-geometry-section.md) <br/> | <span data-ttu-id="e15ec-119">*Y* -折线终顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="e15ec-119">The  *y*  -coordinate of the ending vertex of a polyline.</span></span>  <br/> |
|[<span data-ttu-id="e15ec-120">NURBSTo</span><span class="sxs-lookup"><span data-stu-id="e15ec-120">NURBSTo</span></span>](nurbsto-row-geometry-section.md) <br/> | <span data-ttu-id="e15ec-121">*Y* -非均匀有理 B 样条 (NURBS) 的最后一个控制点的坐标。</span><span class="sxs-lookup"><span data-stu-id="e15ec-121">The  *y*  -coordinate of the last control point of a nonuniform rational B-spline (NURBS).</span></span>  <br/> |
|[<span data-ttu-id="e15ec-122">SplineStart</span><span class="sxs-lookup"><span data-stu-id="e15ec-122">SplineStart</span></span>](splinestart-row-geometry-section.md) <br/> | <span data-ttu-id="e15ec-123">*Y* -样条的第二个控制点的坐标。</span><span class="sxs-lookup"><span data-stu-id="e15ec-123">The  *y*  -coordinate of a spline's second control point.</span></span>  <br/> |
|[<span data-ttu-id="e15ec-124">SplineKnot</span><span class="sxs-lookup"><span data-stu-id="e15ec-124">SplineKnot</span></span>](splineknot-row-geometry-section.md) <br/> | <span data-ttu-id="e15ec-125">*Y* -控制点的坐标。</span><span class="sxs-lookup"><span data-stu-id="e15ec-125">The  *y*  -coordinate of a control point.</span></span>  <br/> |
|[<span data-ttu-id="e15ec-126">InfiniteLine</span><span class="sxs-lookup"><span data-stu-id="e15ec-126">InfiniteLine</span></span>](infiniteline-row-geometry-section.md) <br/> | <span data-ttu-id="e15ec-127">*Y 轴*坐标值无限长线上某个点。</span><span class="sxs-lookup"><span data-stu-id="e15ec-127">A  *y-*  coordinate of a point on the infinite line.</span></span>  <br/> |
|[<span data-ttu-id="e15ec-128">椭圆</span><span class="sxs-lookup"><span data-stu-id="e15ec-128">Ellipse</span></span>](ellipse-row-geometry-section.md) <br/> | <span data-ttu-id="e15ec-129">*Y* -椭圆中心的坐标。</span><span class="sxs-lookup"><span data-stu-id="e15ec-129">The  *y*  -coordinate of the center of the ellipse.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e15ec-130">说明</span><span class="sxs-lookup"><span data-stu-id="e15ec-130">Remarks</span></span>

<span data-ttu-id="e15ec-131">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Y 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="e15ec-131">To get a reference to the Y cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e15ec-132">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e15ec-132">Cell name:</span></span>  <br/> | <span data-ttu-id="e15ec-133">Geometry *i* 。Y *j*其中*i*和*j* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="e15ec-133">Geometry  *i*  .Y  *j*            where  *i*  and  *j*  = <1>, 2, 3...</span></span>  <br/> |
|| <span data-ttu-id="e15ec-134">Geometry *i* 。Y1 （InfiniteLine 和 Ellipse 行） 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="e15ec-134">Geometry  *i*  .Y1 (InfiniteLine and Ellipse rows)            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="e15ec-135">要从某个程序按索引获取对 Y 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="e15ec-135">To get a reference to the Y cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e15ec-136">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e15ec-136">Section index:</span></span>  <br/> |<span data-ttu-id="e15ec-137">**visSectionFirstComponent** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="e15ec-137">**visSectionFirstComponent** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="e15ec-138">行索引：</span><span class="sxs-lookup"><span data-stu-id="e15ec-138">Row index:</span></span>  <br/> |<span data-ttu-id="e15ec-139">**visRowVertex** +  *j*其中*j* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="e15ec-139">**visRowVertex** +  *j*            where  *j*  = 0, 1, 2...</span></span>  <br/> |
||<span data-ttu-id="e15ec-140">**visRowVertex**（InfiniteLine 和 Ellipse 行）</span><span class="sxs-lookup"><span data-stu-id="e15ec-140">**visRowVertex** (InfiniteLine and Ellipse rows)</span></span>  <br/> |
| <span data-ttu-id="e15ec-141">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e15ec-141">Cell index:</span></span>  <br/> |<span data-ttu-id="e15ec-142">**visY**（MoveTo、LineTo、ArcTo、EllipticalArcTo、NURBSTo、Polyline、SplineStart 和 SplineKnot 行）</span><span class="sxs-lookup"><span data-stu-id="e15ec-142">**visY** (MoveTo, LineTo, ArcTo, EllipticalArcTo, NURBSTo, Polyline, SplineStart, and SplineKnot rows)</span></span>  <br/> |
||<span data-ttu-id="e15ec-143">**visInfiniteLineY1**（InfiniteLine 行）</span><span class="sxs-lookup"><span data-stu-id="e15ec-143">**visInfiniteLineY1** (InfiniteLine row)</span></span>  <br/> |
||<span data-ttu-id="e15ec-144">**visEllipseCenterY**（Ellipse 行）</span><span class="sxs-lookup"><span data-stu-id="e15ec-144">**visEllipseCenterY** (Ellipse row)</span></span>  <br/> |
   

