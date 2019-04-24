---
title: current 元素 (weatherType 复杂类型) (Outlook 天气信息架构)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d592a396-f935-c44c-409f-b849c327cfbd
description: 指定当前天气情况。
ms.openlocfilehash: ce92bdd49ee37f939748586c2d63d8a664f664d2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351469"
---
# <a name="current-element-weathertype-complextype-outlook-weather-information-schema"></a>current 元素 (weatherType 复杂类型) (Outlook 天气信息架构)

指定当前天气情况。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[currentType](currenttype-complextype-outlook-weather-information-schema.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|**架构文件** <br/> |getweatherinfo  <br/> |
   
## <a name="definition"></a>定义

```XML
<xs:element name="current"      type="currentType">
  </xs:element>  

```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[气候](weather-element-weatherdata-elementoutlook-weather-information-schema.md) <br/> |[weatherType](weathertype-complextype-outlook-weather-information-schema.md) <br/> |指定位置的天气情况。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|date  <br/> |xs: date  <br/> |必需  <br/> |指定今天的日期。  <br/> |类型 xs: date 的值  <br/> |
|为期  <br/> |xs: string  <br/> |可选  <br/> |指定预测的日期。  <br/> |类型 xs: string 的值  <br/> |
|feelslike  <br/> |xs: integer  <br/> |必需  <br/> |指定当前天气的外观的温度。  <br/> |类型 xs: integer 的值  <br/> |
|湿度  <br/> |xs: integer  <br/> |必需  <br/> |指定当前的数值湿度值。  <br/> |类型 xs: integer 的值  <br/> |
|observationpoint  <br/> |xs: string  <br/> |必需  <br/> |指定观察当前天气信息的位置。  <br/> |类型 xs: string 的值  <br/> |
|observationtime  <br/> |xs: time  <br/> |必需  <br/> |指定何时在中观察当前天气信息。  <br/> |类型 xs: time 的值  <br/> |
|shortday  <br/> |xs: string  <br/> |可选  <br/> |指定缩写形式的日期。  <br/> |类型 xs: string 的值  <br/> |
|skycode  <br/> |xs: integer  <br/> |必需  <br/> |指定当前天气条件的整数代码。  <br/> |类型 xs: integer 的值  <br/> |
|skytext  <br/> |xs: string  <br/> |必需  <br/> |指定一个描述当前天气情况的两个字。  <br/> |类型 xs: string 的值  <br/> |
|量  <br/> |xs: integer  <br/> |必需  <br/> |指定位置的当前温度。  <br/> |类型 xs: integer 的值  <br/> |
|winddisplay  <br/> |xs: string  <br/> |必需  <br/> |一个描述当前风条件的字符串。  <br/> |类型 xs: string 的值  <br/> |
|windspeed  <br/> |xs: integer  <br/> |必需  <br/> |指定当前的数值风速度值。  <br/> |类型 xs: integer 的值  <br/> |
   

