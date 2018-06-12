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
description: 在不同行中表示不同的信息。此表根据 B 单元格所在的行对 B 单元格进行了说明。
ms.openlocfilehash: 7d6f51d037be4852c6a101ad6e576a3a13488cb7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779667"
---
# <a name="b-cell-geometry-section"></a>B 单元格（“Geometry”内容）

在不同行中表示不同的信息。此表根据 B 单元格所在的行对 B 单元格进行了说明。
  
|**Row**|**说明**|
|:-----|:-----|
|[EllipticalArcTo](ellipticalarcto-row-geometry-section.md) <br/> | *Y* -弧形的控制点的坐标。  <br/> |
|[NURBSTo](nurbsto-row-geometry-section.md) <br/> | 非均匀有理 B 样条 (NURBS) 的最后一个权值。  <br/> |
|[SplineStart](splinestart-row-geometry-section.md) <br/> | 样条的第一个节点。  <br/> |
|[InfiniteLine](infiniteline-row-geometry-section.md) <br/> | *Y* -; 无限长线上某个点的坐标与*x*配对- [A](a-cell-geometry-section.md)单元格所表示的坐标。  <br/> |
|[椭圆](ellipse-row-geometry-section.md) <br/> | *Y* -椭圆; 上某个点的坐标与*x*配对- [A](a-cell-geometry-section.md)单元格所表示的坐标。  <br/> |
   
## <a name="remarks"></a>备注

若要从另一个公式或从使用**CellsU**属性的某个程序按名称获取对 B 单元格的引用使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Geometry *i* 。B *j*其中*i*和*j* = < 1 >，2，3...  <br/> |
|| Geometry *i* 。B1 （InfiniteLine 和 Ellipse 行）  <br/> |
   
若要从某个程序按索引获取对 B 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionFirstComponent** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 行索引：  <br/> |**visRowVertex** +  *j*其中*j* = 0、 1、 2...  <br/> |
||**visRowVertex**（InfiniteLine 和 Ellipse 行）  <br/> |
| 单元格索引：  <br/> |**visControlX**（EllipticalArcTo 行）  <br/> |
||**visControlY**（EllipticalArcTo 行）  <br/> |
||**visNURBSWeight**（NURBSTo 行）  <br/> |
||**visSplineKnot2**（SplineStart 行）  <br/> |
||**visInfiniteLineY2**（InfiniteLine 行）  <br/> |
||**visEllipseMajorY**（ellipse 行）  <br/> |
   

