---
title: Cell 元素 ("段落" 部分) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: de0d3aac-1a0f-1bdf-da94-e6699a55d08e
description: 指定形状的文本的段落格式属性, 例如段落的缩进、行间距、项目符号或水平对齐方式。
ms.openlocfilehash: fbb837b96d40f412ddefdf1fac9da0d31a709e39
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539479"
---
# <a name="cell-element-paragraph-section-visio-xml"></a>Cell 元素 ("段落" 部分) (Visio XML)

指定形状的文本的段落格式属性, 例如段落的缩进、行间距、项目符号或水平对齐方式。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |document .xml、master # .xml、第 .xml 页  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Row 元素 ("段落" 部分)](row-element-paragraph-sectionvisio-xml.md) <br/> |[ParagraphRow_Type](paragraphrow_type-complextypevisio-xml.md) <br/> |指定形状的文本的段落格式属性, 例如段落的缩进、行间距、项目符号或水平对齐方式。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[RefBy](refby-element-cell_type-complextypevisio-xml.md) <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |指定对绘图页的引用。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|E  <br/> |xsd: string  <br/> |可选  <br/> |指示公式的计算结果为错误。 **E**的值是当前值 (一条错误消息字符串);**V**属性的值是最后一个有效的值。  <br/> |错误消息字符串。  <br/> |
|F  <br/> |xsd: string  <br/> |可选  <br/> | 代表元素的公式。 此属性可以包含以下字符串之一:  <br/>  "(某些公式)" 如果该公式在本地存在  <br/>  `No Formula`如果公式为本地删除或被阻止  <br/>  `Inh`如果公式是继承的。  <br/> |一个公式。  <br/> |
|N  <br/> |xsd: string  <br/> |必需  <br/> |代表 ShapeSheet 单元格的名称。  <br/> |ShapeSheet 单元格的名称。  <br/> 请参阅下面的 "备注" 部分。  <br/> |
|U  <br/> |xsd: string  <br/> |可选  <br/> |表示一个度量单位, 默认值为 DL。  <br/> |单元格的单位。  <br/> |
|部分  <br/> |xsd: string  <br/> |可选  <br/> |表示单元格的值。  <br/> |ShapeSheet 单元格的值。  <br/> |
   
## <a name="remarks"></a>备注

此**单元格**元素的**N**属性必须是与 ShapeSheet 单元格相对应的一组有限的值之一。 请参阅下表, 以确定此**单元格**元素允许的**N**属性的值。 
  
|**值**|**说明**|**详细信息**|
|:-----|:-----|:-----|
|项目符号  <br/> |确定项目符号的样式。  <br/> |[Bullet Cell (Paragraph Section)](bullet-cell-paragraph-section.md) <br/> |
|BulletFont  <br/> |表示当指定了自定义项目符号字符串并且 Bullet 单元格中的值不为零时，用于设置文字格式的字体编号。  <br/> |[BulletFont Cell (Paragraph Section)](bulletfont-cell-paragraph-section.md) <br/> |
|BulletFontSize  <br/> |指定项目符号的大小。  <br/> |[BulletSize Cell (Paragraph Section)](bulletsize-cell-paragraph-section.md) <br/> |
|BulletStr  <br/> |允许您创建自定义的项目符号样式。  <br/> |[BulletString Cell (Paragraph Section)](bulletstring-cell-paragraph-section.md) <br/> |
|Flags  <br/> |指示文本方向是从左到右还是从右到左。  <br/> |[Flags Cell (Paragraph Section)](flags-cell-paragraph-section.md) <br/> |
|HorzAlign  <br/> |确定形状的文本块中文本的水平对齐方式。  <br/> |[HAlign Cell (Paragraph Section)](halign-cell-paragraph-section.md) <br/> |
|IndFirst  <br/> |代表形状的文本块中每个段落的首行自该段落的左缩进始缩进的距离。此值与绘图比例无关。即使绘图比例进行调整，首行缩进仍保持不变。  <br/> |[IndFirst Cell (Paragraph Section)](indfirst-cell-paragraph-section.md) <br/> |
|IndLeft  <br/> |代表段落中所有文本行自该文本块的左边距始缩进的距离。此值与绘图比例无关。即使绘图比例进行调整，左缩进仍保持不变。  <br/> |[IndLeft Cell (Paragraph Section)](indleft-cell-paragraph-section.md) <br/> |
|IndRight  <br/> |代表段落中所有文本行自该文本块的右边距始缩进的距离。此值与绘图比例无关。即使绘图比例进行调整，右缩进仍保持不变。  <br/> |[IndRight Cell (Paragraph Section)](indright-cell-paragraph-section.md) <br/> |
|SpAfter  <br/> |确定除了在 SpLine 单元格（如果段落为文本块的最后一段，则由 BottomMargin 单元格指定）中指定的任何空间量外还需要在形状的文本块中每个段落后插入的空间量。  <br/> |[SpAfter Cell (Paragraph Section)](spafter-cell-paragraph-section.md) <br/> |
|SpBefore  <br/> |确定除了在 SpLine 单元格（如果段落为文本块的第一个段落，则由 TopMargin 单元格指定）中指定的任何空间量外还需要在形状的文本块中每个段落前插入的空间量。  <br/> |[SpBefore Cell (Paragraph Section)](spbefore-cell-paragraph-section.md) <br/> |
|主  <br/> |确定一行文本和下一行文本之间的距离，用百分比表示，其中 100% 是文本行的高度。  <br/> |[SpLine Cell (Paragraph Section)](spline-cell-paragraph-section.md) <br/> |
|TextPosAfterBullet  <br/> |表示段落的第一行和项目符号之间的距离。  <br/> |[TextPosAfterBullet Cell (Paragraph Section)](textposafterbullet-cell-paragraph-section.md) <br/> |
   

