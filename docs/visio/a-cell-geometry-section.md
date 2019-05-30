---
title: A 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm51215
localization_priority: Normal
ms.assetid: 6853df0f-d22e-89ca-7d34-342b9c0bea23
description: 在不同行中表示不同的信息。 此表根据 A 单元格所在的行对 A 单元格进行了说明。
ms.openlocfilehash: 7009658c7a6844a5c6071f502c05114a4accd7b7
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541300"
---
# <a name="a-cell-geometry-section"></a>A 单元格（“Geometry”内容）

在不同行中表示不同的信息。 此表根据 A 单元格所在的行对 A 单元格进行了说明。
  
|Row|说明|
|:-----|:-----|
|[ArcTo](arcto-row-geometry-section.md) <br/> | 从弧形的中点到对应的弦的中点的距离。  <br/> |
|[EllipticalArcTo](ellipticalarcto-row-geometry-section.md) <br/> | 弧形的控制点 (弧形上的一个点) 的*x*坐标。控制点最适合弧的起始和结束顶点之间的中间点。否则, 弧的大小可能会增大到极大的大小, 以便通过控制点, 从而导致不可预知的结果。  <br/> |
|[PolylineTo](polylineto-row-geometry-section.md) <br/> | 折线公式。  <br/> |
|[NURBSTo](nurbsto-row-geometry-section.md) <br/> | 非均匀有理 B 样条 (NURBS) 的倒数第二个节点。  <br/> |
|[SplineStart](splinestart-row-geometry-section.md) <br/> | 样条的第二个节点。  <br/> |
|[SplineKnot](splineknot-row-geometry-section.md) <br/> | 样条的节点之一（最后一个节点或前两个节点除外）。  <br/> |
|[InfiniteLine](infiniteline-row-geometry-section.md) <br/> | 无限长线上某个点的*x*坐标;与[B](b-cell-geometry-section.md)单元格所表示的*y*坐标配对。  <br/> |
|[椭圆](ellipse-row-geometry-section.md) <br/> | 椭圆上某个点的*x*坐标;与[B](b-cell-geometry-section.md)单元格所表示的*y*坐标配对。  <br/> |
   
## <a name="remarks"></a>备注

要从另一个公式或程序使用 **CellsU** 属性按名称获取对 A 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 几何图形*i* 。*J* *i*和*j* = <1>, 2, 3 .。。  <br/> |
|| 几何图形*i* 。A1 (InfiniteLine 和椭圆行) 其中*i* = <1>, 2, 3 .。。  <br/> |
   
要从某个程序按索引获取对 A 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionFirstComponent** +  *i* = ** 0、1、2 .。。  <br/> |
| 行索引：  <br/> |**visRowVertex** +  *j*其中*j* = 0, 1, 2 .。。  <br/> |
||**visRowVertex**（InfiniteLine 和 Ellipse 行）  <br/> |
| 单元格索引：  <br/> |**visBow**（ArcTo 行）  <br/> |
||**visControlX**（EllipticalArcTo 行）  <br/> |
||**visControlY**（EllipticalArcTo 行）  <br/> |
||**visPolylineData**（Polyline 行）  <br/> |
||**visNURBSKnot**（NURBSTo 行）  <br/> |
||**visSplineKnot**（SplineStart 和 SplineKnot 行）  <br/> |
||**visInfiniteLineX2**（InfiniteLine 行）  <br/> |
||**visEllipseMajorX**（Ellipse 行）  <br/> |
   

