---
title: Y 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251750
localization_priority: Normal
ms.assetid: a53b5787-f419-7a36-3c04-c63b3c173ac7
description: 表示在本地坐标系中形状上的 y 坐标。 该表基于 y 单元格所在的行对它进行说明。
ms.openlocfilehash: 7dea96b544c84f09abe1d72304da0bacaa09432f
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540488"
---
# <a name="y-cell-geometry-section"></a>Y 单元格（“Geometry”内容）

表示在本地坐标系中形状上的*y*坐标。 该表基于 y 单元格所在的行对它进行说明。 
  
|Row|说明|
|:-----|:-----|
|[NURBSTo](nurbsto-row-geometry-section.md) <br/> | 如果 MoveTo 行是该内容中的第一行, 则 Y 单元格表示路径的第一个顶点的*Y*坐标。 如果 MoveTo 行出现在两行之间, 则 Y 单元格表示路径中断开处后的第一个顶点的*y*坐标。  <br/> |
|[LineTo](lineto-row-geometry-section.md) <br/> | 直线段终顶点的*y*坐标。  <br/> |
|[ArcTo](arcto-row-geometry-section.md) <br/> | 弧形终顶点的*y*坐标。  <br/> |
|[EllipticalArcTo](ellipticalarcto-row-geometry-section.md) <br/> | 椭圆弧线终顶点的*y*轴坐标值。  <br/> |
|[PolylineTo](polylineto-row-geometry-section.md) <br/> | 折线终顶点的*y*坐标。  <br/> |
|[NURBSTo](nurbsto-row-geometry-section.md) <br/> | 非均匀有理 B 样条 (NURBS) 的最后一个控制点的*y*坐标。  <br/> |
|[SplineStart](splinestart-row-geometry-section.md) <br/> | 样条第二个控制点的*y*坐标。  <br/> |
|[SplineKnot](splineknot-row-geometry-section.md) <br/> | 控制点的*y*坐标。  <br/> |
|[InfiniteLine](infiniteline-row-geometry-section.md) <br/> | 无限长线上某个点的*y*坐标。  <br/> |
|[椭圆](ellipse-row-geometry-section.md) <br/> | 椭圆中心的*y*轴坐标值。  <br/> |
   
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Y 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 几何图形*i* 。Y *j*其中*i*和*j* = <1>, 2, 3 .。。  <br/> |
|| 几何图形*i* 。Y1 (InfiniteLine 和椭圆行) 其中*i* = <1>, 2, 3 .。。  <br/> |
   
要从某个程序按索引获取对 Y 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionFirstComponent** +  *i* = ** 0、1、2 .。。  <br/> |
| 行索引：  <br/> |**visRowVertex** +  *j*其中*j* = 0, 1, 2 .。。  <br/> |
||**visRowVertex**（InfiniteLine 和 Ellipse 行）  <br/> |
| 单元格索引：  <br/> |**visY**（MoveTo、LineTo、ArcTo、EllipticalArcTo、NURBSTo、Polyline、SplineStart 和 SplineKnot 行）  <br/> |
||**visInfiniteLineY1**（InfiniteLine 行）  <br/> |
||**visEllipseCenterY**（Ellipse 行）  <br/> |
   

