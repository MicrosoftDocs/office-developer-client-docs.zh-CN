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
description: 包含列表的线条和弧组成的形状的顶点坐标的行。
ms.openlocfilehash: 59f85c512b7038f6cfddcb657435730a2e724bd6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780331"
---
# <a name="geometry-section"></a>“Geometry”内容

包含列表的线条和弧组成的形状的顶点坐标的行。 
  
可以在多个**geometry**节中表示形状的几何图形。 多个路径具有不同的属性 （例如[图像剪辑](clippingpath-cell-foreign-image-info-section.md)路径） 时，多个路径可能很有用。 
  
## <a name="remarks"></a>备注

**Geometry**内容包含下面的行类型。 有关详细信息，请参阅行主题。 
  
|**Row**|**说明**|
|:-----|:-----|
|[MoveTo](moveto-row-geometry-section.md) <br/> |移到某一坐标处。  <br/> |
|[LineTo](lineto-row-geometry-section.md) <br/> |绘制一条到某坐标处的直线。  <br/> |
|[ArcTo](arcto-row-geometry-section.md) <br/> |绘制一条到某坐标处的圆弧。  <br/> |
|[EllipticalArcTo](ellipticalarcto-row-geometry-section.md) <br/> |绘制一条到某坐标处的椭圆弧。  <br/> |
|[PolylineTo](polylineto-row-geometry-section.md) <br/> |绘制一条到某坐标处的折线或连续线条。  <br/> |
|[NURBSTo](nurbsto-row-geometry-section.md) <br/> |绘制非均匀有理 B 样条 (NURBS) 到某坐标处。  <br/> |
|[SplineStart](splinestart-row-geometry-section.md) <br/> |开始一个样条。  <br/> |
|[SplineKnot](splineknot-row-geometry-section.md) <br/> |绘制一条到某节点坐标处的样条线段。  <br/> |
|[InfiniteLine](infiniteline-row-geometry-section.md) <br/> |在两个坐标之间绘制一条无限长线。  <br/> |
|[椭圆](ellipse-row-geometry-section.md) <br/> |根据中心坐标和长轴/短轴绘制一个椭圆。  <br/> |
|[RelCubBezTo](relcubbezto-row-geometry-section.md) <br/> |绘制三次相对于的宽度和高度形状的贝赛尔曲线。  <br/> |
|[RelEllipticalArcTo](relellipticalarcto-row-geometry-section.md) <br/> |绘制到相对于的高度和宽度的形状的坐标处的椭圆弧。  <br/> |
|[RelLineTo](rellineto-row-geometry-section.md) <br/> |绘制一条到坐标相对的高度和宽度的形状。  <br/> |
|[RelMoveTo](relmoveto-row-geometry-section.md) <br/> |移到某坐标相对于形状的高度和宽度。  <br/> |
|[RelQuadBezTo](relquadbezto-row-geometry-section.md) <br/> |绘制二次相对于的宽度和高度形状的贝赛尔曲线。  <br/> |
   
若要更改此部分中的行类型，右击该行，，然后单击快捷菜单上的**更改行类型**。 
  

