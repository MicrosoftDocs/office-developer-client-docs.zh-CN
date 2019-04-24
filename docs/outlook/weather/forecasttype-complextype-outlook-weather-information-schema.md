---
title: forecastType 复杂类型 (Outlook 天气信息架构)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6301d6b6-34fa-af8d-e682-605d35cfdf47
description: 定义有关某个位置的预测天气条件的参数。
ms.openlocfilehash: 75f20d7857fac85e1e95d23cf5ac826336648132
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361143"
---
# <a name="forecasttype-complextype-outlook-weather-information-schema"></a>forecastType 复杂类型 (Outlook 天气信息架构)

定义有关某个位置的预测天气条件的参数。
  
## <a name="type-information"></a>类型信息

|||
|:-----|:-----|
|**命名空间** <br/> |https://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|**架构文件** <br/> |getweatherinfo  <br/> |
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

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
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
   

