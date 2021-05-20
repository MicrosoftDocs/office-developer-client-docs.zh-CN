---
title: 'SnapAngles_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1110a656-d8cd-19d0-1af0-31a6675bf89b
ms.openlocfilehash: 1ea5c6d907bf3b3af5664ce3c6f97dfbaa3fd442
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540355"
---
# <a name="snapangles_type-complextype-visio-xml"></a>SnapAngles_Type COMPLEXType (Visio XML) 

## <a name="type-information"></a>类型信息

|||
|:-----|:-----|
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|**架构文件** <br/> |VisioSchema15-2012-06-05.xsd  <br/> |
|**扩展基** <br/> |无  <br/> |
   
## <a name="definition"></a>定义

```XML
          <xs:complexType name="SnapAngles_Type">
          
          <xs:sequence>
    <xs:element name="SnapAngle"  type="SnapAngle_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[SnapAngle](snapangle-element-snapangles_type-complextypevisio-xml.md) <br/> |[SnapAngle_Type](snapangle_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a>Attributes

无。
  

