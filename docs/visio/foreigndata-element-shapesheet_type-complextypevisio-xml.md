---
title: ForeignData 元素 （ShapeSheet_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 59db25bc-0283-6f56-0aa9-9be98a3e9041
description: 包含 MIME （多用途 Internet 邮件扩展） 编码的 BLOB 的图片数据，如 Windows 图元文件、 位图或 OLE 数据。
ms.openlocfilehash: cce7665230fb9e68bf37002e1953944a5b8f8082
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382679"
---
# <a name="foreigndata-element-shapesheettype-complextype-visio-xml"></a>ForeignData 元素 （ShapeSheet_Type 复杂类型） (Visio XML)

包含 MIME （多用途 Internet 邮件扩展） 编码的 BLOB 的图片数据，如 Windows 图元文件、 位图或 OLE 数据。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[ForeignData_Type](foreigndata_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |页面 #.xml、 母版页 #.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="ForeignData" type="ForeignData_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[ShapeSheet_Type](shapesheet_type-complextypevisio-xml.md) <br/> |包含定义形状的**主控形状**、**页面**或组形状元素中的元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Rel](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[Rel_Type](shapesheet_type-complextypevisio-xml.md) <br/> |指定与包含图像数据的部件的关系。  <br/> |
   
### <a name="attributes"></a>Attributes

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|CompressionLevel  <br/> |化  <br/> |可选  <br/> |指定应用于文件的压缩的级别。 此属性才有意义，如果外数据是基于光栅外的对象，例如 DIB、 JPG、 PNG、 TIFF 或 GIF 文件。  <br/> |化类型的值。  <br/> |
|CompressionType  <br/> |xsd:token  <br/> |可选  <br/> |指定应用于文件的压缩的类型。 此属性才有意义，如果外数据是基于光栅外的对象，例如 DIB、 JPG、 PNG、 TIFF 或 GIF 文件  <br/> |Xsd:token 类型的值。  <br/> |
|ExtentX  <br/> |化  <br/> |可选  <br/> |指定水平程度的图元文件。 此属性才有意义的外部数据时图元文件。  <br/> |化类型的值。  <br/> |
|ExtentY  <br/> |化  <br/> |可选  <br/> |指定垂直程度的图元文件。 此属性才有意义的外部数据时图元文件。  <br/> |化类型的值。  <br/> |
|ForeignType  <br/> |xsd:token  <br/> |必需  <br/> |指示图元文件，EnhMetaFile，位图、 对象或墨迹类型。  <br/> |Xsd:token 类型的值。  <br/> |
|MappingMode  <br/> |xsd:unsignedShort  <br/> |可选  <br/> |指定的图元文件映射模式。 此属性才有意义的外部数据时图元文件。  <br/> |Xsd:unsignedShort 类型的值。  <br/> |
|ObjectHeight  <br/> |化  <br/> |可选  <br/> |指定对象的高度以页面单位表示。 此属性才有意义的外部数据时 OLE2 嵌入的对象。  <br/> |化类型的值。  <br/> |
|ObjectType  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |对象类型的整数指示符。 外的类型为对象时使用。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|ObjectWidth  <br/> |化  <br/> |可选  <br/> |以页面单位表示指定对象的宽度。 此属性才有意义的外部数据时 OLE2 嵌入的对象。  <br/> |化类型的值。  <br/> |
|ShowAsIcon  <br/> |化  <br/> |可选  <br/> |指示是否显示或不显示为图标嵌入的数据。  <br/> |化类型的值。  <br/> |
   

