---
title: X 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1135
localization_priority: Normal
ms.assetid: 2416b323-e084-18e1-c9be-a797078dfab9
description: 表示本地坐标中形状上的 x 坐标。 该表基于 X 单元格所在的行对它进行说明。
ms.openlocfilehash: 2b3303533db446780ef797844ac5e1438cec242f
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538212"
---
# <a name="x-cell-geometry-section"></a>X 单元格（“Geometry”内容）

表示本地坐标中形状上的  *x*  坐标。 该表基于 X 单元格所在的行对它进行说明。 
  
|Row|说明|
|:-----|:-----|
|[MoveTo](moveto-row-geometry-section.md) <br/> | 如果 MoveTo 行是内容的第一行，则 X 单元格表示路径的第一个顶点的  *x*  坐标。 如果 MoveTo 行出现在两行之间，则 X 单元格表示路径中中断后的第一个顶点的  *x*  坐标。  <br/> |
|[LineTo](lineto-row-geometry-section.md) <br/> | 直线段终顶点的  *x*  坐标。  <br/> |
|[ArcTo](arcto-row-geometry-section.md) <br/> | 弧形终顶点的  *x*  坐标。  <br/> |
|[EllipticalArcTo](ellipticalarcto-row-geometry-section.md) <br/> | 椭圆弧的终顶点的  *x*  坐标。  <br/> |
|[PolylineTo](polylineto-row-geometry-section.md) <br/> | 折线终顶点的  *x*  坐标。  <br/> |
|[NURBSTo](nurbsto-row-geometry-section.md) <br/> | 非均匀有理 B 样条的最后一个控制点的  *x*  坐标 (NURBS) 。  <br/> |
|[SplineStart](splinestart-row-geometry-section.md) <br/> | *样条* 的第二个控制点的 x 坐标。  <br/> |
|[SplineKnot](splineknot-row-geometry-section.md) <br/> | 控制点的  *x*  坐标。  <br/> |
|[InfiniteLine](infiniteline-row-geometry-section.md) <br/> | 无限  *长*  线上一个点的 x 坐标。  <br/> |
|[Ellipse](ellipse-row-geometry-section.md) <br/> | 椭圆的中心的  *x*  坐标。  <br/> |
   
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 X 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Geometry  *i*  .X  *j*            其中  *i*  和  *j*  = <1>、2、3...  <br/> |
|| Geometry  *i*  .X1 (InfiniteLine 和 Ellipse) 其中  *i*  = <1>、2、3...  <br/> |
   
要从某个程序按索引获取对 X 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionFirstComponent**  +  *i* 其中 *i* = 0、1、2...  <br/> |
| 行索引：  <br/> |**visRowVertex**  +  *j* 其中 *j* = 0、1、2...  <br/> |
||**visRowVertex**（InfiniteLine 和 Ellipse 行）  <br/> |
| 单元格索引：  <br/> |**visX**（MoveTo、LineTo、ArcTo、EllipticalArcTo、NURBSTo、Polyline、SplineStart 和 SplineKnot 行）  <br/> |
||**visInfiniteLineX1**（InfiniteLine 行）  <br/> |
||**visEllipseCenterX**（Ellipse 行）  <br/> |
   

