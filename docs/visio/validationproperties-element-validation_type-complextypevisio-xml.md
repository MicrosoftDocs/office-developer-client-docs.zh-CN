---
title: ValidationProperties 元素 (Validation_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a51a60c9-479b-7d7b-860f-bb46fc8b4d63
description: 封装与文档的验证相关的属性。
ms.openlocfilehash: 35e6f3f13eecef826fdef0d664bba35fceb0e069
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538520"
---
# <a name="validationproperties-element-validationtype-complextype-visio-xml"></a>ValidationProperties 元素 (Validation_Type 复杂类型) (Visio XML)

封装与文档的验证相关的属性。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[ValidationProperties_Type](validationproperties_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |验证 .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="ValidationProperties" type="ValidationProperties_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Validation](validation-elementvisio-xml.md) <br/> |[Validation_Type](validation_type-complextypevisio-xml.md) <br/> |存储有关文档图表验证的信息。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|LastValidated  <br/> |xsd: dateTime  <br/> |必需  <br/> |上次验证文档的日期和时间。  <br/> |Xsd: dateTime 类型的值。  <br/> |
|ShowIgnored  <br/> |xsd: boolean  <br/> |必需  <br/> |指定是否在 "问题" 窗口中显示忽略的验证问题。  <br/> |Xsd: boolean 类型的值。  <br/> |
   

