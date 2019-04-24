---
title: RelCubBezTo 行 ("Geometry" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 77777dd4-5a2c-4048-9ea4-9bd876862963
description: 包含相对于形状的宽度和高度的三次方贝塞尔曲线终结点的 x 坐标和 y 坐标、曲线相对形状的宽度和高度起始控制点的 x 坐标和 y 坐标以及 contro 的 x 坐标和 y 坐标。曲线相对形状的宽度和高度的结束点。
ms.openlocfilehash: cb886706c4c5cbb3488a95b57dcc84e0e45ee326
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320032"
---
# <a name="relcubbezto-row-geometry-section"></a><span data-ttu-id="05a60-103">RelCubBezTo 行 ("Geometry" 部分)</span><span class="sxs-lookup"><span data-stu-id="05a60-103">RelCubBezTo Row (Geometry Section)</span></span>

<span data-ttu-id="05a60-104">包含相对于形状的宽度和高度的三次方贝塞尔曲线终结点的*x*坐标和*y*坐标、曲线相对形状的宽度和高度起始点的*x*坐标和*y*坐标,以及曲线相对形状的宽度和高度的结束控制点的*x*坐标和*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="05a60-104">Contains the  *x*  - and  *y*  -coordinates of the endpoint of a cubic Bézier curve relative to the shape's width and height, the  *x*  - and  *y*  -coordinates of the control point of the beginning of the curve relative shape's width and height, and the  *x*  - and  *y*  -coordinates of the control point of the ending of the curve relative shape's width and height.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="05a60-105">**RelCubBezTo**行只能在 .vsdx、.vsdm、.vstx、.vstm、.vssx 和. .vssm 文件格式中持久化。</span><span class="sxs-lookup"><span data-stu-id="05a60-105">A **RelCubBezTo** row can only be persisted in the .vsdx, .vsdm, .vstx, .vstm, .vssx, and .vssm file formats.</span></span> <span data-ttu-id="05a60-106">将文件保存为 Visio 2003-2010 格式时, **RelCubBezTo**行将转换为[NURBSTo](nurbsto-row-geometry-section.md)行。</span><span class="sxs-lookup"><span data-stu-id="05a60-106">When a file is saved to the Visio 2003-2010 formats, the **RelCubBezTo** row is converted to a [NURBSTo](nurbsto-row-geometry-section.md) row.</span></span> 
  
<span data-ttu-id="05a60-107">**RelCubBezTo**行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="05a60-107">A **RelCubBezTo** row contains the following cells.</span></span> 
  
|<span data-ttu-id="05a60-108">**Cell**</span><span class="sxs-lookup"><span data-stu-id="05a60-108">**Cell**</span></span>|<span data-ttu-id="05a60-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="05a60-109">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="05a60-110">X</span><span class="sxs-lookup"><span data-stu-id="05a60-110">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="05a60-111">一条立方贝塞尔曲线终顶点相对于形状宽度的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="05a60-111">The  *x*  -coordinate of the ending vertex of a cubic Bézier curve relative to the width of the shape.</span></span>  <br/> |
|[<span data-ttu-id="05a60-112">Y</span><span class="sxs-lookup"><span data-stu-id="05a60-112">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="05a60-113">一条立方贝塞尔曲线终顶点的*y*坐标 (相对于形状的高度)。</span><span class="sxs-lookup"><span data-stu-id="05a60-113">The  *y*  -coordinate of the ending vertex of a cubic Bézier curve relative to the height of the shape.</span></span>  <br/> |
|[<span data-ttu-id="05a60-114">A</span><span class="sxs-lookup"><span data-stu-id="05a60-114">A</span></span>](a-cell-geometry-section.md) <br/> |<span data-ttu-id="05a60-115">曲线的起始控制点相对于形状宽度的*x*坐标;弧形上的一点。控制点最好位于弧形的起始和结束顶点之间。</span><span class="sxs-lookup"><span data-stu-id="05a60-115">The  *x*  -coordinate of the curve's beginning control point relative to the shape's width; a point on the arc. The control point is best located between the beginning and ending vertices of the arc.</span></span>  <br/> |
|[<span data-ttu-id="05a60-116">黑白</span><span class="sxs-lookup"><span data-stu-id="05a60-116">B</span></span>](b-cell-geometry-section.md) <br/> |<span data-ttu-id="05a60-117">相对于形状的高度的曲线起点的*y*轴坐标值。</span><span class="sxs-lookup"><span data-stu-id="05a60-117">The  *y*  -coordinate of a curve's beginning control point relative to the shape's height.</span></span>  <br/> |
|[<span data-ttu-id="05a60-118">lc</span><span class="sxs-lookup"><span data-stu-id="05a60-118">C</span></span>](c-cell-geometry-section.md) <br/> |<span data-ttu-id="05a60-119">相对于形状宽度的曲线结束控制点的*x*坐标;弧形上的一点。控制点最适合在弧的起始控制点和结束顶点之间。</span><span class="sxs-lookup"><span data-stu-id="05a60-119">The  *x*  -coordinate of the curve's ending control point relative to the shape's width; a point on the arc. The control point is best located between the beginning control point and ending vertices of the arc.</span></span>  <br/> |
|[<span data-ttu-id="05a60-120">D</span><span class="sxs-lookup"><span data-stu-id="05a60-120">D</span></span>](d-cell-geometry-section.md) <br/> |<span data-ttu-id="05a60-121">相对于形状高度的曲线终点的*y*轴坐标值。</span><span class="sxs-lookup"><span data-stu-id="05a60-121">The  *y*  -coordinate of a curve's ending control point relative to the shape's height.</span></span>  <br/> |
   

