---
title: Cell 元素 ("RelEllipticalArcTo" 行) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: beaa8860-807e-c8dd-8a59-29cd0f91ba45
description: 包含椭圆弧的终点相对于形状的宽度和高度、弧上的控制点相对于该形状的宽度和高度的 x 坐标或 y 坐标、从 x 轴到椭圆的主轴的角度、从 x 轴到椭圆的长轴的比例或椭圆的主要和次要轴。
ms.openlocfilehash: 84d7fe222cd46b54f38bc03e058103cc1d7a9620
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539430"
---
# <a name="cell-element-relellipticalarcto-row-visio-xml"></a>Cell 元素 ("RelEllipticalArcTo" 行) (Visio XML)

包含椭圆弧的终点相对于形状的宽度和高度、弧上的控制点相对于该形状的宽度和高度的 x 坐标或 y 坐标、从 x 轴到椭圆的主轴的角度、从 x 轴到椭圆的长轴的比例或椭圆的主要和次要轴。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |master # .xml、第 .xml 页  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded">
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Row 元素 ("几何")](row-element-geometry-sectionvisio-xml.md) <br/> |[RelEllipticalArcTo_Type](relellipticalarcto_type-complextypevisio-xml.md) <br/> |包含椭圆弧的终点相对于形状的宽度和高度、弧上的控制点相对于该形状的宽度和高度的 x 坐标或 y 坐标、从 x 轴到椭圆的主轴的角度、从 x 轴到椭圆的长轴的比例或椭圆的主要和次要轴。  <br/> |
   
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
|X  <br/> |弧形上的终顶点相对于形状宽度的 x 坐标。  <br/> |[RelEllipticalArcTo 行 ("Geometry" 部分)](relellipticalarcto-row-geometry-section.md) <br/> |
|Y  <br/> |弧形上的终顶点相对于形状高度的 y 坐标。  <br/> |[RelEllipticalArcTo 行 ("Geometry" 部分)](relellipticalarcto-row-geometry-section.md) <br/> |
|A  <br/> |弧形的控制点相对于形状宽度的 x 坐标;弧形上的一点。  <br/> |[RelEllipticalArcTo 行 ("Geometry" 部分)](relellipticalarcto-row-geometry-section.md) <br/> |
|B  <br/> |弧形的控制点相对于形状宽度的 y 轴坐标值。  <br/> |[RelEllipticalArcTo 行 ("Geometry" 部分)](relellipticalarcto-row-geometry-section.md) <br/> |
|C  <br/> |弧形的长轴相对于其父级的 x 轴的角度。  <br/> |[RelEllipticalArcTo 行 ("Geometry" 部分)](relellipticalarcto-row-geometry-section.md) <br/> |
|D  <br/> |弧形的长短轴之比。  <br/> |[RelEllipticalArcTo 行 ("Geometry" 部分)](relellipticalarcto-row-geometry-section.md) <br/> |
   

