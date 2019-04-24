---
title: StyleSheet 元素 (StyleSheets_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 323e1ccd-8ddd-46d3-1032-5d68d01cf4bd
description: 表示在文档中定义的样式。
ms.openlocfilehash: af1f8270be28e7edabf22d93471517531f5cc226
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329797"
---
# <a name="stylesheet-element-stylesheetstype-complextype-visio-xml"></a>StyleSheet 元素 (StyleSheets_Type 复杂类型) ("Visio XML")

表示在文档中定义的样式。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[StyleSheet_Type](stylesheet_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |document .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="StyleSheet" Type="StyleSheet_Type" minOccurs="0" maxOccurs="unbounded" ></xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[StyleSheets](stylesheets-element-visiodocument_type-complextypevisio-xml.md) <br/> |[StyleSheets_Type](stylesheets_type-complextypevisio-xml.md) <br/> |包含文档的**样式表**元素的集合。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Cell](cell-elementvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定一个属性。  <br/> |
|[Section](section-element-sheet_type-complextypevisio-xml.md) <br/> |[Section_Type](section_type-complextypevisio-xml.md) <br/> |指定相关属性的集合。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|FillStyle  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |此样式从中继承填充格式的样式表元素的 ID。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|ID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |元素在其父元素中的唯一 ID。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|IsCustomName  <br/> |xsd: boolean  <br/> |可选  <br/> |指示该名称是否已由用户自定义。  <br/> |xsd: boolean 类型的值。  <br/> |
|IsCustomNameU  <br/> |xsd: boolean  <br/> |可选  <br/> |指示是否已由用户自定义通用名称。  <br/> |xsd: boolean 类型的值。  <br/> |
|LineStyle  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |样式表元素的 ID, 此样式从该元素继承行格式设置。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|名称  <br/> |xsd: string  <br/> |可选  <br/> |元素的名称。  <br/> |xsd: string 类型的值。  <br/> |
|NameU  <br/> |xsd: string  <br/> |可选  <br/> |元素的通用名称。  <br/> |xsd: string 类型的值。  <br/> |
|TextStyle  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |此样式从中继承文本格式的样式表元素的 ID。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
   

