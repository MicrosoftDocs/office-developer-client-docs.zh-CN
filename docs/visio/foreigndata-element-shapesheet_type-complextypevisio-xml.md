---
title: ForeignData 元素 (ShapeSheet_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 59db25bc-0283-6f56-0aa9-9be98a3e9041
description: 包含一个 MIME (多用途 Internet 邮件扩展) 编码的图片数据 (例如, Windows 图元文件、位图或 OLE 数据) 的 BLOB。
ms.openlocfilehash: cce7665230fb9e68bf37002e1953944a5b8f8082
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346030"
---
# <a name="foreigndata-element-shapesheettype-complextype-visio-xml"></a>ForeignData 元素 (ShapeSheet_Type 复杂类型) ("Visio XML")

包含一个 MIME (多用途 Internet 邮件扩展) 编码的图片数据 (例如, Windows 图元文件、位图或 OLE 数据) 的 BLOB。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[ForeignData_Type](foreigndata_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |页面 # .xml、master # .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="ForeignData" type="ForeignData_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[ShapeSheet_Type](shapesheet_type-complextypevisio-xml.md) <br/> |包含用于定义**主控**形状、**页面**或组形状元素中的形状的元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[相对](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[Rel_Type](shapesheet_type-complextypevisio-xml.md) <br/> |指定与包含图像数据的部件的关系。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|CompressionLevel  <br/> |xsd: double  <br/> |可选  <br/> |指定应用于文件的压缩级别。 仅当外部数据是基于栅格的外部对象 (如 DIB、JPG、PNG、TIFF 或 GIF 文件) 时, 此属性才有意义。  <br/> |xsd: double 类型的值。  <br/> |
|CompressionType  <br/> |xsd: token  <br/> |可选  <br/> |指定应用于文件的压缩类型。 仅当外部数据是基于栅格的外部对象 (如 DIB、JPG、PNG、TIFF 或 GIF 文件) 时, 此属性才有意义。  <br/> |xsd: 令牌类型的值。  <br/> |
|ExtentX  <br/> |xsd: double  <br/> |可选  <br/> |指定图元文件的水平范围。 仅当外部数据是图元文件时, 此属性才有意义。  <br/> |xsd: double 类型的值。  <br/> |
|ExtentY  <br/> |xsd: double  <br/> |可选  <br/> |指定图元文件的垂直范围。 仅当外部数据是图元文件时, 此属性才有意义。  <br/> |xsd: double 类型的值。  <br/> |
|ForeignType  <br/> |xsd: token  <br/> |必需  <br/> |指示图元文件、EnhMetaFile、位图、对象或墨迹类型。  <br/> |xsd: 令牌类型的值。  <br/> |
|MappingMode  <br/> |xsd: unsignedShort  <br/> |可选  <br/> |指定图元文件映射模式。 仅当外部数据是图元文件时, 此属性才有意义。  <br/> |xsd: unsignedShort 类型的值。  <br/> |
|ObjectHeight  <br/> |xsd: double  <br/> |可选  <br/> |以页面单位为单位指定对象的高度。 仅当外部数据是 OLE2 的嵌入对象时, 此属性才有意义。  <br/> |xsd: double 类型的值。  <br/> |
|ObjectType  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |对象类型的整数指示符。 当外部类型为 object 时使用。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|ObjectWidth  <br/> |xsd: double  <br/> |可选  <br/> |以页面单位为单位指定对象的宽度。 仅当外部数据是 OLE2 的嵌入对象时, 此属性才有意义。  <br/> |xsd: double 类型的值。  <br/> |
|ShowAsIcon  <br/> |xsd: boolean  <br/> |可选  <br/> |指示是否将嵌入的数据显示为图标。  <br/> |xsd: boolean 类型的值。  <br/> |
   

