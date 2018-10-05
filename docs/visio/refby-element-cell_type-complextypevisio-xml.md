---
title: RefBy 元素 （Cell_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ea2a63d3-d319-4420-1929-013dc832b308
description: 指定绘图中的页面的引用。
ms.openlocfilehash: 1731bd20a5ba4358c72370dfcdc6d8a6fc791e2f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385856"
---
# <a name="refby-element-celltype-complextype-visio-xml"></a>RefBy 元素 （Cell_Type 复杂类型） (Visio XML)

指定绘图中的页面的引用。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |document.xml、 masters.xml、 主 #.xml、 pages.xml、 页 #.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="RefBy" type="RefBy_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Cell 元素（“Action Tag”部分）](cell-element-action-tag-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |定义形状或页上的某个动作标记的一个属性。  <br/> |
|[Cell 元素（“Actions”行）](cell-element-actions-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定快捷菜单或动作标记菜单上的自定义命令与关联的操作的一个的属性。  <br/> |
|[Cell 元素（“ArcTo”行）](cell-element-arcto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含的 x 坐标、 y 坐标或圆弧弓。  <br/> |
|[Cell 元素（“Character”部分）](cell-element-character-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定形状的文本运行格式属性，如字体、 颜色样式、 case、 位置相对于基线，或磅值。  <br/> |
|[Cell 元素（“Connection”行）](cell-element-connection-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含的 x 轴或 y 坐标、 水平或垂直方向或形状上的单个连接点类型。  <br/> |
|[Cell 元素（“Controls”行）](cell-element-controls-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含特定的控制手柄为形状定义的属性。  <br/> |
|[Cell 元素（“Ellipse”行）](cell-element-ellipse-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含 x 坐标或 y 坐标的椭圆中心点和椭圆上的两个点。  <br/> |
|[Cell 元素（“EllipticalArcTo”行）](cell-element-ellipticalarcto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含 x 坐标或 y 坐标的椭圆弧终结点的 x 坐标或 y 坐标控件的 points 弧形，夹角从 x 轴到椭圆的长轴或比椭圆的主要和次要刻度轴上。  <br/> |
|[Cell 元素（“Field”部分）](cell-element-field-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |显示使用“域”对话框在形状的文本中插入的函数和公式。  <br/> |
|[Cell 元素（“Fill Gradient”部分）](cell-element-fill-gradient-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含颜色、 透明度和渐变填充的渐变光圈的位置。  <br/> |
|[Cell 元素（“Geometry”部分）](cell-element-geometry-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |定义用于确定行和弧组成 geometry 内容的格式和行为的属性的属性。  <br/> |
|[Cell 元素（“Hyperlink”行）](cell-element-hyperlink-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含与形状相关联的单个超链接的信息。对于每个超链接，形状中都将包含一个与之对应的 Hyperlink 行。  <br/> |
|[Cell 元素（“InfiniteLine”行）](cell-element-infiniteline-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含无限长线上两个点的 x 坐标或 y。  <br/> |
|[Cell 元素（“Layer”部分）](cell-element-layer-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定一个图层属性或页面其属性。  <br/> |
|[Cell 元素（“Line Gradient”部分）](cell-element-line-gradient-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含颜色、 透明度或行渐变的渐变光圈的位置。  <br/> |
|[Cell 元素（“LineTo”行）](cell-element-lineto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含 x-或直线段终顶点的 y 坐标。  <br/> |
|[Cell 元素（“MoveTo”行）](cell-element-moveto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含形状的第一个顶点的 x 坐标或 y-或者表示路径中断开后的第一个顶点 x 或 y 坐标。  <br/> |
|[Cell 元素（“NURBSTo”行）](cell-element-nurbsto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含第二个最后一个节点的最后一个权重，第一个节点的第一个权重或非均匀有理 B 样条 (NURBS) 公式的位置的位置的位置的 x 坐标或 y 坐标，的位置。  <br/> |
|[Cell 元素（“Paragraph”部分）](cell-element-paragraph-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定段落格式属性形状的文本，如缩进、 行间距、 项目符号或段落的水平对齐方式。  <br/> |
|[Cell 元素（“PolyLineTo”行）](cell-element-splineknot-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含 x 坐标或 y 坐标的最后一个点折线或折线公式。  <br/> |
|[Cell 元素（“RelCubBezTo”行）](cell-element-relcubbezto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含 x 坐标或 y 坐标的相对于形状的宽度和高度的立方贝赛尔曲线的终结点、 的控制点的位于曲线的相对于形状的宽度和高度，开头或 x 坐标或 y 坐标的控制点的 x 坐标或 y 坐标位于曲线的相对于形状的宽度和高度的尾。  <br/> |
|[Cell 元素（“RelEllipticalArcTo”行）](cell-element-relellipticalarcto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含 x 坐标或 y 坐标的相对于形状的宽度和高度的椭圆弧的终点相对于形状的宽度和高度，从椭圆的长轴或比率为 x 轴的角度弧形上控制点的 x 坐标或 y 坐标的控件椭圆的主要和次要刻度坐标轴。  <br/> |
|[单元格元素 （RelLineTo 行）](cell-element-rellineto-rowvisio-xml.md)[单元格](cell-element-rellineto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含 x-或相对于形状的宽度和高度直线段终顶点的 y 坐标。  <br/> |
|[Cell 元素（“RelMoveTo”行）](cell-element-relmoveto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含后的高度和宽度的形状的相对路径中断开的 x 坐标或 y 坐标形状的第一个顶点的 x 坐标或 y 坐标的第一个顶点。  <br/> |
|[单元格元素 （RelQuadBezTo 部分](cell-element-relquadbezto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含 x 坐标或 y 坐标的相对于形状的宽度和高度二次贝塞尔曲线的终结点或曲线相对于形状的宽度和高度的控制点 x 或 y 坐标。  <br/> |
|[Cell 元素（“Scratch”部分）](cell-element-scratch-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定输入和测试可由其他单元格引用的公式的工作区。  <br/> |
|[单元格 （Shape Data 内容元素](cell-element-shape-data-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定形状数据的一个的属性。  <br/> |
|[Cell 元素（“SplineKnot”行）](cell-element-splineknot-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含 x 坐标或 y 坐标样条控制点或样条节点。  <br/> |
|[单元格元素 （SplineStart 部分](cell-element-splinestart-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含 x 坐标或 y 坐标样条的第二个控制点、 它的第二个节点、 第一个节点、 最后一个节点或样条的度数。  <br/> |
|[Cell 元素（“Tabs”部分）](cell-element-tabs-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定形状和样式制表位位置或对齐的控件的属性。  <br/> |
|[Cell 元素（“User-defined Cells”部分）](cell-element-user-defined-cells-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |用户指定的可由其他单元格和加载项工具引用的信息片段一个属性。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|ID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |指定在绘图页的 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|T  <br/> |xsd: string  <br/> |必需  <br/> |指定引用类型。  <br/> |Xsd: string 类型的值。  <br/> |
   

