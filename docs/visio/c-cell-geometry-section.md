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
description: 代表不同行中的不同信息。该表基于 C 单元格所在的行对它进行说明。
ms.openlocfilehash: 1b9a813be825f2deeb5c90d596ffd9f3705bcef6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779815"
---
# <a name="c-cell-geometry-section"></a>C 单元格（“Geometry”部分）

代表不同行中的不同信息。该表基于 C 单元格所在的行对它进行说明。
  
|**Row**|**说明**|
|:-----|:-----|
|[EllipticalArcTo](ellipticalarcto-row-geometry-section.md) <br/> | 弧形的长轴相对于*x*角度-其父级的轴。  <br/> |
|[NURBSTo](nurbsto-row-geometry-section.md) <br/> | 非均匀有理 B 样条 (NURBS) 的第一个节点。  <br/> |
|[SplineStart](splinestart-row-geometry-section.md) <br/> | 样条的最后一个节点。  <br/> |
|[椭圆](ellipse-row-geometry-section.md) <br/> | *X* -椭圆; 上某个点的坐标与*y*配对- [D](d-cell-geometry-section.md)单元格所表示的坐标。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 C 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Geometry *i* 。C *j*其中*i*和*j* = < 1 >，2，3...  <br/> |
|| Geometry *i* 。C1 （Ellipse 行）  <br/> |
   
要从某个程序按索引获取对 C 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionFirstComponent** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 行索引：  <br/> |**visRowVertex** +  *j*其中*j* = 0、 1、 2...  <br/> |
||**visRowVertex**（Ellipse 行）  <br/> |
| 单元格索引：  <br/> |**visEccentricityAngle**（EllipticalArcTo 行）  <br/> |
||**visNURBSKnotPrev**（NURBSTo 行）  <br/> |
||**visSplineKnot3**（SplineStart 行）  <br/> |
||**visEllipseMinorX**（Ellipse 行）  <br/> |
   

