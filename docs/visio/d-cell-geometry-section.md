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
description: 代表不同行中的不同信息。此表基于 D 单元格所在的行对它进行说明。
ms.openlocfilehash: ed67197e46ee159ba2175b0e86623fe1704992d2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780009"
---
# <a name="d-cell-geometry-section"></a><span data-ttu-id="2a33d-104">D 单元格（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="2a33d-104">D Cell (Geometry Section)</span></span>

<span data-ttu-id="2a33d-p102">代表不同行中的不同信息。此表基于 D 单元格所在的行对它进行说明。</span><span class="sxs-lookup"><span data-stu-id="2a33d-p102">Represents different information in different rows. This table describes the D cell based on the row in which it's located.</span></span>
  
|<span data-ttu-id="2a33d-107">**Row**</span><span class="sxs-lookup"><span data-stu-id="2a33d-107">**Row**</span></span>|<span data-ttu-id="2a33d-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="2a33d-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="2a33d-109">EllipticalArcTo</span><span class="sxs-lookup"><span data-stu-id="2a33d-109">EllipticalArcTo</span></span>](ellipticalarcto-row-geometry-section.md) <br/> | <span data-ttu-id="2a33d-p103">弧形的长短轴之比。尽管每一词都有其本义，但在此处“长”轴却并不一定大于“短”轴，所以此比值也就不一定大于 1。如果将此单元格设置为小于等于 0 或大于 1000 的值，可能导致无法预料的结果。</span><span class="sxs-lookup"><span data-stu-id="2a33d-p103">The ratio of an arc's major axis to its minor axis. Despite the usual meaning of these words, the "major" axis does not have to be greater than the "minor" axis, so this ratio does not have to be greater than 1. Setting this cell to a value less than or equal to 0 or greater than 1000 can lead to unpredictable results.</span></span>  <br/> |
|[<span data-ttu-id="2a33d-113">NURBSTo</span><span class="sxs-lookup"><span data-stu-id="2a33d-113">NURBSTo</span></span>](nurbsto-row-geometry-section.md) <br/> | <span data-ttu-id="2a33d-114">非均匀有理 B 样条 (NURBS) 的第一个权。</span><span class="sxs-lookup"><span data-stu-id="2a33d-114">The first weight of the nonuniform rational B-spline (NURBS).</span></span>  <br/> |
|[<span data-ttu-id="2a33d-115">SplineStart</span><span class="sxs-lookup"><span data-stu-id="2a33d-115">SplineStart</span></span>](splinestart-row-geometry-section.md) <br/> | <span data-ttu-id="2a33d-116">样条的角度（从 1 到 25 的整数）。</span><span class="sxs-lookup"><span data-stu-id="2a33d-116">The degree of a spline (an integer from 1 to 25).</span></span>  <br/> |
|[<span data-ttu-id="2a33d-117">椭圆</span><span class="sxs-lookup"><span data-stu-id="2a33d-117">Ellipse</span></span>](ellipse-row-geometry-section.md) <br/> | <span data-ttu-id="2a33d-118">*Y* -椭圆; 上某个点的坐标与*x*配对- [C](c-cell-geometry-section.md)单元格所表示的坐标。</span><span class="sxs-lookup"><span data-stu-id="2a33d-118">A  *y*  -coordinate of a point on an ellipse; paired with the  *x*  -coordinate represented by the [C](c-cell-geometry-section.md) cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2a33d-119">备注</span><span class="sxs-lookup"><span data-stu-id="2a33d-119">Remarks</span></span>

<span data-ttu-id="2a33d-120">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 D 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="2a33d-120">To get a reference to the D cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2a33d-121">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="2a33d-121">Cell name:</span></span>  <br/> | <span data-ttu-id="2a33d-122">Geometry *i* 。D *j*其中*i*和*j* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="2a33d-122">Geometry  *i*  .D  *j*            where  *i*  and  *j*  = <1>, 2, 3...</span></span>  <br/> |
|| <span data-ttu-id="2a33d-123">Geometry *i* 。D1 （Ellipse 行） 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="2a33d-123">Geometry  *i*  .D1 (Ellipse row)            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="2a33d-124">若要从某个程序按索引获取对 D 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="2a33d-124">To get a reference to the D cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2a33d-125">内容索引：</span><span class="sxs-lookup"><span data-stu-id="2a33d-125">Section index:</span></span>  <br/> |<span data-ttu-id="2a33d-126">**visSectionFirstComponent** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="2a33d-126">**visSectionFirstComponent** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="2a33d-127">行索引：</span><span class="sxs-lookup"><span data-stu-id="2a33d-127">Row index:</span></span>  <br/> |<span data-ttu-id="2a33d-128">**visRowVertex** +  *j*其中*j* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="2a33d-128">**visRowVertex** +  *j*            where  *j*  = 0, 1, 2...</span></span>  <br/> |
||<span data-ttu-id="2a33d-129">**visRowVertex**（ellipse 行）</span><span class="sxs-lookup"><span data-stu-id="2a33d-129">**visRowVertex** (Ellipse row)</span></span>  <br/> |
| <span data-ttu-id="2a33d-130">单元格索引</span><span class="sxs-lookup"><span data-stu-id="2a33d-130">Cell index</span></span>  <br/> |<span data-ttu-id="2a33d-131">**visAspectRatio**（EllipticalArcTo 行）</span><span class="sxs-lookup"><span data-stu-id="2a33d-131">**visAspectRatio** (EllipticalArcTo row)</span></span>  <br/> |
||<span data-ttu-id="2a33d-132">**visNURBSWeightPrev**（NURBSTo 行）</span><span class="sxs-lookup"><span data-stu-id="2a33d-132">**visNURBSWeightPrev** (NURBSTo row)</span></span>  <br/> |
||<span data-ttu-id="2a33d-133">**visSplineDegree**（SplineStart 行）</span><span class="sxs-lookup"><span data-stu-id="2a33d-133">**visSplineDegree** (SplineStart row)</span></span>  <br/> |
||<span data-ttu-id="2a33d-134">**visEllipseMinorY**（ellipse 行）</span><span class="sxs-lookup"><span data-stu-id="2a33d-134">**visEllipseMinorY** (Ellipse row)</span></span>  <br/> |
   

