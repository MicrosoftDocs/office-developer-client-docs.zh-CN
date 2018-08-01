---
title: ForeignData_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 21b394a6-6f95-fc17-482c-4cb648a0d9bb
ms.openlocfilehash: 1d9358de2f88a1b9e035ecf4966544ea935f8b2b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780311"
---
# <a name="foreigndatatype-complextype-visio-xml"></a>ForeignData_Type 复杂类型 (Visio XML)

## <a name="type-information"></a>类型信息

|||
|:-----|:-----|
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|**架构文件** <br/> |VisioSchema15 2012 06 05.xsd  <br/> |
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

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Rel](rel-element-foreigndata_type-complextypevisio-xml.md) <br/> |[Rel_Type](rel_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a>Attributes

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|CompressionLevel  <br/> |化  <br/> |可选  <br/> ||化类型的值。  <br/> |
|CompressionType  <br/> |xsd:token  <br/> |可选  <br/> ||Xsd:token 类型的值。  <br/> |
|ExtentX  <br/> |化  <br/> |可选  <br/> ||化类型的值。  <br/> |
|ExtentY  <br/> |化  <br/> |可选  <br/> ||化类型的值。  <br/> |
|ForeignType  <br/> |xsd:token  <br/> |必需  <br/> ||Xsd:token 类型的值。  <br/> |
|MappingMode  <br/> |xsd:unsignedShort  <br/> |可选  <br/> ||Xsd:unsignedShort 类型的值。  <br/> |
|ObjectHeight  <br/> |化  <br/> |可选  <br/> ||化类型的值。  <br/> |
|ObjectType  <br/> |xsd:unsignedInt  <br/> |可选  <br/> ||Xsd:unsignedInt 类型的值。  <br/> |
|ObjectWidth  <br/> |化  <br/> |可选  <br/> ||化类型的值。  <br/> |
|ShowAsIcon  <br/> |化  <br/> |可选  <br/> ||化类型的值。  <br/> |
   

