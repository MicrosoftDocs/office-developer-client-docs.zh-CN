---
title: FaceName 元素 (FaceNames_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b1783f05-ced1-917f-8298-eca4ecfa3912
description: 包含有关字体的信息。
ms.openlocfilehash: 773b5f10607cc6d515671d93d7d4abd9e39e72ff
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541013"
---
# <a name="facename-element-facenamestype-complextype-visio-xml"></a>FaceName 元素 (FaceNames_Type 复杂类型) (Visio XML)

包含有关字体的信息。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[FaceName_Type](facename_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |document .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="FaceName" type="FaceName_Type" minOccurs="1" maxOccurs="unbounded" >
</xs:element > 
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[FaceNames](facenames-element-visiodocument_type-complextypevisio-xml.md) <br/> |[FaceNames_Type](facenames_type-complextypevisio-xml.md) <br/> |包含**FaceName**元素的集合。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|CharSets  <br/> |xsd: string  <br/> |可选  <br/> |受支持的字体字符集。  <br/> |Xsd: string 类型的值。  <br/> |
|Flags  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |指示以下内容的标志: 缺少字体、默认字体、中文字体、复杂字体、垂直字体和字体类型。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|NameU  <br/> |xsd: string  <br/> |必需  <br/> |UTF-16 Unicode 字符串形式的字体名称。  <br/> ||
|Panos  <br/> |xsd: string  <br/> |可选  <br/> |字体的 panose 签名。 Panose 是一个分类系统, 用于根据其视觉特征对它们进行分类。  <br/> |Xsd: string 类型的值。  <br/> |
|UnicodeRanges  <br/> |xsd: string  <br/> |可选  <br/> |所支持的字体的 Unicode 范围。  <br/> |Xsd: string 类型的值。  <br/> |
   

