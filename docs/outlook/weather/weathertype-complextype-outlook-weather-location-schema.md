---
title: weatherType 复杂类型 (Outlook 天气位置架构)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f8054fd9-85ba-fcf6-c96d-a54095d5238c
description: 定义有关位置的天气条件的参数。
ms.openlocfilehash: f7d33cb018daf4ece2ba468b9ebe92b0fc7b1545
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542917"
---
# <a name="weathertype-complextype-outlook-weather-location-schema"></a>weatherType 复杂类型 (Outlook 天气位置架构)

定义有关位置的天气条件的参数。
  
## <a name="type-information"></a>类型信息

|||
|:-----|:-----|
|**命名空间** <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherlocation.xsd  <br/> |
|**架构文件** <br/> |getweatherlocation  <br/> |
|**扩展基** <br/> |无  <br/> |
   
## <a name="definition"></a>定义

```XML
       <xs:complexType name="weatherType">
     <xs:attribute name="weatherlocationname"   type="xs:string"      use="required"     />
     <xs:attribute name="weatherlocationcode"   type="xs:string"      use="required"     />
       </xs:complexType>

```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|weatherlocationcode  <br/> |xs: string  <br/> |必需  <br/> |指定与位置相关联的代码, 以区分具有相同名称的多个位置。  <br/> |类型 xs: string 的值  <br/> |
|表示 weatherlocationname  <br/> |xs: string  <br/> |必需  <br/> |指定位置的名称。  <br/> |类型 xs: string 的值  <br/> |
   

