---
title: 'StyleSheet 元素 (StyleSheets_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 323e1ccd-8ddd-46d3-1032-5d68d01cf4bd
description: 表示在文档中定义的样式。
ms.openlocfilehash: 939180d24972ae68d01b2a707e7806380b706d14
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541937"
---
# <a name="stylesheet-element-stylesheets_type-complextype-visio-xml"></a>StyleSheet 元素 (StyleSheets_Type COMPLEXType)  (Visio XML) 

表示在文档中定义的样式。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[StyleSheet_Type](stylesheet_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |document.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="StyleSheet" Type="StyleSheet_Type" minOccurs="0" maxOccurs="unbounded" ></xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[StyleSheets](stylesheets-element-visiodocument_type-complextypevisio-xml.md) <br/> |[StyleSheets_Type](stylesheets_type-complextypevisio-xml.md) <br/> |包含文档的 **StyleSheet** 元素的集合。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Cell](cell-elementvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定单个属性。  <br/> |
|[Section](section-element-sheet_type-complextypevisio-xml.md) <br/> |[Section_Type](section_type-complextypevisio-xml.md) <br/> |指定相关属性的集合。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|FillStyle  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |样式从其继承填充格式的 StyleSheet 元素的 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|ID  <br/> |xsd：unsignedInt  <br/> |必需  <br/> |元素在其父元素中的唯一 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|IsCustomName  <br/> |xsd：boolean  <br/> |可选  <br/> |指示用户是否已自定义该名称。  <br/> |xsd：boolean 类型的值。  <br/> |
|IsCustomNameU  <br/> |xsd：boolean  <br/> |可选  <br/> |指示用户是否已自定义通用名称。  <br/> |xsd：boolean 类型的值。  <br/> |
|LineStyle  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |样式继承线条格式的 StyleSheet 元素的 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|名称  <br/> |xsd：string  <br/> |可选  <br/> |元素的名称。  <br/> |xsd：string 类型的值。  <br/> |
|NameU  <br/> |xsd：string  <br/> |可选  <br/> |元素的通用名称。  <br/> |xsd：string 类型的值。  <br/> |
|TextStyle  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |样式从其继承文本格式的 StyleSheet 元素的 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
   

