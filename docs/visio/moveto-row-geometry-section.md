---
title: MoveTo 行（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm3030
localization_priority: Normal
ms.assetid: c5b20257-676c-279d-f730-1b6fbbe98305
description: 包含形状的第一个顶点的 x 坐标和 y 坐标，或表示路径中中断后的第一个顶点的 x 坐标和 y 坐标。
ms.openlocfilehash: fc414093348b8da04fa3503053584395976982dd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429696"
---
# <a name="moveto-row-geometry-section"></a>MoveTo 行（“Geometry”内容）

包含形状的第一个顶点的  *x*  坐标和  *y*  坐标，或表示路径中中断后的第一个顶点的  *x*  坐标和  *y*  坐标。 
  
**MoveTo** 行包含以下单元格。 
  
|**Cell**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |如果 **MoveTo** 行是内容的第一行，则 X 单元格表示形状的第一个顶点的  *x*  坐标。 如果 **MoveTo 行** 出现在两行之间，则 X 单元格表示路径中中断后的第一个顶点的  *x*  坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |如果 **MoveTo** 行是内容的第一行，则 Y 单元格表示形状的第一个顶点的  *y*  坐标。 如果 **MoveTo** 行出现在两行之间，则 Y 单元格表示路径中中断后的第一个顶点的  *y*  坐标。  <br/> |
   
## <a name="remarks"></a>备注

如果 **MoveTo** 行是该内容的第一行，则 **MoveTo** 行包含形状的第一个顶点的 *x* 坐标和 *y* 坐标。 通常，这就是绘制形状时放置的第一个顶点，而且不一定与一维形状的起点相对应。 
  
几何图形节必须以 **RelMoveTo** 或 **MoveTo** 行开头，但您也可以使用 **MoveTo** 和 **RelMoveTo** 行来表示形状路径的击键中的间隙。 不过，当该路径用于定义填充区域的边界时，此间隙被解释为直线段。 若要插入这样的间隙，在两行之间插入一行，并将行类型更改为 **MoveTo**。 如果 **MoveTo** 行在两行之间，则它包含形状路径中换行符之后的第一条线的第一个顶点的  *x*  坐标和  *y*  坐标。 
  

