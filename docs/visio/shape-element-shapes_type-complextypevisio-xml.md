---
title: 'Shape 元素 (Shapes_Type complexType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8074bd07-430a-779e-ad1f-e7e3a1c748b1
description: 包含定义 Master、Page 或组合形状元素中的形状的元素。
ms.openlocfilehash: aa7ffa539c9f82adc486bd0848dda66798bac165
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542070"
---
# <a name="shape-element-shapes_type-complextype-visio-xml"></a>Shape 元素 (Shapes_Type complexType)  (Visio XML) 

包含定义 **Master、Page** 或 **组合** 形状元素中形状的元素。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[ShapeSheet_Type](shapesheet_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |page#.xml，master#.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Shape" type="ShapeSheet_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[性状](shapes-element-pagecontents_type-complextypevisio-xml.md) <br/> |[Shapes_Type](shapes_type-complextypevisio-xml.md) <br/> |指定形状的集合。  <br/> |
|[性状](shapes-element-pagecontents_type-complextypevisio-xml.md) <br/> |[Shapes_Type](shapes_type-complextypevisio-xml.md) <br/> |指定形状的集合。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Cell](cell-elementvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定单个属性。  <br/> |
|[Data1](data1-element-shapesheet_type-complextypevisio-xml.md) <br/> |[Data_Type](data_type-complextypevisio-xml.md) <br/> |包含用于提供有关形状的其他信息的任意字符串值。  <br/> |
|[Data2](data2-element-shapesheet_type-complextypevisio-xml.md) <br/> |[Data_Type](data_type-complextypevisio-xml.md) <br/> |包含用于提供有关形状的其他信息的任意字符串值。  <br/> |
|[Data3](data3-element-shapesheet_type-complextypevisio-xml.md) <br/> |[Data_Type](data_type-complextypevisio-xml.md) <br/> |包含用于提供有关形状的其他信息的任意字符串值。  <br/> |
|[ForeignData](foreigndata-element-shapesheet_type-complextypevisio-xml.md) <br/> |[ForeignData_Type](foreigndata_type-complextypevisio-xml.md) <br/> |包含 MIME (多用途 Internet 邮件扩展) 图片数据的编码 BLOB，如Windows图元文件、位图或 OLE 数据。  <br/> |
|[Section](section-element-sheet_type-complextypevisio-xml.md) <br/> |[Section_Type](section_type-complextypevisio-xml.md) <br/> |指定相关属性的集合。  <br/> |
|[性状](shapes-element-shapesheet_type-complextypevisio-xml.md) <br/> |[Shapes_Type](shapes_type-complextypevisio-xml.md) <br/> |指定形状的集合。  <br/> |
|[Text](text-element-shapesheet_type-complextypevisio-xml.md) <br/> |[Text_Type](text_type-complextypevisio-xml.md) <br/> |包含形状的文本。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|Del  <br/> |xsd：boolean  <br/> |可选  <br/> |指示是否在本地删除元素的标志。  <br/> |xsd：boolean 类型的值。  <br/> |
|FillStyle  <br/> |xsd：unsignedInt  <br/> ||此形状从其继承填充格式的 StyleSheet 的 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|ID  <br/> |xsd：unsignedInt  <br/> |必需  <br/> |元素在其父元素中的唯一 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|IsCustomName  <br/> |xsd：boolean  <br/> |可选  <br/> |指示用户是否已自定义该名称。  <br/> |xsd：boolean 类型的值。  <br/> |
|IsCustomNameU  <br/> |xsd：boolean  <br/> |可选  <br/> |指示用户是否已自定义通用名称。  <br/> |xsd：boolean 类型的值。  <br/> |
|LineStyle  <br/> |xsd：unsignedInt  <br/> ||此形状从其继承线条格式的 StyleSheet 的 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|Master  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |形状从其继承其数据的 Master 元素的 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|MasterShape  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |形状从其继承其数据的 Master 元素的 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|名称  <br/> |xsd：string  <br/> |可选  <br/> |元素的名称。  <br/> |xsd：string 类型的值。  <br/> |
|NameU  <br/> |xsd：string  <br/> |可选  <br/> |元素的通用名称。  <br/> |xsd：string 类型的值。  <br/> |
|TextStyle  <br/> |xsd：unsignedInt  <br/> ||此形状从其继承文本格式的 StyleSheet 的 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|类型  <br/> |xsd：token  <br/> |可选  <br/> |形状的类型。 它可以是下列值之一：Group、Shape、Guide 或 Foreign。  <br/> |xsd：token 类型的值。  <br/> |
|UniqueID  <br/> |xsd：string  <br/> |可选  <br/> |GUID (形状) 全局唯一标识符。  <br/> |xsd：string 类型的值。  <br/> |
   

