---
title: 'RelLineTo Row (Geometry Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a900e174-d26a-4314-ae4f-d89e186350ce
description: 包含直线段的终点相对于形状的宽度和高度的 x 坐标和 y 坐标。
ms.openlocfilehash: 2e85033b4a2e16c2df09b1a09655fcd4b97dd03d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437159"
---
# <a name="rellineto-row-geometry-section"></a><span data-ttu-id="fe51a-103">RelLineTo Row (Geometry Section) </span><span class="sxs-lookup"><span data-stu-id="fe51a-103">RelLineTo Row (Geometry Section)</span></span>

<span data-ttu-id="fe51a-104">包含  *直线*  段的终点相对于形状的宽度和高度的 x 坐标和  *y*  坐标。</span><span class="sxs-lookup"><span data-stu-id="fe51a-104">Contains  *x*  -and  *y*  -coordinates of the ending vertex of a straight line segment relative to a shape's width and height.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fe51a-105">**RelLineTo** 行只能保留为 .vsdx、.vsdm、.vstx、.vstm、.vssx 和 .vssm 文件格式。</span><span class="sxs-lookup"><span data-stu-id="fe51a-105">A **RelLineTo** row can only be persisted in the .vsdx, .vsdm, .vstx, .vstm, .vssx, and .vssm file formats.</span></span> <span data-ttu-id="fe51a-106">将文件保存为 Visio 2003-2010 格式时 **，RelLineTo** 行将转换为 [LineTo](lineto-row-geometry-section.md)行。</span><span class="sxs-lookup"><span data-stu-id="fe51a-106">When a file is saved to the Visio 2003-2010 formats, the **RelLineTo** row is converted to a [LineTo](lineto-row-geometry-section.md) row.</span></span> 
  
<span data-ttu-id="fe51a-107">**RelLineTo** 行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="fe51a-107">A **RelLineTo** row contains the following cells.</span></span> 
  
|<span data-ttu-id="fe51a-108">**Cell**</span><span class="sxs-lookup"><span data-stu-id="fe51a-108">**Cell**</span></span>|<span data-ttu-id="fe51a-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe51a-109">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="fe51a-110">X</span><span class="sxs-lookup"><span data-stu-id="fe51a-110">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="fe51a-111">直线段的终点相对于形状宽度的  *x*  坐标。</span><span class="sxs-lookup"><span data-stu-id="fe51a-111">The  *x*  -coordinate of the ending vertex of a straight line segment relative to the shape's width.</span></span>  <br/> |
|[<span data-ttu-id="fe51a-112">Y</span><span class="sxs-lookup"><span data-stu-id="fe51a-112">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="fe51a-113">直线段终顶点相对于形状高度的  *y*  坐标。</span><span class="sxs-lookup"><span data-stu-id="fe51a-113">The  *y*  -coordinate of the ending vertex of a straight line segment relative to the shape's height.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fe51a-114">备注</span><span class="sxs-lookup"><span data-stu-id="fe51a-114">Remarks</span></span>

<span data-ttu-id="fe51a-115">**RelLineTo** 行中的值等效于 [LineTo](lineto-row-geometry-section.md)行中乘以形状的宽度和高度的值。</span><span class="sxs-lookup"><span data-stu-id="fe51a-115">Values in the **RelLineTo** row are equivalent to values in a [LineTo](lineto-row-geometry-section.md) row that are multiplied by the width and height of the shape.</span></span> <span data-ttu-id="fe51a-116">例如：一个 **RelLineTo** 行，其中 **X** 单元格的值为"0"，Y单元格的值为"0.5"，该行可以替换为 **LineTo** 行，其中 **X** 单元格的值是公式"Width *0"，Y* 单元格是公式"Height 0.5"。</span><span class="sxs-lookup"><span data-stu-id="fe51a-116">For example: a **RelLineTo** row where the value of the **X** cell is "0" and the value of the **Y** cell is "0.5" can be replaced with **LineTo** row where the value of the **X** cell is the formula "Width *0" and the **Y** cell is the formula "Height* 0.5."</span></span> 
  

