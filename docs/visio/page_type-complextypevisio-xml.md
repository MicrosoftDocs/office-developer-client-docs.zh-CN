---
title: Page_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4bc5c0c4-3ee3-7f63-541a-1f1854d4201c
ms.openlocfilehash: 3a0153b724539136fe142c2489badcf9895af765
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34537981"
---
# <a name="pagetype-complextype-visio-xml"></a>Page_Type 复杂类型 (Visio XML)

## <a name="type-information"></a>类型信息

|||
|:-----|:-----|
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|**架构文件** <br/> |VisioSchema15-2012-06-05  <br/> |
|**扩展基** <br/> |无  <br/> |
   
## <a name="definition"></a>定义

```XML
          <xs:complexType name="Page_Type">
          
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
    
      </xs:all>
    <xs:attribute name="ID"
  type="xsd:unsignedInt"
     use="required"
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
    <xs:attribute name="Background"
  type="xsd:boolean"
    />
    <xs:attribute name="BackPage"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="ViewScale"
  type="xsd:double"
    />
    <xs:attribute name="ViewCenterX"
  type="xsd:double"
    />
    <xs:attribute name="ViewCenterY"
  type="xsd:double"
    />
    <xs:attribute name="ReviewerID"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="AssociatedPage"
  type="xsd:unsignedInt"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[PageSheet](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> ||
|[相对](rel-element-page_type-complextypevisio-xml.md) <br/> |[Rel_Type](rel_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|AssociatedPage  <br/> |xsd: unsignedInt  <br/> |可选  <br/> ||Xsd: unsignedInt 类型的值。  <br/> |
|背景  <br/> |xsd: boolean  <br/> |可选  <br/> ||Xsd: boolean 类型的值。  <br/> |
|BackPage  <br/> |xsd: unsignedInt  <br/> |可选  <br/> ||Xsd: unsignedInt 类型的值。  <br/> |
|ID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> ||Xsd: unsignedInt 类型的值。  <br/> |
|IsCustomName  <br/> |xsd: boolean  <br/> |可选  <br/> ||Xsd: boolean 类型的值。  <br/> |
|IsCustomNameU  <br/> |xsd: boolean  <br/> |可选  <br/> ||Xsd: boolean 类型的值。  <br/> |
|名称  <br/> |xsd: string  <br/> |可选  <br/> ||Xsd: string 类型的值。  <br/> |
|NameU  <br/> |xsd: string  <br/> |可选  <br/> ||Xsd: string 类型的值。  <br/> |
|ReviewerID  <br/> |xsd: unsignedInt  <br/> |可选  <br/> ||Xsd: unsignedInt 类型的值。  <br/> |
|ViewCenterX  <br/> |xsd: double  <br/> |可选  <br/> ||Xsd: double 类型的值。  <br/> |
|ViewCenterY  <br/> |xsd: double  <br/> |可选  <br/> ||Xsd: double 类型的值。  <br/> |
|ViewScale  <br/> |xsd: double  <br/> |可选  <br/> ||Xsd: double 类型的值。  <br/> |
   

