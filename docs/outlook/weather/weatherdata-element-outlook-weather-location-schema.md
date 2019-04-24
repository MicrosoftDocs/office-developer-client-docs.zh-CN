---
title: weatherdata 元素 (Outlook 天气位置架构)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 14e0c469-31dc-fbe2-0d45-da602df04f13
description: 定义气象元素。
ms.openlocfilehash: ade57264fab592d3314aa9a3376e129a5f3719c0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355032"
---
# <a name="weatherdata-element-outlook-weather-location-schema"></a>weatherdata 元素 (Outlook 天气位置架构)

定义气象元素。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> ||
|**命名空间** <br/> |https://schemas.microsoft.com/office/outlook/15/getweatherlocation.xsd  <br/> |
|**架构文件** <br/> |getweatherlocation  <br/> |
   
## <a name="definition"></a>定义

```XML
    <xs:element name="weatherdata"
    >
          <xs:complexType>
          <xs:sequence>
    <xs:element name="weather"
     type="weatherType" maxOccurs="unbounded"
      >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
    </xs:element>
    
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

无。
  
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[气候](weather-element-weatherdata-elementoutlook-weather-location-schema.md) <br/> |[weatherType](weathertype-complextype-outlook-weather-location-schema.md) <br/> |指定要在其上报告天气的位置。  <br/> |
   
### <a name="attributes"></a>Attributes

无。
  

