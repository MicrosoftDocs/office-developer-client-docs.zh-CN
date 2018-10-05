---
title: 单元格元素 （RelMoveTo 行） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8e91497c-0aa1-2021-9317-cf989e5b84a3
description: 包含后的高度和宽度的形状的相对路径中断开的 x 坐标或 y 坐标形状的第一个顶点的 x 坐标或 y 坐标的第一个顶点。
ms.openlocfilehash: cc81ea1b36541fe471807e83057e7aaaacb70d70
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401578"
---
# <a name="cell-element-relmoveto-row-visio-xml"></a>单元格元素 （RelMoveTo 行） (Visio XML)

包含后的高度和宽度的形状的相对路径中断开的 x 坐标或 y 坐标形状的第一个顶点的 x 坐标或 y 坐标的第一个顶点。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
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
|[Row 元素 （geometry)](row-element-geometry-sectionvisio-xml.md) <br/> |[RelMoveTo_Type](relmoveto_type-complextypevisio-xml.md) <br/> |包含后的高度和宽度的形状的相对路径中断开的 x 坐标或 y 坐标形状的第一个顶点的 x 坐标或 y 坐标的第一个顶点。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[RefBy](refby-element-cell_type-complextypevisio-xml.md) <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |指定向页面的引用。  <br/> |
   
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
|X  <br/> |如果**RelMoveTo**行是该节中的第一行，则**X**单元格表示形状相对于形状的宽度的第一个顶点的 x 坐标。 如果**RelMoveTo**行出现在两行之间，则**X**单元格后路径中断开表示的第一个顶点的 x 坐标。  <br/> |[RelMoveTo 行（“Geometry”部分）](relmoveto-row-geometry-section.md) <br/> |
|Y  <br/> |如果**RelMoveTo**行是该节中的第一行，则**Y**单元格表示形状相对于形状的高度的第一个顶点的 y 坐标。 如果**RelMoveTo**行出现在两行之间，则**Y**单元格后路径中断开表示的第一个顶点的 y 坐标。  <br/> |[RelMoveTo 行（“Geometry”部分）](relmoveto-row-geometry-section.md) <br/> |
   

