---
title: Section 元素 (Sheet_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2e7e5dcc-f667-a08c-caa0-4b81e3126ef9
description: 指定相关属性的集合。
ms.openlocfilehash: e20d076d4e1958cce29554d728b64385c2f8adef
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326080"
---
# <a name="section-element-sheettype-complextype-visio-xml"></a>Section 元素 (Sheet_Type 复杂类型) ("Visio XML")

指定相关属性的集合。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Section_Type](section_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |document .xml、.master、master # .xml、pages、.xml 和第 .xml 页  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Section" type="Section_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |[DocumentSheet_Type](documentsheet_type-complextypevisio-xml.md) <br/> |指定绘图的属性。  <br/> |
|[PageSheet](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> |指定绘图中页面的属性。  <br/> |
|[PageSheet](pagesheet-element-master_type-complextypevisio-xml.md) <br/> |[Master_Type complexType](master_type-complextypevisio-xml.md) <br/> |指定与主控形状相关联的绘图页的属性。  <br/> |
|[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[ShapeSheet_Type](shapesheet_type-complextypevisio-xml.md) <br/> |指定与形状关联的属性的集合。  <br/> |
|[Sheet](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[Sheet_Type](sheet_type-complextypevisio-xml.md) <br/> |指定与样式、绘图、绘图页或形状相关联的属性的集合。  <br/> |
|[单](stylesheet-element-stylesheets_type-complextypevisio-xml.md) <br/> |[StyleSheet_Type](stylesheet_type-complextypevisio-xml.md) <br/> |指定样式表。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Cell](cell-elementvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定一个属性。  <br/> |
|[行](https://msdn.microsoft.com/library/c978e3eb-b895-8fb7-e2ba-88c50e57b3db%28Office.15%29.aspx) <br/> |[Row_Type](row_type-complextypevisio-xml.md) <br/> |指定**Cell_Type**元素的集合。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|键  <br/> |xsd: boolean  <br/> |可选  <br/> |指定是否已删除本来要继承的集合。 它必须等于0或1。 值为1指定未使用该集合, 必须将其忽略。 值0指定属性的集合对形状有效。 如果**Del**属性不存在, 则值为0。  <br/> |xsd: boolean 类型的值。  <br/> |
|IX  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |指定元素的从零开始的索引。 它必须在包含**Sheet_Type**的具有相同**N**个属性的所有**Section_Type**元素之间是唯一的。 它必须大于任何前面的**Section_Type**元素的**IX**属性, 其中包含**Sheet_Type**的同一个**N**属性。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|N  <br/> |xsd: string  <br/> |必需  <br/> |指定属性集合的独立于语言的名称。 它必须在包含**Sheet_Type**元素的所有**Section_Type**元素之间是唯一的, 除非它等于 "Geometry"。 它必须等于**节**中的副标题。  <br/> |xsd: string 类型的值。  <br/> |
   
### <a name="remarks"></a>注解

此**节**元素的**N**属性必须是与**ShapeSheet**单元格相对应的一组有限的值之一。 请参阅下表, 以确定此**节**元素允许的**N**属性的值。 
  
|**Value**|**说明**|**详细信息**|
|:-----|:-----|:-----|
|操作  <br/> |用于计算公式的属性的集合。 它必须具有**ShapeSheet_Type**或**PageSheet_Type**父元素。  <br/> |[Actions Section](actions-section.md) <br/> |
|ActionTag  <br/> |仅用于计算公式的属性的集合。 它必须具有**ShapeSheet_Type**或**PageSheet_Type**父元素。  <br/> |[Action Tag Section](action-tag-section.md) <br/> |
|Connections  <br/> |仅用于计算公式的属性的集合。 它必须具有一个**ShapeSheet_Type**父元素。  <br/> ||
|控件  <br/> |仅用于计算公式的属性的集合。 它必须具有一个**ShapeSheet_Type**父元素。  <br/> |[Controls Section](controls-section.md) <br/> |
|Hyperlink  <br/> |指定形状超链接的相关属性的集合。 它必须具有一个**ShapeSheet_Type**父元素。  <br/> |[Hyperlinks Section](hyperlinks-section.md) <br/> |
|ShapeData  <br/> |指定形状数据的相关属性的集合。 它必须具有一个**ShapeSheet_Type**父元素。  <br/> |[Shape Data Section](shape-data-section.md) <br/> |
|User  <br/> |用于计算公式的属性的集合。 它必须具有**DocumentSheet_Type**、 **PageSheet_Type**或**ShapeSheet_Type**父元素。  <br/> |[User-defined Cells Section](user-defined-cells-section.md) <br/> |
   
此**节**元素的**IX**属性必须是与**ShapeSheet**单元格相对应的一组有限的值之一。 请参阅下表, 以确定此**节**元素允许的**IX**属性的值。 
  
|**Value**|**说明**|**详细信息**|
|:-----|:-----|:-----|
|Annotation  <br/> |包含有关插入到文档页面中的注释的信息的属性的集合。  <br/> |[Annotation Section](annotation-section.md) <br/> |
|字符  <br/> |指定形状的文本的字符属性的相关属性的集合。 它必须具有**ShapeSheet_Type**父元素或**StyleSheet_Type**父元素。  <br/> |[Character Section](character-section.md) <br/> |
|Connections  <br/> |仅用于计算公式的属性的集合。 它必须具有一个**ShapeSheet_Type**父元素。  <br/> |[Connection Points Section](connection-points-section.md) <br/> |
|Field  <br/> |指定形状的文本字段的相关属性的集合。 它必须具有一个**ShapeSheet_Type**父元素。  <br/> |[Text Fields Section](text-fields-section.md) <br/> |
|FillGradient  <br/> |指定形状的填充颜色渐变的属性的集合。 它必须具有**ShapeSheet_Type**或**StyleSheet_Type**父元素。  <br/> |["填充渐变" 部分](fill-gradient-section.md) <br/> |
|几何  <br/> |指定几何图形可视化效果的相关属性的集合。 它必须具有一个**ShapeSheet_Type**父元素。 此元素的第一个**Row_Type**子元素的类型必须为 MoveTo、RelMoveTo、椭圆形或 InfiniteLine。  <br/> |[Geometry Section](geometry-section.md) <br/> |
|Layers  <br/> |显示在绘图页上定义的所有图层的属性的集合。 它必须是**PageSheet_Type**元素的子级。  <br/> |[Layers Section](layers-section.md) <br/> |
|线条渐变  <br/> |指定形状的线条颜色渐变的相关属性的集合。 它必须具有**ShapeSheet_Type**或**StyleSheet_Type**父元素。  <br/> |["线条渐变" 部分](line-gradient-section.md) <br/> |
|Paragraph  <br/> |指定形状文本的段落属性的相关属性的集合。 它必须具有**ShapeSheet_Type**父元素或**StyleSheet_Type**父元素。  <br/> |[Paragraph Section](paragraph-section.md) <br/> |
|Reviewer  <br/> |用于计算公式的属性的集合。 它必须具有一个**DocumentSheet_Type**父元素。  <br/> |[Reviewer Section](reviewer-section.md) <br/> |
|介质  <br/> |用于计算公式的属性的集合。 它必须具有**DocumentSheet_Type**、 **PageSheet_Type**或**ShapeSheet_Type**父元素。  <br/> |[Scratch Section](scratch-section.md) <br/> |
|选项卡  <br/> |指定形状的文本的选项卡属性的相关属性的集合。 它必须具有**ShapeSheet_Type**父元素或**StyleSheet_Type**父元素。  <br/> |[Tabs Section](tabs-section.md) <br/> |
   

