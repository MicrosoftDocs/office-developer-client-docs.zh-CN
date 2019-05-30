---
title: Cell 元素 ("Character" 内容) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6b452591-cf0c-9e1c-c203-e9cf608d3cc3
description: 指定形状的文本运行的格式属性, 如字体、颜色、样式、大小写、相对于基线的位置或磅值。
ms.openlocfilehash: a7d67aa3c53f3a4c673151afc991202904f0557b
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540082"
---
# <a name="cell-element-character-section-visio-xml"></a>Cell 元素 ("Character" 内容) (Visio XML)

指定形状的文本运行的格式属性, 如字体、颜色、样式、大小写、相对于基线的位置或磅值。
  
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
|[Row 元素 ("字符" 部分)](row-element-character-sectionvisio-xml.md) <br/> |[CharacterRow_Type](characterrow_type-complextypevisio-xml.md) <br/> |指定形状的文本运行的格式属性, 如字体、颜色、样式、大小写、相对于基线的位置或磅值。  <br/> |
   
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
|AsianFont  <br/> |包含用于设置包含亚洲字符的文本运行的格式的字体的枚举。  <br/> |[AsianFont Cell (Character Section)](asianfont-cell-character-section.md) <br/> |
|情况  <br/> |确定形状的文本运行的大小写。  <br/> |[Case Cell (Character Section)](case-cell-character-section.md) <br/> |
|颜色  <br/> |确定用于形状的文本运行的颜色。  <br/> |[Color Cell (Character Section)](color-cell-character-section.md) <br/> |
|ColorTrans  <br/> |确定图层或形状的文本运行颜色的透明度, 从 0 (完全不透明) 到 1 (完全透明)。  <br/> |无。  <br/> |
|ComplexScriptFont  <br/> |包含用于设置由复杂脚本字符组成的文本运行的格式的字体编号。  <br/> |[ComplexScriptFont Cell (Character Section)](complexscriptfont-cell-character-section.md) <br/> |
|ComplexScriptSize  <br/> |用于设置由复杂脚本字符组成的文本运行的字体的大小。  <br/> |[ComplexScriptSize Cell (Character Section)](complexscriptsize-cell-character-section.md) <br/> |
|DblUnderline  <br/> |确定文本区域的下面是否有双下划线。  <br/> |[DoubleULine Cell (Character Section)](doubleuline-cell-character-section.md) <br/> |
|DoubleStrikethrough  <br/> |确定是否将文本局部格式化为双删除线。  <br/> |[DoubleStrikethrough Cell (Character Section)](doublestrikethrough-cell-character-section.md) <br/> |
|字体  <br/> |表示用于设置文本运行格式的字体的编号。  <br/> |[Font Cell (Character Section)](font-cell-character-section.md) <br/> |
|FontScale  <br/> |指定字体宽度。  <br/> |无。  <br/> |
|LangID  <br/> |指示输入文本所使用的语言。  <br/> |[LangID Cell (Character Section)](langid-cell-character-section.md) <br/> |
|Letterspace  <br/> |指定两个或多个字符之间的间距量。 空间量可以二十分之一磅为增量增加或减少。  <br/> |无。  <br/> |
|线  <br/> |确定文本是否在其上方有一条线。  <br/> |[Overline Cell (Character Section)](overline-cell-character-section.md) <br/> |
|不仅  <br/> |确定形状的文本局部相对于基线的位置。  <br/> |[Pos Cell (Character Section)](pos-cell-character-section.md) <br/> |
|大小  <br/> |确定形状的文本块中的文本运行的大小。  <br/> |[Size Cell (Character Section)](size-cell-character-section.md) <br/> |
|Strikethru  <br/> |确定是否将文本局部的格式设置为删除线。  <br/> |[Strikethru Cell (Character Section)](strikethru-cell-character-section.md) <br/> |
|Style  <br/> |显示应用于形状的文本块中的文本运行区域的字符格式。  <br/> |[Style Cell (Character Section)](style-cell-character-section.md) <br/> |
   

