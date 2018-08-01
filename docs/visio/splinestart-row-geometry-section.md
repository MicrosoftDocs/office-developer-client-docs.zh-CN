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
description: 包含 x 和 y-坐标样条的第二个控制点、 它的第二个节点、 第一个节点、 最后一个节点和样条的度数。
ms.openlocfilehash: 0944da12e6090fde41dc5927b5705e103d29f76d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781428"
---
# <a name="splinestart-row-geometry-section"></a>SplineStart 行（“Geometry”部分）

包含*x*和*y* -坐标样条的第二个控制点、 它的第二个节点、 第一个节点、 最后一个节点和样条的度数。 
  
SplineStart 行包含以下单元格。
  
|**Cell**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |*X* -样条的第二个控制点的坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |*Y* -样条的第二个控制点的坐标。  <br/> |
|[A](a-cell-geometry-section.md) <br/> |样条的第二个节点。  <br/> |
|[B](b-cell-geometry-section.md) <br/> |样条的第一个节点。  <br/> |
|[C](c-cell-geometry-section.md) <br/> |样条的最后一个节点。  <br/> |
|[D](d-cell-geometry-section.md) <br/> |样条的角度（从 1 到 25 的整数）。  <br/> |
   
## <a name="remarks"></a>注解

Visio 在“Geometry”内容中显示样条的定义，其中包含 SplineStart 行以及其后的一个或多个 SplineKnot 行。SplineStart 行前面必须有其他类型的行（如 MoveTo 行），以指示样条的第一个控制点。如果样条前有相应类型的线段，则前面的行可以是 LineTo、ArcTo、NURBSTo、PolylineTo 或 EllipticalArcTo 行。
  

