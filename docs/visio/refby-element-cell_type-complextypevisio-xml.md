---
title: RefBy 元素 (Cell_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ea2a63d3-d319-4420-1929-013dc832b308
description: 指定对绘图中页面的引用。
ms.openlocfilehash: cb47919a97b8ad42f62bcb1337cd8e6b3596f5ff
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538310"
---
# <a name="refby-element-celltype-complextype-visio-xml"></a>RefBy 元素 (Cell_Type 复杂类型) (Visio XML)

指定对绘图中页面的引用。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |document .xml、.master、master # .xml、pages、.xml 和第 .xml 页  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="RefBy" type="RefBy_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Cell 元素 ("Action Tag" 部分)](cell-element-action-tag-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |定义形状或页面上的动作标记的一个属性。  <br/> |
|[Cell 元素（“Actions”行）](cell-element-actions-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定与快捷菜单或动作标记菜单上的自定义命令相关联的操作的一个属性。  <br/> |
|[Cell 元素（“ArcTo”行）](cell-element-arcto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含 x 坐标、y 坐标或圆弧的曲线。  <br/> |
|[Cell 元素 ("字符" 部分)](cell-element-character-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定形状的文本运行的格式属性, 如字体、颜色、样式、大小写、相对于基线的位置或磅值。  <br/> |
|[Cell 元素（“Connection”行）](cell-element-connection-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含形状上的单个连接点的 x 坐标或 y 坐标、水平或垂直方向或类型。  <br/> |
|[Cell 元素（“Controls”行）](cell-element-controls-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含为形状定义的特定控制手柄的属性。  <br/> |
|[Cell 元素（“Ellipse”行）](cell-element-ellipse-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含椭圆中心点的 x 坐标或 y 坐标以及椭圆上的两个点。  <br/> |
|[Cell 元素（“EllipticalArcTo”行）](cell-element-ellipticalarcto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含椭圆弧端点的 x 坐标或 y 坐标、弧形上控制点的 x 坐标或 y 坐标、从 x 轴到椭圆的主轴的角度或椭圆主要和次要轴的比率。  <br/> |
|[Cell 元素 ("字段" 部分)](cell-element-field-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |显示使用“域”对话框在形状的文本中插入的函数和公式。  <br/> |
|[Cell 元素 ("填充渐变" 部分)](cell-element-fill-gradient-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含颜色、透明度以及填充渐变的渐变停止点的位置。  <br/> |
|[Cell 元素 ("Geometry" 内容)](cell-element-geometry-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |定义用于确定格式和行为属性的属性, 这些属性与构成 "Geometry" 内容的线条和弧形相关。  <br/> |
|[Cell 元素（“Hyperlink”行）](cell-element-hyperlink-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含与形状相关联的单个超链接的信息。 对于每个超链接，形状中都将包含一个与之对应的 Hyperlink 行。  <br/> |
|[Cell 元素（“InfiniteLine”行）](cell-element-infiniteline-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含无限长线上两个点的 x 坐标或 y 坐标。  <br/> |
|[Cell 元素 ("Layer" 部分)](cell-element-layer-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |为某一层或其属性指定一个页面的一个属性。  <br/> |
|[Cell 元素 ("线条渐变" 部分)](cell-element-line-gradient-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含线条渐变的渐变停止点的颜色、透明度或位置。  <br/> |
|[Cell 元素（“LineTo”行）](cell-element-lineto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含直线段终顶点的 x 坐标或 y 坐标。  <br/> |
|[Cell 元素（“MoveTo”行）](cell-element-moveto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含形状的第一个顶点的 x 坐标或 y 坐标, 或表示路径中的断点后的第一个顶点的 x 坐标或 y 坐标。  <br/> |
|[Cell 元素（“NURBSTo”行）](cell-element-nurbsto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含 x 或 y 坐标、第二个节点的位置、最后一个权重的位置、第一个节点的位置、第一个节点的位置、第一个权重的位置或非均匀有理 B 样条 (NURBS) 的公式。  <br/> |
|[Cell 元素 ("段落" 部分)](cell-element-paragraph-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定形状的文本的段落格式属性, 例如段落的缩进、行间距、项目符号或水平对齐方式。  <br/> |
|[Cell 元素（“PolyLineTo”行）](cell-element-splineknot-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含折线或折线公式的最后一个点的 x 坐标或 y 坐标。  <br/> |
|[Cell 元素（“RelCubBezTo”行）](cell-element-relcubbezto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含相对于形状的宽度和高度的三次方贝塞尔曲线端点的 x 坐标或 y 坐标、曲线相对形状的宽度和高度的起点的 x 轴坐标或 y 轴坐标, 或控制点的 x 轴或 y 轴坐标曲线相对形状的宽度和高度的结束位置。  <br/> |
|[Cell 元素（“RelEllipticalArcTo”行）](cell-element-relellipticalarcto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含椭圆弧的终点相对于形状的宽度和高度、弧上的控制点相对于该形状的宽度和高度的 x 坐标或 y 坐标、从 x 轴到椭圆的主轴的角度、从 x 轴到椭圆的长轴的比例或椭圆的主要和次要轴。  <br/> |
|[Cell 元素 ("RelLineTo" 行)](cell-element-rellineto-rowvisio-xml.md)[单元格](cell-element-rellineto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含相对于形状的宽度和高度的直线段终顶点的 x 坐标或 y 坐标。  <br/> |
|[Cell 元素（“RelMoveTo”行）](cell-element-relmoveto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含形状的第一个顶点的 x 坐标或 y 坐标, 或路径中断开点后的第一个顶点的 x 坐标或 y 坐标 (相对于形状的高度和宽度)。  <br/> |
|[Cell 元素 ("RelQuadBezTo" 部分](cell-element-relquadbezto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含相对于形状的宽度和高度或曲线相对形状的宽度和高度的控制点的 x 轴或 y 轴坐标的二次贝塞尔曲线端点的 x 坐标或 y 坐标。  <br/> |
|[Cell 元素 ("草稿" 部分)](cell-element-scratch-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定用于输入和测试可由其他单元格引用的公式的工作区。  <br/> |
|[Cell 元素 ("Shape Data" 内容](cell-element-shape-data-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定形状数据的一个属性。  <br/> |
|[Cell 元素（“SplineKnot”行）](cell-element-splineknot-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含样条的控制点或样条的节点的 x 轴或 y 轴坐标。  <br/> |
|[Cell 元素 ("SplineStart" 部分](cell-element-splinestart-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含样条的第二个控制点、第二个节点、第一个节点、最后一个节点或样条的角度的 x 轴或 y 轴坐标。  <br/> |
|[Cell 元素 ("Tabs" 部分)](cell-element-tabs-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定用于控制形状和样式的制表位位置或对齐方式的属性。  <br/> |
|[Cell 元素 ("用户定义的单元格" 部分)](cell-element-user-defined-cells-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |用户指定的信息部分的一个属性, 可由其他单元格和附加工具引用。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|ID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |指定绘图中页面的 ID。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|T  <br/> |xsd: string  <br/> |必需  <br/> |指定引用类型。  <br/> |Xsd: string 类型的值。  <br/> |
   

