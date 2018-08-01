---
title: 单元格 （Character 内容） (Visio XML) 元素
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6b452591-cf0c-9e1c-c203-e9cf608d3cc3
description: 指定形状的文本运行格式属性，如字体、 颜色样式、 case、 位置相对于基线，或磅值。
ms.openlocfilehash: 0d0725ec6ff19104d95780dcfbb3fff9715cbe92
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779821"
---
# <a name="cell-element-character-section-visio-xml"></a>单元格 （Character 内容） (Visio XML) 元素

指定形状的文本运行格式属性，如字体、 颜色样式、 case、 位置相对于基线，或磅值。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |document.xml，母版页 #.xml、 页面 #.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Row 元素（“Character”部分）](row-element-character-sectionvisio-xml.md) <br/> |[CharacterRow_Type](characterrow_type-complextypevisio-xml.md) <br/> |指定形状的文本运行格式属性，如字体、 颜色样式、 case、 位置相对于基线，或磅值。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[RefBy](refby-element-cell_type-complextypevisio-xml.md) <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |指定在绘图页上的引用。  <br/> |
   
### <a name="attributes"></a>Attributes

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|E  <br/> |xsd: string  <br/> |可选  <br/> |指示该公式计算为错误。 **E**的值是当前值 （错误消息字符串）;**V**属性的值是最后一个有效的值。  <br/> |错误消息字符串。  <br/> |
|F  <br/> |xsd: string  <br/> |可选  <br/> | 代表元素的公式。 此属性可以包含以下字符串之一：  <br/>  （某些公式） 如果公式本地存在  <br/>  `No Formula`如果本地删除或阻止公式  <br/>  `Inh`如果继承的公式。  <br/> |公式。  <br/> |
|N  <br/> |xsd: string  <br/> |必需  <br/> |表示的 ShapeSheet 单元格的名称。  <br/> |ShapeSheet 单元格的名称。  <br/> 请参阅下面的备注部分。  <br/> |
|U  <br/> |xsd: string  <br/> |可选  <br/> |代表单位默认值是度量的 DL。  <br/> |单元格的单位。  <br/> |
|V  <br/> |xsd: string  <br/> |可选  <br/> |代表单元格的值。  <br/> |ShapeSheet 单元格的值。  <br/> |
   
## <a name="remarks"></a>说明

此**单元格**元素的**N**属性必须为一组有限的对应于 ShapeSheet 单元格的值之一。 请参阅下表为确定允许此**单元格**元素的**N**属性的值。 
  
|**值**|**说明**|**更多信息**|
|:-----|:-----|:-----|
|AsianFont  <br/> |包含用于设置格式的文本运行含有亚洲字符的字体的枚举。  <br/> |[AsianFont Cell (Character Section)](asianfont-cell-character-section.md) <br/> |
|Case  <br/> |确定运行的形状的文本的大小写。  <br/> |[Case Cell (Character Section)](case-cell-character-section.md) <br/> |
|颜色  <br/> |确定用于形状的文本运行的颜色。  <br/> |[Color Cell (Character Section)](color-cell-character-section.md) <br/> |
|ColorTrans  <br/> |确定图层或形状的文本从 0 （完全不透明） 到 1 （完全透明） 运行颜色的透明度。  <br/> |无。  <br/> |
|ComplexScriptFont  <br/> |包含用于设置格式的文本运行复杂文种字符组成的字体编号。  <br/> |[ComplexScriptFont Cell (Character Section)](complexscriptfont-cell-character-section.md) <br/> |
|ComplexScriptSize  <br/> |用于设置文本格式的字体的大小运行复杂文种字符组成。  <br/> |[ComplexScriptSize Cell (Character Section)](complexscriptsize-cell-character-section.md) <br/> |
|DblUnderline  <br/> |确定一段连续文本的范围是否具有双下划线。  <br/> |[DoubleULine Cell (Character Section)](doubleuline-cell-character-section.md) <br/> |
|DoubleStrikethrough  <br/> |确定是否一段连续文本的格式设置为双删除线。  <br/> |[DoubleStrikethrough Cell (Character Section)](doublestrikethrough-cell-character-section.md) <br/> |
|字体  <br/> |代表用于格式一段连续文本的字体的数量。  <br/> |[Font Cell (Character Section)](font-cell-character-section.md) <br/> |
|FontScale  <br/> |指定字体的宽度。  <br/> |无。  <br/> |
|LangID  <br/> |指示输入一段连续文本所用的语言。  <br/> |[LangID Cell (Character Section)](langid-cell-character-section.md) <br/> |
|Letterspace  <br/> |指定两个或多个字符之间的空间量。 可以添加或减去 1/20 磅为增量在空间。  <br/> |无。  <br/> |
|Overline  <br/> |确定一段连续文本是否具有之上存在线条。  <br/> |[Overline Cell (Character Section)](overline-cell-character-section.md) <br/> |
|Pos  <br/> |确定形状的文本运行相对于基线的位置。  <br/> |[Pos Cell (Character Section)](pos-cell-character-section.md) <br/> |
|Size  <br/> |确定形状的文本块中连续文本的大小。  <br/> |[Size Cell (Character Section)](size-cell-character-section.md) <br/> |
|Strikethru  <br/> |确定是否一段连续文本的格式设置为删除线。  <br/> |[Strikethru Cell (Character Section)](strikethru-cell-character-section.md) <br/> |
|样式  <br/> |显示的字符格式应用于文本范围中形状的文本块运行。  <br/> |[Style Cell (Character Section)](style-cell-character-section.md) <br/> |
   

