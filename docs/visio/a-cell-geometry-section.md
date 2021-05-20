---
title: A 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm51215
localization_priority: Normal
ms.assetid: 6853df0f-d22e-89ca-7d34-342b9c0bea23
description: 在不同行中表示不同的信息。此表根据 A 单元格所在的行对 A 单元格进行了说明。
ms.openlocfilehash: 7009658c7a6844a5c6071f502c05114a4accd7b7
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541300"
---
# <a name="a-cell-geometry-section"></a><span data-ttu-id="80489-104">A 单元格（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="80489-104">A Cell (Geometry Section)</span></span>

<span data-ttu-id="80489-p102">在不同行中表示不同的信息。此表根据 A 单元格所在的行对 A 单元格进行了说明。</span><span class="sxs-lookup"><span data-stu-id="80489-p102">Represents different information in different rows. This table describes the A cell based on the row in which it's located.</span></span>
  
|<span data-ttu-id="80489-107">Row</span><span class="sxs-lookup"><span data-stu-id="80489-107">Row</span></span>|<span data-ttu-id="80489-108">说明</span><span class="sxs-lookup"><span data-stu-id="80489-108">Description</span></span>|
|:-----|:-----|
|[<span data-ttu-id="80489-109">ArcTo</span><span class="sxs-lookup"><span data-stu-id="80489-109">ArcTo</span></span>](arcto-row-geometry-section.md) <br/> | <span data-ttu-id="80489-110">从弧形的中点到对应的弦的中点的距离。</span><span class="sxs-lookup"><span data-stu-id="80489-110">The distance from the arc's midpoint to the midpoint of its chord.</span></span>  <br/> |
|[<span data-ttu-id="80489-111">EllipticalArcTo</span><span class="sxs-lookup"><span data-stu-id="80489-111">EllipticalArcTo</span></span>](ellipticalarcto-row-geometry-section.md) <br/> | <span data-ttu-id="80489-112">弧形控制点（弧形上的一个点）的  *x*  坐标。控制点最好位于弧形的开始顶点和结束顶点之间的一半左右。否则，弧形可能会增长到极大小，以便通过控制点，从而产生不可预知的结果。</span><span class="sxs-lookup"><span data-stu-id="80489-112">The  *x*  -coordinate of the arc's control point, a point on the arc. The control point is best located about halfway between the beginning and ending vertices of the arc. Otherwise, the arc may grow to an extreme size in order to pass through the control point, with unpredictable results.</span></span>  <br/> |
|[<span data-ttu-id="80489-113">PolylineTo</span><span class="sxs-lookup"><span data-stu-id="80489-113">PolylineTo</span></span>](polylineto-row-geometry-section.md) <br/> | <span data-ttu-id="80489-114">折线公式。</span><span class="sxs-lookup"><span data-stu-id="80489-114">The polyline formula.</span></span>  <br/> |
|[<span data-ttu-id="80489-115">NURBSTo</span><span class="sxs-lookup"><span data-stu-id="80489-115">NURBSTo</span></span>](nurbsto-row-geometry-section.md) <br/> | <span data-ttu-id="80489-116">非均匀有理 B 样条 (NURBS) 的倒数第二个节点。</span><span class="sxs-lookup"><span data-stu-id="80489-116">The second to the last knot of the nonuniform rational B-spline (NURBS).</span></span>  <br/> |
|[<span data-ttu-id="80489-117">SplineStart</span><span class="sxs-lookup"><span data-stu-id="80489-117">SplineStart</span></span>](splinestart-row-geometry-section.md) <br/> | <span data-ttu-id="80489-118">样条的第二个节点。</span><span class="sxs-lookup"><span data-stu-id="80489-118">The second knot of the spline.</span></span>  <br/> |
|[<span data-ttu-id="80489-119">SplineKnot</span><span class="sxs-lookup"><span data-stu-id="80489-119">SplineKnot</span></span>](splineknot-row-geometry-section.md) <br/> | <span data-ttu-id="80489-120">样条的节点之一（最后一个节点或前两个节点除外）。</span><span class="sxs-lookup"><span data-stu-id="80489-120">One of the spline's knots (other than the last one or the first two).</span></span>  <br/> |
|[<span data-ttu-id="80489-121">InfiniteLine</span><span class="sxs-lookup"><span data-stu-id="80489-121">InfiniteLine</span></span>](infiniteline-row-geometry-section.md) <br/> | <span data-ttu-id="80489-122">无限 *长* 线上点的 x 坐标;与 B 单元格表示的 *y* [坐标配对。](b-cell-geometry-section.md)</span><span class="sxs-lookup"><span data-stu-id="80489-122">An  *x*  -coordinate of a point on the infinite line; paired with  *y*  -coordinate represented by the [B](b-cell-geometry-section.md) cell.</span></span>  <br/> |
|[<span data-ttu-id="80489-123">Ellipse</span><span class="sxs-lookup"><span data-stu-id="80489-123">Ellipse</span></span>](ellipse-row-geometry-section.md) <br/> | <span data-ttu-id="80489-124">椭圆上点的 *x* 坐标;与 B 单元格表示的 *y* [坐标配对。](b-cell-geometry-section.md)</span><span class="sxs-lookup"><span data-stu-id="80489-124">An  *x*  -coordinate of a point on the ellipse; paired with  *y*  -coordinate represented by the [B](b-cell-geometry-section.md) cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="80489-125">备注</span><span class="sxs-lookup"><span data-stu-id="80489-125">Remarks</span></span>

<span data-ttu-id="80489-126">要从另一个公式或程序使用 **CellsU** 属性按名称获取对 A 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="80489-126">To get a reference to the A cell by name from another formula, or from a program, using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="80489-127">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="80489-127">Cell name:</span></span>  <br/> | <span data-ttu-id="80489-128">Geometry  *i*  .a  *j*            where  *i*  and  *j*  = <1>， 2， 3...</span><span class="sxs-lookup"><span data-stu-id="80489-128">Geometry  *i*  .A  *j*            where  *i*  and  *j*  = <1>, 2, 3...</span></span>  <br/> |
|| <span data-ttu-id="80489-129">Geometry  *i*  .A1 (InfiniteLine 和 Ellipse) 其中  *i*  = <1>、2、3...</span><span class="sxs-lookup"><span data-stu-id="80489-129">Geometry  *i*  .A1 (InfiniteLine and Ellipse rows)            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="80489-130">要从某个程序按索引获取对 A 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="80489-130">To get a reference to the A cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="80489-131">内容索引：</span><span class="sxs-lookup"><span data-stu-id="80489-131">Section index:</span></span>  <br/> |<span data-ttu-id="80489-132">**visSectionFirstComponent**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="80489-132">**visSectionFirstComponent** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="80489-133">行索引：</span><span class="sxs-lookup"><span data-stu-id="80489-133">Row index:</span></span>  <br/> |<span data-ttu-id="80489-134">**visRowVertex**  +  *j* 其中 *j* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="80489-134">**visRowVertex** +  *j*            where  *j*  = 0, 1, 2...</span></span>  <br/> |
||<span data-ttu-id="80489-135">**visRowVertex**（InfiniteLine 和 Ellipse 行）</span><span class="sxs-lookup"><span data-stu-id="80489-135">**visRowVertex** (InfiniteLine and Ellipse rows)</span></span>  <br/> |
| <span data-ttu-id="80489-136">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="80489-136">Cell index:</span></span>  <br/> |<span data-ttu-id="80489-137">**visBow**（ArcTo 行）</span><span class="sxs-lookup"><span data-stu-id="80489-137">**visBow** (ArcTo row)</span></span>  <br/> |
||<span data-ttu-id="80489-138">**visControlX**（EllipticalArcTo 行）</span><span class="sxs-lookup"><span data-stu-id="80489-138">**visControlX** (EllipticalArcTo row)</span></span>  <br/> |
||<span data-ttu-id="80489-139">**visControlY**（EllipticalArcTo 行）</span><span class="sxs-lookup"><span data-stu-id="80489-139">**visControlY** (EllipticalArcTo row)</span></span>  <br/> |
||<span data-ttu-id="80489-140">**visPolylineData**（Polyline 行）</span><span class="sxs-lookup"><span data-stu-id="80489-140">**visPolylineData** (Polyline row)</span></span>  <br/> |
||<span data-ttu-id="80489-141">**visNURBSKnot**（NURBSTo 行）</span><span class="sxs-lookup"><span data-stu-id="80489-141">**visNURBSKnot** (NURBSTo row)</span></span>  <br/> |
||<span data-ttu-id="80489-142">**visSplineKnot**（SplineStart 和 SplineKnot 行）</span><span class="sxs-lookup"><span data-stu-id="80489-142">**visSplineKnot** (SplineStart and SplineKnot rows)</span></span>  <br/> |
||<span data-ttu-id="80489-143">**visInfiniteLineX2**（InfiniteLine 行）</span><span class="sxs-lookup"><span data-stu-id="80489-143">**visInfiniteLineX2** (InfiniteLine row)</span></span>  <br/> |
||<span data-ttu-id="80489-144">**visEllipseMajorX**（Ellipse 行）</span><span class="sxs-lookup"><span data-stu-id="80489-144">**visEllipseMajorX** (Ellipse row)</span></span>  <br/> |
   

