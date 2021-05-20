---
title: "\"Geometry\" (的 Row)  (Visio XML) "
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2b273958-1997-7c63-4a61-d231f023a81f
description: 包含列出构成形状的线条和弧形的顶点坐标的行。
ms.openlocfilehash: 6dbf18b749ed072645c4941922729010f74fc0ae
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540852"
---
# <a name="row-element-geometry-section-visio-xml"></a>"Geometry" (的 Row)  (Visio XML) 

包含列出构成形状的线条和弧形的顶点坐标的行。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[GeometryRow_Type](geometry_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |master#.xml，page#.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Row" type="GeometryRow_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Section](section-element-sheet_type-complextypevisio-xml.md) <br/> |[Section_Type](section_type-complextypevisio-xml.md) <br/> |包含列出构成形状的线条和弧形的顶点坐标的行。  <br/> |
   
### <a name="child-elements"></a>子元素

> [!NOTE]
> Cell 元素是此元素的唯一子元素。 根据此元素的"T"属性，Cell 元素的含义有所不同。 在下表中，元素名称中的参数文本对应于应用该主题的"T"值。 
  
|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Cell 元素（“ArcTo”行）](arcto-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含圆弧的 x 坐标、y 坐标和弓。  <br/> |
|[Cell 元素（“Ellipse”行）](ellipse-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含椭圆中心点和椭圆上两个点的 x 坐标和 y 坐标。  <br/> |
|[Cell 元素（“EllipticalArcTo”行）](ellipticalarcto-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含椭圆弧端点的 x 坐标和 y 坐标、弧形上控制点的 x 坐标和 y 坐标、x 轴与椭圆长轴之间的夹角以及椭圆长短轴之比。  <br/> |
|[Cell 元素（“InfiniteLine”行）](infiniteline-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含无限长线上两个点的 x 坐标和 y 坐标。  <br/> |
|[Cell 元素（“LineTo”行）](lineto-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含直线段终顶点的 x 坐标和 y 坐标。  <br/> |
|[Cell 元素（“MoveTo”行）](moveto-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含形状的第一个顶点的 x 坐标和 y 坐标，或者表示路径中断开处后的第一个顶点的 x 坐标和 y 坐标。  <br/> |
|[Cell 元素（“NURBSTo”行）](nurbsto-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含非均匀有理 B 样条 (NURBS) 的 x 坐标和 y 坐标、倒数第二个节点的位置、最后一个权重的位置、第一个节点的位置、第一个权重的位置以及样条的公式。  <br/> |
|[Cell 元素（“PolyLineTo”行）](polylineto-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含折线最后一个点的 x 坐标和 y 坐标以及折线公式。  <br/> |
|[Cell 元素（“RelCubBezTo”行）](relcubbezto-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含三次方贝塞尔曲线终点相对于形状的宽度和高度的 x 坐标和 y 坐标、曲线相对形状的宽度和高度的起点的控制点的 x 坐标和 y 坐标，以及曲线相对形状的宽度和高度终点的控制点的 x 坐标和 y 坐标。  <br/> |
|[Cell 元素（“RelQuadBezTo”行）](relquadbezto-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含二次方贝塞尔曲线终点相对于形状的宽度和高度的 x 坐标和 y 坐标，以及曲线相对形状的宽度和高度的控制点的 x 坐标和 y 坐标。  <br/> |
|[Cell 元素（“RelEllipticalArcTo”行）](relellipticalarcto-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含椭圆弧终点相对于形状的宽度和高度的 x 坐标和 y 坐标、弧上控制点的 x 坐标和 y 坐标（相对于形状的宽度和高度、从 x 轴到椭圆主轴的角度）以及椭圆主要轴和次要轴之间的比率。  <br/> |
|[Cell 元素（“RelLineTo”行）](rellineto-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含直线段的终点相对于形状的宽度和高度的 x 坐标和 y 坐标。  <br/> |
|[Cell 元素（“RelMoveTo”行）](relmoveto-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含形状的第一个顶点的 x 坐标和 y 坐标，或者路径中中断后的第一个顶点的 x 坐标和 y 坐标（相对于形状的高度和宽度）。  <br/> |
|[Cell 元素（“RelQuadBezTo”行）](relquadbezto-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含二次方贝塞尔曲线终点相对于形状的宽度和高度的 x 坐标和 y 坐标，以及曲线相对形状的宽度和高度的控制点的 x 坐标和 y 坐标。  <br/> |
|[Cell 元素（“SplineKnot”行）](splineknot-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含样条控制点和样条节点的 x 坐标和 y 坐标。  <br/> |
|[Cell 元素（“SplineStart”行）](splinestart-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含样条第二个控制点的 x 坐标和 y 坐标、它的第二个节点、第一个节点、最后一个节点以及样条的度数。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|Del  <br/> |xsd：boolean  <br/> |可选  <br/> |指定是否已删除从主控形状继承的行。  <br/> |xsd：boolean 类型的值。  <br/> |
|IX  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |指定行的从 1 开始标识符。 它应不唯一，并且大于同一节中的其他标识符。IX 属性仅用于 Character、Connection、Field、FillGradient、Geometry、Layer、LineGradient、Paragraph、Reviewer、Scratch 和 Tabs 部分。 一行只能有一个 IX 或 N 属性。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|LocalName  <br/> |xsd：string  <br/> |可选  <br/> |指定行的唯一依赖于语言的名称。  <br/> |xsd：string 类型的值。  <br/> |
|N  <br/> |xsd：string  <br/> |可选  <br/> |指定行的唯一与语言无关的名称。N 属性仅用于 User、Property、Actions、Control、Connection、Hyperlink 和 ActionTag 部分。 一行只能有一个 IX 或 N 属性。  <br/> |xsd：string 类型的值。  <br/> |
|T  <br/> |xsd：string  <br/> |可选  <br/> |指定由行表示的几何路径类型，并用于几何可视化。 T 属性仅用于"Geometry"内容。  <br/> |xsd：string 类型的值。  <br/> |
   
## <a name="remarks"></a>备注

此 **Row** 元素的 **T** 属性必须是与 ShapeSheet 行对应的一组有限值之一。 请参考下表以确定此 **Row** 元素所允许 **的 T** 属性的值。 
  
|**值**|**说明**|**详细信息**|
|:-----|:-----|:-----|
|ArcTo  <br/> |包含圆弧的 x 坐标、y 坐标和弓。  <br/> |[ArcTo Row (Geometry Section)](arcto-row-geometry-section.md) <br/> |
|Ellipse  <br/> |包含椭圆中心点和椭圆上两个点的 x 坐标和 y 坐标。  <br/> |[Ellipse Row (Geometry Section)](ellipse-row-geometry-section.md) <br/> |
|EllipticalArcTo  <br/> |包含椭圆弧端点的 x 坐标和 y 坐标、弧形上控制点的 x 坐标和 y 坐标、x 轴与椭圆长轴之间的夹角以及椭圆长短轴之比。  <br/> |[EllipticalArcTo Row (Geometry Section)](ellipticalarcto-row-geometry-section.md) <br/> |
|InfiniteLine  <br/> |包含无限长线上两个点的 x 坐标和 y 坐标。  <br/> |[InfiniteLine Row (Geometry Section)](infiniteline-row-geometry-section.md) |
|LineTo  <br/> |包含直线段终顶点的 x 坐标和 y 坐标。  <br/> |[LineTo Row (Geometry Section)](lineto-row-geometry-section.md) <br/> |
|MoveTo  <br/> |包含形状的第一个顶点的 x 坐标和 y 坐标，或者表示路径中断开处后的第一个顶点的 x 坐标和 y 坐标。  <br/> |[MoveTo Row (Geometry Section)](moveto-row-geometry-section.md) <br/> |
|NURBSTo  <br/> |包含非均匀有理 B 样条 (NURBS) 的 x 坐标和 y 坐标、倒数第二个节点的位置、最后一个权重的位置、第一个节点的位置、第一个权重的位置以及样条的公式。  <br/> |[NURBSTo Row (Geometry Section)](nurbsto-row-geometry-section.md) <br/> |
|PolylineTo  <br/> |包含折线最后一个点的 x 坐标和 y 坐标以及折线公式。  <br/> |[PolylineTo Row (Geometry Section)](polylineto-row-geometry-section.md) <br/> |
|RelCubBezTo  <br/> |包含三次方贝塞尔曲线终点相对于形状的宽度和高度的 x 坐标和 y 坐标、曲线相对形状的宽度和高度的起点的控制点的 x 坐标和 y 坐标，以及曲线相对形状的宽度和高度终点的控制点的 x 坐标和 y 坐标。  <br/> |["Geometry"内容 (RelCubBezTo) ](relcubbezto-row-geometry-section.md) <br/> |
|RelEllipticalArcTo  <br/> |包含椭圆弧终点相对于形状的宽度和高度的 x 坐标和 y 坐标、弧上控制点的 x 坐标和 y 坐标（相对于形状的宽度和高度、从 x 轴到椭圆主轴的角度）以及椭圆主要轴和次要轴之间的比率。  <br/> |[RelEllipticalArcTo "Geometry" (行) ](relellipticalarcto-row-geometry-section.md) <br/> |
|RelLineTo  <br/> |包含直线段的终点相对于形状的宽度和高度的 x 坐标和 y 坐标。  <br/> |[RelLineTo Row (Geometry Section) ](rellineto-row-geometry-section.md) <br/> |
|RelMoveTo  <br/> |包含形状的第一个顶点的 x 坐标和 y 坐标，或者路径中中断后的第一个顶点的 x 坐标和 y 坐标（相对于形状的高度和宽度）。  <br/> |[RelMoveTo Row (Geometry Section) ](relmoveto-row-geometry-section.md) <br/> |
|RelQuadBezTo  <br/> |包含二次方贝塞尔曲线终点相对于形状的宽度和高度的 x 坐标和 y 坐标，以及曲线相对形状的宽度和高度的控制点的 x 坐标和 y 坐标。  <br/> |[RelQuadBezTo Row (Geometry Section) ](relquadbezto-row-geometry-section.md) <br/> |
|SplineKnot  <br/> |包含样条控制点和样条节点的 x 坐标和 y 坐标。  <br/> |[SplineKnot Row (Geometry Section)](splineknot-row-geometry-section.md) <br/> |
|SplineStart  <br/> |包含样条第二个控制点的 x 坐标和 y 坐标、它的第二个节点、第一个节点、最后一个节点以及样条的度数。  <br/> |[SplineStart Row (Geometry Section)](splinestart-row-geometry-section.md) <br/> |
   

