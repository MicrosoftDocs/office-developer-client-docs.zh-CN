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
description: 包含 x 和 y-第一个形状的顶点坐标或代表 x-和 y-路径中中断后的第一个顶点的坐标。
ms.openlocfilehash: cee62701074269350ae52c6fa7f7aee5cb612f49
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780778"
---
# <a name="moveto-row-geometry-section"></a>MoveTo 行（“Geometry”部分）

包含*x*和*y* -第一个形状的顶点坐标或代表*x* -和*y* -路径中中断后的第一个顶点的坐标。 
  
**MoveTo**行包含以下单元格。 
  
|**Cell**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |如果**MoveTo**行是部分中的第一行，则 X 单元格表示*x*的形状的第一个顶点的坐标。 如果**MoveTo**行出现在两行之间，则 X 单元格表示*x* -路径中断开后的第一个顶点的坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |如果**MoveTo**行是部分中的第一行，则 Y 单元格表示*y* -形状的第一个顶点的坐标。 如果**MoveTo**行出现在两行之间，则 Y 单元格表示*y* -路径中断开后的第一个顶点的坐标。  <br/> |
   
## <a name="remarks"></a>说明

**MoveTo**行包含*x*和*y* -如果**MoveTo**行是部分中的第一行的形状的第一个顶点的坐标。 通常，这是放置时绘制形状，并且它不一定是对应于一维形状的起点的第一个顶点。 
  
Geometry 内容必须开头**RelMoveTo**或某一**MoveTo**行，但您也可以使用**MoveTo**和**RelMoveTo**行表示中的形状的路径描间隙。 但是，当路径用于定义填充区域的边界，此间隙被解释为直线段。 若要插入此类间隙，两行之间插入一行，并为**MoveTo**更改行类型。 如果**MoveTo**行是两行之间，它包含*x*和*y* -形状的路径中断开后面的行的第一个顶点的坐标。 
  

