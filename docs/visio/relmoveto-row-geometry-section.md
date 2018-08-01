---
title: RelMoveTo 行（“Geometry”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 04a0ba9f-48dd-488f-9c87-3890a12adf89
description: 包含 x 和 y 坐标的形状或 x 的第一个顶点-和 y-中的高度和宽度的形状的相对路径，中断后的第一个顶点的坐标。
ms.openlocfilehash: 77b3e731bfd1f35abe34ffbf3155b57133e56412
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781067"
---
# <a name="relmoveto-row-geometry-section"></a>RelMoveTo 行（“Geometry”部分）

包含*x*和*y*坐标的形状或*x*的第一个顶点-和*y* -中的高度和宽度的形状的相对路径，中断后的第一个顶点的坐标。 
  
> [!NOTE]
> **RelMoveTo**行仅可保持在.vsdx、.vsdm、.vstx、.vstm、.vssx 和.vssm 文件格式。 为 Visio 2003 2010年格式保存文件后， **RelMoveTo**行转换为某一[MoveTo](moveto-row-geometry-section.md)行。 
  
**RelMoveTo**行包含以下单元格。 
  
|**Cell**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |如果**RelMoveTo**行是该节中的第一行，则 X 单元格表示*x* -相对于形状的宽度形状的第一个顶点的坐标。 如果**RelMoveTo**行出现在两行之间，则 X 单元格表示*x* -路径中断开后的第一个顶点的坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |Y 单元格**RelMoveTo**行是否部分中的第一行，代表*y* -形状的第一个顶点的坐标。 如果**RelMoveTo**行出现在两行之间，则 Y 单元格表示*y* -路径中断开后的第一个顶点的坐标。  <br/> |
   
## <a name="remarks"></a>说明

**RelMoveTo**行中的值为等同于乘以的宽度和高度形状的[MoveTo](moveto-row-geometry-section.md)行中的值。 例如： **RelMoveTo**行其中**X**单元格的值是"0"，则**Y**单元格的值是"0.5"可以替换为**MoveTo**行，其中**X**单元格的值是公式"宽度*0" 和**Y**单元格公式"高度*0.5。" 
  
**RelMoveTo**行包含*x*和*y* -如果 MoveTo 行是部分中的第一行的形状的第一个顶点的坐标。 通常，这是放置时绘制形状，并且它不一定是对应于一维形状的起点的第一个顶点。 
  
**Geometry**内容必须**MoveTo**或开头**RelMoveTo**一行，但您也可以使用**RelMoveTo**行和**MoveTo**行表示中的相对于形状的宽度和高度的形状的路径描间隙。 但是，当路径用于定义填充区域的边界，此间隙被解释为直线段。 插入此类间隙、 两行之间插入一行和到**RelMoveTo**更改行类型。 如果两行之间有**RelMoveTo**行，它包含*x*和*y* -形状的路径中断开后面的行的第一个顶点的坐标。 
  

