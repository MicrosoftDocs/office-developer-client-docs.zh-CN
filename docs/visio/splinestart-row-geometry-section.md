---
title: SplineStart 行（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm3055
localization_priority: Normal
ms.assetid: 8e327e00-0844-efa4-900b-6954d3b009bb
description: 包含样条的第二个控制点、其第二个节点、第一个节点、最后一个节点和样条的度数的 x 坐标和 y 坐标。
ms.openlocfilehash: 2ec06619770af4e5dbcc1a763595b6e01a39052b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417474"
---
# <a name="splinestart-row-geometry-section"></a>SplineStart 行（“Geometry”内容）

包含  *样*  条的第二个控制点、其第二个节点、第一个节点、最后一个节点和样条的度数的 x 坐标和  *y*  坐标。 
  
SplineStart 行包含以下单元格。
  
|**Cell**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |*样条* 的第二个控制点的 x 坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |样条的第二个控制点的  *y*  坐标。  <br/> |
|[A](a-cell-geometry-section.md) <br/> |样条的第二个节点。  <br/> |
|[B](b-cell-geometry-section.md) <br/> |样条的第一个节点。  <br/> |
|[C](c-cell-geometry-section.md) <br/> |样条的最后一个节点。  <br/> |
|[D](d-cell-geometry-section.md) <br/> |样条的角度（从 1 到 25 的整数）。  <br/> |
   
## <a name="remarks"></a>备注

Visio 在“Geometry”内容中显示样条的定义，其中包含 SplineStart 行以及其后的一个或多个 SplineKnot 行。SplineStart 行前面必须有其他类型的行（如 MoveTo 行），以指示样条的第一个控制点。如果样条前有相应类型的线段，则前面的行可以是 LineTo、ArcTo、NURBSTo、PolylineTo 或 EllipticalArcTo 行。
  

