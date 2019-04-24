---
title: CellDef_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 87ea346d-1786-dc87-073d-8e7459b7fef1
ms.openlocfilehash: bdcfadc36f278fc97b8589b2989d214e5f4b3333
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327123"
---
# <a name="celldeftype-complextype-visio-xml"></a>CellDef_Type 复杂类型 ("Visio XML")

## <a name="type-information"></a>类型信息

|||
|:-----|:-----|
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|**架构文件** <br/> |VisioSchema15-2012-06-05  <br/> |
|**扩展基** <br/> |无  <br/> |
   
## <a name="definition"></a>定义

```XML
      <xs:complexType name="CellDef_Type">
    <xs:attribute name="N"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="T"
  type="xsd:token"
     use="required"
    />
    <xs:attribute name="F"
  type="xsd:string"
    />
    <xs:attribute name="IX"
  type="xsd:unsignedByte"
    />
    <xs:attribute name="S"
  type="xsd:unsignedByte"
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
|F  <br/> |xsd: string  <br/> |可选  <br/> ||xsd: string 类型的值。  <br/> |
|IX  <br/> |xsd: unsignedByte  <br/> |可选  <br/> ||xsd: unsignedByte 类型的值。  <br/> |
|N  <br/> |xsd: string  <br/> |必需  <br/> ||xsd: string 类型的值。  <br/> |
|S  <br/> |xsd: unsignedByte  <br/> |可选  <br/> ||xsd: unsignedByte 类型的值。  <br/> |
|T  <br/> |xsd: token  <br/> |必需  <br/> ||xsd: 令牌类型的值。  <br/> |
   

