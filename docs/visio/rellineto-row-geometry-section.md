---
title: RelLineTo 行（“Geometry”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a900e174-d26a-4314-ae4f-d89e186350ce
description: 包含 x-和 y-相对于形状的宽度和高度直线段终顶点的坐标。
ms.openlocfilehash: 26cb63ac6cc0708be4e5668174022af63391c129
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781056"
---
# <a name="rellineto-row-geometry-section"></a><span data-ttu-id="5b25f-103">RelLineTo 行（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="5b25f-103">RelLineTo Row (Geometry Section)</span></span>

<span data-ttu-id="5b25f-104">包含*x* -和*y* -相对于形状的宽度和高度直线段终顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="5b25f-104">Contains  *x*  -and  *y*  -coordinates of the ending vertex of a straight line segment relative to a shape's width and height.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5b25f-105">**RelLineTo**行仅可保持在.vsdx、.vsdm、.vstx、.vstm、.vssx 和.vssm 文件格式。</span><span class="sxs-lookup"><span data-stu-id="5b25f-105">A **RelLineTo** row can only be persisted in the .vsdx, .vsdm, .vstx, .vstm, .vssx, and .vssm file formats.</span></span> <span data-ttu-id="5b25f-106">为 Visio 2003 2010年格式保存文件后， **RelLineTo**行转换为某一[LineTo](lineto-row-geometry-section.md)行。</span><span class="sxs-lookup"><span data-stu-id="5b25f-106">When a file is saved to the Visio 2003-2010 formats, the **RelLineTo** row is converted to a [LineTo](lineto-row-geometry-section.md) row.</span></span> 
  
<span data-ttu-id="5b25f-107">**RelLineTo**行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="5b25f-107">A **RelLineTo** row contains the following cells.</span></span> 
  
|<span data-ttu-id="5b25f-108">**Cell**</span><span class="sxs-lookup"><span data-stu-id="5b25f-108">**Cell**</span></span>|<span data-ttu-id="5b25f-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="5b25f-109">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="5b25f-110">X</span><span class="sxs-lookup"><span data-stu-id="5b25f-110">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="5b25f-111">*X* -相对于形状的宽度直线段终顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="5b25f-111">The  *x*  -coordinate of the ending vertex of a straight line segment relative to the shape's width.</span></span>  <br/> |
|[<span data-ttu-id="5b25f-112">Y</span><span class="sxs-lookup"><span data-stu-id="5b25f-112">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="5b25f-113">*Y* -相对于形状的高度直线段终顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="5b25f-113">The  *y*  -coordinate of the ending vertex of a straight line segment relative to the shape's height.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5b25f-114">说明</span><span class="sxs-lookup"><span data-stu-id="5b25f-114">Remarks</span></span>

<span data-ttu-id="5b25f-115">**RelLineTo**行中的值为等同于乘以的宽度和高度形状[LineTo](lineto-row-geometry-section.md)行中的值。</span><span class="sxs-lookup"><span data-stu-id="5b25f-115">Values in the **RelLineTo** row are equivalent to values in a [LineTo](lineto-row-geometry-section.md) row that are multiplied by the width and height of the shape.</span></span> <span data-ttu-id="5b25f-116">例如： **RelLineTo**行其中**X**单元格的值是"0"，则**Y**单元格的值是"0.5"可以被替换为**LineTo**行，其中**X**单元格的值是公式"宽度*0" 和**Y**单元格公式"高度*0.5。"</span><span class="sxs-lookup"><span data-stu-id="5b25f-116">For example: a **RelLineTo** row where the value of the **X** cell is "0" and the value of the **Y** cell is "0.5" can be replaced with **LineTo** row where the value of the **X** cell is the formula "Width*0" and the **Y** cell is the formula "Height*0.5."</span></span> 
  

