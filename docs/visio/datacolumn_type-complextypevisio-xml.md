---
title: 'DataColumn_Type XML (Visio complexType) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bee50623-cdf7-b9d7-867a-70c86922cbac
ms.openlocfilehash: 7f35cd2ef1f6d710644033599fe4a90a0f2978ef
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541209"
---
# <a name="datacolumn_type-complextype-visio-xml"></a>DataColumn_Type XML (Visio complexType) 

## <a name="type-information"></a>类型信息

|||
|:-----|:-----|
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|**架构文件** <br/> |VisioSchema15-2012-06-05.xsd  <br/> |
|**扩展基** <br/> |无  <br/> |
   
## <a name="definition"></a>定义

```XML
      <xs:complexType name="DataColumn_Type">
    <xs:attribute name="ColumnNameID"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="Name"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="Label"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="OrigLabel"
  type="xsd:string"
    />
    <xs:attribute name="LangID"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="Calendar"
  type="xsd:unsignedShort"
    />
    <xs:attribute name="DataType"
  type="xsd:unsignedShort"
    />
    <xs:attribute name="UnitType"
  type="xsd:string"
    />
    <xs:attribute name="Currency"
  type="xsd:unsignedShort"
    />
    <xs:attribute name="Degree"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="DisplayWidth"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="DisplayOrder"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="Mapped"
  type="xsd:boolean"
    />
    <xs:attribute name="Hyperlink"
  type="xsd:boolean"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|日历  <br/> |xsd：unsignedShort  <br/> |可选  <br/> ||xsd：unsignedShort 类型的值。  <br/> |
|ColumnNameID  <br/> |xsd：string  <br/> |必需  <br/> ||xsd：string 类型的值。  <br/> |
|货币  <br/> |xsd：unsignedShort  <br/> |可选  <br/> ||xsd：unsignedShort 类型的值。  <br/> |
|DataType  <br/> |xsd：unsignedShort  <br/> |可选  <br/> ||xsd：unsignedShort 类型的值。  <br/> |
|Degree  <br/> |xsd：unsignedInt  <br/> |可选  <br/> ||xsd：unsignedInt 类型的值。  <br/> |
|DisplayOrder  <br/> |xsd：unsignedInt  <br/> |可选  <br/> ||xsd：unsignedInt 类型的值。  <br/> |
|DisplayWidth  <br/> |xsd：unsignedInt  <br/> |可选  <br/> ||xsd：unsignedInt 类型的值。  <br/> |
|Hyperlink  <br/> |xsd：boolean  <br/> |可选  <br/> ||xsd：boolean 类型的值。  <br/> |
|标签  <br/> |xsd：string  <br/> |必需  <br/> ||xsd：string 类型的值。  <br/> |
|LangID  <br/> |xsd：unsignedInt  <br/> |可选  <br/> ||xsd：unsignedInt 类型的值。  <br/> |
|映射  <br/> |xsd：boolean  <br/> |可选  <br/> ||xsd：boolean 类型的值。  <br/> |
|名称  <br/> |xsd：string  <br/> |必需  <br/> ||xsd：string 类型的值。  <br/> |
|OrigLabel  <br/> |xsd：string  <br/> |可选  <br/> ||xsd：string 类型的值。  <br/> |
|UnitType  <br/> |xsd：string  <br/> |可选  <br/> ||xsd：string 类型的值。  <br/> |
   

