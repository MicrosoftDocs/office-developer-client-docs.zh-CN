---
title: 'RefBy 元素 (Cell_Type COMPLEXType)  (Visio XML) '
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
# <a name="refby-element-cell_type-complextype-visio-xml"></a>RefBy 元素 (Cell_Type COMPLEXType)  (Visio XML) 

指定对绘图中页面的引用。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |document.xml、masters.xml、master#.xml、pages.xml、page#.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="RefBy" type="RefBy_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Cell 元素 (Action Tag Section) ](cell-element-action-tag-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |为形状或页面上的动作标记定义一个属性。  <br/> |
|[Cell 元素（“Actions”行）](cell-element-actions-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定与快捷菜单或动作标记菜单上的自定义命令相关联的动作的一个属性。  <br/> |
|[Cell 元素（“ArcTo”行）](cell-element-arcto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含圆弧的 x 坐标、y 坐标或弓形。  <br/> |
|[Cell 元素 (Character Section) ](cell-element-character-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定形状的文本域的格式属性，如字体、颜色、样式、大小写、相对于基线的位置或点大小。  <br/> |
|[Cell 元素（“Connection”行）](cell-element-connection-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含形状上的单个连接点的 x 坐标或 y 坐标、水平或垂直方向或类型。  <br/> |
|[Cell 元素（“Controls”行）](cell-element-controls-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含为形状定义的特定控制手柄的属性。  <br/> |
|[Cell 元素（“Ellipse”行）](cell-element-ellipse-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含椭圆的中心点和椭圆上的两个点的 x 坐标或 y 坐标。  <br/> |
|[Cell 元素（“EllipticalArcTo”行）](cell-element-ellipticalarcto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含椭圆弧终点的 x 坐标或 y 坐标、弧形上控制点的 x 坐标或 y 坐标、从 x 轴到椭圆主轴的角度，或者椭圆主轴和次要轴之间的比值。  <br/> |
|[Field Section (Cell 元素) ](cell-element-field-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |显示使用“域”对话框在形状的文本中插入的函数和公式。  <br/> |
|[Fill Gradient Section (Cell 元素) ](cell-element-fill-gradient-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含填充渐变的渐变停点的颜色、透明度以及位置。  <br/> |
|["Geometry" (Cell 元素) ](cell-element-geometry-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |定义用于确定与"Geometry"内容中的线条和弧有关的格式和行为属性的属性。  <br/> |
|[Cell 元素（“Hyperlink”行）](cell-element-hyperlink-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含与形状相关联的单个超链接的信息。对于每个超链接，形状中都将包含一个与之对应的 Hyperlink 行。  <br/> |
|[Cell 元素（“InfiniteLine”行）](cell-element-infiniteline-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含无限长线上两个点的 x 坐标或 y 坐标。  <br/> |
|[Layer Section (Cell 元素) ](cell-element-layer-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |为图层指定一个属性，或者为页面指定其属性。  <br/> |
|[Line Gradient Section (Cell 元素) ](cell-element-line-gradient-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含线条渐变的渐变停点的颜色、透明度或位置。  <br/> |
|[Cell 元素（“LineTo”行）](cell-element-lineto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含直线段终顶点的 x 或 y 坐标。  <br/> |
|[Cell 元素（“MoveTo”行）](cell-element-moveto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含形状的第一个顶点的 x 坐标或 y 坐标，或表示路径中中断后的第一个顶点的 x 或 y 坐标。  <br/> |
|[Cell 元素（“NURBSTo”行）](cell-element-nurbsto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含 x 坐标或 y 坐标、第二个到最后一个节点的位置、最后一个权重的位置、第一个节点的位置、第一个权重的位置或非均匀有理 B 样条 (NURBS) 。  <br/> |
|[Cell 元素 (Paragraph Section) ](cell-element-paragraph-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定形状文本的段落格式属性，如缩进、行距、项目符号或段落的水平对齐方式。  <br/> |
|[Cell 元素（“PolyLineTo”行）](cell-element-splineknot-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含折线或折线公式的最后一个点的 x 坐标或 y 坐标。  <br/> |
|[Cell 元素（“RelCubBezTo”行）](cell-element-relcubbezto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含三次方贝塞尔曲线终点相对于形状的宽度和高度的 x 坐标或 y 坐标、曲线相对形状的宽度和高度的起点的控制点的 x 坐标或 y 坐标，或者曲线相对形状的宽度和高度终点的控制点的 x 或 y 坐标。  <br/> |
|[Cell 元素（“RelEllipticalArcTo”行）](cell-element-relellipticalarcto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含椭圆弧的终点相对于形状的宽度和高度的 x 坐标或 y 坐标、弧上控制点的 x 坐标或 y 坐标（相对于形状的宽度和高度、从 x 轴到椭圆的主要轴的角度，或者椭圆的主要轴和次要轴之间的比率）。  <br/> |
|[Cell 元素 (RelLineTo Row) ](cell-element-rellineto-rowvisio-xml.md) [Cell](cell-element-rellineto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含直线段终顶点相对于形状的宽度和高度的 x 或 y 坐标。  <br/> |
|[Cell 元素（“RelMoveTo”行）](cell-element-relmoveto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含形状的第一个顶点的 x 坐标或 y 坐标，或者路径中中断后的第一个顶点的 x 或 y 坐标（相对于形状的高度和宽度）。  <br/> |
|[Cell 元素 (RelQuadBezTo Section](cell-element-relquadbezto-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含二次方贝塞尔曲线终点相对于形状的宽度和高度的 x 坐标或 y 坐标，或者曲线相对形状的宽度和高度的控制点的 x 坐标或 y 坐标。  <br/> |
|[Scratch Section (Cell 元素) ](cell-element-scratch-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定用于输入和测试其他单元格可引用的公式的工作区。  <br/> |
|[Shape Data (Cell 元素](cell-element-shape-data-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定形状数据的一个属性。  <br/> |
|[Cell 元素（“SplineKnot”行）](cell-element-splineknot-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含样条的控制点或样条节点的 x 坐标或 y 坐标。  <br/> |
|[SplineStart (Cell 元素](cell-element-splinestart-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含样条的第二个控制点、其第二个节点、第一个节点、最后一个节点或样条的度数的 x 或 y 坐标。  <br/> |
|["Tabs"内容 (Cell 元素) ](cell-element-tabs-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定控制形状和样式制表位位置或对齐方式的属性。  <br/> |
|[User-defined Cells (的 Cell 元素) ](cell-element-user-defined-cells-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |用户指定的信息块的一个属性，其他单元格和加载项工具可以引用这些信息。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|ID  <br/> |xsd：unsignedInt  <br/> |必需  <br/> |指定绘图中页面的 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|T  <br/> |xsd：string  <br/> |必需  <br/> |指定引用类型。  <br/> |xsd：string 类型的值。  <br/> |
   

