---
title: 单元格元素 （草稿的部分） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: af17b1c5-51ee-f46f-79d0-4f33369b66f1
description: 指定输入和测试可由其他单元格引用的公式的工作区。
ms.openlocfilehash: c8917a8d4bcf26789f631238e6a9547e9ca2d59c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779855"
---
# <a name="cell-element-scratch-section-visio-xml"></a>单元格元素 （草稿的部分） (Visio XML)

指定输入和测试可由其他单元格引用的公式的工作区。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |document.xml、 masters.xml、 主 #.xml、 pages.xml、 页 #.xml  <br/> |
   
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
|[Row 元素 （草稿内容）](row-element-scratch-sectionvisio-xml.md) <br/> |[ScratchRow_Type](scratch_type-complextypevisio-xml.md) <br/> |指定输入和测试可由其他单元格引用的公式的工作区。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[RefBy](refby-element-cell_type-complextypevisio-xml.md) <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |指定向页面的引用。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|E  <br/> |xsd: string  <br/> |可选  <br/> |指示该公式计算为错误。 **E**的值是当前值 （错误消息字符串）;**V**属性的值是最后一个有效的值。  <br/> |错误消息字符串。  <br/> |
|F  <br/> |xsd: string  <br/> |可选  <br/> | 代表元素的公式。 此属性可以包含以下字符串之一：  <br/>  （某些公式） 如果公式本地存在  <br/>  `No Formula`如果本地删除或阻止公式  <br/>  `Inh`如果继承的公式。  <br/> |公式。  <br/> |
|N  <br/> |xsd: string  <br/> |必需  <br/> |表示的 ShapeSheet 单元格的名称。  <br/> |ShapeSheet 单元格的名称。  <br/> 请参阅下面的备注部分。  <br/> |
|U  <br/> |xsd: string  <br/> |可选  <br/> |代表单位默认值是度量的 DL。  <br/> |单元格的单位。  <br/> |
|V  <br/> |xsd: string  <br/> |可选  <br/> |代表单元格的值。  <br/> |ShapeSheet 单元格的值。  <br/> |
   
### <a name="remarks"></a>备注

此**单元格**元素的**N**属性必须为一组有限的对应于 ShapeSheet 单元格的值之一。 请参阅下表为确定允许此**单元格**元素的**N**属性的值。 
  
|**值**|**说明**|**详细信息**|
|:-----|:-----|:-----|
|A  <br/> |一种草稿单元格，可用于输入或测试公式。  <br/> |[Scratch Section](scratch-section.md) <br/> |
|B  <br/> |一种草稿单元格，可用于输入或测试公式。  <br/> |[Scratch Section](scratch-section.md) <br/> |
|C  <br/> |一种草稿单元格，可用于输入或测试公式。  <br/> |[Scratch Section](scratch-section.md) <br/> |
|D  <br/> |一种草稿单元格，可用于输入或测试公式。  <br/> |[Scratch Section](scratch-section.md) <br/> |
|X  <br/> |一种草稿单元格，可用于输入或测试公式。  <br/> |[Scratch Section](scratch-section.md) <br/> |
|Y  <br/> |一种草稿单元格，可用于输入或测试公式。  <br/> |[Scratch Section](scratch-section.md) <br/> |
   

