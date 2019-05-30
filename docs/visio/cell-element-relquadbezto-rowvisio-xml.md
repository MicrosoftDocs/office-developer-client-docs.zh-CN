---
title: Cell 元素 ("RelQuadBezTo" 行) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8b3aea70-a69f-a85e-83d8-c0fa2ee68836
description: 包含相对于形状的宽度和高度或曲线相对形状的宽度和高度的控制点的 x 轴或 y 轴坐标的二次贝塞尔曲线端点的 x 坐标或 y 坐标。
ms.openlocfilehash: 7bdd55cfd5401c8455f09cf7d237117572d12723
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542385"
---
# <a name="cell-element-relquadbezto-row-visio-xml"></a>Cell 元素 ("RelQuadBezTo" 行) (Visio XML)

包含相对于形状的宽度和高度或曲线相对形状的宽度和高度的控制点的 x 轴或 y 轴坐标的二次贝塞尔曲线端点的 x 坐标或 y 坐标。
  
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

### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Row 元素 ("几何")](row-element-geometry-sectionvisio-xml.md) <br/> |[RelQuadBezTo_Type](relquadbezto_type-complextypevisio-xml.md) <br/> |包含相对于形状的宽度和高度或曲线相对形状的宽度和高度的控制点的 x 轴或 y 轴坐标的二次贝塞尔曲线端点的 x 坐标或 y 坐标。  <br/> |
   
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
|X  <br/> |一条二次贝塞尔曲线终顶点相对于形状宽度的 x 坐标。  <br/> |[RelQuadBezTo 行 ("Geometry" 部分)](relquadbezto-row-geometry-section.md) <br/> |
|Y  <br/> |一条二次贝塞尔曲线终顶点的 y 坐标 (相对于形状的高度)。  <br/> |[RelQuadBezTo 行 ("Geometry" 部分)](relquadbezto-row-geometry-section.md) <br/> |
|A  <br/> |曲线的控制点相对于形状宽度的 x 坐标;弧形上的一点。控制点最适合弧的起始和结束顶点之间的中间点。  <br/> |[RelQuadBezTo 行 ("Geometry" 部分)](relquadbezto-row-geometry-section.md) <br/> |
|B  <br/> |曲线的控制点相对于形状高度的 y 轴坐标值。  <br/> |[RelQuadBezTo 行 ("Geometry" 部分)](relquadbezto-row-geometry-section.md) <br/> |
   

