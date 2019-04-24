---
title: Row 元素 ("Geometry" 内容) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2b273958-1997-7c63-4a61-d231f023a81f
description: 包含列出构成形状的线条和弧形的顶点坐标的行。
ms.openlocfilehash: 53482b0db3f2deb3c8e2ba30f41be67f0d9e27a0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358550"
---
# <a name="row-element-geometry-section-visio-xml"></a>Row 元素 ("Geometry" 内容) ("Visio XML")

包含列出构成形状的线条和弧形的顶点坐标的行。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[GeometryRow_Type](geometry_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |master # .xml、第 .xml 页  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Row" type="GeometryRow_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Section](section-element-sheet_type-complextypevisio-xml.md) <br/> |[Section_Type](section_type-complextypevisio-xml.md) <br/> |包含列出构成形状的线条和弧形的顶点坐标的行。  <br/> |
   
### <a name="child-elements"></a>子元素

> [!NOTE]
> Cell 元素是此元素的唯一子元素。 根据此元素的 "T" 属性, Cell 元素的意义各不相同。 在下表中, 元素名称中的 parathetical 文本对应于应用该主题的 "T" 值。 
  
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
|[Cell 元素（“RelCubBezTo”行）](relcubbezto-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含相对于形状的宽度和高度的三次方贝塞尔曲线端点的 x 坐标和 y 坐标、曲线相对形状的宽度和高度的起点的 x 轴坐标和 y 轴坐标以及该控件的 x 坐标和 y 坐标曲线相对形状的宽度和高度的结束点。  <br/> |
|[Cell 元素（“RelQuadBezTo”行）](relquadbezto-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含相对于形状的宽度和高度以及曲线相对形状的宽度和高度的控制点的 x 坐标和 y 坐标的二次贝塞尔曲线端点的 x 坐标和 y 坐标。  <br/> |
|[Cell 元素（“RelEllipticalArcTo”行）](relellipticalarcto-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含椭圆弧的终点相对于形状的宽度和高度的 x 坐标和 y 坐标、弧形上的控制点相对于形状的宽度和高度的 x 坐标和 y 坐标、从 x 轴到椭圆主轴的角度、与之间的比率椭圆的主要和次要轴。  <br/> |
|[Cell 元素（“RelLineTo”行）](rellineto-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含相对于形状的宽度和高度的直线段终顶点的 x 坐标和 y 坐标。  <br/> |
|[Cell 元素（“RelMoveTo”行）](relmoveto-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含形状的第一个顶点的 x 坐标和 y 坐标, 或路径中断开点后的第一个顶点的 x 坐标和 y 坐标 (相对于形状的高度和宽度)。  <br/> |
|[Cell 元素（“RelQuadBezTo”行）](relquadbezto-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含相对于形状的宽度和高度以及曲线相对形状的宽度和高度的控制点的 x 坐标和 y 坐标的二次贝塞尔曲线端点的 x 坐标和 y 坐标。  <br/> |
|[Cell 元素（“SplineKnot”行）](splineknot-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含样条控制点和样条节点的 x 坐标和 y 坐标。  <br/> |
|[Cell 元素（“SplineStart”行）](splinestart-row-geometry-section.md) <br/> |[Cell_Type](https://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含样条第二个控制点的 x 坐标和 y 坐标、它的第二个节点、第一个节点、最后一个节点以及样条的度数。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|键  <br/> |xsd: boolean  <br/> |可选  <br/> |指定是否已删除要从主控形状继承的行。  <br/> |xsd: boolean 类型的值。  <br/> |
|IX  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |指定行的从1开始的标识符。 它应是唯一, 并且大于同一节中的其他标识符。IX 属性仅用于字符、Connection、Field、FillGradient、Geometry、Layer、LineGradient、段落、审阅者、草稿和选项卡部分。 行只能具有 IX 或 N 属性中的一个。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|LocalName  <br/> |xsd: string  <br/> |可选  <br/> |指定行的与语言相关的唯一名称。  <br/> |xsd: string 类型的值。  <br/> |
|N  <br/> |xsd: string  <br/> |可选  <br/> |指定行的与语言无关的唯一名称。N 属性仅用于用户、属性、操作、控制、Connection、Hyperlink 和 ActionTag 节。 行只能具有 IX 或 N 属性中的一个。  <br/> |xsd: string 类型的值。  <br/> |
|T  <br/> |xsd: string  <br/> |可选  <br/> |指定由行表示并在几何图形可视化中使用的几何路径的类型。 T 属性仅用于 "Geometry" 部分。  <br/> |xsd: string 类型的值。  <br/> |
   
## <a name="remarks"></a>注解

**此行**元素的**T**属性必须是与 ShapeSheet 行相对应的一组有限的值之一。 请参阅下表, 以确定此**Row**元素允许的**T**属性的值。 
  
|**Value**|**说明**|**详细信息**|
|:-----|:-----|:-----|
|ArcTo  <br/> |包含圆弧的 x 坐标、y 坐标和弓。  <br/> |[ArcTo Row (Geometry Section)](arcto-row-geometry-section.md) <br/> |
|椭圆  <br/> |包含椭圆中心点和椭圆上两个点的 x 坐标和 y 坐标。  <br/> |[Ellipse Row (Geometry Section)](ellipse-row-geometry-section.md) <br/> |
|EllipticalArcTo  <br/> |包含椭圆弧端点的 x 坐标和 y 坐标、弧形上控制点的 x 坐标和 y 坐标、x 轴与椭圆长轴之间的夹角以及椭圆长短轴之比。  <br/> |[EllipticalArcTo Row (Geometry Section)](ellipticalarcto-row-geometry-section.md) <br/> |
|InfiniteLine  <br/> |包含无限长线上两个点的 x 坐标和 y 坐标。  <br/> |[InfiniteLine Row (Geometry Section)](infiniteline-row-geometry-section.md) |
|LineTo  <br/> |包含直线段终顶点的 x 坐标和 y 坐标。  <br/> |[LineTo Row (Geometry Section)](lineto-row-geometry-section.md) <br/> |
|MoveTo  <br/> |包含形状的第一个顶点的 x 坐标和 y 坐标，或者表示路径中断开处后的第一个顶点的 x 坐标和 y 坐标。  <br/> |[MoveTo Row (Geometry Section)](moveto-row-geometry-section.md) <br/> |
|NURBSTo  <br/> |包含非均匀有理 B 样条 (NURBS) 的 x 坐标和 y 坐标、倒数第二个节点的位置、最后一个权重的位置、第一个节点的位置、第一个权重的位置以及样条的公式。  <br/> |[NURBSTo Row (Geometry Section)](nurbsto-row-geometry-section.md) <br/> |
|PolylineTo  <br/> |包含折线最后一个点的 x 坐标和 y 坐标以及折线公式。  <br/> |[PolylineTo Row (Geometry Section)](polylineto-row-geometry-section.md) <br/> |
|RelCubBezTo  <br/> |包含相对于形状的宽度和高度的三次方贝塞尔曲线端点的 x 坐标和 y 坐标、曲线相对形状的宽度和高度的起点的 x 轴坐标和 y 轴坐标以及该控件的 x 坐标和 y 坐标曲线相对形状的宽度和高度的结束点。  <br/> |[RelCubBezTo 行 ("Geometry" 部分)](relcubbezto-row-geometry-section.md) <br/> |
|RelEllipticalArcTo  <br/> |包含椭圆弧的终点相对于形状的宽度和高度的 x 坐标和 y 坐标、弧形上的控制点相对于形状的宽度和高度的 x 坐标和 y 坐标、从 x 轴到椭圆主轴的角度、与之间的比率椭圆的主要和次要轴。  <br/> |[RelEllipticalArcTo 行 ("Geometry" 部分)](relellipticalarcto-row-geometry-section.md) <br/> |
|RelLineTo  <br/> |包含相对于形状的宽度和高度的直线段终顶点的 x 坐标和 y 坐标。  <br/> |[RelLineTo 行 ("Geometry" 部分)](rellineto-row-geometry-section.md) <br/> |
|RelMoveTo  <br/> |包含形状的第一个顶点的 x 坐标和 y 坐标, 或路径中断开点后的第一个顶点的 x 坐标和 y 坐标 (相对于形状的高度和宽度)。  <br/> |[RelMoveTo 行 ("Geometry" 部分)](relmoveto-row-geometry-section.md) <br/> |
|RelQuadBezTo  <br/> |包含相对于形状的宽度和高度以及曲线相对形状的宽度和高度的控制点的 x 坐标和 y 坐标的二次贝塞尔曲线端点的 x 坐标和 y 坐标。  <br/> |[RelQuadBezTo 行 ("Geometry" 部分)](relquadbezto-row-geometry-section.md) <br/> |
|SplineKnot  <br/> |包含样条控制点和样条节点的 x 坐标和 y 坐标。  <br/> |[SplineKnot Row (Geometry Section)](splineknot-row-geometry-section.md) <br/> |
|SplineStart  <br/> |包含样条第二个控制点的 x 坐标和 y 坐标、它的第二个节点、第一个节点、最后一个节点以及样条的度数。  <br/> |[SplineStart Row (Geometry Section)](splinestart-row-geometry-section.md) <br/> |
   

