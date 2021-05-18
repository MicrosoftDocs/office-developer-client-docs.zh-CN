---
title: 'RelEllipticalArcTo (Geometry Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9b7da082-5e55-411d-b109-7fb6fa8f6e8e
description: 包含椭圆弧终点相对于形状的宽度和高度的 x 坐标和 y 坐标、弧上控制点的 x 坐标和 y 坐标（相对于形状的宽度和高度、从 x 轴到椭圆主轴的角度，以及椭圆的主要轴和次要轴之间的比率）。
ms.openlocfilehash: e38f5f2baf6bb9ade31c2778799a3ece968147f4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409095"
---
# <a name="relellipticalarcto-row-geometry-section"></a>RelEllipticalArcTo (Geometry Section) 

包含椭圆弧终点相对于形状的宽度和高度的  *x*  坐标和  *y*  坐标、弧上控制点的  *x*  坐标和  *y*  坐标（相对于形状的宽度和高度、从  *x*  轴到椭圆主轴的角度，以及椭圆的主要轴和次要轴之间的比率）。 
  
> [!NOTE]
> **RelEllipticalArcTo** 行只能保留为 .vsdx、.vsdm、.vstx、.vstm、.vssx 和 .vssm 文件格式。 将文件保存为 Visio 2003-2010 格式时 **，RelEllipticalArcTo** 行将转换为 [EllipticalArcTo](ellipticalarcto-row-geometry-section.md)行。 
  
**RelEllipticalArcTo** 行包含以下单元格。 
  
|**Cell**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |弧形上终顶点相对于形状宽度的  *x*  坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |弧形上终顶点相对于形状高度的  *y*  坐标。  <br/> |
|[A](a-cell-geometry-section.md) <br/> |弧形控制点相对于形状宽度的  *x*  坐标;弧形上的点。控制点最好位于弧形的开始顶点和结束顶点之间的一半左右。否则，弧形可能会增长到极大小，以便通过控制点，从而产生不可预知的结果。  <br/> |
|[B](b-cell-geometry-section.md) <br/> |弧形控制点相对于形状宽度的  *y*  坐标。  <br/> |
|[C](c-cell-geometry-section.md) <br/> |弧形主轴相对于其父级  *的 x*  轴的角度。  <br/> |
|[D](d-cell-geometry-section.md) <br/> |弧形的长短轴之比。尽管每一词都有其本义，但在此处“长”轴却并不一定大于“短”轴，所以此比值也就不一定大于 1。如果将此单元格设置为小于等于 0 或大于 1000 的值，可能导致无法预料的结果。  <br/> |
   
## <a name="remarks"></a>备注

**RelEllipticalArcTo** 行中的值等效于 [EllipticalArcTo](ellipticalarcto-row-geometry-section.md)行中的值，乘以形状的宽度和高度。 例如 **：RelEllipticalArcTo** 行，其中X、Y、A、B、C 和 **D** 单元格的值为 1， 1、1.5、0.5、15 deg 和 1.5 () 可以分别替换为 **EllipticalArcTo** 行，其单元格公式分别为 `Width*1` `Height*1'` `Width*1.5` `Height*0.5`) 、15 deg 和 1.5 (。
  

