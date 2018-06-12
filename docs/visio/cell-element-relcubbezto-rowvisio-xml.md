---
title: 单元格元素 （RelCubBezTo 行） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: daa5c527-65fe-a1e4-ab3e-24e77bdb522b
description: 包含 x 坐标或 y 坐标的相对于形状的宽度和高度的立方贝赛尔曲线的终结点、 的控制点的位于曲线的相对于形状的宽度和高度，开头或 x 坐标或 y 坐标的控制点的 x 坐标或 y 坐标位于曲线的相对于形状的宽度和高度的尾。
ms.openlocfilehash: e4a5353f3ecfb514b61ee893905e54c8951a2be5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779833"
---
# <a name="cell-element-relcubbezto-row-visio-xml"></a>单元格元素 （RelCubBezTo 行） (Visio XML)

包含 x 坐标或 y 坐标的相对于形状的宽度和高度的立方贝赛尔曲线的终结点、 的控制点的位于曲线的相对于形状的宽度和高度，开头或 x 坐标或 y 坐标的控制点的 x 坐标或 y 坐标位于曲线的相对于形状的宽度和高度的尾。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |母版页 #.xml、 页面 #.xml  <br/> |
   
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
|[Row 元素 （geometry)](row-element-geometry-sectionvisio-xml.md) <br/> |[RelCubBezTo_Type](relcubbezto_type-complextypevisio-xml.md) <br/> |包含 x 坐标或 y 坐标的相对于形状的宽度和高度的立方贝赛尔曲线的终结点、 的控制点的位于曲线的相对于形状的宽度和高度，开头或 x 坐标或 y 坐标的控制点的 x 坐标或 y 坐标位于曲线的相对于形状的宽度和高度的尾。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[RefBy](refby-element-cell_type-complextypevisio-xml.md) <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |指定在绘图页上的引用。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|E  <br/> |xsd: string  <br/> |可选  <br/> |指示该公式计算为错误。 **E**的值是当前值 （错误消息字符串）;**V**属性的值是最后一个有效的值。  <br/> |错误消息字符串。  <br/> |
|F  <br/> |xsd: string  <br/> |可选  <br/> | 代表元素的公式。 此属性可以包含以下字符串之一：  <br/>  （某些公式） 如果公式本地存在  <br/>  `No Formula`如果本地删除或阻止公式  <br/>  `Inh`如果继承的公式。  <br/> |公式。  <br/> |
|N  <br/> |xsd: string  <br/> |必需  <br/> |表示的 ShapeSheet 单元格的名称。  <br/> |ShapeSheet 单元格的名称。  <br/> 请参阅下面的备注部分。  <br/> |
|U  <br/> |xsd: string  <br/> |可选  <br/> |代表单位默认值是度量的 DL。  <br/> |单元格的单位。  <br/> |
|V  <br/> |xsd: string  <br/> |可选  <br/> |代表单元格的值。  <br/> |ShapeSheet 单元格的值。  <br/> |
   
## <a name="remarks"></a>备注

此**单元格**元素的**N**属性必须为一组有限的对应于 ShapeSheet 单元格的值之一。 请参阅下表为确定允许此**单元格**元素的**N**属性的值。 
  
|**值**|**说明**|**详细信息**|
|:-----|:-----|:-----|
|X  <br/> |终顶点相对于形状的宽度的立方贝赛尔曲线的 x 轴坐标值。  <br/> |[RelCubBezTo 行 （geometry 内容）](relcubbezto-row-geometry-section.md) <br/> |
|Y  <br/> |终顶点相对于形状的高度的立方贝赛尔曲线的 y 轴坐标值。  <br/> |[RelCubBezTo 行 （geometry 内容）](relcubbezto-row-geometry-section.md) <br/> |
|A  <br/> |相对于形状的宽度; 控制点的位于曲线的起点控件的 x 坐标弧形上某个点。最佳位于之间的开始和终顶点的弧的控制点。  <br/> |[RelCubBezTo 行 （geometry 内容）](relcubbezto-row-geometry-section.md) <br/> |
|B  <br/> |相对于形状的高度控制点曲线的起点控件的 y 坐标。  <br/> |[RelCubBezTo 行 （geometry 内容）](relcubbezto-row-geometry-section.md) <br/> |
|C  <br/> |曲线的控件终点相对于形状的宽度; x 轴坐标值弧形上某个点。弧的起点控件点和结束顶点之间最佳位于控制点。  <br/> |[RelCubBezTo 行 （geometry 内容）](relcubbezto-row-geometry-section.md) <br/> |
|D  <br/> |曲线控件终点相对于形状的高度 y 轴坐标值。  <br/> |[RelCubBezTo 行 （geometry 内容）](relcubbezto-row-geometry-section.md) <br/> |
   

