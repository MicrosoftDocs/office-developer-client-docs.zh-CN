---
title: Section 元素 （Sheet_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2e7e5dcc-f667-a08c-caa0-4b81e3126ef9
description: 指定相关的属性的集合。
ms.openlocfilehash: 7cb5e1c30960e69b252abc7af38e021607fd3502
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781234"
---
# <a name="section-element-sheettype-complextype-visio-xml"></a>Section 元素 （Sheet_Type 复杂类型） (Visio XML)

指定相关的属性的集合。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Section_Type](section_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |document.xml、 masters.xml、 主 #.xml、 pages.xml、 页 #.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Section" type="Section_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |[DocumentSheet_Type](documentsheet_type-complextypevisio-xml.md) <br/> |指定绘图的属性。  <br/> |
|[PageSheet](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> |指定与绘图中的页面的属性。  <br/> |
|[PageSheet](pagesheet-element-master_type-complextypevisio-xml.md) <br/> |[Master_Type complexType](master_type-complextypevisio-xml.md) <br/> |指定绘图页主控形状相关联的属性。  <br/> |
|[形状](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[ShapeSheet_Type](shapesheet_type-complextypevisio-xml.md) <br/> |指定与形状关联的属性集合。  <br/> |
|[Sheet](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[Sheet_Type](sheet_type-complextypevisio-xml.md) <br/> |指定样式、 绘图、 绘图页上或形状相关联的属性的集合。  <br/> |
|[样式表](stylesheet-element-stylesheets_type-complextypevisio-xml.md) <br/> |[StyleSheet_Type](stylesheet_type-complextypevisio-xml.md) <br/> |指定样式表。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Cell](http://msdn.microsoft.com/library/70a9d6d6-a4ff-2b0d-febc-789a04a2f5b0%28Office.15%29.aspx) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定单个属性。  <br/> |
|[Row](http://msdn.microsoft.com/library/c978e3eb-b895-8fb7-e2ba-88c50e57b3db%28Office.15%29.aspx) <br/> |[Row_Type](row_type-complextypevisio-xml.md) <br/> |指定**Cell_Type**元素的集合。  <br/> |
   
### <a name="attributes"></a>Attributes

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|Del  <br/> |化  <br/> |可选  <br/> |指定是否已删除继承的集合。 它必须等于 0 或 1。 值为 1 指定集合未和必须被忽略。 值 0 指定属性的集合是有效的形状。 如果**Del**属性不存在，则值为 0。  <br/> |化类型的值。  <br/> |
|IX  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |指定的元素的从零开始的索引。 它必须是唯一的所有**Section_Type**元素包含**Sheet_Type**的相同**N**属性使用。 它必须是大于任何上述**Section_Type**元素的**IX**属性，包含**Sheet_Type**的相同**N**属性。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|N  <br/> |xsd: string  <br/> |必需  <br/> |指定的属性的集合的独立于语言的名称。 它必须是唯一的所有**Section_Type**元素包含**Sheet_Type**元素的除非它等于"几何"。 它必须等于**各节**中下面的副标题。  <br/> |Xsd: string 类型的值。  <br/> |
   
### <a name="remarks"></a>说明

此**部分**元素的**N**属性必须为一组有限的对应于**ShapeSheet**单元格的值之一。 请参阅下表为确定允许此**部分**元素的**N**属性的值。 
  
|**值**|**说明**|**更多信息**|
|:-----|:-----|:-----|
|操作  <br/> |用于公式计算的属性的集合。 它必须具有**ShapeSheet_Type**或**PageSheet_Type**父元素。  <br/> |[Actions Section](actions-section.md) <br/> |
|ActionTag  <br/> |用于仅公式计算的属性的集合。 它必须具有**ShapeSheet_Type**或**PageSheet_Type**父元素。  <br/> |[Action Tag Section](action-tag-section.md) <br/> |
|连接  <br/> |用于仅公式计算的属性的集合。 它必须具有**ShapeSheet_Type**父元素。  <br/> ||
|控件  <br/> |用于仅公式计算的属性的集合。 它必须具有**ShapeSheet_Type**父元素。  <br/> |[Controls Section](controls-section.md) <br/> |
|超链接  <br/> |指定的形状的超链接的相关属性的集合。 它必须具有**ShapeSheet_Type**父元素。  <br/> |[Hyperlinks Section](hyperlinks-section.md) <br/> |
|ShapeData  <br/> |指定的形状数据的相关属性的集合。 它必须具有**ShapeSheet_Type**父元素。  <br/> |[Shape Data Section](shape-data-section.md) <br/> |
|用户  <br/> |用于公式计算的属性的集合。 它必须具有**DocumentSheet_Type**、 **PageSheet_Type**或**ShapeSheet_Type**父元素。  <br/> |[User-defined Cells Section](user-defined-cells-section.md) <br/> |
   
此**部分**元素的**IX**属性必须为一组有限的对应于**ShapeSheet**单元格的值之一。 请参阅下表为确定允许此**部分**元素的**IX**属性的值。 
  
|**值**|**说明**|**更多信息**|
|:-----|:-----|:-----|
|Annotation  <br/> |包含插入到文档页中的注释有关的信息的属性的集合。  <br/> |[Annotation Section](annotation-section.md) <br/> |
|字符  <br/> |相关的属性指定的形状的文本的字符属性的集合。 它必须具有**ShapeSheet_Type**父元素或**StyleSheet_Type**父元素。  <br/> |[Character Section](character-section.md) <br/> |
|连接  <br/> |用于仅公式计算的属性的集合。 它必须具有**ShapeSheet_Type**父元素。  <br/> |[Connection Points Section](connection-points-section.md) <br/> |
|Field  <br/> |指定形状的文本字段的相关属性的集合。 它必须具有**ShapeSheet_Type**父元素。  <br/> |[Text Fields Section](text-fields-section.md) <br/> |
|FillGradient  <br/> |指定形状的填充颜色渐变属性的集合。 它必须具有**ShapeSheet_Type**或**StyleSheet_Type**父元素。  <br/> |[“Fill Gradient”部分](fill-gradient-section.md) <br/> |
|几何图形  <br/> |指定 geometry 可视化的相关属性的集合。 它必须具有**ShapeSheet_Type**父元素。 此元素的第一个**Row_Type**子元素必须类型 MoveTo，RelMoveTo、 椭圆或 InfiniteLine。  <br/> |[Geometry Section](geometry-section.md) <br/> |
|Layers  <br/> |显示在绘图页中定义的所有图层属性的集合。 它必须是**PageSheet_Type**元素的子级。  <br/> |[Layers Section](layers-section.md) <br/> |
|行渐变  <br/> |指定形状的线条颜色渐变的相关属性的集合。 它必须具有**ShapeSheet_Type**或**StyleSheet_Type**父元素。  <br/> |[“Line Gradient”部分](line-gradient-section.md) <br/> |
|Paragraph  <br/> |相关的属性指定的形状的文本的段落属性的集合。 它必须具有**ShapeSheet_Type**父元素或**StyleSheet_Type**父元素。  <br/> |[Paragraph Section](paragraph-section.md) <br/> |
|Reviewer  <br/> |用于公式计算的属性的集合。 它必须具有**DocumentSheet_Type**父元素。  <br/> |[Reviewer Section](reviewer-section.md) <br/> |
|挑战  <br/> |用于公式计算的属性的集合。 它必须具有**DocumentSheet_Type**、 **PageSheet_Type**或**ShapeSheet_Type**父元素。  <br/> |[Scratch Section](scratch-section.md) <br/> |
|选项卡  <br/> |相关的属性指定的形状的文本的选项卡属性的集合。 它必须具有**ShapeSheet_Type**父元素或**StyleSheet_Type**父元素。  <br/> |[Tabs Section](tabs-section.md) <br/> |
   

