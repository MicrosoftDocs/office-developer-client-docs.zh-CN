---
title: ForeignData_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 21b394a6-6f95-fc17-482c-4cb648a0d9bb
ms.openlocfilehash: 6630c8b33dc1c4c7cbb12bb9727d4f0b1e1b19d2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346009"
---
# <a name="foreigndatatype-complextype-visio-xml"></a>ForeignData_Type 复杂类型 ("Visio XML")

## <a name="type-information"></a>类型信息

|||
|:-----|:-----|
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|**架构文件** <br/> |VisioSchema15-2012-06-05  <br/> |
|**扩展基** <br/> |无  <br/> |
   
## <a name="definition"></a>定义

```XML
          <xs:complexType name="ForeignData_Type">
          
          <xs:sequence>
    <xs:element name="Rel"  type="Rel_Type"
     minOccurs="1"
     maxOccurs="1"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="ForeignType"
  type="xsd:token"
     use="required"
    />
    <xs:attribute name="ObjectType"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="ShowAsIcon"
  type="xsd:boolean"
    />
    <xs:attribute name="ObjectWidth"
  type="xsd:double"
    />
    <xs:attribute name="ObjectHeight"
  type="xsd:double"
    />
    <xs:attribute name="MappingMode"
  type="xsd:unsignedShort"
    />
    <xs:attribute name="ExtentX"
  type="xsd:double"
    />
    <xs:attribute name="ExtentY"
  type="xsd:double"
    />
    <xs:attribute name="CompressionType"
  type="xsd:token"
    />
    <xs:attribute name="CompressionLevel"
  type="xsd:double"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[相对](rel-element-foreigndata_type-complextypevisio-xml.md) <br/> |[Rel_Type](rel_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|CompressionLevel  <br/> |xsd: double  <br/> |可选  <br/> ||xsd: double 类型的值。  <br/> |
|CompressionType  <br/> |xsd: token  <br/> |可选  <br/> ||xsd: 令牌类型的值。  <br/> |
|ExtentX  <br/> |xsd: double  <br/> |可选  <br/> ||xsd: double 类型的值。  <br/> |
|ExtentY  <br/> |xsd: double  <br/> |可选  <br/> ||xsd: double 类型的值。  <br/> |
|ForeignType  <br/> |xsd: token  <br/> |必需  <br/> ||xsd: 令牌类型的值。  <br/> |
|MappingMode  <br/> |xsd: unsignedShort  <br/> |可选  <br/> ||xsd: unsignedShort 类型的值。  <br/> |
|ObjectHeight  <br/> |xsd: double  <br/> |可选  <br/> ||xsd: double 类型的值。  <br/> |
|ObjectType  <br/> |xsd: unsignedInt  <br/> |可选  <br/> ||xsd: unsignedInt 类型的值。  <br/> |
|ObjectWidth  <br/> |xsd: double  <br/> |可选  <br/> ||xsd: double 类型的值。  <br/> |
|ShowAsIcon  <br/> |xsd: boolean  <br/> |可选  <br/> ||xsd: boolean 类型的值。  <br/> |
   

