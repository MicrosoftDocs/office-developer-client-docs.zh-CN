---
title: RelLineTo 行 ("Geometry" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a900e174-d26a-4314-ae4f-d89e186350ce
description: 包含相对于形状的宽度和高度的直线段终顶点的 x 坐标和 y 坐标。
ms.openlocfilehash: 2e85033b4a2e16c2df09b1a09655fcd4b97dd03d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320067"
---
# <a name="rellineto-row-geometry-section"></a>RelLineTo 行 ("Geometry" 部分)

包含相对于形状的宽度和高度的直线段终顶点的*x*坐标和*y*坐标。 
  
> [!NOTE]
> **RelLineTo**行只能在 .vsdx、.vsdm、.vstx、.vstm、.vssx 和. .vssm 文件格式中持久化。 将文件保存为 Visio 2003-2010 格式时, **RelLineTo**行将转换为[LineTo](lineto-row-geometry-section.md)行。 
  
**RelLineTo**行包含以下单元格。 
  
|**Cell**|**Description**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |直线线段终顶点相对于形状宽度的*x*坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |直线线段终顶点相对于形状高度的*y*轴坐标值。  <br/> |
   
## <a name="remarks"></a>注解

**RelLineTo**行中的值等效于[LineTo](lineto-row-geometry-section.md)行中与形状的宽度和高度相乘的值。 例如: 一个**RelLineTo**行, 其中**x**单元格的值为 "0", **Y**单元格的值是 "0.5", 可以替换为 " **LineTo** " 行, 其中**X**单元格的值是 "Width*0" 公式, **Y**单元格是 "Width 0", Y 单元格是公式 "Height*0.5"。 
  

