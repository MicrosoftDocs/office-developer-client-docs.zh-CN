---
title: B 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251751
localization_priority: Normal
ms.assetid: b0fb6a47-47d8-ab9c-854d-0b0bbfdfcc27
description: 在不同行中表示不同的信息。此表根据 B 单元格所在的行对 B 单元格进行了说明。
ms.openlocfilehash: 7d6f51d037be4852c6a101ad6e576a3a13488cb7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779667"
---
# <a name="b-cell-geometry-section"></a><span data-ttu-id="4e724-104">B 单元格（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="4e724-104">B Cell (Geometry Section)</span></span>

<span data-ttu-id="4e724-p102">在不同行中表示不同的信息。此表根据 B 单元格所在的行对 B 单元格进行了说明。</span><span class="sxs-lookup"><span data-stu-id="4e724-p102">Represents different information in different rows. This table describes the B cell based on the row in which it's located.</span></span>
  
|<span data-ttu-id="4e724-107">**Row**</span><span class="sxs-lookup"><span data-stu-id="4e724-107">**Row**</span></span>|<span data-ttu-id="4e724-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="4e724-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="4e724-109">EllipticalArcTo</span><span class="sxs-lookup"><span data-stu-id="4e724-109">EllipticalArcTo</span></span>](ellipticalarcto-row-geometry-section.md) <br/> | <span data-ttu-id="4e724-110">*Y* -弧形的控制点的坐标。</span><span class="sxs-lookup"><span data-stu-id="4e724-110">The  *y*  -coordinate of an arc's control point.</span></span>  <br/> |
|[<span data-ttu-id="4e724-111">NURBSTo</span><span class="sxs-lookup"><span data-stu-id="4e724-111">NURBSTo</span></span>](nurbsto-row-geometry-section.md) <br/> | <span data-ttu-id="4e724-112">非均匀有理 B 样条 (NURBS) 的最后一个权值。</span><span class="sxs-lookup"><span data-stu-id="4e724-112">The last weight of the nonuniform rational B-spline (NURBS).</span></span>  <br/> |
|[<span data-ttu-id="4e724-113">SplineStart</span><span class="sxs-lookup"><span data-stu-id="4e724-113">SplineStart</span></span>](splinestart-row-geometry-section.md) <br/> | <span data-ttu-id="4e724-114">样条的第一个节点。</span><span class="sxs-lookup"><span data-stu-id="4e724-114">The first knot of a spline.</span></span>  <br/> |
|[<span data-ttu-id="4e724-115">InfiniteLine</span><span class="sxs-lookup"><span data-stu-id="4e724-115">InfiniteLine</span></span>](infiniteline-row-geometry-section.md) <br/> | <span data-ttu-id="4e724-116">*Y* -; 无限长线上某个点的坐标与*x*配对- [A](a-cell-geometry-section.md)单元格所表示的坐标。</span><span class="sxs-lookup"><span data-stu-id="4e724-116">A  *y*  -coordinate of a point on an infinite line; paired with  *x*  -coordinate represented by the [A](a-cell-geometry-section.md) cell.</span></span>  <br/> |
|[<span data-ttu-id="4e724-117">椭圆</span><span class="sxs-lookup"><span data-stu-id="4e724-117">Ellipse</span></span>](ellipse-row-geometry-section.md) <br/> | <span data-ttu-id="4e724-118">*Y* -椭圆; 上某个点的坐标与*x*配对- [A](a-cell-geometry-section.md)单元格所表示的坐标。</span><span class="sxs-lookup"><span data-stu-id="4e724-118">A  *y*  -coordinate of a point on an ellipse; paired with  *x*  -coordinate represented by the [A](a-cell-geometry-section.md) cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4e724-119">备注</span><span class="sxs-lookup"><span data-stu-id="4e724-119">Remarks</span></span>

<span data-ttu-id="4e724-120">若要从另一个公式或从使用**CellsU**属性的某个程序按名称获取对 B 单元格的引用使用：</span><span class="sxs-lookup"><span data-stu-id="4e724-120">To get a reference to the B cell by name from another formula, or from a program, using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4e724-121">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4e724-121">Cell name:</span></span>  <br/> | <span data-ttu-id="4e724-122">Geometry *i* 。B *j*其中*i*和*j* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="4e724-122">Geometry  *i*  .B  *j*            where  *i*  and  *j*  = <1>, 2, 3...</span></span>  <br/> |
|| <span data-ttu-id="4e724-123">Geometry *i* 。B1 （InfiniteLine 和 Ellipse 行）</span><span class="sxs-lookup"><span data-stu-id="4e724-123">Geometry  *i*  .B1 (InfiniteLine and Ellipse rows)</span></span>  <br/> |
   
<span data-ttu-id="4e724-124">若要从某个程序按索引获取对 B 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="4e724-124">To get a reference to the B cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4e724-125">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4e724-125">Section index:</span></span>  <br/> |<span data-ttu-id="4e724-126">**visSectionFirstComponent** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="4e724-126">**visSectionFirstComponent** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="4e724-127">行索引：</span><span class="sxs-lookup"><span data-stu-id="4e724-127">Row index:</span></span>  <br/> |<span data-ttu-id="4e724-128">**visRowVertex** +  *j*其中*j* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="4e724-128">**visRowVertex** +  *j*            where  *j*  = 0, 1, 2...</span></span>  <br/> |
||<span data-ttu-id="4e724-129">**visRowVertex**（InfiniteLine 和 Ellipse 行）</span><span class="sxs-lookup"><span data-stu-id="4e724-129">**visRowVertex** (InfiniteLine and Ellipse rows)</span></span>  <br/> |
| <span data-ttu-id="4e724-130">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4e724-130">Cell index:</span></span>  <br/> |<span data-ttu-id="4e724-131">**visControlX**（EllipticalArcTo 行）</span><span class="sxs-lookup"><span data-stu-id="4e724-131">**visControlX** (EllipticalArcTo row)</span></span>  <br/> |
||<span data-ttu-id="4e724-132">**visControlY**（EllipticalArcTo 行）</span><span class="sxs-lookup"><span data-stu-id="4e724-132">**visControlY** (EllipticalArcTo row)</span></span>  <br/> |
||<span data-ttu-id="4e724-133">**visNURBSWeight**（NURBSTo 行）</span><span class="sxs-lookup"><span data-stu-id="4e724-133">**visNURBSWeight** (NURBSTo row)</span></span>  <br/> |
||<span data-ttu-id="4e724-134">**visSplineKnot2**（SplineStart 行）</span><span class="sxs-lookup"><span data-stu-id="4e724-134">**visSplineKnot2** (SplineStart row)</span></span>  <br/> |
||<span data-ttu-id="4e724-135">**visInfiniteLineY2**（InfiniteLine 行）</span><span class="sxs-lookup"><span data-stu-id="4e724-135">**visInfiniteLineY2** (InfiniteLine row)</span></span>  <br/> |
||<span data-ttu-id="4e724-136">**visEllipseMajorY**（ellipse 行）</span><span class="sxs-lookup"><span data-stu-id="4e724-136">**visEllipseMajorY** (Ellipse row)</span></span>  <br/> |
   

