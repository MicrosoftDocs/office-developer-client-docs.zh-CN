---
title: 'current 元素 (weatherType complexType)  (Outlook Weather Information Schema) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d592a396-f935-c44c-409f-b849c327cfbd
description: 指定当前天气状况。
ms.openlocfilehash: 1303212da1336112599ae5328498cca0d4ab5f89
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541006"
---
# <a name="current-element-weathertype-complextype-outlook-weather-information-schema"></a>current 元素 (weatherType complexType)  (Outlook Weather Information Schema) 

指定当前天气状况。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[currentType](currenttype-complextype-outlook-weather-information-schema.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|**架构文件** <br/> |getweatherinfo.xsd  <br/> |
   
## <a name="definition"></a>定义

```XML
<xs:element name="current"      type="currentType">
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
|date  <br/> |xs：date  <br/> |必需  <br/> |指定今天的日期。  <br/> |xs：date 类型的值  <br/> |
|day  <br/> |xs：string  <br/> |可选  <br/> |指定预测的一天。  <br/> |xs：string 类型的值  <br/> |
|感觉相似  <br/> |xs：integer  <br/> |必需  <br/> |指定当前天气的温度。  <br/> |xs：integer 类型的值  <br/> |
|一些  <br/> |xs：integer  <br/> |必需  <br/> |指定当前的数值数值。  <br/> |xs：integer 类型的值  <br/> |
|观察点  <br/> |xs：string  <br/> |必需  <br/> |指定从何处观测当前天气信息。  <br/> |xs：string 类型的值  <br/> |
|观察时间  <br/> |xs：time  <br/> |必需  <br/> |指定何时观测到当前天气信息。  <br/> |xs：time 类型的值  <br/> |
|shortday  <br/> |xs：string  <br/> |可选  <br/> |以缩写形式指定一天。  <br/> |xs：string 类型的值  <br/> |
|skycode  <br/> |xs：integer  <br/> |必需  <br/> |指定当前天气条件的整数代码。  <br/> |xs：integer 类型的值  <br/> |
|skytext  <br/> |xs：string  <br/> |必需  <br/> |指定描述当前天气条件的一到两个单词。  <br/> |xs：string 类型的值  <br/> |
|temperature  <br/> |xs：integer  <br/> |必需  <br/> |指定位置的当前温度。  <br/> |xs：integer 类型的值  <br/> |
|winddisplay  <br/> |xs：string  <br/> |必需  <br/> |一个描述当前温度条件的字符串。  <br/> |xs：string 类型的值  <br/> |
|将  <br/> |xs：integer  <br/> |必需  <br/> |指定当前数值的时速值。  <br/> |xs：integer 类型的值  <br/> |
   

