---
title: “Geometry”内容
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm2055
localization_priority: Normal
ms.assetid: 75601a1e-6b1a-27ee-a2bd-69e569315982
description: 包含列出构成形状的线条和弧形的顶点坐标的行。
ms.openlocfilehash: d45f960ecc697dc6f0f5a0efa18e6cbbc6e4fff0
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542280"
---
# <a name="geometry-section"></a><span data-ttu-id="5ad18-103">“Geometry”内容</span><span class="sxs-lookup"><span data-stu-id="5ad18-103">Geometry Section</span></span>

<span data-ttu-id="5ad18-104">包含列出构成形状的线条和弧形的顶点坐标的行。</span><span class="sxs-lookup"><span data-stu-id="5ad18-104">Contains rows that list the coordinates of the vertices for the lines and arcs that make up the shape.</span></span> 
  
<span data-ttu-id="5ad18-105">形状的几何图形可以用多个"Geometry" **内容** 表示。</span><span class="sxs-lookup"><span data-stu-id="5ad18-105">The geometry of a shape can be expressed in multiple **Geometry** sections.</span></span> <span data-ttu-id="5ad18-106">当多个路径具有不同的属性（例如，图像剪辑路径 (）时，多个路径) 。 [](clippingpath-cell-foreign-image-info-section.md)</span><span class="sxs-lookup"><span data-stu-id="5ad18-106">Multiple paths can be useful when multiple paths have different properties (e.g. [image clipping](clippingpath-cell-foreign-image-info-section.md) paths).</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="5ad18-107">备注</span><span class="sxs-lookup"><span data-stu-id="5ad18-107">Remarks</span></span>

<span data-ttu-id="5ad18-108">**"Geometry"** 内容包含以下行类型。</span><span class="sxs-lookup"><span data-stu-id="5ad18-108">The **Geometry** section contains the following row types.</span></span> <span data-ttu-id="5ad18-109">有关详细信息，请参阅行主题。</span><span class="sxs-lookup"><span data-stu-id="5ad18-109">For details, see the row topics.</span></span> 
  
|<span data-ttu-id="5ad18-110">Row</span><span class="sxs-lookup"><span data-stu-id="5ad18-110">Row</span></span>|<span data-ttu-id="5ad18-111">说明</span><span class="sxs-lookup"><span data-stu-id="5ad18-111">Description</span></span>|
|:-----|:-----|
|[<span data-ttu-id="5ad18-112">MoveTo</span><span class="sxs-lookup"><span data-stu-id="5ad18-112">MoveTo</span></span>](moveto-row-geometry-section.md) <br/> |<span data-ttu-id="5ad18-113">移到某一坐标处。</span><span class="sxs-lookup"><span data-stu-id="5ad18-113">Move to a coordinate.</span></span>  <br/> |
|[<span data-ttu-id="5ad18-114">LineTo</span><span class="sxs-lookup"><span data-stu-id="5ad18-114">LineTo</span></span>](lineto-row-geometry-section.md) <br/> |<span data-ttu-id="5ad18-115">绘制一条到某坐标处的直线。</span><span class="sxs-lookup"><span data-stu-id="5ad18-115">Draw a line to a coordinate.</span></span>  <br/> |
|[<span data-ttu-id="5ad18-116">ArcTo</span><span class="sxs-lookup"><span data-stu-id="5ad18-116">ArcTo</span></span>](arcto-row-geometry-section.md) <br/> |<span data-ttu-id="5ad18-117">绘制一条到某坐标处的圆弧。</span><span class="sxs-lookup"><span data-stu-id="5ad18-117">Draw a circular arc to a coordinate.</span></span>  <br/> |
|[<span data-ttu-id="5ad18-118">EllipticalArcTo</span><span class="sxs-lookup"><span data-stu-id="5ad18-118">EllipticalArcTo</span></span>](ellipticalarcto-row-geometry-section.md) <br/> |<span data-ttu-id="5ad18-119">绘制一条到某坐标处的椭圆弧。</span><span class="sxs-lookup"><span data-stu-id="5ad18-119">Draw an elliptical arc to a coordinate.</span></span>  <br/> |
|[<span data-ttu-id="5ad18-120">PolylineTo</span><span class="sxs-lookup"><span data-stu-id="5ad18-120">PolylineTo</span></span>](polylineto-row-geometry-section.md) <br/> |<span data-ttu-id="5ad18-121">绘制一条到某坐标处的折线或连续线条。</span><span class="sxs-lookup"><span data-stu-id="5ad18-121">Draw a polyline, or consecutive lines, to a coordinate.</span></span>  <br/> |
|[<span data-ttu-id="5ad18-122">NURBSTo</span><span class="sxs-lookup"><span data-stu-id="5ad18-122">NURBSTo</span></span>](nurbsto-row-geometry-section.md) <br/> |<span data-ttu-id="5ad18-123">绘制非统一有理 B 样条 (NURBS) 坐标。</span><span class="sxs-lookup"><span data-stu-id="5ad18-123">Draw a non-uniform rational B-spline (NURBS) to a coordinate.</span></span>  <br/> |
|[<span data-ttu-id="5ad18-124">SplineStart</span><span class="sxs-lookup"><span data-stu-id="5ad18-124">SplineStart</span></span>](splinestart-row-geometry-section.md) <br/> |<span data-ttu-id="5ad18-125">开始一个样条。</span><span class="sxs-lookup"><span data-stu-id="5ad18-125">Start a spline.</span></span>  <br/> |
|[<span data-ttu-id="5ad18-126">SplineKnot</span><span class="sxs-lookup"><span data-stu-id="5ad18-126">SplineKnot</span></span>](splineknot-row-geometry-section.md) <br/> |<span data-ttu-id="5ad18-127">绘制一条到某节点坐标处的样条线段。</span><span class="sxs-lookup"><span data-stu-id="5ad18-127">Draw a spline segment to a knot coordinate.</span></span>  <br/> |
|[<span data-ttu-id="5ad18-128">InfiniteLine</span><span class="sxs-lookup"><span data-stu-id="5ad18-128">InfiniteLine</span></span>](infiniteline-row-geometry-section.md) <br/> |<span data-ttu-id="5ad18-129">在两个坐标之间绘制一条无限长线。</span><span class="sxs-lookup"><span data-stu-id="5ad18-129">Draw an infinite line from one coordinate to another.</span></span>  <br/> |
|[<span data-ttu-id="5ad18-130">Ellipse</span><span class="sxs-lookup"><span data-stu-id="5ad18-130">Ellipse</span></span>](ellipse-row-geometry-section.md) <br/> |<span data-ttu-id="5ad18-131">根据中心坐标和长轴/短轴绘制一个椭圆。</span><span class="sxs-lookup"><span data-stu-id="5ad18-131">Draw an ellipse from a center coordinate and a major/minor axis.</span></span>  <br/> |
|[<span data-ttu-id="5ad18-132">RelCubBezTo</span><span class="sxs-lookup"><span data-stu-id="5ad18-132">RelCubBezTo</span></span>](relcubbezto-row-geometry-section.md) <br/> |<span data-ttu-id="5ad18-133">绘制一条相对于形状的宽度和高度的三次方贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="5ad18-133">Draw a cubic Bezier curve relative to the width and height of the shape.</span></span>  <br/> |
|[<span data-ttu-id="5ad18-134">RelEllipticalArcTo</span><span class="sxs-lookup"><span data-stu-id="5ad18-134">RelEllipticalArcTo</span></span>](relellipticalarcto-row-geometry-section.md) <br/> |<span data-ttu-id="5ad18-135">为相对于形状的高度和宽度的坐标绘制椭圆弧。</span><span class="sxs-lookup"><span data-stu-id="5ad18-135">Draw an elliptical arc to a coordinate relative to the height and width of the shape.</span></span>  <br/> |
|[<span data-ttu-id="5ad18-136">RelLineTo</span><span class="sxs-lookup"><span data-stu-id="5ad18-136">RelLineTo</span></span>](rellineto-row-geometry-section.md) <br/> |<span data-ttu-id="5ad18-137">绘制一条相对于形状的高度和宽度的坐标的线条。</span><span class="sxs-lookup"><span data-stu-id="5ad18-137">Draw a line to a coordinate relative the height and width of a shape.</span></span>  <br/> |
|[<span data-ttu-id="5ad18-138">RelMoveTo</span><span class="sxs-lookup"><span data-stu-id="5ad18-138">RelMoveTo</span></span>](relmoveto-row-geometry-section.md) <br/> |<span data-ttu-id="5ad18-139">移动到相对于形状的宽度和高度的坐标。</span><span class="sxs-lookup"><span data-stu-id="5ad18-139">Move to a coordinate relative to the width and height of the shape.</span></span>  <br/> |
|[<span data-ttu-id="5ad18-140">RelQuadBezTo</span><span class="sxs-lookup"><span data-stu-id="5ad18-140">RelQuadBezTo</span></span>](relquadbezto-row-geometry-section.md) <br/> |<span data-ttu-id="5ad18-141">绘制一条相对于形状的宽度和高度的二次方贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="5ad18-141">Draws a quadratic Bezier curve relative to the width and height of the shape.</span></span>  <br/> |
   
<span data-ttu-id="5ad18-142">若要在此内容中更改行的类型，请右击该行，然后在快捷菜单上单击 **“更改行类型”**。</span><span class="sxs-lookup"><span data-stu-id="5ad18-142">To change a row type in this section, right-click the row, and then click **Change Row Type** on the shortcut menu.</span></span> 
  

