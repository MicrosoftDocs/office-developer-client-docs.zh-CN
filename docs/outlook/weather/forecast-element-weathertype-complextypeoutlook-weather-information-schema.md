---
title: 预报元素 (weatherType 复杂类型) (Outlook 天气信息架构)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9124fa30-d58b-8354-91e9-8d2237a8251d
description: '指定至少三天前的后续天气条件, 包括今天: 今天、明天、一天后。'
ms.openlocfilehash: 01604796d4460cc14005ee00ea6b8f46f04d4742
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339562"
---
# <a name="forecast-element-weathertype-complextype-outlook-weather-information-schema"></a>预报元素 (weatherType 复杂类型) (Outlook 天气信息架构)

指定至少三天前的后续天气条件, 包括今天: 今天、明天、一天后。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[forecastType](forecasttype-complextype-outlook-weather-information-schema.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|**架构文件** <br/> |getweatherinfo  <br/> |
   
## <a name="definition"></a>定义

```XML
<xs:element name="forecast"      type="forecastType" minOccurs="3"     maxOccurs="unbounded"    >
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
|date  <br/> |xs: date  <br/> |必需  <br/> |指定预测的日期。  <br/> |类型 xs: date 的值  <br/> |
|为期  <br/> |xs: string  <br/> |必需  <br/> |指定预测的日期。  <br/> |类型 xs: string 的值  <br/> |
|高效  <br/> |xs: integer  <br/> |必需  <br/> |指定预测的最高温度。  <br/> |类型 xs: integer 的值  <br/> |
|降低  <br/> |xs: integer  <br/> |必需  <br/> |指定预测的最低温度。  <br/> |类型 xs: integer 的值  <br/> |
|precip  <br/> |xs: integer  <br/> |必需  <br/> |指定 precipitation 的百分比可能性。  <br/> |类型 xs: integer 的值  <br/> |
|shortday  <br/> |xs: string  <br/> |必需  <br/> |指定缩写形式的日期。  <br/> |类型 xs: string 的值  <br/> |
|skycodeday  <br/> |xs: integer  <br/> |必需  <br/> |指定预测条件的代码。  <br/> |类型 xs: integer 的值  <br/> |
|skytextday  <br/> |xs: string  <br/> |必需  <br/> |指定一到两个描述预测条件的词。  <br/> |类型 xs: string 的值  <br/> |
   

