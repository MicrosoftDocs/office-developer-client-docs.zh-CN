---
title: Connect_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2230976b-f2a8-425b-b8b0-a7fd5efb4536
ms.openlocfilehash: 158fad1f3ec18bbc9565229338f4710c145c17e7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327081"
---
# <a name="connecttype-complextype-visio-xml"></a>Connect_Type 复杂类型 ("Visio XML")

## <a name="type-information"></a>类型信息

|||
|:-----|:-----|
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|**架构文件** <br/> |VisioSchema15-2012-06-05  <br/> |
|**扩展基** <br/> |无  <br/> |
   
## <a name="definition"></a>定义

```XML
      <xs:complexType name="Connect_Type">
    <xs:attribute name="FromSheet"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="FromCell"
  type="xsd:string"
    />
    <xs:attribute name="FromPart"
  type="xsd:int"
    />
    <xs:attribute name="ToSheet"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="ToCell"
  type="xsd:string"
    />
    <xs:attribute name="ToPart"
  type="xsd:int"
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
|FromCell  <br/> |xsd: string  <br/> |可选  <br/> ||xsd: string 类型的值。  <br/> |
|FromPart  <br/> |xsd: int  <br/> |可选  <br/> ||xsd: int 类型的值。  <br/> |
|FromSheet  <br/> |xsd: unsignedInt  <br/> |必需  <br/> ||xsd: unsignedInt 类型的值。  <br/> |
|ToCell  <br/> |xsd: string  <br/> |可选  <br/> ||xsd: string 类型的值。  <br/> |
|ToPart  <br/> |xsd: int  <br/> |可选  <br/> ||xsd: int 类型的值。  <br/> |
|ToSheet  <br/> |xsd: unsignedInt  <br/> |必需  <br/> ||xsd: unsignedInt 类型的值。  <br/> |
   

