---
title: SplineKnot 行（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm3050
localization_priority: Normal
ms.assetid: 9fbae27d-4f1b-c5f7-aacb-16f359331e83
description: 包含样条的控制点和样条节点的 x 坐标和 y 坐标。
ms.openlocfilehash: 432b714772d96e0ab0861bbfb62075258404e607
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407415"
---
# <a name="splineknot-row-geometry-section"></a>SplineKnot 行（“Geometry”内容）

包含  *样*  条的控制点和样条节点的 x 坐标和  *y*  坐标。 
  
SplineKnot 行包含以下单元格。
  
|**Cell**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |控制点的  *x*  坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |*控制点的 y* 坐标。  <br/> |
|[A](a-cell-geometry-section.md) <br/> |样条的节点之一（最后一个节点或前两个节点除外）。  <br/> |
   
## <a name="remarks"></a>备注

Visio 在“Geometry”内容中显示样条的定义，其中包含 SplineStart 行以及其后的一个或多个 SplineKnot 行。SplineStart 行前面必须有其他类型的行（如 MoveTo 行），以指示样条的第一个控制点。如果样条前有相应类型的线段，则前面的行可以是 LineTo、ArcTo、NURBSTo、PolylineTo 或 EllipticalArcTo 行。
  

