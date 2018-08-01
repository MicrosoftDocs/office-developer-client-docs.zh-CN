---
title: RelCubBezTo 行（“Geometry”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 77777dd4-5a2c-4048-9ea4-9bd876862963
description: 包含 x 和 y 坐标的终结点的相对于形状的宽度和高度，x 三次贝赛尔曲线-和 y 坐标的位于曲线的相对于形状的宽度和高度和 x 开头的控制点-和 y-坐标控制l 曲线相对于形状的宽度和高度的结束点。
ms.openlocfilehash: 918701c19e36753dcbf1a210dda2234d1e540d6d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781052"
---
# <a name="relcubbezto-row-geometry-section"></a><span data-ttu-id="ecc6a-103">RelCubBezTo 行（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="ecc6a-103">RelCubBezTo Row (Geometry Section)</span></span>

<span data-ttu-id="ecc6a-104">包含*x*和*y*坐标的终结点的相对于形状的宽度和高度， *x*三次贝赛尔曲线-和*y* -的位于曲线的相对于形状的宽度和高度，开头的控制点的坐标和*x*和*y* -曲线相对于形状的宽度和高度的结束的控制点的坐标。</span><span class="sxs-lookup"><span data-stu-id="ecc6a-104">Contains the  *x*  - and  *y*  -coordinates of the endpoint of a cubic Bézier curve relative to the shape's width and height, the  *x*  - and  *y*  -coordinates of the control point of the beginning of the curve relative shape's width and height, and the  *x*  - and  *y*  -coordinates of the control point of the ending of the curve relative shape's width and height.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ecc6a-105">**RelCubBezTo**行仅可保持在.vsdx、.vsdm、.vstx、.vstm、.vssx 和.vssm 文件格式。</span><span class="sxs-lookup"><span data-stu-id="ecc6a-105">A **RelCubBezTo** row can only be persisted in the .vsdx, .vsdm, .vstx, .vstm, .vssx, and .vssm file formats.</span></span> <span data-ttu-id="ecc6a-106">为 Visio 2003 2010年格式保存文件后， **RelCubBezTo**行转换为某一[NURBSTo](nurbsto-row-geometry-section.md)行。</span><span class="sxs-lookup"><span data-stu-id="ecc6a-106">When a file is saved to the Visio 2003-2010 formats, the **RelCubBezTo** row is converted to a [NURBSTo](nurbsto-row-geometry-section.md) row.</span></span> 
  
<span data-ttu-id="ecc6a-107">**RelCubBezTo**行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="ecc6a-107">A **RelCubBezTo** row contains the following cells.</span></span> 
  
|<span data-ttu-id="ecc6a-108">**Cell**</span><span class="sxs-lookup"><span data-stu-id="ecc6a-108">**Cell**</span></span>|<span data-ttu-id="ecc6a-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="ecc6a-109">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="ecc6a-110">X</span><span class="sxs-lookup"><span data-stu-id="ecc6a-110">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="ecc6a-111">*X* -相对于形状的宽度的立方贝赛尔曲线终顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="ecc6a-111">The  *x*  -coordinate of the ending vertex of a cubic Bézier curve relative to the width of the shape.</span></span>  <br/> |
|[<span data-ttu-id="ecc6a-112">Y</span><span class="sxs-lookup"><span data-stu-id="ecc6a-112">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="ecc6a-113">*Y* -相对于形状的高度的立方贝赛尔曲线终顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="ecc6a-113">The  *y*  -coordinate of the ending vertex of a cubic Bézier curve relative to the height of the shape.</span></span>  <br/> |
|[<span data-ttu-id="ecc6a-114">A</span><span class="sxs-lookup"><span data-stu-id="ecc6a-114">A</span></span>](a-cell-geometry-section.md) <br/> |<span data-ttu-id="ecc6a-115">*X* -曲线的坐标的开始控制点相对于形状的宽度;弧形上某个点。最佳位于之间的开始和终顶点的弧的控制点。</span><span class="sxs-lookup"><span data-stu-id="ecc6a-115">The  *x*  -coordinate of the curve's beginning control point relative to the shape's width; a point on the arc. The control point is best located between the beginning and ending vertices of the arc.</span></span>  <br/> |
|[<span data-ttu-id="ecc6a-116">B</span><span class="sxs-lookup"><span data-stu-id="ecc6a-116">B</span></span>](b-cell-geometry-section.md) <br/> |<span data-ttu-id="ecc6a-117">*Y* -曲线的坐标的开始控制点相对于形状的高度。</span><span class="sxs-lookup"><span data-stu-id="ecc6a-117">The  *y*  -coordinate of a curve's beginning control point relative to the shape's height.</span></span>  <br/> |
|[<span data-ttu-id="ecc6a-118">C</span><span class="sxs-lookup"><span data-stu-id="ecc6a-118">C</span></span>](c-cell-geometry-section.md) <br/> |<span data-ttu-id="ecc6a-119">*X* -曲线的坐标的结束控制点相对于形状的宽度;弧形上某个点。弧的起点控件点和结束顶点之间最佳位于控制点。</span><span class="sxs-lookup"><span data-stu-id="ecc6a-119">The  *x*  -coordinate of the curve's ending control point relative to the shape's width; a point on the arc. The control point is best located between the beginning control point and ending vertices of the arc.</span></span>  <br/> |
|[<span data-ttu-id="ecc6a-120">D</span><span class="sxs-lookup"><span data-stu-id="ecc6a-120">D</span></span>](d-cell-geometry-section.md) <br/> |<span data-ttu-id="ecc6a-121">*Y* -曲线的坐标的结束控制点相对于形状的高度。</span><span class="sxs-lookup"><span data-stu-id="ecc6a-121">The  *y*  -coordinate of a curve's ending control point relative to the shape's height.</span></span>  <br/> |
   

