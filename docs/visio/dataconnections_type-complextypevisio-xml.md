---
title: 'DataConnections_Type XML (Visio complexType) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 83a3c944-9582-bf80-ec2a-7a752da03cd3
ms.openlocfilehash: 712632a74b0ffad6d0c9ca8745d67018518d87de
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542455"
---
# <a name="dataconnections_type-complextype-visio-xml"></a>DataConnections_Type XML (Visio complexType) 

## <a name="type-information"></a>类型信息

|||
|:-----|:-----|
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|**架构文件** <br/> |VisioSchema15-2012-06-05.xsd  <br/> |
|**扩展基** <br/> |无  <br/> |
   
## <a name="definition"></a>定义

```XML
          <xs:complexType name="DataConnections_Type">
          
          <xs:sequence>
    <xs:element name="DataConnection"  type="DataConnection_Type"
     minOccurs="1"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="NextID"
  type="xsd:unsignedInt"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DataConnection](dataconnection-element-dataconnections_type-complextypevisio-xml.md) <br/> |[DataConnection_Type](dataconnection_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|NextID  <br/> |xsd：unsignedInt  <br/> |必需  <br/> ||xsd：unsignedInt 类型的值。  <br/> |
   

