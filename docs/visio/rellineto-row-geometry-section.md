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
# <a name="rellineto-row-geometry-section"></a>RelLineTo Row (Geometry Section) 

包含  *直线*  段的终点相对于形状的宽度和高度的 x 坐标和  *y*  坐标。 
  
> [!NOTE]
> **RelLineTo** 行只能保留为 .vsdx、.vsdm、.vstx、.vstm、.vssx 和 .vssm 文件格式。 将文件保存为 Visio 2003-2010 格式时 **，RelLineTo** 行将转换为 [LineTo](lineto-row-geometry-section.md)行。 
  
**RelLineTo** 行包含以下单元格。 
  
|**Cell**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |直线段的终点相对于形状宽度的  *x*  坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |直线段终顶点相对于形状高度的  *y*  坐标。  <br/> |
   
## <a name="remarks"></a>备注

**RelLineTo** 行中的值等效于 [LineTo](lineto-row-geometry-section.md)行中乘以形状的宽度和高度的值。 例如：一个 **RelLineTo** 行，其中 **X** 单元格的值为"0"，Y单元格的值为"0.5"，该行可以替换为 **LineTo** 行，其中 **X** 单元格的值是公式"Width *0"，Y* 单元格是公式"Height 0.5"。 
  

