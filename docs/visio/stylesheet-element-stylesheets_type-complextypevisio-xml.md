---
title: 样式表元素 （StyleSheets_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 323e1ccd-8ddd-46d3-1032-5d68d01cf4bd
description: 表示在文档中定义的样式。
ms.openlocfilehash: af1f8270be28e7edabf22d93471517531f5cc226
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384568"
---
# <a name="stylesheet-element-stylesheetstype-complextype-visio-xml"></a>样式表元素 （StyleSheets_Type 复杂类型） (Visio XML)

表示在文档中定义的样式。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[StyleSheet_Type](stylesheet_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |document.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="StyleSheet" Type="StyleSheet_Type" minOccurs="0" maxOccurs="unbounded" ></xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[StyleSheets](stylesheets-element-visiodocument_type-complextypevisio-xml.md) <br/> |[StyleSheets_Type](stylesheets_type-complextypevisio-xml.md) <br/> |包含文档的**样式表**元素的集合。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Cell](cell-elementvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定单个属性。  <br/> |
|[Section](section-element-sheet_type-complextypevisio-xml.md) <br/> |[Section_Type](section_type-complextypevisio-xml.md) <br/> |指定相关的属性的集合。  <br/> |
   
### <a name="attributes"></a>Attributes

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|FillStyle  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |从中此样式继承填充格式样式表元素的 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|ID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |其父元素中的元素的唯一 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|IsCustomName  <br/> |化  <br/> |可选  <br/> |指示是否由用户自定义名称。  <br/> |化类型的值。  <br/> |
|IsCustomNameU  <br/> |化  <br/> |可选  <br/> |指示是否由用户自定义的通用名称。  <br/> |化类型的值。  <br/> |
|LineStyle  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |从中此样式继承线条格式样式表元素的 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|名称  <br/> |xsd: string  <br/> |可选  <br/> |元素的名称。  <br/> |Xsd: string 类型的值。  <br/> |
|NameU  <br/> |xsd: string  <br/> |可选  <br/> |元素的通用名称。  <br/> |Xsd: string 类型的值。  <br/> |
|TextStyle  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |从中此样式继承文本格式样式表元素的 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
   

