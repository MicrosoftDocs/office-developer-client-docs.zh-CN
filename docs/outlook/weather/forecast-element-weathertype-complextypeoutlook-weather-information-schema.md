---
title: 预测元素 （weatherType 复杂类型） （Outlook 天气信息架构）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9124fa30-d58b-8354-91e9-8d2237a8251d
description: 指定至少三天提前包括今天的未来的天气条件： 今天，明天，天 after 明天。
ms.openlocfilehash: c618b753ddf8a72fce270800675982f1a7f7af5b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779343"
---
# <a name="forecast-element-weathertype-complextype-outlook-weather-information-schema"></a>预测元素 （weatherType 复杂类型） （Outlook 天气信息架构）

指定至少三天提前包括今天的未来的天气条件： 今天，明天，天 after 明天。
  
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

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[天气](weather-element-weatherdata-elementoutlook-weather-information-schema.md) <br/> |[weatherType](weathertype-complextype-outlook-weather-information-schema.md) <br/> |指定一个位置的天气条件。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|date  <br/> |xs: date  <br/> |必需  <br/> |指定为预测的日期。  <br/> |值为类型 xs: date  <br/> |
|一天  <br/> |xs:string  <br/> |必需  <br/> |指定为预测一天。  <br/> |类型将一个值  <br/> |
|高  <br/> |xs:integer  <br/> |必需  <br/> |指定的预测的最高温度。  <br/> |值为类型 xs:integer  <br/> |
|低  <br/> |xs:integer  <br/> |必需  <br/> |指定的预测的最低温度。  <br/> |值为类型 xs:integer  <br/> |
|precip  <br/> |xs:integer  <br/> |必需  <br/> |指定雨百分比的可能性。  <br/> |值为类型 xs:integer  <br/> |
|shortday  <br/> |xs:string  <br/> |必需  <br/> |缩写形式指定一天。  <br/> |类型将一个值  <br/> |
|skycodeday  <br/> |xs:integer  <br/> |必需  <br/> |指定的预测的条件的代码。  <br/> |值为类型 xs:integer  <br/> |
|skytextday  <br/> |xs:string  <br/> |必需  <br/> |指定一到两个单词的描述的预测的条件。  <br/> |类型将一个值  <br/> |
   

