---
title: 'ForeignData 元素 (ShapeSheet_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 59db25bc-0283-6f56-0aa9-9be98a3e9041
description: 包含 MIME (多用途 Internet 邮件扩展) 图片数据的编码 BLOB，如Windows图元文件、位图或 OLE 数据。
ms.openlocfilehash: 6b130b5a50a51d5d909b843e805d197735dc7146
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539840"
---
# <a name="foreigndata-element-shapesheet_type-complextype-visio-xml"></a>ForeignData 元素 (ShapeSheet_Type COMPLEXType)  (Visio XML) 

包含 MIME (多用途 Internet 邮件扩展) 图片数据的编码 BLOB，如Windows图元文件、位图或 OLE 数据。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[ForeignData_Type](foreigndata_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |page#.xml，master#.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="ForeignData" type="ForeignData_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[ShapeSheet_Type](shapesheet_type-complextypevisio-xml.md) <br/> |包含定义 **Master、Page** 或 **组合** 形状元素中形状的元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Rel](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[Rel_Type](shapesheet_type-complextypevisio-xml.md) <br/> |指定与包含图像数据的部件的关系。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|CompressionLevel  <br/> |xsd：double  <br/> |可选  <br/> |指定应用于文件的压缩级别。 只有当外数据是一个基于光栅的外对象（如 DIB、JPG、PNG、TIFF 或 GIF 文件）时，此属性才有意义。  <br/> |xsd：double 类型的值。  <br/> |
|CompressionType  <br/> |xsd：token  <br/> |可选  <br/> |指定应用于文件的压缩类型。 此属性仅在外数据为基于光栅的外对象（如 DIB、JPG、PNG、TIFF 或 GIF 文件）时有意义  <br/> |xsd：token 类型的值。  <br/> |
|ExtentX  <br/> |xsd：double  <br/> |可选  <br/> |指定图元文件的水平范围。 此属性仅在外数据是图元文件时有意义。  <br/> |xsd：double 类型的值。  <br/> |
|ExtentY  <br/> |xsd：double  <br/> |可选  <br/> |指定图元文件垂直范围。 此属性仅在外数据是图元文件时有意义。  <br/> |xsd：double 类型的值。  <br/> |
|ForeignType  <br/> |xsd：token  <br/> |必需  <br/> |指示图元文件、EnhMetaFile、位图、对象或墨迹类型。  <br/> |xsd：token 类型的值。  <br/> |
|MappingMode  <br/> |xsd：unsignedShort  <br/> |可选  <br/> |指定图元文件映射模式。 此属性仅在外数据是图元文件时有意义。  <br/> |xsd：unsignedShort 类型的值。  <br/> |
|ObjectHeight  <br/> |xsd：double  <br/> |可选  <br/> |指定对象的高度（以页面单位表示）。 此属性仅在外数据是 OLE2 嵌入对象时有意义。  <br/> |xsd：double 类型的值。  <br/> |
|ObjectType  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |整数指示符对象类型。 当 Foreign 类型为对象时使用。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|ObjectWidth  <br/> |xsd：double  <br/> |可选  <br/> |指定对象的宽度（以页面单位表示）。 此属性仅在外数据是 OLE2 嵌入对象时有意义。  <br/> |xsd：double 类型的值。  <br/> |
|ShowAsIcon  <br/> |xsd：boolean  <br/> |可选  <br/> |指示是否以图标显示嵌入数据。  <br/> |xsd：boolean 类型的值。  <br/> |
   

