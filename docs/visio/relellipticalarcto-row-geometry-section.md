---
title: RelEllipticalArcTo 行（“Geometry”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9b7da082-5e55-411d-b109-7fb6fa8f6e8e
description: 包含 x 和 y 坐标的椭圆弧的终点相对于形状的宽度和高度，x-和 y-相对于形状的宽度和高度，弧形上的控件点的坐标从 x angle-轴椭圆的长轴和 t 比率他椭圆的主要和次要刻度坐标轴。
ms.openlocfilehash: 417a2a92bc5c94f9620c7c6f1081ba81d93aa890
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781054"
---
# <a name="relellipticalarcto-row-geometry-section"></a><span data-ttu-id="d0873-103">RelEllipticalArcTo 行（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="d0873-103">RelEllipticalArcTo Row (Geometry Section)</span></span>

<span data-ttu-id="d0873-104">包含*x*和*y*坐标的椭圆弧的终点相对于形状的宽度和高度， *x* -和*y* -相对于形状的宽度和高度，弧形上的控件点的坐标从*x* angle  -椭圆的长轴和比率椭圆的主要和次要刻度轴的轴。</span><span class="sxs-lookup"><span data-stu-id="d0873-104">Contains  *x*  - and  *y*  -coordinates of an elliptical arc's endpoint relative to the shape's width and height,  *x*  - and  *y*  -coordinates of the control points on the arc relative to the shape's width and height, angle from the  *x*  -axis to the ellipse's major axis, and ratio between the ellipse's major and minor axes.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d0873-105">**RelEllipticalArcTo**行仅可保持在.vsdx、.vsdm、.vstx、.vstm、.vssx 和.vssm 文件格式。</span><span class="sxs-lookup"><span data-stu-id="d0873-105">A **RelEllipticalArcTo** row can only be persisted in the .vsdx, .vsdm, .vstx, .vstm, .vssx, and .vssm file formats.</span></span> <span data-ttu-id="d0873-106">为 Visio 2003 2010年格式保存文件后， **RelEllipticalArcTo**行转换为某一[EllipticalArcTo](ellipticalarcto-row-geometry-section.md)行。</span><span class="sxs-lookup"><span data-stu-id="d0873-106">When a file is saved to the Visio 2003-2010 formats, the **RelEllipticalArcTo** row is converted to an [EllipticalArcTo](ellipticalarcto-row-geometry-section.md) row.</span></span> 
  
<span data-ttu-id="d0873-107">**RelEllipticalArcTo**行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="d0873-107">A **RelEllipticalArcTo** row contains the following cells.</span></span> 
  
|<span data-ttu-id="d0873-108">**Cell**</span><span class="sxs-lookup"><span data-stu-id="d0873-108">**Cell**</span></span>|<span data-ttu-id="d0873-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="d0873-109">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="d0873-110">X</span><span class="sxs-lookup"><span data-stu-id="d0873-110">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="d0873-111">*X* -相对于形状的宽度弧形上的终顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="d0873-111">The  *x*  -coordinate of the ending vertex on an arc relative to the width of the shape.</span></span>  <br/> |
|[<span data-ttu-id="d0873-112">Y</span><span class="sxs-lookup"><span data-stu-id="d0873-112">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="d0873-113">*Y* -相对于形状的高度弧形上的终顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="d0873-113">The  *y*  -coordinate of the ending vertex on an arc relative to the height of the shape.</span></span>  <br/> |
|[<span data-ttu-id="d0873-114">A</span><span class="sxs-lookup"><span data-stu-id="d0873-114">A</span></span>](a-cell-geometry-section.md) <br/> |<span data-ttu-id="d0873-115">*X* -相对于形状的宽度; 弧的控制点的坐标弧形上某个点。是最好位于之间的开始和结束顶点的一半的控制点。否则，以便通过的控制点，无法预料的结果的极大增长可能弧。</span><span class="sxs-lookup"><span data-stu-id="d0873-115">The  *x*  -coordinate of the arc's control point relative to the shape's width; a point on the arc. The control point is best located about halfway between the beginning and ending vertices of the arc. Otherwise, the arc may grow to an extreme size in order to pass through the control point, with unpredictable results.</span></span>  <br/> |
|[<span data-ttu-id="d0873-116">B</span><span class="sxs-lookup"><span data-stu-id="d0873-116">B</span></span>](b-cell-geometry-section.md) <br/> |<span data-ttu-id="d0873-117">*Y* -相对于形状的宽度弧形的控制点的坐标。</span><span class="sxs-lookup"><span data-stu-id="d0873-117">The  *y*  -coordinate of an arc's control point relative to the shape's width.</span></span>  <br/> |
|[<span data-ttu-id="d0873-118">C</span><span class="sxs-lookup"><span data-stu-id="d0873-118">C</span></span>](c-cell-geometry-section.md) <br/> |<span data-ttu-id="d0873-119">弧形的长轴相对于*x*角度-其父级的轴。</span><span class="sxs-lookup"><span data-stu-id="d0873-119">The angle of an arc's major axis relative to the  *x*  -axis of its parent.</span></span>  <br/> |
|[<span data-ttu-id="d0873-120">D</span><span class="sxs-lookup"><span data-stu-id="d0873-120">D</span></span>](d-cell-geometry-section.md) <br/> |<span data-ttu-id="d0873-p102">弧形的长短轴之比。尽管每一词都有其本义，但在此处“长”轴却并不一定大于“短”轴，所以此比值也就不一定大于 1。如果将此单元格设置为小于等于 0 或大于 1000 的值，可能导致无法预料的结果。</span><span class="sxs-lookup"><span data-stu-id="d0873-p102">The ratio of an arc's major axis to its minor axis. Despite the usual meaning of these words, the "major" axis does not have to be greater than the "minor" axis, so this ratio does not have to be greater than 1. Setting this cell to a value less than or equal to 0 or greater than 1000 can lead to unpredictable results.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d0873-124">说明</span><span class="sxs-lookup"><span data-stu-id="d0873-124">Remarks</span></span>

<span data-ttu-id="d0873-125">**RelEllipticalArcTo**行中的值为等同于中某一[EllipticalArcTo](ellipticalarcto-row-geometry-section.md)行，乘以的形状的高度和宽度值。</span><span class="sxs-lookup"><span data-stu-id="d0873-125">Values in the **RelEllipticalArcTo** row are equivalent to values in an [EllipticalArcTo](ellipticalarcto-row-geometry-section.md) row, multiplied by the width and height of the shape.</span></span> <span data-ttu-id="d0873-126">例如： **RelEllipticalArcTo**行位置的**X**、 **Y**、 **A**、 **B**、 **C**和**D**单元格包含值 1、 1、 1.5、 0.5、 15 度和 1.5 （分别） 可以被替换为与某一**EllipticalArcTo**行单元格公式`Width*1`， `Height*1'`， `Width*1.5`， `Height*0.5`、 15 度和 1.5 （分别）。</span><span class="sxs-lookup"><span data-stu-id="d0873-126">For example: a **RelEllipticalArcTo** row where the **X**, **Y**, **A**, **B**, **C**, and **D** cells have the values 1, 1, 1.5, 0.5, 15 deg, and 1.5 (respectively) can be replaced with an **EllipticalArcTo** row with the cell formulas  `Width*1`,  `Height*1'`,  `Width*1.5`,  `Height*0.5`, 15 deg, and 1.5 (respectively).</span></span>
  

