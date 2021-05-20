---
title: 'forecast 元素 (weatherType complexType)  (Outlook Weather Information Schema) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9124fa30-d58b-8354-91e9-8d2237a8251d
description: 指定至少提前三天的未来天气条件，包括今天、明天、明天后一天。
ms.openlocfilehash: 5e442ee5995bbd51c5e518162286bc199a625dbd
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540978"
---
# <a name="forecast-element-weathertype-complextype-outlook-weather-information-schema"></a>forecast 元素 (weatherType complexType)  (Outlook Weather Information Schema) 

指定至少提前三天的未来天气条件，包括今天、明天、明天后一天。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[forecastType](forecasttype-complextype-outlook-weather-information-schema.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|**架构文件** <br/> |getweatherinfo.xsd  <br/> |
   
## <a name="definition"></a>定义

```XML
<xs:element name="forecast"      type="forecastType" minOccurs="3"     maxOccurs="unbounded"    >
  </xs:element>  

```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[weather](weather-element-weatherdata-elementoutlook-weather-information-schema.md) <br/> |[weatherType](weathertype-complextype-outlook-weather-information-schema.md) <br/> |指定位置的天气状况。  <br/> |
   
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
   

