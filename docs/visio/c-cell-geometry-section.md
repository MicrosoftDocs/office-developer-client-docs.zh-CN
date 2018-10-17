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
description: 代表不同行中的不同信息。该表基于 C 单元格所在的行对它进行说明。
ms.openlocfilehash: 1b9a813be825f2deeb5c90d596ffd9f3705bcef6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779815"
---
# <a name="c-cell-geometry-section"></a><span data-ttu-id="94cc0-104">C 单元格（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="94cc0-104">C Cell (Geometry Section)</span></span>

<span data-ttu-id="94cc0-p102">代表不同行中的不同信息。该表基于 C 单元格所在的行对它进行说明。</span><span class="sxs-lookup"><span data-stu-id="94cc0-p102">Represents different information in different rows. This table describes the C cell based on the row in which it's located.</span></span>
  
|<span data-ttu-id="94cc0-107">**Row**</span><span class="sxs-lookup"><span data-stu-id="94cc0-107">**Row**</span></span>|<span data-ttu-id="94cc0-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="94cc0-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="94cc0-109">EllipticalArcTo</span><span class="sxs-lookup"><span data-stu-id="94cc0-109">EllipticalArcTo</span></span>](ellipticalarcto-row-geometry-section.md) <br/> | <span data-ttu-id="94cc0-110">弧形的长轴相对于*x*角度-其父级的轴。</span><span class="sxs-lookup"><span data-stu-id="94cc0-110">The angle of an arc's major axis relative to the  *x*  -axis of its parent.</span></span>  <br/> |
|[<span data-ttu-id="94cc0-111">NURBSTo</span><span class="sxs-lookup"><span data-stu-id="94cc0-111">NURBSTo</span></span>](nurbsto-row-geometry-section.md) <br/> | <span data-ttu-id="94cc0-112">非均匀有理 B 样条 (NURBS) 的第一个节点。</span><span class="sxs-lookup"><span data-stu-id="94cc0-112">The first knot of the nonuniform rational B-spline (NURBS).</span></span>  <br/> |
|[<span data-ttu-id="94cc0-113">SplineStart</span><span class="sxs-lookup"><span data-stu-id="94cc0-113">SplineStart</span></span>](splinestart-row-geometry-section.md) <br/> | <span data-ttu-id="94cc0-114">样条的最后一个节点。</span><span class="sxs-lookup"><span data-stu-id="94cc0-114">The last knot of a spline.</span></span>  <br/> |
|[<span data-ttu-id="94cc0-115">椭圆</span><span class="sxs-lookup"><span data-stu-id="94cc0-115">Ellipse</span></span>](ellipse-row-geometry-section.md) <br/> | <span data-ttu-id="94cc0-116">*X* -椭圆; 上某个点的坐标与*y*配对- [D](d-cell-geometry-section.md)单元格所表示的坐标。</span><span class="sxs-lookup"><span data-stu-id="94cc0-116">An  *x*  -coordinate of a point on an ellipse; paired with the  *y*  -coordinate represented by the [D](d-cell-geometry-section.md) cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="94cc0-117">说明</span><span class="sxs-lookup"><span data-stu-id="94cc0-117">Remarks</span></span>

<span data-ttu-id="94cc0-118">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 C 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="94cc0-118">To get a reference to the C cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="94cc0-119">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="94cc0-119">Cell name:</span></span>  <br/> | <span data-ttu-id="94cc0-120">Geometry *i* 。C *j*其中*i*和*j* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="94cc0-120">Geometry  *i*  .C  *j*            where  *i*  and  *j*  = <1>, 2, 3...</span></span>  <br/> |
|| <span data-ttu-id="94cc0-121">Geometry *i* 。C1 （Ellipse 行）</span><span class="sxs-lookup"><span data-stu-id="94cc0-121">Geometry  *i*  .C1 (Ellipse row)</span></span>  <br/> |
   
<span data-ttu-id="94cc0-122">要从某个程序按索引获取对 C 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="94cc0-122">To get a reference to the C cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="94cc0-123">内容索引：</span><span class="sxs-lookup"><span data-stu-id="94cc0-123">Section index:</span></span>  <br/> |<span data-ttu-id="94cc0-124">**visSectionFirstComponent** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="94cc0-124">**visSectionFirstComponent** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="94cc0-125">行索引：</span><span class="sxs-lookup"><span data-stu-id="94cc0-125">Row index:</span></span>  <br/> |<span data-ttu-id="94cc0-126">**visRowVertex** +  *j*其中*j* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="94cc0-126">**visRowVertex** +  *j*            where  *j*  = 0, 1, 2...</span></span>  <br/> |
||<span data-ttu-id="94cc0-127">**visRowVertex**（Ellipse 行）</span><span class="sxs-lookup"><span data-stu-id="94cc0-127">**visRowVertex** (Ellipse row)</span></span>  <br/> |
| <span data-ttu-id="94cc0-128">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="94cc0-128">Cell index:</span></span>  <br/> |<span data-ttu-id="94cc0-129">**visEccentricityAngle**（EllipticalArcTo 行）</span><span class="sxs-lookup"><span data-stu-id="94cc0-129">**visEccentricityAngle** (EllipticalArcTo row)</span></span>  <br/> |
||<span data-ttu-id="94cc0-130">**visNURBSKnotPrev**（NURBSTo 行）</span><span class="sxs-lookup"><span data-stu-id="94cc0-130">**visNURBSKnotPrev** (NURBSTo row)</span></span>  <br/> |
||<span data-ttu-id="94cc0-131">**visSplineKnot3**（SplineStart 行）</span><span class="sxs-lookup"><span data-stu-id="94cc0-131">**visSplineKnot3** (SplineStart row)</span></span>  <br/> |
||<span data-ttu-id="94cc0-132">**visEllipseMinorX**（Ellipse 行）</span><span class="sxs-lookup"><span data-stu-id="94cc0-132">**visEllipseMinorX** (Ellipse row)</span></span>  <br/> |
   
