---
title: 'RelQuadBezTo Row (Geometry Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5ae57707-5a50-43f0-8c78-516790b5034e
description: 包含二次方贝塞尔曲线终点相对于形状的宽度和高度的 x 坐标和 y 坐标，以及曲线相对形状的宽度和高度的控制点的 x 坐标和 y 坐标。
ms.openlocfilehash: f517fa006c6630a26e9162adfbb1be2139487e63
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423354"
---
# <a name="relquadbezto-row-geometry-section"></a><span data-ttu-id="ba04b-103">RelQuadBezTo Row (Geometry Section) </span><span class="sxs-lookup"><span data-stu-id="ba04b-103">RelQuadBezTo Row (Geometry Section)</span></span>

<span data-ttu-id="ba04b-104">包含二次方贝塞尔曲线终点相对于形状的宽度和高度的  *x*  坐标和  *y*  坐标，以及曲线相对形状的宽度和高度的控制点的  *x*  坐标和  *y*  坐标。</span><span class="sxs-lookup"><span data-stu-id="ba04b-104">Contains the  *x*  - and  *y*  -coordinates of the endpoint of a quadratic Bézier curve relative to the shape's width and height and the  *x*  - and  *y*  -coordinates of the control point of the curve relative shape's width and height.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ba04b-105">**RelQuadBezTo** 行只能保留为 .vsdx、.vsdm、.vstx、.vstm、.vssx 和 .vssm 文件格式。</span><span class="sxs-lookup"><span data-stu-id="ba04b-105">A **RelQuadBezTo** row can only be persisted in the .vsdx, .vsdm, .vstx, .vstm, .vssx, and .vssm file formats.</span></span> <span data-ttu-id="ba04b-106">将文件保存为 Visio 2003-2010 格式时 **，RelQuadBezTo** 行将转换为 [NURBSTo](nurbsto-row-geometry-section.md)行。</span><span class="sxs-lookup"><span data-stu-id="ba04b-106">When a file is saved to the Visio 2003-2010 formats, the **RelQuadBezTo** row is converted to a [NURBSTo](nurbsto-row-geometry-section.md) row.</span></span> 
  
<span data-ttu-id="ba04b-107">**RelQuadBezTo** 行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="ba04b-107">A **RelQuadBezTo** row contains the following cells.</span></span> 
  
|<span data-ttu-id="ba04b-108">**Cell**</span><span class="sxs-lookup"><span data-stu-id="ba04b-108">**Cell**</span></span>|<span data-ttu-id="ba04b-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="ba04b-109">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="ba04b-110">X</span><span class="sxs-lookup"><span data-stu-id="ba04b-110">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="ba04b-111">二次方贝塞尔曲线的终顶点相对于形状宽度的  *x*  坐标。</span><span class="sxs-lookup"><span data-stu-id="ba04b-111">The  *x*  -coordinate of the ending vertex of a quadratic Bézier curve relative to the width of the shape.</span></span>  <br/> |
|[<span data-ttu-id="ba04b-112">Y</span><span class="sxs-lookup"><span data-stu-id="ba04b-112">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="ba04b-113">二次方贝塞尔曲线的终顶点相对于形状高度的  *y*  坐标。</span><span class="sxs-lookup"><span data-stu-id="ba04b-113">The  *y*  -coordinate of the ending vertex of a quadratic Bézier curve relative to the height of the shape.</span></span>  <br/> |
|[<span data-ttu-id="ba04b-114">A</span><span class="sxs-lookup"><span data-stu-id="ba04b-114">A</span></span>](a-cell-geometry-section.md) <br/> |<span data-ttu-id="ba04b-115">曲线控制点相对于形状宽度的  *x*  坐标;弧形上的点。控制点最好位于弧形的开始顶点和结束顶点之间的一半左右。</span><span class="sxs-lookup"><span data-stu-id="ba04b-115">The  *x*  -coordinate of the curve's control point relative to the shape's width; a point on the arc. The control point is best located about halfway between the beginning and ending vertices of the arc.</span></span>  <br/> |
|[<span data-ttu-id="ba04b-116">B</span><span class="sxs-lookup"><span data-stu-id="ba04b-116">B</span></span>](b-cell-geometry-section.md) <br/> |<span data-ttu-id="ba04b-117">曲线控制点相对于形状高度的  *y*  坐标。</span><span class="sxs-lookup"><span data-stu-id="ba04b-117">The  *y*  -coordinate of a curve's control point relative to the shape's height.</span></span>  <br/> |
   

