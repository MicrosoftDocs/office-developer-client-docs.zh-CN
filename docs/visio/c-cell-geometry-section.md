---
title: C 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm140
localization_priority: Normal
ms.assetid: d51a1dd8-678a-a34d-658d-bd7a027dd379
description: 代表不同行中的不同信息。 该表基于 C 单元格所在的行对它进行说明。
ms.openlocfilehash: 0284fea02c7eb890b56b6c865a69eb36662d8ae6
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541888"
---
# <a name="c-cell-geometry-section"></a>C 单元格（“Geometry”内容）

代表不同行中的不同信息。 该表基于 C 单元格所在的行对它进行说明。
  
|Row|说明|
|:-----|:-----|
|[EllipticalArcTo](ellipticalarcto-row-geometry-section.md) <br/> | 弧形的长轴相对于其父级的*x*轴的角度。  <br/> |
|[NURBSTo](nurbsto-row-geometry-section.md) <br/> | 非均匀有理 B 样条 (NURBS) 的第一个节点。  <br/> |
|[SplineStart](splinestart-row-geometry-section.md) <br/> | 样条的最后一个节点。  <br/> |
|[椭圆](ellipse-row-geometry-section.md) <br/> | 椭圆上某个点的*x*坐标;与[D](d-cell-geometry-section.md)单元格所表示的*y*坐标配对。  <br/> |
   
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 C 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 几何图形*i* 。C *j*其中*i*和*j* = <1>, 2, 3 .。。  <br/> |
|| 几何图形*i* 。C1 (椭圆行)  <br/> |
   
要从某个程序按索引获取对 C 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionFirstComponent** +  *i* = ** 0、1、2 .。。  <br/> |
| 行索引：  <br/> |**visRowVertex** +  *j*其中*j* = 0, 1, 2 .。。  <br/> |
||**visRowVertex**（Ellipse 行）  <br/> |
| 单元格索引：  <br/> |**visEccentricityAngle**（EllipticalArcTo 行）  <br/> |
||**visNURBSKnotPrev**（NURBSTo 行）  <br/> |
||**visSplineKnot3**（SplineStart 行）  <br/> |
||**visEllipseMinorX**（Ellipse 行）  <br/> |
   

