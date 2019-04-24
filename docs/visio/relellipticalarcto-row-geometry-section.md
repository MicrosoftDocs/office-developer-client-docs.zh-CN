---
title: RelEllipticalArcTo 行 ("Geometry" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9b7da082-5e55-411d-b109-7fb6fa8f6e8e
description: 包含椭圆弧的终点相对于形状的宽度和高度的 x 坐标和 y 坐标、弧形上的控制点相对于形状的宽度和高度的 x 坐标和 y 坐标、从 x 轴到椭圆的长轴的夹角以及 t 之间的比率椭圆的主要和次要轴。
ms.openlocfilehash: e38f5f2baf6bb9ade31c2778799a3ece968147f4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359960"
---
# <a name="relellipticalarcto-row-geometry-section"></a><span data-ttu-id="ce42d-103">RelEllipticalArcTo 行 ("Geometry" 部分)</span><span class="sxs-lookup"><span data-stu-id="ce42d-103">RelEllipticalArcTo Row (Geometry Section)</span></span>

<span data-ttu-id="ce42d-104">包含椭圆弧形终点相对于形状的宽度和高度的*x*坐标和*y*坐标、弧形上的控制点\*\* 相对于形状\*\* 的宽度和高度的 x 坐标和 y 坐标 (从*x*开始的角度)  -轴到椭圆的主轴, 以及椭圆的主要和次要轴之间的比率。</span><span class="sxs-lookup"><span data-stu-id="ce42d-104">Contains  *x*  - and  *y*  -coordinates of an elliptical arc's endpoint relative to the shape's width and height,  *x*  - and  *y*  -coordinates of the control points on the arc relative to the shape's width and height, angle from the  *x*  -axis to the ellipse's major axis, and ratio between the ellipse's major and minor axes.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ce42d-105">**RelEllipticalArcTo**行只能在 .vsdx、.vsdm、.vstx、.vstm、.vssx 和. .vssm 文件格式中持久化。</span><span class="sxs-lookup"><span data-stu-id="ce42d-105">A **RelEllipticalArcTo** row can only be persisted in the .vsdx, .vsdm, .vstx, .vstm, .vssx, and .vssm file formats.</span></span> <span data-ttu-id="ce42d-106">将文件保存为 Visio 2003-2010 格式时, **RelEllipticalArcTo**行将转换为[EllipticalArcTo](ellipticalarcto-row-geometry-section.md)行。</span><span class="sxs-lookup"><span data-stu-id="ce42d-106">When a file is saved to the Visio 2003-2010 formats, the **RelEllipticalArcTo** row is converted to an [EllipticalArcTo](ellipticalarcto-row-geometry-section.md) row.</span></span> 
  
<span data-ttu-id="ce42d-107">**RelEllipticalArcTo**行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="ce42d-107">A **RelEllipticalArcTo** row contains the following cells.</span></span> 
  
|<span data-ttu-id="ce42d-108">**Cell**</span><span class="sxs-lookup"><span data-stu-id="ce42d-108">**Cell**</span></span>|<span data-ttu-id="ce42d-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="ce42d-109">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="ce42d-110">X</span><span class="sxs-lookup"><span data-stu-id="ce42d-110">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="ce42d-111">弧形上的终顶点相对于形状宽度的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="ce42d-111">The  *x*  -coordinate of the ending vertex on an arc relative to the width of the shape.</span></span>  <br/> |
|[<span data-ttu-id="ce42d-112">Y</span><span class="sxs-lookup"><span data-stu-id="ce42d-112">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="ce42d-113">弧形上的终顶点相对于形状高度的*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="ce42d-113">The  *y*  -coordinate of the ending vertex on an arc relative to the height of the shape.</span></span>  <br/> |
|[<span data-ttu-id="ce42d-114">A</span><span class="sxs-lookup"><span data-stu-id="ce42d-114">A</span></span>](a-cell-geometry-section.md) <br/> |<span data-ttu-id="ce42d-115">弧形的控制点相对于形状宽度的*x*坐标;弧形上的一点。控制点最适合弧的起始和结束顶点之间的中间点。否则, 弧的大小可能会增大到极大的大小, 以便通过控制点, 从而导致不可预知的结果。</span><span class="sxs-lookup"><span data-stu-id="ce42d-115">The  *x*  -coordinate of the arc's control point relative to the shape's width; a point on the arc. The control point is best located about halfway between the beginning and ending vertices of the arc. Otherwise, the arc may grow to an extreme size in order to pass through the control point, with unpredictable results.</span></span>  <br/> |
|[<span data-ttu-id="ce42d-116">黑白</span><span class="sxs-lookup"><span data-stu-id="ce42d-116">B</span></span>](b-cell-geometry-section.md) <br/> |<span data-ttu-id="ce42d-117">弧形的控制点相对于形状宽度的*y*轴坐标值。</span><span class="sxs-lookup"><span data-stu-id="ce42d-117">The  *y*  -coordinate of an arc's control point relative to the shape's width.</span></span>  <br/> |
|[<span data-ttu-id="ce42d-118">lc</span><span class="sxs-lookup"><span data-stu-id="ce42d-118">C</span></span>](c-cell-geometry-section.md) <br/> |<span data-ttu-id="ce42d-119">弧形的长轴相对于其父级的*x*轴的角度。</span><span class="sxs-lookup"><span data-stu-id="ce42d-119">The angle of an arc's major axis relative to the  *x*  -axis of its parent.</span></span>  <br/> |
|[<span data-ttu-id="ce42d-120">D</span><span class="sxs-lookup"><span data-stu-id="ce42d-120">D</span></span>](d-cell-geometry-section.md) <br/> |<span data-ttu-id="ce42d-p102">弧形的长短轴之比。尽管每一词都有其本义，但在此处“长”轴却并不一定大于“短”轴，所以此比值也就不一定大于 1。如果将此单元格设置为小于等于 0 或大于 1000 的值，可能导致无法预料的结果。</span><span class="sxs-lookup"><span data-stu-id="ce42d-p102">The ratio of an arc's major axis to its minor axis. Despite the usual meaning of these words, the "major" axis does not have to be greater than the "minor" axis, so this ratio does not have to be greater than 1. Setting this cell to a value less than or equal to 0 or greater than 1000 can lead to unpredictable results.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ce42d-124">注解</span><span class="sxs-lookup"><span data-stu-id="ce42d-124">Remarks</span></span>

<span data-ttu-id="ce42d-125">**RelEllipticalArcTo**行中的值等效于[EllipticalArcTo](ellipticalarcto-row-geometry-section.md)行中的值, 乘以形状的宽度和高度。</span><span class="sxs-lookup"><span data-stu-id="ce42d-125">Values in the **RelEllipticalArcTo** row are equivalent to values in an [EllipticalArcTo](ellipticalarcto-row-geometry-section.md) row, multiplied by the width and height of the shape.</span></span> <span data-ttu-id="ce42d-126">例如: 一个**RelEllipticalArcTo**行, 其中**X**、 **Y**、 **a**、 **B**、 **C**和**D**单元格具有值1、1、1.5、0.5、15度和 1.5 (分别) 可以替换为具有以下条件的**EllipticalArcTo**行:单元格公式`Width*1`、 `Height*1'`、 `Width*1.5` `Height*0.5`、、15度和 1.5 (分别)。</span><span class="sxs-lookup"><span data-stu-id="ce42d-126">For example: a **RelEllipticalArcTo** row where the **X**, **Y**, **A**, **B**, **C**, and **D** cells have the values 1, 1, 1.5, 0.5, 15 deg, and 1.5 (respectively) can be replaced with an **EllipticalArcTo** row with the cell formulas  `Width*1`,  `Height*1'`,  `Width*1.5`,  `Height*0.5`, 15 deg, and 1.5 (respectively).</span></span>
  

