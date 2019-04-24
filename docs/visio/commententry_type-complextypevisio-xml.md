---
title: CommentEntry_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6d9e99b8-fcd6-f36b-960e-bcf3a23afe04
ms.openlocfilehash: eabfe218414874cdc7f10234ed6eeb1fa2f75cf4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334942"
---
# <a name="commententrytype-complextype-visio-xml"></a>CommentEntry_Type 复杂类型 ("Visio XML")

## <a name="type-information"></a>类型信息

|||
|:-----|:-----|
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|**架构文件** <br/> |VisioSchema15-2012-06-05  <br/> |
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

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|AuthorID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> ||xsd: unsignedInt 类型的值。  <br/> |
|AutoCommentType  <br/> |xsd: unsignedInt  <br/> |可选  <br/> ||xsd: unsignedInt 类型的值。  <br/> |
|CommentID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> ||xsd: unsignedInt 类型的值。  <br/> |
|日期  <br/> |xsd: dateTime  <br/> |必需  <br/> ||xsd: dateTime 类型的值。  <br/> |
|Done  <br/> |xsd: boolean  <br/> |可选  <br/> ||xsd: boolean 类型的值。  <br/> |
|EditDate  <br/> |xsd: dateTime  <br/> |可选  <br/> ||xsd: dateTime 类型的值。  <br/> |
|PageID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> ||xsd: unsignedInt 类型的值。  <br/> |
|ShapeID  <br/> |xsd: unsignedInt  <br/> |可选  <br/> ||xsd: unsignedInt 类型的值。  <br/> |
   

