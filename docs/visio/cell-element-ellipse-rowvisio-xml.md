---
title: 单元格元素 （Ellipse 行） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 210e6731-7c94-90b1-c7c4-635df974fdb6
description: 包含 x 坐标或 y 坐标的椭圆中心点和椭圆上的两个点。
ms.openlocfilehash: 75c3cf86b7c8668b70915117e1fc70b07d2cef0b
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25394387"
---
# <a name="cell-element-ellipse-row-visio-xml"></a>单元格元素 （Ellipse 行） (Visio XML)

包含 x 坐标或 y 坐标的椭圆中心点和椭圆上的两个点。
  
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
|[Row 元素 （geometry)](row-element-geometry-sectionvisio-xml.md) <br/> |[Ellipse_Type](ellipse_type-complextypevisio-xml.md) <br/> |包含 x 坐标或 y 坐标的椭圆中心点和椭圆上的两个点。  <br/> |
   
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
|X  <br/> |中心点的 x 坐标。  <br/> |[Ellipse Row (Geometry Section)](ellipse-row-geometry-section.md) <br/> |
|Y  <br/> |中心点的 y 坐标。  <br/> |[Ellipse Row (Geometry Section)](ellipse-row-geometry-section.md) <br/> |
|A  <br/> |椭圆; 上的第一个点的 x 坐标与 B 单元格所表示的 y 轴坐标配对。  <br/> |[Ellipse Row (Geometry Section)](ellipse-row-geometry-section.md) <br/> |
|B  <br/> |个椭圆; 上的第一个点的 y 坐标与 A 单元格所表示的 x 轴坐标配对。  <br/> |[Ellipse Row (Geometry Section)](ellipse-row-geometry-section.md) <br/> |
|C  <br/> |椭圆; 上第二个点的 x 坐标与 D 单元格所表示的 y 轴坐标配对。  <br/> |[Ellipse Row (Geometry Section)](ellipse-row-geometry-section.md) <br/> |
|D  <br/> |个椭圆; 上第二个点的 y 坐标与 C 单元格所表示的 y 轴坐标配对。  <br/> |[Ellipse Row (Geometry Section)](ellipse-row-geometry-section.md) <br/> |
   

