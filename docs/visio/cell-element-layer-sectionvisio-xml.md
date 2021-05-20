---
title: 'Cell 元素 (Layer Section)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f9896839-ca36-b82b-7412-e57195d4b8e2
description: 为图层指定一个属性，或者为页面指定其属性。
ms.openlocfilehash: 119c82f84c76f735a5d9b73b4bea8beda0a7e476
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539755"
---
# <a name="cell-element-layer-section-visio-xml"></a>Cell 元素 (Layer Section)  (Visio XML) 

为图层指定一个属性，或者为页面指定其属性。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |masters.xml、pages.xml  <br/> |
   
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
|[Layer Section (Row 元素) ](row-element-layer-sectionvisio-xml.md) <br/> |[LayerRow_Type](layerrow_type-complextypevisio-xml.md) <br/> |为图层指定一个属性，或者为页面指定其属性。  <br/> |
   
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
|活动  <br/> |指定图层是否处于活动状态。  <br/> |无。  <br/> |
|颜色  <br/> |指定下列值之一：颜色表中用于显示图层的颜色索引或指定不在颜色表中的自定义颜色的 RGB 值。  <br/> |无。  <br/> |
|ColorTrans  <br/> |确定图层或形状的文本颜色的透明度，从 0 到 1，从 0 (完全不透明) 到 1 (透明) 。  <br/> |无。  <br/> |
|Glue  <br/> |指定是否可粘附属于图层的形状。  <br/> |无。  <br/> |
|Lock  <br/> |指定是否锁定属于该图层的形状，以免选取或编辑这些形状。  <br/> |无。  <br/> |
|名称  <br/> |图层的名称。  <br/> |无。  <br/> |
|NameUniv  <br/> |指定图层的通用名称。  <br/> |无。  <br/> |
|打印  <br/> |指定在打印绘图时是否打印属于图层的形状。  <br/> |无。  <br/> |
|贴靠  <br/> |指定其他形状是否可以与分配给图层的形状对齐。  <br/> |无。  <br/> |
|状态  <br/> |指定图层是否是文档的有效图层。  <br/> |无。  <br/> |
|Visible  <br/> |指定属于该图层的形状在绘图页上是否显示出来。  <br/> |无。  <br/> |
   

