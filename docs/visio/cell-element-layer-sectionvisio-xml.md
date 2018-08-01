---
title: 单元格元素 （层部分） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f9896839-ca36-b82b-7412-e57195d4b8e2
description: 指定一个图层属性或页面其属性。
ms.openlocfilehash: 92be29321ba637bb694c0cf5d3cddcb888618c1d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779859"
---
# <a name="cell-element-layer-section-visio-xml"></a>单元格元素 （层部分） (Visio XML)

指定一个图层属性或页面其属性。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |masters.xml、 pages.xml  <br/> |
   
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
|[Row 元素（“Layer”部分）](row-element-layer-sectionvisio-xml.md) <br/> |[LayerRow_Type](layerrow_type-complextypevisio-xml.md) <br/> |指定一个图层属性或页面其属性。  <br/> |
   
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
|活跃  <br/> |指定是否是活动图层。  <br/> |无。  <br/> |
|颜色  <br/> |指定以下项之一： 用于显示图层或一个颜色表中没有指定自定义颜色的 RGB 值的颜色表中的颜色索引。  <br/> |无。  <br/> |
|ColorTrans  <br/> |确定图层或从 0 （完全不透明） 到 1 （完全透明） 形状的文本颜色的透明度。  <br/> |无。  <br/> |
|粘附  <br/> |指定是否可以属于该图层的形状粘附到。  <br/> |无。  <br/> |
|Lock  <br/> |指定是否锁定属于该图层的形状，以免选取或编辑这些形状。  <br/> |无。  <br/> |
|名称  <br/> |图层的名称。  <br/> |无。  <br/> |
|NameUniv  <br/> |指定图层的通用名称。  <br/> |无。  <br/> |
|打印  <br/> |指定打印绘图时是否打印属于该图层的形状。  <br/> |无。  <br/> |
|管理单元  <br/> |指定其他形状是否可以与分配给该图层的形状对齐。  <br/> |无。  <br/> |
|Status  <br/> |指定该图层是否有效图层的文档。  <br/> |无。  <br/> |
|Visible  <br/> |指定属于该图层的形状在绘图页上是否显示出来。  <br/> |无。  <br/> |
   

