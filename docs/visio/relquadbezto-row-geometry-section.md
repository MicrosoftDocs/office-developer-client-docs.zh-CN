---
title: RelQuadBezTo 行 ("Geometry" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5ae57707-5a50-43f0-8c78-516790b5034e
description: 包含相对于形状的宽度和高度以及曲线相对形状的宽度和高度的控制点的 x 坐标和 y 坐标的二次贝塞尔曲线端点的 x 坐标和 y 坐标。
ms.openlocfilehash: f517fa006c6630a26e9162adfbb1be2139487e63
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319927"
---
# <a name="relquadbezto-row-geometry-section"></a><span data-ttu-id="8170e-103">RelQuadBezTo 行 ("Geometry" 部分)</span><span class="sxs-lookup"><span data-stu-id="8170e-103">RelQuadBezTo Row (Geometry Section)</span></span>

<span data-ttu-id="8170e-104">包含相对于形状的宽度和高度以及曲线相对形状的宽度和高度的控制点的*x*坐标和*y*坐标的二次贝塞尔曲线端点的*x*坐标和*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="8170e-104">Contains the  *x*  - and  *y*  -coordinates of the endpoint of a quadratic Bézier curve relative to the shape's width and height and the  *x*  - and  *y*  -coordinates of the control point of the curve relative shape's width and height.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8170e-105">**RelQuadBezTo**行只能在 .vsdx、.vsdm、.vstx、.vstm、.vssx 和. .vssm 文件格式中持久化。</span><span class="sxs-lookup"><span data-stu-id="8170e-105">A **RelQuadBezTo** row can only be persisted in the .vsdx, .vsdm, .vstx, .vstm, .vssx, and .vssm file formats.</span></span> <span data-ttu-id="8170e-106">将文件保存为 Visio 2003-2010 格式时, **RelQuadBezTo**行将转换为[NURBSTo](nurbsto-row-geometry-section.md)行。</span><span class="sxs-lookup"><span data-stu-id="8170e-106">When a file is saved to the Visio 2003-2010 formats, the **RelQuadBezTo** row is converted to a [NURBSTo](nurbsto-row-geometry-section.md) row.</span></span> 
  
<span data-ttu-id="8170e-107">**RelQuadBezTo**行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="8170e-107">A **RelQuadBezTo** row contains the following cells.</span></span> 
  
|<span data-ttu-id="8170e-108">**Cell**</span><span class="sxs-lookup"><span data-stu-id="8170e-108">**Cell**</span></span>|<span data-ttu-id="8170e-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="8170e-109">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="8170e-110">X</span><span class="sxs-lookup"><span data-stu-id="8170e-110">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="8170e-111">一条二次贝塞尔曲线终顶点相对于形状宽度的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="8170e-111">The  *x*  -coordinate of the ending vertex of a quadratic Bézier curve relative to the width of the shape.</span></span>  <br/> |
|[<span data-ttu-id="8170e-112">Y</span><span class="sxs-lookup"><span data-stu-id="8170e-112">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="8170e-113">一条二次贝塞尔曲线终顶点的*y*坐标 (相对于形状的高度)。</span><span class="sxs-lookup"><span data-stu-id="8170e-113">The  *y*  -coordinate of the ending vertex of a quadratic Bézier curve relative to the height of the shape.</span></span>  <br/> |
|[<span data-ttu-id="8170e-114">A</span><span class="sxs-lookup"><span data-stu-id="8170e-114">A</span></span>](a-cell-geometry-section.md) <br/> |<span data-ttu-id="8170e-115">曲线的控制点相对于形状宽度的*x*坐标;弧形上的一点。控制点最适合弧的起始和结束顶点之间的中间点。</span><span class="sxs-lookup"><span data-stu-id="8170e-115">The  *x*  -coordinate of the curve's control point relative to the shape's width; a point on the arc. The control point is best located about halfway between the beginning and ending vertices of the arc.</span></span>  <br/> |
|[<span data-ttu-id="8170e-116">黑白</span><span class="sxs-lookup"><span data-stu-id="8170e-116">B</span></span>](b-cell-geometry-section.md) <br/> |<span data-ttu-id="8170e-117">曲线的控制点相对于形状高度的*y*轴坐标值。</span><span class="sxs-lookup"><span data-stu-id="8170e-117">The  *y*  -coordinate of a curve's control point relative to the shape's height.</span></span>  <br/> |
   

