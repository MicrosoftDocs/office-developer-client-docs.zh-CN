---
title: ColorEntry 元素 (Colors_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3f325ad8-bbc7-28bf-9e48-1fde4fbdbdc0
description: 包含颜色表项。
ms.openlocfilehash: 14ef92069ce8d963ce4a0770324843321804c5cd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358084"
---
# <a name="colorentry-element-colorstype-complextype-visio-xml"></a>ColorEntry 元素 (Colors_Type 复杂类型) ("Visio XML")

包含颜色表项。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[ColorEntry_Type](colorentry_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |document .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="ColorEntry" type="ColorEntry_Type" minOccurs="1" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Colors](colors-element-visiodocument_type-complextypevisio-xml.md) <br/> |[Colors_Type](colors_type-complextypevisio-xml.md) <br/> |包含文档的颜色表。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|IX  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |元素在其父元素中的从零开始的索引。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|RGB  <br/> |xsd: string  <br/> |必需  <br/> |颜色表项的十六进制值。  <br/> |xsd: string 类型的值。  <br/> |
   

