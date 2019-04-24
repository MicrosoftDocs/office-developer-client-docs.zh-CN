---
title: Cell 元素 ("图层" 部分) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f9896839-ca36-b82b-7412-e57195d4b8e2
description: 为某一层或其属性指定一个页面的一个属性。
ms.openlocfilehash: e96fdc1dcd5c9a7a2cb8753beaff766c2b477af2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318170"
---
# <a name="cell-element-layer-section-visio-xml"></a>Cell 元素 ("图层" 部分) ("Visio XML")

为某一层或其属性指定一个页面的一个属性。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |"xml"、"pages"  <br/> |
   
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
|[Row 元素 ("层" 部分)](row-element-layer-sectionvisio-xml.md) <br/> |[LayerRow_Type](layerrow_type-complextypevisio-xml.md) <br/> |为某一层或其属性指定一个页面的一个属性。  <br/> |
   
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
   
## <a name="remarks"></a>注解

此**单元格**元素的**N**属性必须是与 ShapeSheet 单元格相对应的一组有限的值之一。 请参阅下表, 以确定此**单元格**元素允许的**N**属性的值。 
  
|**Value**|**说明**|**详细信息**|
|:-----|:-----|:-----|
|Active  <br/> |指定图层是否处于活动状态。  <br/> |无。  <br/> |
|颜色  <br/> |指定以下各项之一: 颜色表中用于显示图层的颜色的索引, 或指定颜色表中不存在的自定义颜色的 RGB 值。  <br/> |无。  <br/> |
|ColorTrans  <br/> |确定图层或形状的文本颜色的透明度, 从 0 (完全不透明) 到 1 (完全透明)。  <br/> |无。  <br/> |
|粘附  <br/> |指定是否可以将属于该图层的形状粘附到。  <br/> |无。  <br/> |
|Lock  <br/> |指定是否锁定属于该图层的形状，以免选取或编辑这些形状。  <br/> |无。  <br/> |
|名称  <br/> |层的名称。  <br/> |无。  <br/> |
|NameUniv  <br/> |指定层的通用名称。  <br/> |无。  <br/> |
|Print  <br/> |指定打印绘图时是否打印属于该图层的形状。  <br/> |无。  <br/> |
|管理单元  <br/> |指定其他形状是否可以与分配给该图层的形状对齐。  <br/> |无。  <br/> |
|状态  <br/> |指定图层是否为文档的有效层。  <br/> |无。  <br/> |
|Visible  <br/> |指定属于该图层的形状在绘图页上是否显示出来。  <br/> |无。  <br/> |
   

