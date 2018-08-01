---
title: RelQuadBezTo 行（“Geometry”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5ae57707-5a50-43f0-8c78-516790b5034e
description: 包含 x 和 y 坐标的终点相对于形状的宽度和高度和 x 二次贝塞尔曲线的-和 y-曲线相对于形状的宽度和高度的控制点的坐标。
ms.openlocfilehash: 99796e85a857fd320598cb48993fc29bdfa4964d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781100"
---
# <a name="relquadbezto-row-geometry-section"></a><span data-ttu-id="777a7-103">RelQuadBezTo 行（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="777a7-103">RelQuadBezTo Row (Geometry Section)</span></span>

<span data-ttu-id="777a7-104">包含*x*和*y*坐标的终点相对于形状的宽度和高度和*x*二次贝塞尔曲线的-和*y* -曲线相对于形状的宽度和高度的控制点的坐标。</span><span class="sxs-lookup"><span data-stu-id="777a7-104">Contains the  *x*  - and  *y*  -coordinates of the endpoint of a quadratic Bézier curve relative to the shape's width and height and the  *x*  - and  *y*  -coordinates of the control point of the curve relative shape's width and height.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="777a7-105">**RelQuadBezTo**行仅可保持在.vsdx、.vsdm、.vstx、.vstm、.vssx 和.vssm 文件格式。</span><span class="sxs-lookup"><span data-stu-id="777a7-105">A **RelQuadBezTo** row can only be persisted in the .vsdx, .vsdm, .vstx, .vstm, .vssx, and .vssm file formats.</span></span> <span data-ttu-id="777a7-106">为 Visio 2003 2010年格式保存文件后， **RelQuadBezTo**行转换为某一[NURBSTo](nurbsto-row-geometry-section.md)行。</span><span class="sxs-lookup"><span data-stu-id="777a7-106">When a file is saved to the Visio 2003-2010 formats, the **RelQuadBezTo** row is converted to a [NURBSTo](nurbsto-row-geometry-section.md) row.</span></span> 
  
<span data-ttu-id="777a7-107">**RelQuadBezTo**行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="777a7-107">A **RelQuadBezTo** row contains the following cells.</span></span> 
  
|<span data-ttu-id="777a7-108">**Cell**</span><span class="sxs-lookup"><span data-stu-id="777a7-108">**Cell**</span></span>|<span data-ttu-id="777a7-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="777a7-109">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="777a7-110">X</span><span class="sxs-lookup"><span data-stu-id="777a7-110">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="777a7-111">*X* -相对于形状的宽度二次贝塞尔曲线终顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="777a7-111">The  *x*  -coordinate of the ending vertex of a quadratic Bézier curve relative to the width of the shape.</span></span>  <br/> |
|[<span data-ttu-id="777a7-112">Y</span><span class="sxs-lookup"><span data-stu-id="777a7-112">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="777a7-113">*Y* -相对于形状的高度二次贝塞尔曲线终顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="777a7-113">The  *y*  -coordinate of the ending vertex of a quadratic Bézier curve relative to the height of the shape.</span></span>  <br/> |
|[<span data-ttu-id="777a7-114">A</span><span class="sxs-lookup"><span data-stu-id="777a7-114">A</span></span>](a-cell-geometry-section.md) <br/> |<span data-ttu-id="777a7-115">*X* -相对于形状的宽度; 曲线的控制点的坐标弧形上某个点。是最好位于之间的开始和结束顶点的一半的控制点。</span><span class="sxs-lookup"><span data-stu-id="777a7-115">The  *x*  -coordinate of the curve's control point relative to the shape's width; a point on the arc. The control point is best located about halfway between the beginning and ending vertices of the arc.</span></span>  <br/> |
|[<span data-ttu-id="777a7-116">B</span><span class="sxs-lookup"><span data-stu-id="777a7-116">B</span></span>](b-cell-geometry-section.md) <br/> |<span data-ttu-id="777a7-117">*Y* -相对于形状的高度曲线的控制点的坐标。</span><span class="sxs-lookup"><span data-stu-id="777a7-117">The  *y*  -coordinate of a curve's control point relative to the shape's height.</span></span>  <br/> |
   

