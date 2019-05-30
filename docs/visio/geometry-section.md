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
# <a name="geometry-section"></a><span data-ttu-id="328bb-103">“Geometry”内容</span><span class="sxs-lookup"><span data-stu-id="328bb-103">Geometry Section</span></span>

<span data-ttu-id="328bb-104">包含列出构成形状的线条和弧形的顶点坐标的行。</span><span class="sxs-lookup"><span data-stu-id="328bb-104">Contains rows that list the coordinates of the vertices for the lines and arcs that make up the shape.</span></span> 
  
<span data-ttu-id="328bb-105">可在多个 " **geometry** " 内容中表示形状的几何图形。</span><span class="sxs-lookup"><span data-stu-id="328bb-105">The geometry of a shape can be expressed in multiple **Geometry** sections.</span></span> <span data-ttu-id="328bb-106">当多个路径具有不同的属性 (例如,[图像剪切](clippingpath-cell-foreign-image-info-section.md)路径) 时, 多个路径可能很有用。</span><span class="sxs-lookup"><span data-stu-id="328bb-106">Multiple paths can be useful when multiple paths have different properties (e.g. [image clipping](clippingpath-cell-foreign-image-info-section.md) paths).</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="328bb-107">备注</span><span class="sxs-lookup"><span data-stu-id="328bb-107">Remarks</span></span>

<span data-ttu-id="328bb-108">" **Geometry** " 内容包含以下行类型。</span><span class="sxs-lookup"><span data-stu-id="328bb-108">The **Geometry** section contains the following row types.</span></span> <span data-ttu-id="328bb-109">有关详细信息，请参阅行主题。</span><span class="sxs-lookup"><span data-stu-id="328bb-109">For details, see the row topics.</span></span> 
  
|<span data-ttu-id="328bb-110">Row</span><span class="sxs-lookup"><span data-stu-id="328bb-110">Row</span></span>|<span data-ttu-id="328bb-111">说明</span><span class="sxs-lookup"><span data-stu-id="328bb-111">Description</span></span>|
|:-----|:-----|
|[<span data-ttu-id="328bb-112">MoveTo</span><span class="sxs-lookup"><span data-stu-id="328bb-112">MoveTo</span></span>](moveto-row-geometry-section.md) <br/> |<span data-ttu-id="328bb-113">移到某一坐标处。</span><span class="sxs-lookup"><span data-stu-id="328bb-113">Move to a coordinate.</span></span>  <br/> |
|[<span data-ttu-id="328bb-114">LineTo</span><span class="sxs-lookup"><span data-stu-id="328bb-114">LineTo</span></span>](lineto-row-geometry-section.md) <br/> |<span data-ttu-id="328bb-115">绘制一条到某坐标处的直线。</span><span class="sxs-lookup"><span data-stu-id="328bb-115">Draw a line to a coordinate.</span></span>  <br/> |
|[<span data-ttu-id="328bb-116">ArcTo</span><span class="sxs-lookup"><span data-stu-id="328bb-116">ArcTo</span></span>](arcto-row-geometry-section.md) <br/> |<span data-ttu-id="328bb-117">绘制一条到某坐标处的圆弧。</span><span class="sxs-lookup"><span data-stu-id="328bb-117">Draw a circular arc to a coordinate.</span></span>  <br/> |
|[<span data-ttu-id="328bb-118">EllipticalArcTo</span><span class="sxs-lookup"><span data-stu-id="328bb-118">EllipticalArcTo</span></span>](ellipticalarcto-row-geometry-section.md) <br/> |<span data-ttu-id="328bb-119">绘制一条到某坐标处的椭圆弧。</span><span class="sxs-lookup"><span data-stu-id="328bb-119">Draw an elliptical arc to a coordinate.</span></span>  <br/> |
|[<span data-ttu-id="328bb-120">PolylineTo</span><span class="sxs-lookup"><span data-stu-id="328bb-120">PolylineTo</span></span>](polylineto-row-geometry-section.md) <br/> |<span data-ttu-id="328bb-121">绘制一条到某坐标处的折线或连续线条。</span><span class="sxs-lookup"><span data-stu-id="328bb-121">Draw a polyline, or consecutive lines, to a coordinate.</span></span>  <br/> |
|[<span data-ttu-id="328bb-122">NURBSTo</span><span class="sxs-lookup"><span data-stu-id="328bb-122">NURBSTo</span></span>](nurbsto-row-geometry-section.md) <br/> |<span data-ttu-id="328bb-123">将非统一的有理 B 样条 (NURBS) 绘制到坐标。</span><span class="sxs-lookup"><span data-stu-id="328bb-123">Draw a non-uniform rational B-spline (NURBS) to a coordinate.</span></span>  <br/> |
|[<span data-ttu-id="328bb-124">SplineStart</span><span class="sxs-lookup"><span data-stu-id="328bb-124">SplineStart</span></span>](splinestart-row-geometry-section.md) <br/> |<span data-ttu-id="328bb-125">开始一个样条。</span><span class="sxs-lookup"><span data-stu-id="328bb-125">Start a spline.</span></span>  <br/> |
|[<span data-ttu-id="328bb-126">SplineKnot</span><span class="sxs-lookup"><span data-stu-id="328bb-126">SplineKnot</span></span>](splineknot-row-geometry-section.md) <br/> |<span data-ttu-id="328bb-127">绘制一条到某节点坐标处的样条线段。</span><span class="sxs-lookup"><span data-stu-id="328bb-127">Draw a spline segment to a knot coordinate.</span></span>  <br/> |
|[<span data-ttu-id="328bb-128">InfiniteLine</span><span class="sxs-lookup"><span data-stu-id="328bb-128">InfiniteLine</span></span>](infiniteline-row-geometry-section.md) <br/> |<span data-ttu-id="328bb-129">在两个坐标之间绘制一条无限长线。</span><span class="sxs-lookup"><span data-stu-id="328bb-129">Draw an infinite line from one coordinate to another.</span></span>  <br/> |
|[<span data-ttu-id="328bb-130">椭圆</span><span class="sxs-lookup"><span data-stu-id="328bb-130">Ellipse</span></span>](ellipse-row-geometry-section.md) <br/> |<span data-ttu-id="328bb-131">根据中心坐标和长轴/短轴绘制一个椭圆。</span><span class="sxs-lookup"><span data-stu-id="328bb-131">Draw an ellipse from a center coordinate and a major/minor axis.</span></span>  <br/> |
|[<span data-ttu-id="328bb-132">RelCubBezTo</span><span class="sxs-lookup"><span data-stu-id="328bb-132">RelCubBezTo</span></span>](relcubbezto-row-geometry-section.md) <br/> |<span data-ttu-id="328bb-133">相对于形状的宽度和高度绘制一条三次方贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="328bb-133">Draw a cubic Bezier curve relative to the width and height of the shape.</span></span>  <br/> |
|[<span data-ttu-id="328bb-134">RelEllipticalArcTo</span><span class="sxs-lookup"><span data-stu-id="328bb-134">RelEllipticalArcTo</span></span>](relellipticalarcto-row-geometry-section.md) <br/> |<span data-ttu-id="328bb-135">相对于形状的高度和宽度绘制一条椭圆弧。</span><span class="sxs-lookup"><span data-stu-id="328bb-135">Draw an elliptical arc to a coordinate relative to the height and width of the shape.</span></span>  <br/> |
|[<span data-ttu-id="328bb-136">RelLineTo</span><span class="sxs-lookup"><span data-stu-id="328bb-136">RelLineTo</span></span>](rellineto-row-geometry-section.md) <br/> |<span data-ttu-id="328bb-137">绘制一条相对于形状的高度和宽度的坐标线。</span><span class="sxs-lookup"><span data-stu-id="328bb-137">Draw a line to a coordinate relative the height and width of a shape.</span></span>  <br/> |
|[<span data-ttu-id="328bb-138">RelMoveTo</span><span class="sxs-lookup"><span data-stu-id="328bb-138">RelMoveTo</span></span>](relmoveto-row-geometry-section.md) <br/> |<span data-ttu-id="328bb-139">移动到相对于形状的宽度和高度的坐标。</span><span class="sxs-lookup"><span data-stu-id="328bb-139">Move to a coordinate relative to the width and height of the shape.</span></span>  <br/> |
|[<span data-ttu-id="328bb-140">RelQuadBezTo</span><span class="sxs-lookup"><span data-stu-id="328bb-140">RelQuadBezTo</span></span>](relquadbezto-row-geometry-section.md) <br/> |<span data-ttu-id="328bb-141">相对于形状的宽度和高度绘制一条二次贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="328bb-141">Draws a quadratic Bezier curve relative to the width and height of the shape.</span></span>  <br/> |
   
<span data-ttu-id="328bb-142">若要在此内容中更改行的类型，请右击该行，然后在快捷菜单上单击 **“更改行类型”**。</span><span class="sxs-lookup"><span data-stu-id="328bb-142">To change a row type in this section, right-click the row, and then click **Change Row Type** on the shortcut menu.</span></span> 
  

