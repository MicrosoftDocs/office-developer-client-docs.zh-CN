---
title: C 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm140
localization_priority: Normal
ms.assetid: d51a1dd8-678a-a34d-658d-bd7a027dd379
description: 代表不同行中的不同信息。 该表基于 C 单元格所在的行对它进行说明。
ms.openlocfilehash: 5599c09ad3656653c486d7feff9aed2ee89e4614
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337490"
---
# <a name="c-cell-geometry-section"></a><span data-ttu-id="c5ead-104">C 单元格（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="c5ead-104">C Cell (Geometry Section)</span></span>

<span data-ttu-id="c5ead-105">代表不同行中的不同信息。</span><span class="sxs-lookup"><span data-stu-id="c5ead-105">Represents different information in different rows.</span></span> <span data-ttu-id="c5ead-106">该表基于 C 单元格所在的行对它进行说明。</span><span class="sxs-lookup"><span data-stu-id="c5ead-106">This table describes the C cell based on the row in which it's located.</span></span>
  
|<span data-ttu-id="c5ead-107">**行**</span><span class="sxs-lookup"><span data-stu-id="c5ead-107">**Row**</span></span>|<span data-ttu-id="c5ead-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="c5ead-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="c5ead-109">EllipticalArcTo</span><span class="sxs-lookup"><span data-stu-id="c5ead-109">EllipticalArcTo</span></span>](ellipticalarcto-row-geometry-section.md) <br/> | <span data-ttu-id="c5ead-110">弧形的长轴相对于其父级的*x*轴的角度。</span><span class="sxs-lookup"><span data-stu-id="c5ead-110">The angle of an arc's major axis relative to the  *x*  -axis of its parent.</span></span>  <br/> |
|[<span data-ttu-id="c5ead-111">NURBSTo</span><span class="sxs-lookup"><span data-stu-id="c5ead-111">NURBSTo</span></span>](nurbsto-row-geometry-section.md) <br/> | <span data-ttu-id="c5ead-112">非均匀有理 B 样条 (NURBS) 的第一个节点。</span><span class="sxs-lookup"><span data-stu-id="c5ead-112">The first knot of the nonuniform rational B-spline (NURBS).</span></span>  <br/> |
|[<span data-ttu-id="c5ead-113">SplineStart</span><span class="sxs-lookup"><span data-stu-id="c5ead-113">SplineStart</span></span>](splinestart-row-geometry-section.md) <br/> | <span data-ttu-id="c5ead-114">样条的最后一个节点。</span><span class="sxs-lookup"><span data-stu-id="c5ead-114">The last knot of a spline.</span></span>  <br/> |
|[<span data-ttu-id="c5ead-115">椭圆</span><span class="sxs-lookup"><span data-stu-id="c5ead-115">Ellipse</span></span>](ellipse-row-geometry-section.md) <br/> | <span data-ttu-id="c5ead-116">椭圆上某个点的*x*坐标;与[D](d-cell-geometry-section.md)单元格所表示的*y*坐标配对。</span><span class="sxs-lookup"><span data-stu-id="c5ead-116">An  *x*  -coordinate of a point on an ellipse; paired with the  *y*  -coordinate represented by the [D](d-cell-geometry-section.md) cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c5ead-117">注解</span><span class="sxs-lookup"><span data-stu-id="c5ead-117">Remarks</span></span>

<span data-ttu-id="c5ead-118">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 C 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="c5ead-118">To get a reference to the C cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c5ead-119">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c5ead-119">Cell name:</span></span>  <br/> | <span data-ttu-id="c5ead-120">几何图形*i* 。C *j*其中*i*和*j* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="c5ead-120">Geometry  *i*  .C  *j*            where  *i*  and  *j*  = <1>, 2, 3...</span></span>  <br/> |
|| <span data-ttu-id="c5ead-121">几何图形*i* 。C1 (椭圆行)</span><span class="sxs-lookup"><span data-stu-id="c5ead-121">Geometry  *i*  .C1 (Ellipse row)</span></span>  <br/> |
   
<span data-ttu-id="c5ead-122">要从某个程序按索引获取对 C 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="c5ead-122">To get a reference to the C cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c5ead-123">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c5ead-123">Section index:</span></span>  <br/> |<span data-ttu-id="c5ead-124">**visSectionFirstComponent** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="c5ead-124">**visSectionFirstComponent** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="c5ead-125">行索引：</span><span class="sxs-lookup"><span data-stu-id="c5ead-125">Row index:</span></span>  <br/> |<span data-ttu-id="c5ead-126">**visRowVertex** +  *j*其中*j* = 0, 1, 2 .。。</span><span class="sxs-lookup"><span data-stu-id="c5ead-126">**visRowVertex** +  *j*            where  *j*  = 0, 1, 2...</span></span>  <br/> |
||<span data-ttu-id="c5ead-127">**visRowVertex**（Ellipse 行）</span><span class="sxs-lookup"><span data-stu-id="c5ead-127">**visRowVertex** (Ellipse row)</span></span>  <br/> |
| <span data-ttu-id="c5ead-128">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c5ead-128">Cell index:</span></span>  <br/> |<span data-ttu-id="c5ead-129">**visEccentricityAngle**（EllipticalArcTo 行）</span><span class="sxs-lookup"><span data-stu-id="c5ead-129">**visEccentricityAngle** (EllipticalArcTo row)</span></span>  <br/> |
||<span data-ttu-id="c5ead-130">**visNURBSKnotPrev**（NURBSTo 行）</span><span class="sxs-lookup"><span data-stu-id="c5ead-130">**visNURBSKnotPrev** (NURBSTo row)</span></span>  <br/> |
||<span data-ttu-id="c5ead-131">**visSplineKnot3**（SplineStart 行）</span><span class="sxs-lookup"><span data-stu-id="c5ead-131">**visSplineKnot3** (SplineStart row)</span></span>  <br/> |
||<span data-ttu-id="c5ead-132">**visEllipseMinorX**（Ellipse 行）</span><span class="sxs-lookup"><span data-stu-id="c5ead-132">**visEllipseMinorX** (Ellipse row)</span></span>  <br/> |
   

