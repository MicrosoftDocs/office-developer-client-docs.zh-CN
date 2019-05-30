---
title: 气象元素 (weatherdata 元素) (Outlook 天气信息架构)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: de3c35ef-84a3-b991-7c98-3eca720c9ba0
description: 指定位置的天气情况。
ms.openlocfilehash: 18669dfc4636c28e03a582bc0c8df512aa38a4e4
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541265"
---
# <a name="weather-element-weatherdata-element-outlook-weather-information-schema"></a>气象元素 (weatherdata 元素) (Outlook 天气信息架构)

指定位置的天气情况。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[weatherType](weathertype-complextype-outlook-weather-information-schema.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|**架构文件** <br/> |getweatherinfo  <br/> |
   
## <a name="definition"></a>定义

```XML
<xs:element name="weather"      type="weatherType">
  </xs:element>  

```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[weatherdata](weatherdata-element-outlook-weather-information-schema.md) <br/> ||定义气象元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[目前](current-element-weathertype-complextypeoutlook-weather-information-schema.md) <br/> |[currentType](currenttype-complextype-outlook-weather-information-schema.md) <br/> |指定当前天气情况。  <br/> |
|[预测](forecast-element-weathertype-complextypeoutlook-weather-information-schema.md) <br/> |[forecastType](forecasttype-complextype-outlook-weather-information-schema.md) <br/> |指定至少三天前的后续天气条件, 包括今天: 今天、明天、一天后。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|attribution  <br/> |xs: string  <br/> |必需  <br/> |指定天气信息的来源。  <br/> |类型 xs: string 的值  <br/> |
|degreetype  <br/> |xs: string  <br/> |必需  <br/> |指定位置温度的单位 (例如, 摄氏温度)。  <br/> |C、F  <br/> |
|imagerelativeurl  <br/> |xs: string  <br/> |必需  <br/> |指定位置的图像的 URL。  <br/> |类型 xs: string 的值  <br/> |
|时区  <br/> |xs: integer  <br/> |必需  <br/> |指定 GMT 偏移量。  <br/> |介于-11 和12之间的值 (含)  <br/> |
|url  <br/> |xs: string  <br/> |必需  <br/> |指定包含指定位置的天气信息的天气服务网页的 URL。  <br/> |类型 xs: string 的值  <br/> |
|weatherlocationcode  <br/> |xs: string  <br/> |必需  <br/> |指定与用于区分具有相同名称的多个位置的位置相关联的代码。  <br/> |类型 xs: string 的值  <br/> |
|表示 weatherlocationname  <br/> |xs: string  <br/> |必需  <br/> |指定在下拉控件中显示的位置的名称。  <br/> |类型 xs: string 的值  <br/> |
   

