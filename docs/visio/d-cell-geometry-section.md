---
title: D 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251753
localization_priority: Normal
ms.assetid: 5f1fdf59-db58-561c-e187-1af72a8b87f2
description: 代表不同行中的不同信息。 此表基于 D 单元格所在的行对它进行说明。
ms.openlocfilehash: a76093f028986907b58175bc6b8c81a7056cfe07
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542497"
---
# <a name="d-cell-geometry-section"></a>D 单元格（“Geometry”内容）

代表不同行中的不同信息。 此表基于 D 单元格所在的行对它进行说明。
  
|Row|说明|
|:-----|:-----|
|[EllipticalArcTo](ellipticalarcto-row-geometry-section.md) <br/> | 弧形的长短轴之比。尽管每一词都有其本义，但在此处“长”轴却并不一定大于“短”轴，所以此比值也就不一定大于 1。如果将此单元格设置为小于等于 0 或大于 1000 的值，可能导致无法预料的结果。  <br/> |
|[NURBSTo](nurbsto-row-geometry-section.md) <br/> | 非均匀有理 B 样条 (NURBS) 的第一个权。  <br/> |
|[SplineStart](splinestart-row-geometry-section.md) <br/> | 样条的角度（从 1 到 25 的整数）。  <br/> |
|[椭圆](ellipse-row-geometry-section.md) <br/> | 椭圆上某个点的*y*坐标;与[C](c-cell-geometry-section.md)单元格所表示的*x*坐标配对。  <br/> |
   
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 D 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 几何图形*i* 。D *j*其中*i*和*j* = <1>, 2, 3 .。。  <br/> |
|| 几何图形*i* 。D1 (椭圆行) 其中*i* = <1>, 2, 3 .。。  <br/> |
   
要从某个程序按索引获取对 D 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionFirstComponent** +  *i* = ** 0、1、2 .。。  <br/> |
| 行索引：  <br/> |**visRowVertex** +  *j*其中*j* = 0, 1, 2 .。。  <br/> |
||**visRowVertex**（Ellipse 行）  <br/> |
| 单元格索引  <br/> |**visAspectRatio**（EllipticalArcTo 行）  <br/> |
||**visNURBSWeightPrev**（NURBSTo 行）  <br/> |
||**visSplineDegree**（SplineStart 行）  <br/> |
||**visEllipseMinorY**（Ellipse 行）  <br/> |
   

