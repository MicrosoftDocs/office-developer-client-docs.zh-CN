---
title: 'RelMoveTo Row (Geometry Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 04a0ba9f-48dd-488f-9c87-3890a12adf89
description: 包含形状的第一个顶点的 x 坐标和 y 坐标，或路径中中断后第一个顶点的 x 坐标和 y 坐标（相对于形状的高度和宽度）。
ms.openlocfilehash: 488945dbeeea177514770da57b5f26ac947053a3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414198"
---
# <a name="relmoveto-row-geometry-section"></a>RelMoveTo Row (Geometry Section) 

包含形状的第一个顶点的  *x*  坐标和  *y*  坐标，或路径中中断后第一个顶点的  *x*  坐标和  *y*  坐标（相对于形状的高度和宽度）。 
  
> [!NOTE]
> **RelMoveTo** 行只能保留为 .vsdx、.vsdm、.vstx、.vstm、.vssx 和 .vssm 文件格式。 将文件保存为 Visio 2003-2010 格式时 **，RelMoveTo** 行将转换为 [MoveTo](moveto-row-geometry-section.md)行。 
  
**RelMoveTo** 行包含以下单元格。 
  
|**Cell**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |如果 **RelMoveTo** 行是该内容的第一行，则 X 单元格代表形状的第一个顶点相对于形状宽度的  *x*  坐标。 如果 **RelMoveTo** 行出现在两行之间，则 X 单元格表示路径中中断后的第一个顶点的  *x*  坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |如果 **RelMoveTo** 行是该内容的第一行，则 Y 单元格表示形状的第一个顶点的  *y*  坐标。 如果 **RelMoveTo** 行出现在两行之间，则 Y 单元格表示路径中中断后的第一个顶点的  *y*  坐标。  <br/> |
   
## <a name="remarks"></a>备注

**RelMoveTo** 行中的值等效于 [MoveTo](moveto-row-geometry-section.md)行中乘以形状的宽度和高度的值。 例如 **：X** 单元格的值为"0"且 **Y** 单元格的值为"0.5"的 **RelMoveTo** 行可以替换为 **MoveTo** 行，其中 **X** 单元格的值是公式"Width *0"，Y* 单元格是公式"Height 0.5"。 
  
如果 MoveTo 行是该内容的第一行，则 **RelMoveTo** 行包含形状的第一个顶点的  *x*  坐标和  *y*  坐标。 通常，这就是绘制形状时放置的第一个顶点，而且不一定与一维形状的起点相对应。 
  
**"Geometry"** 内容必须以 **MoveTo** 或 **RelMoveTo** 行开头，但您也可以使用 **RelMoveTo** 行和 **MoveTo** 行来表示形状的路径相对于形状的宽度和高度的击键中的间隙。 不过，当该路径用于定义填充区域的边界时，此间隙被解释为直线段。 若要插入这样的间隙，在两行之间插入一行，并将行类型更改为 **RelMoveTo**。 如果 **RelMoveTo** 行在两行之间，则它包含在形状路径中断开处之后的第一条线的第一个顶点的  *x*  坐标和  *y*  坐标。 
  

