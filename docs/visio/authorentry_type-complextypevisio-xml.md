---
title: 'AuthorEntry_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6ea7b946-ecd3-1524-5e36-a2c35cb11d7a
ms.openlocfilehash: 41279e9f4ffa0bba17d4f74eb2f40d724589c17d
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34537876"
---
# <a name="authorentry_type-complextype-visio-xml"></a>AuthorEntry_Type COMPLEXType (Visio XML) 

## <a name="type-information"></a>类型信息

|||
|:-----|:-----|
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|**架构文件** <br/> |VisioSchema15-2012-06-05.xsd  <br/> |
|**扩展基** <br/> |无  <br/> |
   
## <a name="definition"></a>定义

```XML
      <xs:complexType name="AuthorEntry_Type">
    <xs:attribute name="Name"
  type="xsd:string"
    />
    <xs:attribute name="Initials"
  type="xsd:string"
    />
    <xs:attribute name="ResolutionID"
  type="xsd:string"
    />
    <xs:attribute name="ID"
  type="xsd:unsignedInt"
     use="required"
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
|ID  <br/> |xsd：unsignedInt  <br/> |必需  <br/> ||xsd：unsignedInt 类型的值。  <br/> |
|Initials  <br/> |xsd：string  <br/> |可选  <br/> ||xsd：string 类型的值。  <br/> |
|名称  <br/> |xsd：string  <br/> |可选  <br/> ||xsd：string 类型的值。  <br/> |
|ResolutionID  <br/> |xsd：string  <br/> |可选  <br/> ||xsd：string 类型的值。  <br/> |
   

