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
description: 代表 y-坐标在本地坐标系中的形状。 下表描述了基于在它的行的 Y 单元格所在。
ms.openlocfilehash: 461fd0ec41d34132f469c811292550d2f7e094f0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781710"
---
# <a name="y-cell-geometry-section"></a>Y 单元格（“Geometry”部分）

代表*y* -坐标在本地坐标系中的形状。 下表描述了基于在它的行的 Y 单元格所在。 
  
|**Row**|**说明**|
|:-----|:-----|
|[NURBSTo](nurbsto-row-geometry-section.md) <br/> | 如果 MoveTo 行是部分中的第一行，则 Y 单元格表示*y* -路径的第一个顶点的坐标。 如果 MoveTo 行出现在两行之间，则 Y 单元格表示*y* -路径中断开后的第一个顶点的坐标。  <br/> |
|[LineTo](lineto-row-geometry-section.md) <br/> | *Y* -直线段终顶点的坐标。  <br/> |
|[ArcTo](arcto-row-geometry-section.md) <br/> | *Y* -弧形终顶点的坐标。  <br/> |
|[EllipticalArcTo](ellipticalarcto-row-geometry-section.md) <br/> | *Y* -椭圆弧线终顶点的坐标。  <br/> |
|[PolylineTo](polylineto-row-geometry-section.md) <br/> | *Y* -折线终顶点的坐标。  <br/> |
|[NURBSTo](nurbsto-row-geometry-section.md) <br/> | *Y* -非均匀有理 B 样条 (NURBS) 的最后一个控制点的坐标。  <br/> |
|[SplineStart](splinestart-row-geometry-section.md) <br/> | *Y* -样条的第二个控制点的坐标。  <br/> |
|[SplineKnot](splineknot-row-geometry-section.md) <br/> | *Y* -控制点的坐标。  <br/> |
|[InfiniteLine](infiniteline-row-geometry-section.md) <br/> | *Y 轴*坐标值无限长线上某个点。  <br/> |
|[椭圆](ellipse-row-geometry-section.md) <br/> | *Y* -椭圆中心的坐标。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Y 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Geometry *i* 。Y *j*其中*i*和*j* = < 1 >，2，3...  <br/> |
|| Geometry *i* 。Y1 （InfiniteLine 和 Ellipse 行） 其中*i* = < 1 >，2，3...  <br/> |
   
要从某个程序按索引获取对 Y 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionFirstComponent** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 行索引：  <br/> |**visRowVertex** +  *j*其中*j* = 0、 1、 2...  <br/> |
||**visRowVertex**（InfiniteLine 和 Ellipse 行）  <br/> |
| 单元格索引：  <br/> |**visY**（MoveTo、LineTo、ArcTo、EllipticalArcTo、NURBSTo、Polyline、SplineStart 和 SplineKnot 行）  <br/> |
||**visInfiniteLineY1**（InfiniteLine 行）  <br/> |
||**visEllipseCenterY**（Ellipse 行）  <br/> |
   

