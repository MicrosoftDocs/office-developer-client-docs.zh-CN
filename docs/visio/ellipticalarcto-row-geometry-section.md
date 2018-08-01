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
description: 包含 x 和 y-的椭圆弧终结点、 x 和 y 坐标-、 弧形上的控件点的坐标从 x angle-椭圆的长轴和比率椭圆的主要和次要刻度轴的轴。
ms.openlocfilehash: 9a356429f14a20b72a8bd55689855e2954d4a807
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780171"
---
# <a name="ellipticalarcto-row-geometry-section"></a><span data-ttu-id="0ee42-103">EllipticalArcTo 行（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="0ee42-103">EllipticalArcTo Row (Geometry Section)</span></span>

<span data-ttu-id="0ee42-104">包含*x*和*y*坐标的椭圆弧终结点， *x* -和*y* -、 弧形上的控件点的坐标从*x* angle-轴椭圆的长轴和椭圆的主要和 mino 比率r 坐标轴。</span><span class="sxs-lookup"><span data-stu-id="0ee42-104">Contains  *x*  - and  *y*  -coordinates of an elliptical arc's endpoint,  *x*  - and  *y*  -coordinates of the control points on the arc, angle from the  *x*  -axis to the ellipse's major axis, and ratio between the ellipse's major and minor axes.</span></span> 
  
<span data-ttu-id="0ee42-105">EllipticalArcTo 行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="0ee42-105">An EllipticalArcTo row contains the following cells.</span></span>
  
|<span data-ttu-id="0ee42-106">**Cell**</span><span class="sxs-lookup"><span data-stu-id="0ee42-106">**Cell**</span></span>|<span data-ttu-id="0ee42-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="0ee42-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="0ee42-108">X</span><span class="sxs-lookup"><span data-stu-id="0ee42-108">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="0ee42-109">*X* -弧形上的终顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="0ee42-109">The  *x*  -coordinate of the ending vertex on an arc.</span></span>  <br/> |
|[<span data-ttu-id="0ee42-110">Y</span><span class="sxs-lookup"><span data-stu-id="0ee42-110">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="0ee42-111">*Y* -弧形上的终顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="0ee42-111">The  *y*  -coordinate of the ending vertex on an arc.</span></span>  <br/> |
|[<span data-ttu-id="0ee42-112">A</span><span class="sxs-lookup"><span data-stu-id="0ee42-112">A</span></span>](a-cell-geometry-section.md) <br/> |<span data-ttu-id="0ee42-113">*X* -坐标的弧的控制点;弧形上某个点。是最好位于之间的开始和结束顶点的一半的控制点。否则，以便通过的控制点，无法预料的结果的极大增长可能弧。</span><span class="sxs-lookup"><span data-stu-id="0ee42-113">The  *x*  -coordinate of the arc's control point; a point on the arc. The control point is best located about halfway between the beginning and ending vertices of the arc. Otherwise, the arc may grow to an extreme size in order to pass through the control point, with unpredictable results.</span></span>  <br/> |
|[<span data-ttu-id="0ee42-114">B</span><span class="sxs-lookup"><span data-stu-id="0ee42-114">B</span></span>](b-cell-geometry-section.md) <br/> |<span data-ttu-id="0ee42-115">*Y* -弧形的控制点的坐标。</span><span class="sxs-lookup"><span data-stu-id="0ee42-115">The  *y*  -coordinate of an arc's control point.</span></span>  <br/> |
|[<span data-ttu-id="0ee42-116">C</span><span class="sxs-lookup"><span data-stu-id="0ee42-116">C</span></span>](c-cell-geometry-section.md) <br/> |<span data-ttu-id="0ee42-117">弧形的长轴相对于*x*角度-其父级的轴。</span><span class="sxs-lookup"><span data-stu-id="0ee42-117">The angle of an arc's major axis relative to the  *x*  -axis of its parent.</span></span>  <br/> |
|[<span data-ttu-id="0ee42-118">D</span><span class="sxs-lookup"><span data-stu-id="0ee42-118">D</span></span>](d-cell-geometry-section.md) <br/> |<span data-ttu-id="0ee42-p101">弧形的长短轴之比。尽管每一词都有其本义，但在此处“长”轴却并不一定大于“短”轴，所以此比值也就不一定大于 1。如果将此单元格设置为小于等于 0 或大于 1000 的值，可能导致无法预料的结果。</span><span class="sxs-lookup"><span data-stu-id="0ee42-p101">The ratio of an arc's major axis to its minor axis. Despite the usual meaning of these words, the "major" axis does not have to be greater than the "minor" axis, so this ratio does not have to be greater than 1. Setting this cell to a value less than or equal to 0 or greater than 1000 can lead to unpredictable results.</span></span>  <br/> |
   

