---
title: 'RelCubBezTo Row (Geometry Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 77777dd4-5a2c-4048-9ea4-9bd876862963
description: 包含三次方贝塞尔曲线终点相对于形状的宽度和高度的 x 坐标和 y 坐标，曲线相对形状的宽度和高度的起点的控制点的 x 坐标和 y 坐标，以及曲线相对形状的宽度和高度终点的控制点的 x 坐标和 y 坐标。
ms.openlocfilehash: cb886706c4c5cbb3488a95b57dcc84e0e45ee326
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430327"
---
# <a name="relcubbezto-row-geometry-section"></a><span data-ttu-id="1f43b-103">RelCubBezTo Row (Geometry Section) </span><span class="sxs-lookup"><span data-stu-id="1f43b-103">RelCubBezTo Row (Geometry Section)</span></span>

<span data-ttu-id="1f43b-104">包含三次方贝塞尔曲线终点相对于形状的宽度和高度的  *x*  坐标和  *y*  坐标，曲线相对形状的宽度和高度的起点的控制点的  *x*  坐标和  *y*  坐标，以及曲线相对形状的宽度和高度终点的控制点的  *x*  坐标和  *y*  坐标。</span><span class="sxs-lookup"><span data-stu-id="1f43b-104">Contains the  *x*  - and  *y*  -coordinates of the endpoint of a cubic Bézier curve relative to the shape's width and height, the  *x*  - and  *y*  -coordinates of the control point of the beginning of the curve relative shape's width and height, and the  *x*  - and  *y*  -coordinates of the control point of the ending of the curve relative shape's width and height.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1f43b-105">**RelCubBezTo** 行只能保留为 .vsdx、.vsdm、.vstx、.vstm、.vssx 和 .vssm 文件格式。</span><span class="sxs-lookup"><span data-stu-id="1f43b-105">A **RelCubBezTo** row can only be persisted in the .vsdx, .vsdm, .vstx, .vstm, .vssx, and .vssm file formats.</span></span> <span data-ttu-id="1f43b-106">将文件保存为 Visio 2003-2010 格式时 **，RelCubBezTo** 行将转换为 [NURBSTo](nurbsto-row-geometry-section.md)行。</span><span class="sxs-lookup"><span data-stu-id="1f43b-106">When a file is saved to the Visio 2003-2010 formats, the **RelCubBezTo** row is converted to a [NURBSTo](nurbsto-row-geometry-section.md) row.</span></span> 
  
<span data-ttu-id="1f43b-107">**RelCubBezTo** 行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="1f43b-107">A **RelCubBezTo** row contains the following cells.</span></span> 
  
|<span data-ttu-id="1f43b-108">**Cell**</span><span class="sxs-lookup"><span data-stu-id="1f43b-108">**Cell**</span></span>|<span data-ttu-id="1f43b-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="1f43b-109">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="1f43b-110">X</span><span class="sxs-lookup"><span data-stu-id="1f43b-110">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="1f43b-111">三次方贝塞尔曲线的终顶点相对于形状宽度的  *x*  坐标。</span><span class="sxs-lookup"><span data-stu-id="1f43b-111">The  *x*  -coordinate of the ending vertex of a cubic Bézier curve relative to the width of the shape.</span></span>  <br/> |
|[<span data-ttu-id="1f43b-112">Y</span><span class="sxs-lookup"><span data-stu-id="1f43b-112">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="1f43b-113">三次方贝塞尔曲线终顶点相对于形状高度的  *y*  坐标。</span><span class="sxs-lookup"><span data-stu-id="1f43b-113">The  *y*  -coordinate of the ending vertex of a cubic Bézier curve relative to the height of the shape.</span></span>  <br/> |
|[<span data-ttu-id="1f43b-114">A</span><span class="sxs-lookup"><span data-stu-id="1f43b-114">A</span></span>](a-cell-geometry-section.md) <br/> |<span data-ttu-id="1f43b-115">曲线的起点控制点相对于形状宽度的  *x*  坐标;弧形上的点。控制点最好位于弧形的开始顶点和结束顶点之间。</span><span class="sxs-lookup"><span data-stu-id="1f43b-115">The  *x*  -coordinate of the curve's beginning control point relative to the shape's width; a point on the arc. The control point is best located between the beginning and ending vertices of the arc.</span></span>  <br/> |
|[<span data-ttu-id="1f43b-116">B</span><span class="sxs-lookup"><span data-stu-id="1f43b-116">B</span></span>](b-cell-geometry-section.md) <br/> |<span data-ttu-id="1f43b-117">曲线的起点控制点相对于形状高度的  *y*  坐标。</span><span class="sxs-lookup"><span data-stu-id="1f43b-117">The  *y*  -coordinate of a curve's beginning control point relative to the shape's height.</span></span>  <br/> |
|[<span data-ttu-id="1f43b-118">C</span><span class="sxs-lookup"><span data-stu-id="1f43b-118">C</span></span>](c-cell-geometry-section.md) <br/> |<span data-ttu-id="1f43b-119">曲线的结束控制点相对于形状宽度的  *x*  坐标;弧形上的点。控制点最好位于弧形的开始控制点和结束顶点之间。</span><span class="sxs-lookup"><span data-stu-id="1f43b-119">The  *x*  -coordinate of the curve's ending control point relative to the shape's width; a point on the arc. The control point is best located between the beginning control point and ending vertices of the arc.</span></span>  <br/> |
|[<span data-ttu-id="1f43b-120">D</span><span class="sxs-lookup"><span data-stu-id="1f43b-120">D</span></span>](d-cell-geometry-section.md) <br/> |<span data-ttu-id="1f43b-121">曲线的结束控制点相对于形状高度的  *y*  坐标。</span><span class="sxs-lookup"><span data-stu-id="1f43b-121">The  *y*  -coordinate of a curve's ending control point relative to the shape's height.</span></span>  <br/> |
   

