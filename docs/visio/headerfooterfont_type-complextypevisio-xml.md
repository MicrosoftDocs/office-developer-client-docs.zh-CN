---
title: HeaderFooterFont_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1e4134be-fb18-768e-b477-f9f40f72548d
ms.openlocfilehash: dd99d87e0d80aad3bcde31e4834337ee59088da2
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541069"
---
# <a name="headerfooterfonttype-complextype-visio-xml"></a>HeaderFooterFont_Type 复杂类型 (Visio XML)

## <a name="type-information"></a>类型信息

|||
|:-----|:-----|
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|**架构文件** <br/> |VisioSchema15-2012-06-05  <br/> |
|**扩展基** <br/> |无  <br/> |
   
## <a name="definition"></a>定义

```XML
      <xs:complexType name="HeaderFooterFont_Type">
    <xs:attribute name="Height"
  type="xsd:int"
    />
    <xs:attribute name="Width"
  type="xsd:int"
    />
    <xs:attribute name="Escapement"
  type="xsd:int"
    />
    <xs:attribute name="Orientation"
  type="xsd:int"
    />
    <xs:attribute name="Weight"
  type="xsd:int"
    />
    <xs:attribute name="Italic"
  type="xsd:unsignedByte"
    />
    <xs:attribute name="Underline"
  type="xsd:unsignedByte"
    />
    <xs:attribute name="StrikeOut"
  type="xsd:unsignedByte"
    />
    <xs:attribute name="CharSet"
  type="xsd:unsignedByte"
    />
    <xs:attribute name="OutPrecision"
  type="xsd:unsignedByte"
    />
    <xs:attribute name="ClipPrecision"
  type="xsd:unsignedByte"
    />
    <xs:attribute name="Quality"
  type="xsd:unsignedByte"
    />
    <xs:attribute name="PitchAndFamily"
  type="xsd:unsignedByte"
    />
    <xs:attribute name="FaceName"
  type="xsd:string"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|CharSet  <br/> |xsd: unsignedByte  <br/> |可选  <br/> ||Xsd: unsignedByte 类型的值。  <br/> |
|ClipPrecision  <br/> |xsd: unsignedByte  <br/> |可选  <br/> ||Xsd: unsignedByte 类型的值。  <br/> |
|又  <br/> |xsd: int  <br/> |可选  <br/> ||Xsd: int 类型的值。  <br/> |
|FaceName  <br/> |xsd: string  <br/> |可选  <br/> ||Xsd: string 类型的值。  <br/> |
|Height  <br/> |xsd: int  <br/> |可选  <br/> ||Xsd: int 类型的值。  <br/> |
|斜体  <br/> |xsd: unsignedByte  <br/> |可选  <br/> ||Xsd: unsignedByte 类型的值。  <br/> |
|Orientation  <br/> |xsd: int  <br/> |可选  <br/> ||Xsd: int 类型的值。  <br/> |
|OutPrecision  <br/> |xsd: unsignedByte  <br/> |可选  <br/> ||Xsd: unsignedByte 类型的值。  <br/> |
|PitchAndFamily  <br/> |xsd: unsignedByte  <br/> |可选  <br/> ||Xsd: unsignedByte 类型的值。  <br/> |
|Quality  <br/> |xsd: unsignedByte  <br/> |可选  <br/> ||Xsd: unsignedByte 类型的值。  <br/> |
|删除线  <br/> |xsd: unsignedByte  <br/> |可选  <br/> ||Xsd: unsignedByte 类型的值。  <br/> |
|下划线  <br/> |xsd: unsignedByte  <br/> |可选  <br/> ||Xsd: unsignedByte 类型的值。  <br/> |
|粗细  <br/> |xsd: int  <br/> |可选  <br/> ||Xsd: int 类型的值。  <br/> |
|Width  <br/> |xsd: int  <br/> |可选  <br/> ||Xsd: int 类型的值。  <br/> |
   

