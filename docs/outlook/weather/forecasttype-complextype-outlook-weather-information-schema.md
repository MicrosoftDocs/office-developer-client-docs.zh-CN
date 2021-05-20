---
title: 'forecastType complexType (Outlook天气信息架构) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6301d6b6-34fa-af8d-e682-605d35cfdf47
description: 定义有关位置的天气预报条件的参数。
ms.openlocfilehash: e799ebbea72daa1788aedbdcadbc523b5e4dff0d
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540950"
---
# <a name="forecasttype-complextype-outlook-weather-information-schema"></a>forecastType complexType (Outlook天气信息架构) 

定义有关位置的天气预报条件的参数。
  
## <a name="type-information"></a>类型信息

|||
|:-----|:-----|
|**命名空间** <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|**架构文件** <br/> |getweatherinfo.xsd  <br/> |
|**扩展基** <br/> |无  <br/> |
   
## <a name="definition"></a>定义

```XML
       <xs:complexType name="forecastType">
     <xs:attribute name="shortday"   type="xs:string"      use="required"     />
     <xs:attribute name="day"   type="xs:string"      use="required"     />
     <xs:attribute name="date"   type="xs:date"      use="required"     />
     <xs:attribute name="precip"   type="xs:integer"      use="required"     />
     <xs:attribute name="skytextday"   type="xs:string"      use="required"     />
     <xs:attribute name="skycodeday"   type="xs:integer"      use="required"     />
     <xs:attribute name="high"   type="xs:integer"      use="required"     />
     <xs:attribute name="low"   type="xs:integer"      use="required"     />
       </xs:complexType>

```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|date  <br/> |xs：date  <br/> |必需  <br/> |指定预测的日期。  <br/> |xs：date 类型的值  <br/> |
|day  <br/> |xs：string  <br/> |必需  <br/> |指定预测的一天。  <br/> |xs：string 类型的值  <br/> |
|high  <br/> |xs：integer  <br/> |必需  <br/> |指定预测的最高温度。  <br/> |xs：integer 类型的值  <br/> |
|low  <br/> |xs：integer  <br/> |必需  <br/> |指定预测的最低温度。  <br/> |xs：integer 类型的值  <br/> |
|precip  <br/> |xs：integer  <br/> |必需  <br/> |指定可能性的百分比。  <br/> |xs：integer 类型的值  <br/> |
|shortday  <br/> |xs：string  <br/> |必需  <br/> |以缩写形式指定一天。  <br/> |xs：string 类型的值  <br/> |
|skycodeday  <br/> |xs：integer  <br/> |必需  <br/> |指定预测条件的代码。  <br/> |xs：integer 类型的值  <br/> |
|skytextday  <br/> |xs：string  <br/> |必需  <br/> |指定描述预测条件的一到两个单词。  <br/> |xs：string 类型的值  <br/> |
   

