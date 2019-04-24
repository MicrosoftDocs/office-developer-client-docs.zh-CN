---
title: DataRecordSets_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 04448cfa-7eb4-62ca-97d2-409b59a8db90
ms.openlocfilehash: 1705d0ea92e278008c33321f135409373b7317fd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360345"
---
# <a name="datarecordsetstype-complextype-visio-xml"></a>DataRecordSets_Type 复杂类型 ("Visio XML")

## <a name="type-information"></a>类型信息

|||
|:-----|:-----|
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|**架构文件** <br/> |VisioSchema15-2012-06-05  <br/> |
|**扩展基** <br/> |无  <br/> |
   
## <a name="definition"></a>定义

```XML
          <xs:complexType name="DataRecordSets_Type">
          
          <xs:sequence>
    <xs:element name="DataRecordSet"  type="DataRecordSet_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="NextID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="ActiveRecordsetID"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="DataWindowOrder"
  type="xsd:string"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DataRecordSet](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[DataRecordSet_Type](datarecordset_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|ActiveRecordsetID  <br/> |xsd: unsignedInt  <br/> |可选  <br/> ||xsd: unsignedInt 类型的值。  <br/> |
|DataWindowOrder  <br/> |xsd: string  <br/> |可选  <br/> ||xsd: string 类型的值。  <br/> |
|NextID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> ||xsd: unsignedInt 类型的值。  <br/> |
   

