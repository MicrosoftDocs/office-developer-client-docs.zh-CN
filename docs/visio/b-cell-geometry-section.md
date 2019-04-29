---
title: B 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251751
localization_priority: Normal
ms.assetid: b0fb6a47-47d8-ab9c-854d-0b0bbfdfcc27
description: 在不同行中表示不同的信息。 此表根据 B 单元格所在的行对 B 单元格进行了说明。
ms.openlocfilehash: ff032b5af2918ec9865360ede5c3d76e8e872e9a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423305"
---
# <a name="b-cell-geometry-section"></a>B 单元格（“Geometry”内容）

在不同行中表示不同的信息。 此表根据 B 单元格所在的行对 B 单元格进行了说明。
  
|**行**|**说明**|
|:-----|:-----|
|[EllipticalArcTo](ellipticalarcto-row-geometry-section.md) <br/> | 弧形的控制点的*y*坐标。  <br/> |
|[NURBSTo](nurbsto-row-geometry-section.md) <br/> | 非均匀有理 B 样条 (NURBS) 的最后一个权值。  <br/> |
|[SplineStart](splinestart-row-geometry-section.md) <br/> | 样条的第一个节点。  <br/> |
|[InfiniteLine](infiniteline-row-geometry-section.md) <br/> | 无限长线上某个点的*y*坐标;与[A](a-cell-geometry-section.md)单元格所表示的*x*坐标配对。  <br/> |
|[椭圆](ellipse-row-geometry-section.md) <br/> | 椭圆上某个点的*y*坐标;与[A](a-cell-geometry-section.md)单元格所表示的*x*坐标配对。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式或程序使用 **CellsU** 属性按名称获取对 B 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 几何图形*i* 。B *j*其中*i*和*j* = <1>, 2, 3 .。。  <br/> |
|| 几何图形*i* 。B1 (InfiniteLine 和椭圆行)  <br/> |
   
要从某个程序按索引获取对 B 单元格的引用，请使用带下列参数的  **CellsSRC**  属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionFirstComponent** +  *i* = ** 0、1、2 .。。  <br/> |
| 行索引：  <br/> |**visRowVertex** +  *j*其中*j* = 0, 1, 2 .。。  <br/> |
||**visRowVertex**（InfiniteLine 和 Ellipse 行）  <br/> |
| 单元格索引：  <br/> |**visControlX**（EllipticalArcTo 行）  <br/> |
||**visControlY**（EllipticalArcTo 行）  <br/> |
||**visNURBSWeight**（NURBSTo 行）  <br/> |
||**visSplineKnot2**（SplineStart 行）  <br/> |
||**visInfiniteLineY2**（InfiniteLine 行）  <br/> |
||**visEllipseMajorY**（Ellipse 行）  <br/> |
   

