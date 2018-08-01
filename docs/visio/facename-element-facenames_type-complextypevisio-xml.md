---
title: FaceName 元素 （FaceNames_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b1783f05-ced1-917f-8298-eca4ecfa3912
description: 包含有关字体的信息。
ms.openlocfilehash: 8a66d5294e239e4540939cc7053e1f67a777144d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780201"
---
# <a name="facename-element-facenamestype-complextype-visio-xml"></a>FaceName 元素 （FaceNames_Type 复杂类型） (Visio XML)

包含有关字体的信息。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[FaceName_Type](facename_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |document.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="FaceName" type="FaceName_Type" minOccurs="1" maxOccurs="unbounded" >
</xs:element > 
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[FaceNames](facenames-element-visiodocument_type-complextypevisio-xml.md) <br/> |[FaceNames_Type](facenames_type-complextypevisio-xml.md) <br/> |包含**FaceName**元素的集合。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|CharSets  <br/> |xsd: string  <br/> |可选  <br/> |支持的字符的字体设置。  <br/> |Xsd: string 类型的值。  <br/> |
|Flags  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |这些标志指示以下： 缺少字体、 默认字体、 亚洲字体、 复杂的字体、 垂直字体和字体类型。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|NameU  <br/> |xsd: string  <br/> |必需  <br/> |为 utf-16 Unicode 字符串字体的名称。  <br/> ||
|Panos  <br/> |xsd: string  <br/> |可选  <br/> |字体的 panose 签名。 Panose 是对其根据其 visual 特征进行分类的分类系统的字体。  <br/> |Xsd: string 类型的值。  <br/> |
|UnicodeRanges  <br/> |xsd: string  <br/> |可选  <br/> |支持的 Unicode 范围的字体。  <br/> |Xsd: string 类型的值。  <br/> |
   

