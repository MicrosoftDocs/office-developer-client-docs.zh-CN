---
title: Row 元素 ("操作标记" 部分) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 54c3315f-770f-6995-d0d8-ab66e4fe10d9
description: 定义形状或页面上的操作标记。
ms.openlocfilehash: 1ecdb256fbde4a667ade747c2c7216cd0d248fc2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358434"
---
# <a name="row-element-action-tag-section-visio-xml"></a>Row 元素 ("操作标记" 部分) ("Visio XML")

定义形状或页面上的操作标记。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[ActionTagRow_Type](actiontagrow_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |.master、主 # .xml、pages、.xml、.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Row" type="ActionTagRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Section](section-element-sheet_type-complextypevisio-xml.md) <br/> |[Section_Type](section_type-complextypevisio-xml.md) <br/> |定义形状或页面上的操作标记。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Cell](cell-element-action-tag-sectionvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |定义形状或页面上的动作标记的一个属性。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|键  <br/> |xsd: boolean  <br/> |可选  <br/> |指定是否已删除要从主控形状继承的行。  <br/> |xsd: boolean 类型的值。  <br/> |
|IX  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |指定行的从1开始的标识符。 它应是唯一, 并且大于同一节中的其他标识符。IX 属性仅用于字符、Connection、Field、FillGradient、Geometry、Layer、LineGradient、段落、审阅者、草稿和选项卡部分。 行只能具有 IX 或 N 属性中的一个。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|LocalName  <br/> |xsd: string  <br/> |可选  <br/> |指定行的与语言相关的唯一名称。  <br/> |xsd: string 类型的值。  <br/> |
|N  <br/> |xsd: string  <br/> |可选  <br/> |指定行的与语言无关的唯一名称。N 属性仅用于用户、属性、操作、控制、Connection、Hyperlink 和 ActionTag 节。 行只能具有 IX 或 N 属性中的一个。  <br/> |xsd: string 类型的值。  <br/> |
|T  <br/> |xsd: string  <br/> |可选  <br/> |指定由行表示并在几何图形可视化中使用的几何路径的类型。 T 属性仅用于 "Geometry" 部分。  <br/> |xsd: string 类型的值。  <br/> |
   

