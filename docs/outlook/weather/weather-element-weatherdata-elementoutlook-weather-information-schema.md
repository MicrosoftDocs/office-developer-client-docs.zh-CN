---
title: 天气元素 （weatherdata 元素） （Outlook 天气信息架构）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: de3c35ef-84a3-b991-7c98-3eca720c9ba0
description: 指定一个位置的天气条件。
ms.openlocfilehash: 19e6669d51aa38d10587c6334aef0409f31baf58
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25390658"
---
# <a name="weather-element-weatherdata-element-outlook-weather-information-schema"></a>天气元素 （weatherdata 元素） （Outlook 天气信息架构）

指定一个位置的天气条件。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[weatherType](weathertype-complextype-outlook-weather-information-schema.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|**架构文件** <br/> |getweatherinfo.xsd  <br/> |
   
## <a name="definition"></a>定义

```XML
<xs:element name="weather"      type="weatherType">
  </xs:element>  

```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[weatherdata](weatherdata-element-outlook-weather-information-schema.md) <br/> ||定义的天气元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[当前](current-element-weathertype-complextypeoutlook-weather-information-schema.md) <br/> |[currentType](currenttype-complextype-outlook-weather-information-schema.md) <br/> |指定当前的天气条件。  <br/> |
|[预测](forecast-element-weathertype-complextypeoutlook-weather-information-schema.md) <br/> |[forecastType](forecasttype-complextype-outlook-weather-information-schema.md) <br/> |指定至少三天提前包括今天的未来的天气条件： 今天，明天，天 after 明天。  <br/> |
   
### <a name="attributes"></a>Attributes

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|属性  <br/> |xs:string  <br/> |必需  <br/> |指定的天气信息的源。  <br/> |类型将一个值  <br/> |
|degreetype  <br/> |xs:string  <br/> |必需  <br/> |指定的位置，如摄氏度温度的单位。  <br/> |C F  <br/> |
|imagerelativeurl  <br/> |xs:string  <br/> |必需  <br/> |指定位置的图像的 URL。  <br/> |类型将一个值  <br/> |
|timezone  <br/> |xs:integer  <br/> |必需  <br/> |指定格林威治标准时间偏移量。  <br/> |-11 和 12 非独占之间的值  <br/> |
|url  <br/> |xs:string  <br/> |必需  <br/> |指定包含指定的位置的天气信息的天气服务网页的 URL。  <br/> |类型将一个值  <br/> |
|weatherlocationcode  <br/> |xs:string  <br/> |必需  <br/> |指定与用于区分具有相同名称的多个位置的位置相关联的代码。  <br/> |类型将一个值  <br/> |
|weatherlocationname  <br/> |xs:string  <br/> |必需  <br/> |在下拉列表控件中指定的位置的显示名称。  <br/> |类型将一个值  <br/> |
   

