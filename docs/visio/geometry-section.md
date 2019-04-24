---
title: “Geometry”内容
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm2055
localization_priority: Normal
ms.assetid: 75601a1e-6b1a-27ee-a2bd-69e569315982
description: 包含列出构成形状的线条和弧形的顶点坐标的行。
ms.openlocfilehash: 32a815015c7d1764399215767b674668b7235832
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345113"
---
# <a name="geometry-section"></a>“Geometry”内容

包含列出构成形状的线条和弧形的顶点坐标的行。 
  
可在多个 " **geometry** " 内容中表示形状的几何图形。 当多个路径具有不同的属性 (例如,[图像剪切](clippingpath-cell-foreign-image-info-section.md)路径) 时, 多个路径可能很有用。 
  
## <a name="remarks"></a>注解

" **Geometry** " 内容包含以下行类型。 有关详细信息，请参阅行主题。 
  
|**行**|**说明**|
|:-----|:-----|
|[MoveTo](moveto-row-geometry-section.md) <br/> |移到某一坐标处。  <br/> |
|[LineTo](lineto-row-geometry-section.md) <br/> |绘制一条到某坐标处的直线。  <br/> |
|[ArcTo](arcto-row-geometry-section.md) <br/> |绘制一条到某坐标处的圆弧。  <br/> |
|[EllipticalArcTo](ellipticalarcto-row-geometry-section.md) <br/> |绘制一条到某坐标处的椭圆弧。  <br/> |
|[PolylineTo](polylineto-row-geometry-section.md) <br/> |绘制一条到某坐标处的折线或连续线条。  <br/> |
|[NURBSTo](nurbsto-row-geometry-section.md) <br/> |将非统一的有理 B 样条 (NURBS) 绘制到坐标。  <br/> |
|[SplineStart](splinestart-row-geometry-section.md) <br/> |开始一个样条。  <br/> |
|[SplineKnot](splineknot-row-geometry-section.md) <br/> |绘制一条到某节点坐标处的样条线段。  <br/> |
|[InfiniteLine](infiniteline-row-geometry-section.md) <br/> |在两个坐标之间绘制一条无限长线。  <br/> |
|[椭圆](ellipse-row-geometry-section.md) <br/> |根据中心坐标和长轴/短轴绘制一个椭圆。  <br/> |
|[RelCubBezTo](relcubbezto-row-geometry-section.md) <br/> |相对于形状的宽度和高度绘制一条三次方贝塞尔曲线。  <br/> |
|[RelEllipticalArcTo](relellipticalarcto-row-geometry-section.md) <br/> |相对于形状的高度和宽度绘制一条椭圆弧。  <br/> |
|[RelLineTo](rellineto-row-geometry-section.md) <br/> |绘制一条相对于形状的高度和宽度的坐标线。  <br/> |
|[RelMoveTo](relmoveto-row-geometry-section.md) <br/> |移动到相对于形状的宽度和高度的坐标。  <br/> |
|[RelQuadBezTo](relquadbezto-row-geometry-section.md) <br/> |相对于形状的宽度和高度绘制一条二次贝塞尔曲线。  <br/> |
   
若要在此内容中更改行的类型，请右击该行，然后在快捷菜单上单击 **“更改行类型”**。 
  

