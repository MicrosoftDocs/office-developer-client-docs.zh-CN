---
title: RelLineTo 行 ("Geometry" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a900e174-d26a-4314-ae4f-d89e186350ce
description: 包含相对于形状的宽度和高度的直线段终顶点的 x 坐标和 y 坐标。
ms.openlocfilehash: 2e85033b4a2e16c2df09b1a09655fcd4b97dd03d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320067"
---
# <a name="rellineto-row-geometry-section"></a><span data-ttu-id="17212-103">RelLineTo 行 ("Geometry" 部分)</span><span class="sxs-lookup"><span data-stu-id="17212-103">RelLineTo Row (Geometry Section)</span></span>

<span data-ttu-id="17212-104">包含相对于形状的宽度和高度的直线段终顶点的*x*坐标和*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="17212-104">Contains  *x*  -and  *y*  -coordinates of the ending vertex of a straight line segment relative to a shape's width and height.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="17212-105">**RelLineTo**行只能在 .vsdx、.vsdm、.vstx、.vstm、.vssx 和. .vssm 文件格式中持久化。</span><span class="sxs-lookup"><span data-stu-id="17212-105">A **RelLineTo** row can only be persisted in the .vsdx, .vsdm, .vstx, .vstm, .vssx, and .vssm file formats.</span></span> <span data-ttu-id="17212-106">将文件保存为 Visio 2003-2010 格式时, **RelLineTo**行将转换为[LineTo](lineto-row-geometry-section.md)行。</span><span class="sxs-lookup"><span data-stu-id="17212-106">When a file is saved to the Visio 2003-2010 formats, the **RelLineTo** row is converted to a [LineTo](lineto-row-geometry-section.md) row.</span></span> 
  
<span data-ttu-id="17212-107">**RelLineTo**行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="17212-107">A **RelLineTo** row contains the following cells.</span></span> 
  
|<span data-ttu-id="17212-108">**Cell**</span><span class="sxs-lookup"><span data-stu-id="17212-108">**Cell**</span></span>|<span data-ttu-id="17212-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="17212-109">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="17212-110">X</span><span class="sxs-lookup"><span data-stu-id="17212-110">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="17212-111">直线线段终顶点相对于形状宽度的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="17212-111">The  *x*  -coordinate of the ending vertex of a straight line segment relative to the shape's width.</span></span>  <br/> |
|[<span data-ttu-id="17212-112">Y</span><span class="sxs-lookup"><span data-stu-id="17212-112">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="17212-113">直线线段终顶点相对于形状高度的*y*轴坐标值。</span><span class="sxs-lookup"><span data-stu-id="17212-113">The  *y*  -coordinate of the ending vertex of a straight line segment relative to the shape's height.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="17212-114">注解</span><span class="sxs-lookup"><span data-stu-id="17212-114">Remarks</span></span>

<span data-ttu-id="17212-115">**RelLineTo**行中的值等效于[LineTo](lineto-row-geometry-section.md)行中与形状的宽度和高度相乘的值。</span><span class="sxs-lookup"><span data-stu-id="17212-115">Values in the **RelLineTo** row are equivalent to values in a [LineTo](lineto-row-geometry-section.md) row that are multiplied by the width and height of the shape.</span></span> <span data-ttu-id="17212-116">例如: 一个**RelLineTo**行, 其中**x**单元格的值为 "0", **Y**单元格的值是 "0.5", 可以替换为 " **LineTo** " 行, 其中**X**单元格的值是 "Width*0" 公式, **Y**单元格是 "Width 0", Y 单元格是公式 "Height*0.5"。</span><span class="sxs-lookup"><span data-stu-id="17212-116">For example: a **RelLineTo** row where the value of the **X** cell is "0" and the value of the **Y** cell is "0.5" can be replaced with **LineTo** row where the value of the **X** cell is the formula "Width*0" and the **Y** cell is the formula "Height*0.5."</span></span> 
  

