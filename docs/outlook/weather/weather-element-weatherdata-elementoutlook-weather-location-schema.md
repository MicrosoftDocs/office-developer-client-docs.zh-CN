---
title: 气象元素 (weatherdata 元素) (Outlook 天气位置架构)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1127956a-37aa-c39e-60b4-343dcc4ead82
description: 指定要在其上报告天气的位置。
ms.openlocfilehash: a907fb9df02d88d317a73e409ea8738273eb2cb1
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539010"
---
# <a name="weather-element-weatherdata-element-outlook-weather-location-schema"></a>气象元素 (weatherdata 元素) (Outlook 天气位置架构)

指定要在其上报告天气的位置。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[weatherType](weathertype-complextype-outlook-weather-location-schema.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherlocation.xsd  <br/> |
|**架构文件** <br/> |getweatherlocation  <br/> |
   
## <a name="definition"></a>定义

```XML
<xs:element name="weather"      type="weatherType" maxOccurs="unbounded"    >
  </xs:element>  

```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[weatherdata](weatherdata-element-outlook-weather-location-schema.md) <br/> ||定义气象元素。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|weatherlocationcode  <br/> |xs: string  <br/> |必需  <br/> |指定与位置相关联的代码, 以区分具有相同名称的多个位置。  <br/> |类型 xs: string 的值  <br/> |
|表示 weatherlocationname  <br/> |xs: string  <br/> |必需  <br/> |指定位置的名称。  <br/> |类型 xs: string 的值  <br/> |
   

