---
title: Row 元素 （geometry 内容） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2b273958-1997-7c63-4a61-d231f023a81f
description: 包含列表的线条和弧组成的形状的顶点坐标的行。
ms.openlocfilehash: 1581c87ae34eff4f01054a2340c18f1e55456cfb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581690"
---
# <a name="row-element-geometry-section-visio-xml"></a>Row 元素 （geometry 内容） (Visio XML)

包含列表的线条和弧组成的形状的顶点坐标的行。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[GeometryRow_Type](geometry_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |母版页 #.xml、 页面 #.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Row" type="GeometryRow_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Section](section-element-sheet_type-complextypevisio-xml.md) <br/> |[Section_Type](section_type-complextypevisio-xml.md) <br/> |包含列表的线条和弧组成的形状的顶点坐标的行。  <br/> |
   
### <a name="child-elements"></a>子元素

> [!NOTE]
> 单元格元素是此元素的唯一子级。 根据此元素的"T"属性，将不同单元格元素的含义。 下表中 parathetical 文本元素名称中的对应于主题应用到"T"值。 
  
|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Cell 元素（“ArcTo”行）](arcto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含圆弧的 x 坐标、y 坐标和弓。  <br/> |
|[Cell 元素（“Ellipse”行）](ellipse-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含椭圆中心点和椭圆上两个点的 x 坐标和 y 坐标。  <br/> |
|[Cell 元素（“EllipticalArcTo”行）](ellipticalarcto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含椭圆弧端点的 x 坐标和 y 坐标、弧形上控制点的 x 坐标和 y 坐标、x 轴与椭圆长轴之间的夹角以及椭圆长短轴之比。  <br/> |
|[Cell 元素（“InfiniteLine”行）](infiniteline-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含无限长线上两个点的 x 坐标和 y 坐标。  <br/> |
|[Cell 元素（“LineTo”行）](lineto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含直线段终顶点的 x 坐标和 y 坐标。  <br/> |
|[Cell 元素（“MoveTo”行）](moveto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含形状的第一个顶点的 x 坐标和 y 坐标，或者表示路径中断开处后的第一个顶点的 x 坐标和 y 坐标。  <br/> |
|[Cell 元素（“NURBSTo”行）](nurbsto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含非均匀有理 B 样条 (NURBS) 的 x 坐标和 y 坐标、倒数第二个节点的位置、最后一个权重的位置、第一个节点的位置、第一个权重的位置以及样条的公式。  <br/> |
|[Cell 元素（“PolyLineTo”行）](polylineto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含折线最后一个点的 x 坐标和 y 坐标以及折线公式。  <br/> |
|[Cell 元素（“RelCubBezTo”行）](relcubbezto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含 x 坐标和 y 坐标的相对于形状的宽度和高度的立方贝赛尔曲线的终结点、 曲线相对于形状的宽度和高度的开头和控件 x 和 y 坐标的控制点 x 和 y 坐标曲线相对于形状的宽度和高度的结束点。  <br/> |
|[Cell 元素（“RelQuadBezTo”行）](relquadbezto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含 x 坐标和 y 坐标的相对于形状的宽度和高度二次贝塞尔曲线的终结点和曲线相对于形状的宽度和高度的控制点 x 和 y 坐标。  <br/> |
|[Cell 元素（“RelEllipticalArcTo”行）](relellipticalarcto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含 x 坐标和 y 坐标的椭圆弧的终点相对于形状的宽度和高度的、 x 坐标和 y 坐标的相对于形状的宽度和高度，从 x 轴的角度椭圆的长轴和比率弧形上的控件点椭圆的主要和次要刻度坐标轴。  <br/> |
|[Cell 元素（“RelLineTo”行）](rellineto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含 x-和相对于形状的宽度和高度直线段终顶点的 y 坐标。  <br/> |
|[Cell 元素（“RelMoveTo”行）](relmoveto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含后的高度和宽度的形状的相对路径中断开的 x 坐标和 y 坐标形状的第一个顶点的 x 坐标和 y 坐标的第一个顶点。  <br/> |
|[Cell 元素（“RelQuadBezTo”行）](relquadbezto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含 x 坐标和 y 坐标的相对于形状的宽度和高度二次贝塞尔曲线的终结点和曲线相对于形状的宽度和高度的控制点 x 和 y 坐标。  <br/> |
|[Cell 元素（“SplineKnot”行）](splineknot-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含样条控制点和样条节点的 x 坐标和 y 坐标。  <br/> |
|[Cell 元素（“SplineStart”行）](splinestart-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |包含样条第二个控制点的 x 坐标和 y 坐标、它的第二个节点、第一个节点、最后一个节点以及样条的度数。  <br/> |
   
### <a name="attributes"></a>Attributes

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|Del  <br/> |化  <br/> |可选  <br/> |指定是否已删除的行，否则将继承主控形状。  <br/> |化类型的值。  <br/> |
|IX  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |指定行的基于一的标识符。 该文件应该是唯一且大于同一节中的其他标识符。IX 属性只用于字符、 连接、 字段、 FillGradient、 geometry、 层、 LineGradient、 段落、 审核、 挑战和选项卡部分。 行只能有一个 IX 或 N 属性。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|LocalName  <br/> |xsd: string  <br/> |可选  <br/> |指定行的唯一依赖于语言的名称。  <br/> |Xsd: string 类型的值。  <br/> |
|N  <br/> |xsd: string  <br/> |可选  <br/> |指定行的唯一的独立于语言的名称。N 属性仅用于用户、 属性、 操作、 控件、 连接、 超链接和 ActionTag 部分。 行只能有一个 IX 或 N 属性。  <br/> |Xsd: string 类型的值。  <br/> |
|T  <br/> |xsd: string  <br/> |可选  <br/> |指定由行和 geometry 可视化中使用的几何路径类型。 T 属性只用于 geometry 内容。  <br/> |Xsd: string 类型的值。  <br/> |
   
## <a name="remarks"></a>注解

此**Row**元素的**T**属性必须为一组有限的 ShapeSheet 行对应的值之一。 请参阅下表为确定允许此**行**元素的**T**属性的值。 
  
|**值**|**说明**|**更多信息**|
|:-----|:-----|:-----|
|ArcTo  <br/> |包含圆弧的 x 坐标、y 坐标和弓。  <br/> |[ArcTo Row (Geometry Section)](arcto-row-geometry-section.md) <br/> |
|椭圆  <br/> |包含椭圆中心点和椭圆上两个点的 x 坐标和 y 坐标。  <br/> |[Ellipse Row (Geometry Section)](ellipse-row-geometry-section.md) <br/> |
|EllipticalArcTo  <br/> |包含椭圆弧端点的 x 坐标和 y 坐标、弧形上控制点的 x 坐标和 y 坐标、x 轴与椭圆长轴之间的夹角以及椭圆长短轴之比。  <br/> |[EllipticalArcTo Row (Geometry Section)](ellipticalarcto-row-geometry-section.md) <br/> |
|InfiniteLine  <br/> |包含无限长线上两个点的 x 坐标和 y 坐标。  <br/> |[InfiniteLine Row (Geometry Section)](infiniteline-row-geometry-section.md) |
|LineTo  <br/> |包含直线段终顶点的 x 坐标和 y 坐标。  <br/> |[LineTo Row (Geometry Section)](lineto-row-geometry-section.md) <br/> |
|MoveTo  <br/> |包含形状的第一个顶点的 x 坐标和 y 坐标，或者表示路径中断开处后的第一个顶点的 x 坐标和 y 坐标。  <br/> |[MoveTo Row (Geometry Section)](moveto-row-geometry-section.md) <br/> |
|NURBSTo  <br/> |包含非均匀有理 B 样条 (NURBS) 的 x 坐标和 y 坐标、倒数第二个节点的位置、最后一个权重的位置、第一个节点的位置、第一个权重的位置以及样条的公式。  <br/> |[NURBSTo Row (Geometry Section)](nurbsto-row-geometry-section.md) <br/> |
|PolylineTo  <br/> |包含折线最后一个点的 x 坐标和 y 坐标以及折线公式。  <br/> |[PolylineTo Row (Geometry Section)](polylineto-row-geometry-section.md) <br/> |
|RelCubBezTo  <br/> |包含 x 坐标和 y 坐标的相对于形状的宽度和高度的立方贝赛尔曲线的终结点、 曲线相对于形状的宽度和高度的开头和控件 x 和 y 坐标的控制点 x 和 y 坐标曲线相对于形状的宽度和高度的结束点。  <br/> |[RelCubBezTo 行（“Geometry”部分）](relcubbezto-row-geometry-section.md) <br/> |
|RelEllipticalArcTo  <br/> |包含 x 坐标和 y 坐标的椭圆弧的终点相对于形状的宽度和高度的、 x 坐标和 y 坐标的相对于形状的宽度和高度，从 x 轴的角度椭圆的长轴和比率弧形上的控件点椭圆的主要和次要刻度坐标轴。  <br/> |[RelEllipticalArcTo 行（“Geometry”部分）](relellipticalarcto-row-geometry-section.md) <br/> |
|RelLineTo  <br/> |包含 x-和相对于形状的宽度和高度直线段终顶点的 y 坐标。  <br/> |[RelLineTo 行（“Geometry”部分）](rellineto-row-geometry-section.md) <br/> |
|RelMoveTo  <br/> |包含后的高度和宽度的形状的相对路径中断开的 x 坐标和 y 坐标形状的第一个顶点的 x 坐标和 y 坐标的第一个顶点。  <br/> |[RelMoveTo 行（“Geometry”部分）](relmoveto-row-geometry-section.md) <br/> |
|RelQuadBezTo  <br/> |包含 x 坐标和 y 坐标的相对于形状的宽度和高度二次贝塞尔曲线的终结点和曲线相对于形状的宽度和高度的控制点 x 和 y 坐标。  <br/> |[RelQuadBezTo 行（“Geometry”部分）](relquadbezto-row-geometry-section.md) <br/> |
|SplineKnot  <br/> |包含样条控制点和样条节点的 x 坐标和 y 坐标。  <br/> |[SplineKnot Row (Geometry Section)](splineknot-row-geometry-section.md) <br/> |
|SplineStart  <br/> |包含样条第二个控制点的 x 坐标和 y 坐标、它的第二个节点、第一个节点、最后一个节点以及样条的度数。  <br/> |[SplineStart Row (Geometry Section)](splinestart-row-geometry-section.md) <br/> |
   

