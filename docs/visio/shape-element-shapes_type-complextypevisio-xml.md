---
title: 形状元素 （Shapes_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8074bd07-430a-779e-ad1f-e7e3a1c748b1
description: 包含定义母版页、 页面或组形状元素中的形状的元素。
ms.openlocfilehash: 8c0a288858e2aaccbd3afadcdc1b057565dd30ab
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781268"
---
# <a name="shape-element-shapestype-complextype-visio-xml"></a>形状元素 （Shapes_Type 复杂类型） (Visio XML)

包含定义形状的**主控形状**、**页面**或组形状元素中的元素。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[ShapeSheet_Type](shapesheet_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |页面 #.xml、 母版页 #.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Shape" type="ShapeSheet_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Shapes](shapes-element-pagecontents_type-complextypevisio-xml.md) <br/> |[Shapes_Type](shapes_type-complextypevisio-xml.md) <br/> |指定形状的集合。  <br/> |
|[Shapes](shapes-element-pagecontents_type-complextypevisio-xml.md) <br/> |[Shapes_Type](shapes_type-complextypevisio-xml.md) <br/> |指定形状的集合。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Cell](cell-elementvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定单个属性。  <br/> |
|[Data1](data1-element-shapesheet_type-complextypevisio-xml.md) <br/> |[Data_Type](data_type-complextypevisio-xml.md) <br/> |包含用于提供有关形状的其他信息的任意字符串值。  <br/> |
|[Data2](data2-element-shapesheet_type-complextypevisio-xml.md) <br/> |[Data_Type](data_type-complextypevisio-xml.md) <br/> |包含用于提供有关形状的其他信息的任意字符串值。  <br/> |
|[Data3](data3-element-shapesheet_type-complextypevisio-xml.md) <br/> |[Data_Type](data_type-complextypevisio-xml.md) <br/> |包含用于提供有关形状的其他信息的任意字符串值。  <br/> |
|[ForeignData](foreigndata-element-shapesheet_type-complextypevisio-xml.md) <br/> |[ForeignData_Type](foreigndata_type-complextypevisio-xml.md) <br/> |包含 MIME （多用途 Internet 邮件扩展） 编码的 BLOB 的图片数据，如 Windows 图元文件、 位图或 OLE 数据。  <br/> |
|[Section](section-element-sheet_type-complextypevisio-xml.md) <br/> |[Section_Type](section_type-complextypevisio-xml.md) <br/> |指定相关的属性的集合。  <br/> |
|[Shapes](shapes-element-shapesheet_type-complextypevisio-xml.md) <br/> |[Shapes_Type](shapes_type-complextypevisio-xml.md) <br/> |指定形状的集合。  <br/> |
|[Text](text-element-shapesheet_type-complextypevisio-xml.md) <br/> |[Text_Type](text_type-complextypevisio-xml.md) <br/> |包含形状的文本。  <br/> |
   
### <a name="attributes"></a>Attributes

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|Del  <br/> |化  <br/> |可选  <br/> |表明该元素删除本地的标志。  <br/> |化类型的值。  <br/> |
|FillStyle  <br/> |xsd:unsignedInt  <br/> ||此形状所继承的填充格式的样式表的 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|ID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |其父元素中的元素的唯一 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|IsCustomName  <br/> |化  <br/> |可选  <br/> |指示是否由用户自定义名称。  <br/> |化类型的值。  <br/> |
|IsCustomNameU  <br/> |化  <br/> |可选  <br/> |指示是否由用户自定义的通用名称。  <br/> |化类型的值。  <br/> |
|LineStyle  <br/> |xsd:unsignedInt  <br/> ||此形状所继承的线条格式样式表的 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|Master  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |主控形状的 ID 元素形状继承其数据。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|MasterShape  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |主控形状的 ID 元素形状继承其数据。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|名称  <br/> |xsd: string  <br/> |可选  <br/> |元素的名称。  <br/> |Xsd: string 类型的值。  <br/> |
|NameU  <br/> |xsd: string  <br/> |可选  <br/> |元素的通用名称。  <br/> |Xsd: string 类型的值。  <br/> |
|TextStyle  <br/> |xsd:unsignedInt  <br/> ||此形状所继承的文本格式的样式表的 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|类型  <br/> |xsd:token  <br/> |可选  <br/> |形状的类型。 它可以是下列值之一： 组、 形状、 参考线或 Foreign。  <br/> |Xsd:token 类型的值。  <br/> |
|UniqueID  <br/> |xsd: string  <br/> |可选  <br/> |分配到的形状的 GUID （全局唯一标识符）。  <br/> |Xsd: string 类型的值。  <br/> |
   

