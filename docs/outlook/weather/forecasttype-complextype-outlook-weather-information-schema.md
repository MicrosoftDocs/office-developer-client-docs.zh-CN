---
title: forecastType 复杂类型 （Outlook 天气信息架构）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6301d6b6-34fa-af8d-e682-605d35cfdf47
description: 定义有关的位置的预报的天气条件的参数。
ms.openlocfilehash: 886c6cdbbeb9f07564854dc6a62cbcdad9703b62
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779337"
---
# <a name="forecasttype-complextype-outlook-weather-information-schema"></a>forecastType 复杂类型 （Outlook 天气信息架构）

定义有关的位置的预报的天气条件的参数。
  
## <a name="type-information"></a>类型信息

|||
|:-----|:-----|
|**命名空间** <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|**架构文件** <br/> |getweatherinfo.xsd  <br/> |
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

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
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
   

