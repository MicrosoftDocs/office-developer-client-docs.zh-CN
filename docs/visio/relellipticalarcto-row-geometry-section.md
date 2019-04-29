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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409095"
---
# <a name="relellipticalarcto-row-geometry-section"></a>RelEllipticalArcTo 行 ("Geometry" 部分)

包含椭圆弧形终点相对于形状的宽度和高度的*x*坐标和*y*坐标、弧形上的控制点** 相对于形状** 的宽度和高度的 x 坐标和 y 坐标 (从*x*开始的角度)  -轴到椭圆的主轴, 以及椭圆的主要和次要轴之间的比率。 
  
> [!NOTE]
> **RelEllipticalArcTo**行只能在 .vsdx、.vsdm、.vstx、.vstm、.vssx 和. .vssm 文件格式中持久化。 将文件保存为 Visio 2003-2010 格式时, **RelEllipticalArcTo**行将转换为[EllipticalArcTo](ellipticalarcto-row-geometry-section.md)行。 
  
**RelEllipticalArcTo**行包含以下单元格。 
  
|**单元格**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |弧形上的终顶点相对于形状宽度的*x*坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |弧形上的终顶点相对于形状高度的*y*坐标。  <br/> |
|[A](a-cell-geometry-section.md) <br/> |弧形的控制点相对于形状宽度的*x*坐标;弧形上的一点。控制点最适合弧的起始和结束顶点之间的中间点。否则, 弧的大小可能会增大到极大的大小, 以便通过控制点, 从而导致不可预知的结果。  <br/> |
|[黑白](b-cell-geometry-section.md) <br/> |弧形的控制点相对于形状宽度的*y*轴坐标值。  <br/> |
|[lc](c-cell-geometry-section.md) <br/> |弧形的长轴相对于其父级的*x*轴的角度。  <br/> |
|[D](d-cell-geometry-section.md) <br/> |弧形的长短轴之比。尽管每一词都有其本义，但在此处“长”轴却并不一定大于“短”轴，所以此比值也就不一定大于 1。如果将此单元格设置为小于等于 0 或大于 1000 的值，可能导致无法预料的结果。  <br/> |
   
## <a name="remarks"></a>说明

**RelEllipticalArcTo**行中的值等效于[EllipticalArcTo](ellipticalarcto-row-geometry-section.md)行中的值, 乘以形状的宽度和高度。 例如: 一个**RelEllipticalArcTo**行, 其中**X**、 **Y**、 **a**、 **B**、 **C**和**D**单元格具有值1、1、1.5、0.5、15度和 1.5 (分别) 可以替换为具有以下条件的**EllipticalArcTo**行:单元格公式`Width*1`、 `Height*1'`、 `Width*1.5` `Height*0.5`、、15度和 1.5 (分别)。
  

