---
title: Shape 元素 (Shapes_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8074bd07-430a-779e-ad1f-e7e3a1c748b1
description: 包含用于定义主控形状、页面或组形状元素中的形状的元素。
ms.openlocfilehash: 6308b8dd21c92f6ced9ea7f03ec8aa85773fa2bb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326570"
---
# <a name="shape-element-shapestype-complextype-visio-xml"></a>Shape 元素 (Shapes_Type 复杂类型) ("Visio XML")

包含用于定义**主控**形状、**页面**或组形状元素中的形状的元素。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[ShapeSheet_Type](shapesheet_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |页面 # .xml、master # .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Shape" type="ShapeSheet_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Shapes](shapes-element-pagecontents_type-complextypevisio-xml.md) <br/> |[Shapes_Type](shapes_type-complextypevisio-xml.md) <br/> |指定形状的集合。  <br/> |
|[Shapes](shapes-element-pagecontents_type-complextypevisio-xml.md) <br/> |[Shapes_Type](shapes_type-complextypevisio-xml.md) <br/> |指定形状的集合。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Cell](cell-elementvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定一个属性。  <br/> |
|[Data1](data1-element-shapesheet_type-complextypevisio-xml.md) <br/> |[Data_Type](data_type-complextypevisio-xml.md) <br/> |包含用于提供有关形状的其他信息的任意字符串值。  <br/> |
|[Data2](data2-element-shapesheet_type-complextypevisio-xml.md) <br/> |[Data_Type](data_type-complextypevisio-xml.md) <br/> |包含用于提供有关形状的其他信息的任意字符串值。  <br/> |
|[Data3](data3-element-shapesheet_type-complextypevisio-xml.md) <br/> |[Data_Type](data_type-complextypevisio-xml.md) <br/> |包含用于提供有关形状的其他信息的任意字符串值。  <br/> |
|[ForeignData](foreigndata-element-shapesheet_type-complextypevisio-xml.md) <br/> |[ForeignData_Type](foreigndata_type-complextypevisio-xml.md) <br/> |包含一个 MIME (多用途 Internet 邮件扩展) 编码的图片数据 (例如, Windows 图元文件、位图或 OLE 数据) 的 BLOB。  <br/> |
|[Section](section-element-sheet_type-complextypevisio-xml.md) <br/> |[Section_Type](section_type-complextypevisio-xml.md) <br/> |指定相关属性的集合。  <br/> |
|[Shapes](shapes-element-shapesheet_type-complextypevisio-xml.md) <br/> |[Shapes_Type](shapes_type-complextypevisio-xml.md) <br/> |指定形状的集合。  <br/> |
|[Text](text-element-shapesheet_type-complextypevisio-xml.md) <br/> |[Text_Type](text_type-complextypevisio-xml.md) <br/> |包含形状的文本。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|键  <br/> |xsd: boolean  <br/> |可选  <br/> |指示元素是否在本地删除的标志。  <br/> |xsd: boolean 类型的值。  <br/> |
|FillStyle  <br/> |xsd: unsignedInt  <br/> ||此形状从中继承填充格式的样式表的 ID。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|ID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |元素在其父元素中的唯一 ID。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|IsCustomName  <br/> |xsd: boolean  <br/> |可选  <br/> |指示该名称是否已由用户自定义。  <br/> |xsd: boolean 类型的值。  <br/> |
|IsCustomNameU  <br/> |xsd: boolean  <br/> |可选  <br/> |指示通用名称是否已由用户自定义。。  <br/> |xsd: boolean 类型的值。  <br/> |
|LineStyle  <br/> |xsd: unsignedInt  <br/> ||此形状从中继承行格式的样式表的 ID。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|Master  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |主控形状元素的 ID, 该形状从中继承其数据。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|MasterShape  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |主控形状元素的 ID, 该形状从中继承其数据。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|名称  <br/> |xsd: string  <br/> |可选  <br/> |元素的名称。  <br/> |xsd: string 类型的值。  <br/> |
|NameU  <br/> |xsd: string  <br/> |可选  <br/> |元素的通用名称。  <br/> |xsd: string 类型的值。  <br/> |
|TextStyle  <br/> |xsd: unsignedInt  <br/> ||此形状从中继承文本格式的样式表的 ID。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|类型  <br/> |xsd: token  <br/> |可选  <br/> |形状的类型。 它可以是下列值之一: Group、Shape、Guide 或 Foreign。  <br/> |xsd: 令牌类型的值。  <br/> |
|UniqueID  <br/> |xsd: string  <br/> |可选  <br/> |分配给形状的 GUID (全局唯一标识符)。  <br/> |xsd: string 类型的值。  <br/> |
   

