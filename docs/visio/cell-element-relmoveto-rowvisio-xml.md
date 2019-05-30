---
title: Cell 元素 ("RelMoveTo" 行) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8e91497c-0aa1-2021-9317-cf989e5b84a3
description: 包含形状的第一个顶点的 x 坐标或 y 坐标, 或路径中断开点后的第一个顶点的 x 坐标或 y 坐标 (相对于形状的高度和宽度)。
ms.openlocfilehash: 6ec7990887ed59ae229e88b6ad02a7759c770700
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539402"
---
# <a name="cell-element-relmoveto-row-visio-xml"></a>Cell 元素 ("RelMoveTo" 行) (Visio XML)

包含形状的第一个顶点的 x 坐标或 y 坐标, 或路径中断开点后的第一个顶点的 x 坐标或 y 坐标 (相对于形状的高度和宽度)。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |master # .xml、第 .xml 页  <br/> |
   
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
|[Row 元素 ("几何")](row-element-geometry-sectionvisio-xml.md) <br/> |[RelMoveTo_Type](relmoveto_type-complextypevisio-xml.md) <br/> |包含形状的第一个顶点的 x 坐标或 y 坐标, 或路径中断开点后的第一个顶点的 x 坐标或 y 坐标 (相对于形状的高度和宽度)。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[RefBy](refby-element-cell_type-complextypevisio-xml.md) <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |指定对页面的引用。  <br/> |
   
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
|X  <br/> |如果**RelMoveTo**行是该内容中的第一行, 则**X**单元格表示形状的第一个顶点相对于形状宽度的 X 坐标。 如果**RelMoveTo**行出现在两行之间, 则**X**单元格表示路径中断开处后的第一个顶点的 x 坐标。  <br/> |[RelMoveTo 行 ("Geometry" 部分)](relmoveto-row-geometry-section.md) <br/> |
|Y  <br/> |如果**RelMoveTo**行是该内容中的第一行, 则**Y**单元格表示形状的第一个顶点相对于形状的高度的 Y 坐标。 如果**RelMoveTo**行出现在两行之间, 则**Y**单元格表示路径中断开处后的第一个顶点的 y 坐标。  <br/> |[RelMoveTo 行 ("Geometry" 部分)](relmoveto-row-geometry-section.md) <br/> |
   

