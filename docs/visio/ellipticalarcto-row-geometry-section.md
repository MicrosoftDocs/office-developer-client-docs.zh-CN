---
title: EllipticalArcTo 行（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm3015
localization_priority: Normal
ms.assetid: 7ceb30a8-1d05-feff-35d8-08a198784a27
description: 包含椭圆弧终点的 x 坐标和 y 坐标、弧形上控制点的 x 坐标和 y 坐标、从 x 轴到椭圆主轴的角度，以及椭圆主轴和次要轴之间的比值。
ms.openlocfilehash: c6db7560a05652ca3bfcadb2fd4857ac39370562
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421401"
---
# <a name="ellipticalarcto-row-geometry-section"></a>EllipticalArcTo 行（“Geometry”内容）

包含椭圆弧终点的  *x*  坐标和  *y*  坐标、弧形上控制点的  *x*  坐标和  *y*  坐标、从  *x*  轴到椭圆主轴的角度，以及椭圆主轴和次要轴之间的比值。 
  
EllipticalArcTo 行包含以下单元格。
  
|**Cell**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |弧形上终顶点的  *x*  坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |弧形上的结束顶点的  *y*  坐标。  <br/> |
|[A](a-cell-geometry-section.md) <br/> |弧形控制点的  *x*  坐标;弧形上的点。控制点最好位于弧形的开始顶点和结束顶点之间的一半左右。否则，弧形可能会增长到极大小，以便通过控制点，从而产生不可预知的结果。  <br/> |
|[B](b-cell-geometry-section.md) <br/> |弧形控制点的  *y*  坐标。  <br/> |
|[C](c-cell-geometry-section.md) <br/> |弧形主轴相对于其父级  *的 x*  轴的角度。  <br/> |
|[D](d-cell-geometry-section.md) <br/> |弧形的长短轴之比。尽管每一词都有其本义，但在此处“长”轴却并不一定大于“短”轴，所以此比值也就不一定大于 1。如果将此单元格设置为小于等于 0 或大于 1000 的值，可能导致无法预料的结果。  <br/> |
   

