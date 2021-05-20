---
title: 'Master_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2d799074-13d9-3c98-3bee-b57af9966c81
ms.openlocfilehash: 22b619149fc5393f085ca6e245c65ed6058538ae
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538065"
---
# <a name="master_type-complextype-visio-xml"></a>Master_Type COMPLEXType (Visio XML) 

## <a name="type-information"></a>类型信息

|||
|:-----|:-----|
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|**架构文件** <br/> |VisioSchema15-2012-06-05.xsd  <br/> |
|**扩展基** <br/> |无  <br/> |
   
## <a name="definition"></a>定义

```XML
          <xs:complexType name="Master_Type">
          
          <xs:all>
    <xs:element name="PageSheet"  type="PageSheet_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="Rel"  type="Rel_Type"
     minOccurs="1"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="Icon"  type="Icon_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
      </xs:all>
    <xs:attribute name="ID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="BaseID"
  type="xsd:string"
    />
    <xs:attribute name="UniqueID"
  type="xsd:string"
    />
    <xs:attribute name="MatchByName"
  type="xsd:boolean"
    />
    <xs:attribute name="Name"
  type="xsd:string"
    />
    <xs:attribute name="NameU"
  type="xsd:string"
    />
    <xs:attribute name="IsCustomName"
  type="xsd:boolean"
    />
    <xs:attribute name="IsCustomNameU"
  type="xsd:boolean"
    />
    <xs:attribute name="IconSize"
  type="xsd:unsignedShort"
    />
    <xs:attribute name="PatternFlags"
  type="xsd:unsignedShort"
    />
    <xs:attribute name="Prompt"
  type="xsd:string"
    />
    <xs:attribute name="Hidden"
  type="xsd:boolean"
    />
    <xs:attribute name="IconUpdate"
  type="xsd:boolean"
    />
    <xs:attribute name="AlignName"
  type="xsd:unsignedShort"
    />
    <xs:attribute name="MasterType"
  type="xsd:unsignedShort"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Icon](icon-element-master_type-complextypevisio-xml.md) <br/> |[Icon_Type](icon_type-complextypevisio-xml.md) <br/> ||
|[PageSheet](pagesheet-element-master_type-complextypevisio-xml.md) <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> ||
|[Rel](rel-element-master_type-complextypevisio-xml.md) <br/> |[Rel_Type](rel_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|AlignName  <br/> |xsd：unsignedShort  <br/> |可选  <br/> ||xsd：unsignedShort 类型的值。  <br/> |
|BaseID  <br/> |xsd：string  <br/> |可选  <br/> ||xsd：string 类型的值。  <br/> |
|Hidden  <br/> |xsd：boolean  <br/> |可选  <br/> ||xsd：boolean 类型的值。  <br/> |
|IconSize  <br/> |xsd：unsignedShort  <br/> |可选  <br/> ||xsd：unsignedShort 类型的值。  <br/> |
|IconUpdate  <br/> |xsd：boolean  <br/> |可选  <br/> ||xsd：boolean 类型的值。  <br/> |
|ID  <br/> |xsd：unsignedInt  <br/> |必需  <br/> ||xsd：unsignedInt 类型的值。  <br/> |
|IsCustomName  <br/> |xsd：boolean  <br/> |可选  <br/> ||xsd：boolean 类型的值。  <br/> |
|IsCustomNameU  <br/> |xsd：boolean  <br/> |可选  <br/> ||xsd：boolean 类型的值。  <br/> |
|MasterType  <br/> |xsd：unsignedShort  <br/> |可选  <br/> ||xsd：unsignedShort 类型的值。  <br/> |
|MatchByName  <br/> |xsd：boolean  <br/> |可选  <br/> ||xsd：boolean 类型的值。  <br/> |
|名称  <br/> |xsd：string  <br/> |可选  <br/> ||xsd：string 类型的值。  <br/> |
|NameU  <br/> |xsd：string  <br/> |可选  <br/> ||xsd：string 类型的值。  <br/> |
|PatternFlags  <br/> |xsd：unsignedShort  <br/> |可选  <br/> ||xsd：unsignedShort 类型的值。  <br/> |
|Prompt  <br/> |xsd：string  <br/> |可选  <br/> ||xsd：string 类型的值。  <br/> |
|UniqueID  <br/> |xsd：string  <br/> |可选  <br/> ||xsd：string 类型的值。  <br/> |
   

