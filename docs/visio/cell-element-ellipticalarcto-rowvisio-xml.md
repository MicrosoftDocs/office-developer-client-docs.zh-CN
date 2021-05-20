---
title: 'Cell 元素 (EllipticalArcTo Row)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3c0aa7a3-cc54-ffac-2c62-917b3d0a357e
description: 包含椭圆弧终点的 x 坐标或 y 坐标、弧形上控制点的 x 坐标或 y 坐标、从 x 轴到椭圆主轴的角度，或者椭圆主轴和次要轴之间的比值。
ms.openlocfilehash: 396575c069925fe472fa3df0543e29303881dad3
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539826"
---
# <a name="cell-element-ellipticalarcto-row-visio-xml"></a>Cell 元素 (EllipticalArcTo Row)  (Visio XML) 

包含椭圆弧终点的 x 坐标或 y 坐标、弧形上控制点的 x 坐标或 y 坐标、从 x 轴到椭圆主轴的角度，或者椭圆主轴和次要轴之间的比值。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |master#.xml，page#.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Geometry (Row) ](row-element-geometry-sectionvisio-xml.md) <br/> |[EllipticalArcTo_Type](ellipticalarcto_type-complextypevisio-xml.md) <br/> |包含椭圆弧终点的 x 坐标或 y 坐标、弧形上控制点的 x 坐标或 y 坐标、从 x 轴到椭圆主轴的角度，或者椭圆主轴和次要轴之间的比值。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[RefBy](refby-element-cell_type-complextypevisio-xml.md) <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |指定对绘图页的引用。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|E  <br/> |xsd：string  <br/> |可选  <br/> |指示公式计算结果为错误。 **E** 的值是错误消息字符串 (的当前) ;**V** 属性的值是最后一个有效值。  <br/> |错误消息字符串。  <br/> |
|F  <br/> |xsd：string  <br/> |可选  <br/> | 表示元素的公式。 此属性可以包含以下字符串之一：  <br/>  如果 (存在) ，则"设置一些公式"。  <br/>  `No Formula` 如果公式在本地删除或阻止  <br/>  `Inh` 如果公式是继承的。  <br/> |公式。  <br/> |
|N  <br/> |xsd：string  <br/> |必需  <br/> |代表 ShapeSheet 单元格的名称。  <br/> |ShapeSheet 单元格的名称。  <br/> 请参阅下面的"备注"部分。  <br/> |
|U  <br/> |xsd：string  <br/> |可选  <br/> |表示度量单位 默认值为 DL。  <br/> |单元格的单位。  <br/> |
|V  <br/> |xsd：string  <br/> |可选  <br/> |表示单元格的值。  <br/> |ShapeSheet 单元格的值。  <br/> |
   
## <a name="remarks"></a>备注

此 **Cell** 元素的 **N** 属性必须是与 ShapeSheet 单元格对应的一组有限值之一。 请参阅下表以确定此 **Cell** 元素允许的 **N** 属性的值。 
  
|**值**|**说明**|**详细信息**|
|:-----|:-----|:-----|
|X  <br/> |弧形上的终顶点的 x 坐标。  <br/> |[EllipticalArcTo Row (Geometry Section)](ellipticalarcto-row-geometry-section.md) <br/> |
|Y  <br/> |弧形上的终顶点的 y 坐标。  <br/> |[EllipticalArcTo Row (Geometry Section)](ellipticalarcto-row-geometry-section.md) <br/> |
|A  <br/> |弧形的控制点（弧形上的一个点）的 x 坐标。控制点最好位于弧形的始顶点和终顶点的中间附近。否则，弧形可能要变得极大才能穿过该控制点，因而结果将难以预料。  <br/> |[EllipticalArcTo Row (Geometry Section)](ellipticalarcto-row-geometry-section.md) <br/> |
|B  <br/> |弧形的控制点的 y 坐标。  <br/> |[EllipticalArcTo Row (Geometry Section)](ellipticalarcto-row-geometry-section.md) <br/> |
|C  <br/> |弧形主轴相对于其父形状的 x 轴的角度。  <br/> |[EllipticalArcTo Row (Geometry Section)](ellipticalarcto-row-geometry-section.md) <br/> |
|D  <br/> |弧形的长短轴之比。尽管每一词都有其本义，但在此处“长”轴却并不一定大于“短”轴，所以此比值也就不一定大于 1。如果将此单元格设置为小于等于 0 或大于 1000 的值，可能导致无法预料的结果。  <br/> |[EllipticalArcTo Row (Geometry Section)](ellipticalarcto-row-geometry-section.md) <br/> |
   

