---
title: EllipticalArcTo 行（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm3015
localization_priority: Normal
ms.assetid: 7ceb30a8-1d05-feff-35d8-08a198784a27
description: 包含椭圆弧端点的 x 坐标和 y 坐标、弧形上控制点的 x 坐标和 y 坐标、从 x 轴到椭圆主轴的夹角以及椭圆主要和次要轴的比率。
ms.openlocfilehash: c6db7560a05652ca3bfcadb2fd4857ac39370562
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345673"
---
# <a name="ellipticalarcto-row-geometry-section"></a><span data-ttu-id="49b2a-103">EllipticalArcTo 行（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="49b2a-103">EllipticalArcTo Row (Geometry Section)</span></span>

<span data-ttu-id="49b2a-104">包含椭圆弧端点的*x*坐标和*y*坐标、弧形上控制点的*x*坐标和*y*坐标、从*x*轴到椭圆主轴的夹角以及椭圆的主要和 mino 之间的比率。r 轴。</span><span class="sxs-lookup"><span data-stu-id="49b2a-104">Contains  *x*  - and  *y*  -coordinates of an elliptical arc's endpoint,  *x*  - and  *y*  -coordinates of the control points on the arc, angle from the  *x*  -axis to the ellipse's major axis, and ratio between the ellipse's major and minor axes.</span></span> 
  
<span data-ttu-id="49b2a-105">EllipticalArcTo 行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="49b2a-105">An EllipticalArcTo row contains the following cells.</span></span>
  
|<span data-ttu-id="49b2a-106">**Cell**</span><span class="sxs-lookup"><span data-stu-id="49b2a-106">**Cell**</span></span>|<span data-ttu-id="49b2a-107">**Description**</span><span class="sxs-lookup"><span data-stu-id="49b2a-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="49b2a-108">X</span><span class="sxs-lookup"><span data-stu-id="49b2a-108">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="49b2a-109">弧形上的终顶点的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="49b2a-109">The  *x*  -coordinate of the ending vertex on an arc.</span></span>  <br/> |
|[<span data-ttu-id="49b2a-110">Y</span><span class="sxs-lookup"><span data-stu-id="49b2a-110">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="49b2a-111">弧形上的终顶点的*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="49b2a-111">The  *y*  -coordinate of the ending vertex on an arc.</span></span>  <br/> |
|[<span data-ttu-id="49b2a-112">A</span><span class="sxs-lookup"><span data-stu-id="49b2a-112">A</span></span>](a-cell-geometry-section.md) <br/> |<span data-ttu-id="49b2a-113">弧形的控制点的*x*坐标;弧形上的一点。控制点最适合弧的起始和结束顶点之间的中间点。否则, 弧的大小可能会增大到极大的大小, 以便通过控制点, 从而导致不可预知的结果。</span><span class="sxs-lookup"><span data-stu-id="49b2a-113">The  *x*  -coordinate of the arc's control point; a point on the arc. The control point is best located about halfway between the beginning and ending vertices of the arc. Otherwise, the arc may grow to an extreme size in order to pass through the control point, with unpredictable results.</span></span>  <br/> |
|[<span data-ttu-id="49b2a-114">黑白</span><span class="sxs-lookup"><span data-stu-id="49b2a-114">B</span></span>](b-cell-geometry-section.md) <br/> |<span data-ttu-id="49b2a-115">弧形的控制点的*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="49b2a-115">The  *y*  -coordinate of an arc's control point.</span></span>  <br/> |
|[<span data-ttu-id="49b2a-116">lc</span><span class="sxs-lookup"><span data-stu-id="49b2a-116">C</span></span>](c-cell-geometry-section.md) <br/> |<span data-ttu-id="49b2a-117">弧形的长轴相对于其父级的*x*轴的角度。</span><span class="sxs-lookup"><span data-stu-id="49b2a-117">The angle of an arc's major axis relative to the  *x*  -axis of its parent.</span></span>  <br/> |
|[<span data-ttu-id="49b2a-118">D</span><span class="sxs-lookup"><span data-stu-id="49b2a-118">D</span></span>](d-cell-geometry-section.md) <br/> |<span data-ttu-id="49b2a-p101">弧形的长短轴之比。尽管每一词都有其本义，但在此处“长”轴却并不一定大于“短”轴，所以此比值也就不一定大于 1。如果将此单元格设置为小于等于 0 或大于 1000 的值，可能导致无法预料的结果。</span><span class="sxs-lookup"><span data-stu-id="49b2a-p101">The ratio of an arc's major axis to its minor axis. Despite the usual meaning of these words, the "major" axis does not have to be greater than the "minor" axis, so this ratio does not have to be greater than 1. Setting this cell to a value less than or equal to 0 or greater than 1000 can lead to unpredictable results.</span></span>  <br/> |
   

