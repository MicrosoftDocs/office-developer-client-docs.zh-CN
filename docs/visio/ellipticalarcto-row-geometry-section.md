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
description: 包含 x 和 y-的椭圆弧终结点、 x 和 y 坐标-、 弧形上的控件点的坐标从 x angle-椭圆的长轴和比率椭圆的主要和次要刻度轴的轴。
ms.openlocfilehash: 9a356429f14a20b72a8bd55689855e2954d4a807
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780171"
---
# <a name="ellipticalarcto-row-geometry-section"></a>EllipticalArcTo 行（“Geometry”部分）

包含*x*和*y*坐标的椭圆弧终结点， *x* -和*y* -、 弧形上的控件点的坐标从*x* angle-轴椭圆的长轴和椭圆的主要和 mino 比率r 坐标轴。 
  
EllipticalArcTo 行包含以下单元格。
  
|**Cell**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |*X* -弧形上的终顶点的坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |*Y* -弧形上的终顶点的坐标。  <br/> |
|[A](a-cell-geometry-section.md) <br/> |*X* -坐标的弧的控制点;弧形上某个点。是最好位于之间的开始和结束顶点的一半的控制点。否则，以便通过的控制点，无法预料的结果的极大增长可能弧。  <br/> |
|[B](b-cell-geometry-section.md) <br/> |*Y* -弧形的控制点的坐标。  <br/> |
|[C](c-cell-geometry-section.md) <br/> |弧形的长轴相对于*x*角度-其父级的轴。  <br/> |
|[D](d-cell-geometry-section.md) <br/> |弧形的长短轴之比。尽管每一词都有其本义，但在此处“长”轴却并不一定大于“短”轴，所以此比值也就不一定大于 1。如果将此单元格设置为小于等于 0 或大于 1000 的值，可能导致无法预料的结果。  <br/> |
   

