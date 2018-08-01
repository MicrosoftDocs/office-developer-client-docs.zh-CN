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
# <a name="relellipticalarcto-row-geometry-section"></a>RelEllipticalArcTo 行（“Geometry”部分）

包含*x*和*y*坐标的椭圆弧的终点相对于形状的宽度和高度， *x* -和*y* -相对于形状的宽度和高度，弧形上的控件点的坐标从*x* angle  -椭圆的长轴和比率椭圆的主要和次要刻度轴的轴。 
  
> [!NOTE]
> **RelEllipticalArcTo**行仅可保持在.vsdx、.vsdm、.vstx、.vstm、.vssx 和.vssm 文件格式。 为 Visio 2003 2010年格式保存文件后， **RelEllipticalArcTo**行转换为某一[EllipticalArcTo](ellipticalarcto-row-geometry-section.md)行。 
  
**RelEllipticalArcTo**行包含以下单元格。 
  
|**Cell**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |*X* -相对于形状的宽度弧形上的终顶点的坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |*Y* -相对于形状的高度弧形上的终顶点的坐标。  <br/> |
|[A](a-cell-geometry-section.md) <br/> |*X* -相对于形状的宽度; 弧的控制点的坐标弧形上某个点。是最好位于之间的开始和结束顶点的一半的控制点。否则，以便通过的控制点，无法预料的结果的极大增长可能弧。  <br/> |
|[B](b-cell-geometry-section.md) <br/> |*Y* -相对于形状的宽度弧形的控制点的坐标。  <br/> |
|[C](c-cell-geometry-section.md) <br/> |弧形的长轴相对于*x*角度-其父级的轴。  <br/> |
|[D](d-cell-geometry-section.md) <br/> |弧形的长短轴之比。尽管每一词都有其本义，但在此处“长”轴却并不一定大于“短”轴，所以此比值也就不一定大于 1。如果将此单元格设置为小于等于 0 或大于 1000 的值，可能导致无法预料的结果。  <br/> |
   
## <a name="remarks"></a>说明

**RelEllipticalArcTo**行中的值为等同于中某一[EllipticalArcTo](ellipticalarcto-row-geometry-section.md)行，乘以的形状的高度和宽度值。 例如： **RelEllipticalArcTo**行位置的**X**、 **Y**、 **A**、 **B**、 **C**和**D**单元格包含值 1、 1、 1.5、 0.5、 15 度和 1.5 （分别） 可以被替换为与某一**EllipticalArcTo**行单元格公式`Width*1`， `Height*1'`， `Width*1.5`， `Height*0.5`、 15 度和 1.5 （分别）。
  

