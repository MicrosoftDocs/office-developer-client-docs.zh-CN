---
title: 单元格元素 （NURBSTo 行） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e76bae8f-b9de-39ef-1f56-b00a6cd2ba6c
description: 包含第二个最后一个节点的最后一个权重，第一个节点的第一个权重或非均匀有理 B 样条 (NURBS) 公式的位置的位置的位置的 x 坐标或 y 坐标，的位置。
ms.openlocfilehash: f23f73d67d72f9536dc7ffe9e083058ea9306217
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392800"
---
# <a name="cell-element-nurbsto-row-visio-xml"></a>单元格元素 （NURBSTo 行） (Visio XML)

包含第二个最后一个节点的最后一个权重，第一个节点的第一个权重或非均匀有理 B 样条 (NURBS) 公式的位置的位置的位置的 x 坐标或 y 坐标，的位置。
  
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
|[Row 元素 （geometry)](row-element-geometry-sectionvisio-xml.md) <br/> |[NURBSTo_Type](nurbsto_type-complextypevisio-xml.md) <br/> |包含第二个最后一个节点的最后一个权重，第一个节点的第一个权重或非均匀有理 B 样条 (NURBS) 公式的位置的位置的位置的 x 坐标或 y 坐标，的位置。  <br/> |
   
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
|X  <br/> |NURBS 的最后一个控制点的 x 坐标。  <br/> |[NURBSTo Row (Geometry Section)](nurbsto-row-geometry-section.md) <br/> |
|Y  <br/> |NURBS 的最后一个控制点的 y 坐标。  <br/> |[NURBSTo Row (Geometry Section)](nurbsto-row-geometry-section.md) <br/> |
|A  <br/> |NURBS 的倒数第二个节点。  <br/> |[NURBSTo Row (Geometry Section)](nurbsto-row-geometry-section.md) <br/> |
|B  <br/> |NURBS 的最后一个权重。  <br/> |[NURBSTo Row (Geometry Section)](nurbsto-row-geometry-section.md) <br/> |
|C  <br/> |NURBS 的第一个节点。  <br/> |[NURBSTo Row (Geometry Section)](nurbsto-row-geometry-section.md) <br/> |
|D  <br/> |NURBS 的第一个权重。  <br/> |[NURBSTo Row (Geometry Section)](nurbsto-row-geometry-section.md) <br/> |
|E  <br/> |NURBS 公式。  <br/> |[NURBSTo Row (Geometry Section)](nurbsto-row-geometry-section.md) <br/> |
   

