---
title: 天气元素 （weatherdata 元素） （Outlook 天气位置架构）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1127956a-37aa-c39e-60b4-343dcc4ead82
description: 指定报告天气位置上。
ms.openlocfilehash: f6642b3f477b9fe45ed0e6a43efcd40e21559b7e
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398295"
---
# <a name="weather-element-weatherdata-element-outlook-weather-location-schema"></a>天气元素 （weatherdata 元素） （Outlook 天气位置架构）

指定报告天气位置上。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[weatherType](weathertype-complextype-outlook-weather-location-schema.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/outlook/15/getweatherlocation.xsd  <br/> |
|**架构文件** <br/> |getweatherlocation.xsd  <br/> |
   
## <a name="definition"></a>定义

```XML
<xs:element name="weather"      type="weatherType" maxOccurs="unbounded"    >
  </xs:element>  

```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[weatherdata](weatherdata-element-outlook-weather-location-schema.md) <br/> ||定义的天气元素。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|weatherlocationcode  <br/> |xs:string  <br/> |必需  <br/> |指定与要区分具有相同名称的多个位置的位置相关联的代码。  <br/> |类型将一个值  <br/> |
|weatherlocationname  <br/> |xs:string  <br/> |必需  <br/> |指定的位置的名称。  <br/> |类型将一个值  <br/> |
   

