---
title: D 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251753
localization_priority: Normal
ms.assetid: 5f1fdf59-db58-561c-e187-1af72a8b87f2
description: 代表不同行中的不同信息。 此表基于 D 单元格所在的行对它进行说明。
ms.openlocfilehash: 1da6ac19e6a50ea87f07bf3e3c9f96378b512ba8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424376"
---
# <a name="d-cell-geometry-section"></a><span data-ttu-id="c20a0-104">D 单元格（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="c20a0-104">D Cell (Geometry Section)</span></span>

<span data-ttu-id="c20a0-105">代表不同行中的不同信息。</span><span class="sxs-lookup"><span data-stu-id="c20a0-105">Represents different information in different rows.</span></span> <span data-ttu-id="c20a0-106">此表基于 D 单元格所在的行对它进行说明。</span><span class="sxs-lookup"><span data-stu-id="c20a0-106">This table describes the D cell based on the row in which it's located.</span></span>
  
|<span data-ttu-id="c20a0-107">**行**</span><span class="sxs-lookup"><span data-stu-id="c20a0-107">**Row**</span></span>|<span data-ttu-id="c20a0-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="c20a0-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="c20a0-109">EllipticalArcTo</span><span class="sxs-lookup"><span data-stu-id="c20a0-109">EllipticalArcTo</span></span>](ellipticalarcto-row-geometry-section.md) <br/> | <span data-ttu-id="c20a0-p103">弧形的长短轴之比。尽管每一词都有其本义，但在此处“长”轴却并不一定大于“短”轴，所以此比值也就不一定大于 1。如果将此单元格设置为小于等于 0 或大于 1000 的值，可能导致无法预料的结果。</span><span class="sxs-lookup"><span data-stu-id="c20a0-p103">The ratio of an arc's major axis to its minor axis. Despite the usual meaning of these words, the "major" axis does not have to be greater than the "minor" axis, so this ratio does not have to be greater than 1. Setting this cell to a value less than or equal to 0 or greater than 1000 can lead to unpredictable results.</span></span>  <br/> |
|[<span data-ttu-id="c20a0-113">NURBSTo</span><span class="sxs-lookup"><span data-stu-id="c20a0-113">NURBSTo</span></span>](nurbsto-row-geometry-section.md) <br/> | <span data-ttu-id="c20a0-114">非均匀有理 B 样条 (NURBS) 的第一个权。</span><span class="sxs-lookup"><span data-stu-id="c20a0-114">The first weight of the nonuniform rational B-spline (NURBS).</span></span>  <br/> |
|[<span data-ttu-id="c20a0-115">SplineStart</span><span class="sxs-lookup"><span data-stu-id="c20a0-115">SplineStart</span></span>](splinestart-row-geometry-section.md) <br/> | <span data-ttu-id="c20a0-116">样条的角度（从 1 到 25 的整数）。</span><span class="sxs-lookup"><span data-stu-id="c20a0-116">The degree of a spline (an integer from 1 to 25).</span></span>  <br/> |
|[<span data-ttu-id="c20a0-117">椭圆</span><span class="sxs-lookup"><span data-stu-id="c20a0-117">Ellipse</span></span>](ellipse-row-geometry-section.md) <br/> | <span data-ttu-id="c20a0-118">椭圆上某个点的*y*坐标;与[C](c-cell-geometry-section.md)单元格所表示的*x*坐标配对。</span><span class="sxs-lookup"><span data-stu-id="c20a0-118">A  *y*  -coordinate of a point on an ellipse; paired with the  *x*  -coordinate represented by the [C](c-cell-geometry-section.md) cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c20a0-119">说明</span><span class="sxs-lookup"><span data-stu-id="c20a0-119">Remarks</span></span>

<span data-ttu-id="c20a0-120">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 D 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="c20a0-120">To get a reference to the D cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c20a0-121">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c20a0-121">Cell name:</span></span>  <br/> | <span data-ttu-id="c20a0-122">几何图形*i* 。D *j*其中*i*和*j* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="c20a0-122">Geometry  *i*  .D  *j*            where  *i*  and  *j*  = <1>, 2, 3...</span></span>  <br/> |
|| <span data-ttu-id="c20a0-123">几何图形*i* 。D1 (椭圆行) 其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="c20a0-123">Geometry  *i*  .D1 (Ellipse row)            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="c20a0-124">要从某个程序按索引获取对 D 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="c20a0-124">To get a reference to the D cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c20a0-125">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c20a0-125">Section index:</span></span>  <br/> |<span data-ttu-id="c20a0-126">**visSectionFirstComponent** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="c20a0-126">**visSectionFirstComponent** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="c20a0-127">行索引：</span><span class="sxs-lookup"><span data-stu-id="c20a0-127">Row index:</span></span>  <br/> |<span data-ttu-id="c20a0-128">**visRowVertex** +  *j*其中*j* = 0, 1, 2 .。。</span><span class="sxs-lookup"><span data-stu-id="c20a0-128">**visRowVertex** +  *j*            where  *j*  = 0, 1, 2...</span></span>  <br/> |
||<span data-ttu-id="c20a0-129">**visRowVertex**（Ellipse 行）</span><span class="sxs-lookup"><span data-stu-id="c20a0-129">**visRowVertex** (Ellipse row)</span></span>  <br/> |
| <span data-ttu-id="c20a0-130">单元格索引</span><span class="sxs-lookup"><span data-stu-id="c20a0-130">Cell index</span></span>  <br/> |<span data-ttu-id="c20a0-131">**visAspectRatio**（EllipticalArcTo 行）</span><span class="sxs-lookup"><span data-stu-id="c20a0-131">**visAspectRatio** (EllipticalArcTo row)</span></span>  <br/> |
||<span data-ttu-id="c20a0-132">**visNURBSWeightPrev**（NURBSTo 行）</span><span class="sxs-lookup"><span data-stu-id="c20a0-132">**visNURBSWeightPrev** (NURBSTo row)</span></span>  <br/> |
||<span data-ttu-id="c20a0-133">**visSplineDegree**（SplineStart 行）</span><span class="sxs-lookup"><span data-stu-id="c20a0-133">**visSplineDegree** (SplineStart row)</span></span>  <br/> |
||<span data-ttu-id="c20a0-134">**visEllipseMinorY**（Ellipse 行）</span><span class="sxs-lookup"><span data-stu-id="c20a0-134">**visEllipseMinorY** (Ellipse row)</span></span>  <br/> |
   

