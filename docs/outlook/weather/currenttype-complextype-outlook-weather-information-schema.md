---
title: currentType 复杂类型 （Outlook 天气信息架构）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9f4663ac-13d3-6c46-f839-ba6bca4047a3
description: 定义有关的当前的天气条件的位置的参数。
ms.openlocfilehash: 55ea2cfa6904d88c695268675bc7a893fa643010
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779342"
---
# <a name="currenttype-complextype-outlook-weather-information-schema"></a>currentType 复杂类型 （Outlook 天气信息架构）

定义有关的当前的天气条件的位置的参数。
  
## <a name="type-information"></a>类型信息

|||
|:-----|:-----|
|**命名空间** <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|**架构文件** <br/> |getweatherinfo.xsd  <br/> |
|**扩展基** <br/> |无  <br/> |
   
## <a name="definition"></a>定义

```XML
       <xs:complexType name="currentType">
     <xs:attribute name="winddisplay"   type="xs:string"      use="required"     />
     <xs:attribute name="windspeed"   type="xs:integer"      use="required"     />
     <xs:attribute name="humidity"   type="xs:integer"      use="required"     />
     <xs:attribute name="feelslike"   type="xs:integer"      use="required"     />
     <xs:attribute name="observationpoint"   type="xs:string"      use="required"     />
     <xs:attribute name="observationtime"   type="xs:time"      use="required"     />
     <xs:attribute name="date"   type="xs:date"      use="required"     />
     <xs:attribute name="skytext"   type="xs:string"      use="required"     />
     <xs:attribute name="skycode"   type="xs:integer"      use="required"     />
     <xs:attribute name="temperature"   type="xs:integer"      use="required"     />
     <xs:attribute name="shortday"   type="xs:string"      use="optional"     />
     <xs:attribute name="day"   type="xs:string"      use="optional"     />
       </xs:complexType>

```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|date  <br/> |xs: date  <br/> |必需  <br/> |指定今天的日期。  <br/> |值为类型 xs: date  <br/> |
|一天  <br/> |xs:string  <br/> |可选  <br/> |指定为预测一天。  <br/> |类型将一个值  <br/> |
|feelslike  <br/> |xs:integer  <br/> |必需  <br/> |指定如何当前天气外观的温度。  <br/> |值为类型 xs:integer  <br/> |
|湿度  <br/> |xs:integer  <br/> |必需  <br/> |指定当前的数字湿度值。  <br/> |值为类型 xs:integer  <br/> |
|observationpoint  <br/> |xs:string  <br/> |必需  <br/> |指定从其中观察到当前的天气信息。  <br/> |类型将一个值  <br/> |
|observationtime  <br/> |xs:time  <br/> |必需  <br/> |指定当在观察到当前的天气信息。  <br/> |值为类型 xs:time  <br/> |
|shortday  <br/> |xs:string  <br/> |可选  <br/> |缩写形式指定一天。  <br/> |类型将一个值  <br/> |
|skycode  <br/> |xs:integer  <br/> |必需  <br/> |指定为当前的天气条件整数代码。  <br/> |值为类型 xs:integer  <br/> |
|skytext  <br/> |xs:string  <br/> |必需  <br/> |指定一到两个单词描述当前天气条件。  <br/> |类型将一个值  <br/> |
|温度  <br/> |xs:integer  <br/> |必需  <br/> |指定当前温度的位置。  <br/> |值为类型 xs:integer  <br/> |
|winddisplay  <br/> |xs:string  <br/> |必需  <br/> |描述的当前风条件的字符串。  <br/> |类型将一个值  <br/> |
|windspeed  <br/> |xs:integer  <br/> |必需  <br/> |指定当前数字风速度值。  <br/> |值为类型 xs:integer  <br/> |
   

