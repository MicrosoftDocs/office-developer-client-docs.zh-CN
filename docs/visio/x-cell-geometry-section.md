---
title: X 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1135
localization_priority: Normal
ms.assetid: 2416b323-e084-18e1-c9be-a797078dfab9
description: 表示在本地坐标系中的形状的 x 坐标。 该表基于 X 单元格所在的行对它进行说明。
ms.openlocfilehash: 6554000a86a6bf27d343a5647161bbe416725e64
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285110"
---
# <a name="x-cell-geometry-section"></a><span data-ttu-id="098c8-104">X 单元格（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="098c8-104">X Cell (Geometry Section)</span></span>

<span data-ttu-id="098c8-105">表示在本地坐标系中的形状的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="098c8-105">Represents an  *x*  -coordinate on a shape in local coordinates.</span></span> <span data-ttu-id="098c8-106">该表基于 X 单元格所在的行对它进行说明。</span><span class="sxs-lookup"><span data-stu-id="098c8-106">This table describes the X cell based on the row in which it's located.</span></span> 
  
|<span data-ttu-id="098c8-107">**行**</span><span class="sxs-lookup"><span data-stu-id="098c8-107">**Row**</span></span>|<span data-ttu-id="098c8-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="098c8-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="098c8-109">MoveTo</span><span class="sxs-lookup"><span data-stu-id="098c8-109">MoveTo</span></span>](moveto-row-geometry-section.md) <br/> | <span data-ttu-id="098c8-110">如果 MoveTo 行是该内容中的第一行, 则 X 单元格表示路径的第一个顶点的*X*坐标。</span><span class="sxs-lookup"><span data-stu-id="098c8-110">If the MoveTo row is the first row in the section, the X cell represents the  *x*  -coordinate of the first vertex of a path.</span></span> <span data-ttu-id="098c8-111">如果 MoveTo 行出现在两行之间, 则 X 单元格表示路径中断开处后的第一个顶点的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="098c8-111">If the MoveTo row appears between two rows, the X cell represents the  *x*  -coordinate of the first vertex after the break in the path.</span></span>  <br/> |
|[<span data-ttu-id="098c8-112">LineTo</span><span class="sxs-lookup"><span data-stu-id="098c8-112">LineTo</span></span>](lineto-row-geometry-section.md) <br/> | <span data-ttu-id="098c8-113">直线段终顶点的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="098c8-113">The  *x*  -coordinate of the ending vertex of a straight line segment.</span></span>  <br/> |
|[<span data-ttu-id="098c8-114">ArcTo</span><span class="sxs-lookup"><span data-stu-id="098c8-114">ArcTo</span></span>](arcto-row-geometry-section.md) <br/> | <span data-ttu-id="098c8-115">弧形终顶点的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="098c8-115">The  *x*  -coordinate of the ending vertex of an arc.</span></span>  <br/> |
|[<span data-ttu-id="098c8-116">EllipticalArcTo</span><span class="sxs-lookup"><span data-stu-id="098c8-116">EllipticalArcTo</span></span>](ellipticalarcto-row-geometry-section.md) <br/> | <span data-ttu-id="098c8-117">椭圆弧线终顶点的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="098c8-117">The  *x*  -coordinate of the ending vertex of an elliptical arc.</span></span>  <br/> |
|[<span data-ttu-id="098c8-118">PolylineTo</span><span class="sxs-lookup"><span data-stu-id="098c8-118">PolylineTo</span></span>](polylineto-row-geometry-section.md) <br/> | <span data-ttu-id="098c8-119">折线终顶点的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="098c8-119">The  *x*  -coordinate of the ending vertex of a polyline.</span></span>  <br/> |
|[<span data-ttu-id="098c8-120">NURBSTo</span><span class="sxs-lookup"><span data-stu-id="098c8-120">NURBSTo</span></span>](nurbsto-row-geometry-section.md) <br/> | <span data-ttu-id="098c8-121">非均匀有理 B 样条 (NURBS) 的最后一个控制点的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="098c8-121">The  *x*  -coordinate of the last control point of a nonuniform rational B-spline (NURBS).</span></span>  <br/> |
|[<span data-ttu-id="098c8-122">SplineStart</span><span class="sxs-lookup"><span data-stu-id="098c8-122">SplineStart</span></span>](splinestart-row-geometry-section.md) <br/> | <span data-ttu-id="098c8-123">样条第二个控制点的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="098c8-123">The  *x*  -coordinate of a spline's second control point.</span></span>  <br/> |
|[<span data-ttu-id="098c8-124">SplineKnot</span><span class="sxs-lookup"><span data-stu-id="098c8-124">SplineKnot</span></span>](splineknot-row-geometry-section.md) <br/> | <span data-ttu-id="098c8-125">控制点的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="098c8-125">The  *x*  -coordinate of a control point.</span></span>  <br/> |
|[<span data-ttu-id="098c8-126">InfiniteLine</span><span class="sxs-lookup"><span data-stu-id="098c8-126">InfiniteLine</span></span>](infiniteline-row-geometry-section.md) <br/> | <span data-ttu-id="098c8-127">无限长线上某个点的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="098c8-127">An  *x*  -coordinate of a point on the infinite line.</span></span>  <br/> |
|[<span data-ttu-id="098c8-128">椭圆</span><span class="sxs-lookup"><span data-stu-id="098c8-128">Ellipse</span></span>](ellipse-row-geometry-section.md) <br/> | <span data-ttu-id="098c8-129">椭圆中心的*x*轴坐标值。</span><span class="sxs-lookup"><span data-stu-id="098c8-129">The  *x*  -coordinate of the center of the ellipse.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="098c8-130">注解</span><span class="sxs-lookup"><span data-stu-id="098c8-130">Remarks</span></span>

<span data-ttu-id="098c8-131">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 X 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="098c8-131">To get a reference to the X cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="098c8-132">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="098c8-132">Cell name:</span></span>  <br/> | <span data-ttu-id="098c8-133">几何图形*i* 。X *j*其中*i*和*j* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="098c8-133">Geometry  *i*  .X  *j*            where  *i*  and  *j*  = <1>, 2, 3...</span></span>  <br/> |
|| <span data-ttu-id="098c8-134">几何图形*i* 。X1 (InfiniteLine 和椭圆行) 其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="098c8-134">Geometry  *i*  .X1 (InfiniteLine and Ellipse rows)            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="098c8-135">要从某个程序按索引获取对 X 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="098c8-135">To get a reference to the X cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="098c8-136">内容索引：</span><span class="sxs-lookup"><span data-stu-id="098c8-136">Section index:</span></span>  <br/> |<span data-ttu-id="098c8-137">**visSectionFirstComponent** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="098c8-137">**visSectionFirstComponent** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="098c8-138">行索引：</span><span class="sxs-lookup"><span data-stu-id="098c8-138">Row index:</span></span>  <br/> |<span data-ttu-id="098c8-139">**visRowVertex** +  *j*其中*j* = 0, 1, 2 .。。</span><span class="sxs-lookup"><span data-stu-id="098c8-139">**visRowVertex** +  *j*            where  *j*  = 0, 1, 2...</span></span>  <br/> |
||<span data-ttu-id="098c8-140">**visRowVertex**（InfiniteLine 和 Ellipse 行）</span><span class="sxs-lookup"><span data-stu-id="098c8-140">**visRowVertex** (InfiniteLine and Ellipse rows)</span></span>  <br/> |
| <span data-ttu-id="098c8-141">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="098c8-141">Cell index:</span></span>  <br/> |<span data-ttu-id="098c8-142">**visX**（MoveTo、LineTo、ArcTo、EllipticalArcTo、NURBSTo、Polyline、SplineStart 和 SplineKnot 行）</span><span class="sxs-lookup"><span data-stu-id="098c8-142">**visX** (MoveTo, LineTo, ArcTo, EllipticalArcTo, NURBSTo, Polyline, SplineStart, and SplineKnot rows)</span></span>  <br/> |
||<span data-ttu-id="098c8-143">**visInfiniteLineX1**（InfiniteLine 行）</span><span class="sxs-lookup"><span data-stu-id="098c8-143">**visInfiniteLineX1** (InfiniteLine row)</span></span>  <br/> |
||<span data-ttu-id="098c8-144">**visEllipseCenterX**（Ellipse 行）</span><span class="sxs-lookup"><span data-stu-id="098c8-144">**visEllipseCenterX** (Ellipse row)</span></span>  <br/> |
   

