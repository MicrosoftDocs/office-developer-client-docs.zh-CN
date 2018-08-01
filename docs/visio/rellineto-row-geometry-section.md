---
title: RelLineTo 行（“Geometry”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a900e174-d26a-4314-ae4f-d89e186350ce
description: 包含 x-和 y-相对于形状的宽度和高度直线段终顶点的坐标。
ms.openlocfilehash: 26cb63ac6cc0708be4e5668174022af63391c129
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781056"
---
# <a name="rellineto-row-geometry-section"></a>RelLineTo 行（“Geometry”部分）

包含*x* -和*y* -相对于形状的宽度和高度直线段终顶点的坐标。 
  
> [!NOTE]
> **RelLineTo**行仅可保持在.vsdx、.vsdm、.vstx、.vstm、.vssx 和.vssm 文件格式。 为 Visio 2003 2010年格式保存文件后， **RelLineTo**行转换为某一[LineTo](lineto-row-geometry-section.md)行。 
  
**RelLineTo**行包含以下单元格。 
  
|**Cell**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |*X* -相对于形状的宽度直线段终顶点的坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |*Y* -相对于形状的高度直线段终顶点的坐标。  <br/> |
   
## <a name="remarks"></a>说明

**RelLineTo**行中的值为等同于乘以的宽度和高度形状[LineTo](lineto-row-geometry-section.md)行中的值。 例如： **RelLineTo**行其中**X**单元格的值是"0"，则**Y**单元格的值是"0.5"可以被替换为**LineTo**行，其中**X**单元格的值是公式"宽度*0" 和**Y**单元格公式"高度*0.5。" 
  

