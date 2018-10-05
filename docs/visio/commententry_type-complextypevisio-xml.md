---
title: CommentEntry_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6d9e99b8-fcd6-f36b-960e-bcf3a23afe04
ms.openlocfilehash: eabfe218414874cdc7f10234ed6eeb1fa2f75cf4
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384792"
---
# <a name="commententrytype-complextype-visio-xml"></a>CommentEntry_Type 复杂类型 (Visio XML)

## <a name="type-information"></a>类型信息

|||
|:-----|:-----|
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|**架构文件** <br/> |VisioSchema15 2012 06 05.xsd  <br/> |
|**扩展基** <br/> |xsd: string  <br/> |
   
## <a name="definition"></a>定义

```XML
      <xs:complexType name="CommentEntry_Type">
        <xs:complexContent>
        <xs:extension base="xsd:string">
      
    <xs:attribute name="AuthorID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="PageID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="ShapeID"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="Date"
  type="xsd:dateTime"
     use="required"
    />
    <xs:attribute name="EditDate"
  type="xsd:dateTime"
    />
    <xs:attribute name="Done"
  type="xsd:boolean"
    />
    <xs:attribute name="CommentID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="AutoCommentType"
  type="xsd:unsignedInt"
    />
        </xs:extension>
        </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|作者 Id  <br/> |xsd:unsignedInt  <br/> |必需  <br/> ||Xsd:unsignedInt 类型的值。  <br/> |
|AutoCommentType  <br/> |xsd:unsignedInt  <br/> |可选  <br/> ||Xsd:unsignedInt 类型的值。  <br/> |
|CommentID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> ||Xsd:unsignedInt 类型的值。  <br/> |
|Date  <br/> |化  <br/> |必需  <br/> ||化类型的值。  <br/> |
|完成  <br/> |化  <br/> |可选  <br/> ||化类型的值。  <br/> |
|EditDate  <br/> |化  <br/> |可选  <br/> ||化类型的值。  <br/> |
|PageID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> ||Xsd:unsignedInt 类型的值。  <br/> |
|ShapeID  <br/> |xsd:unsignedInt  <br/> |可选  <br/> ||Xsd:unsignedInt 类型的值。  <br/> |
   

