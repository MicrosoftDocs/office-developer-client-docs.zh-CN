---
title: FaceNames 元素 (VisioDocument_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 61e30f57-abd6-9378-45ed-51236ab3d3ee
description: 包含 FaceName 元素的集合。
ms.openlocfilehash: ce18847fdd46a0c703a0df5e8d8c7a877f864d35
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539711"
---
# <a name="facenames-element-visiodocumenttype-complextype-visio-xml"></a>FaceNames 元素 (VisioDocument_Type 复杂类型) (Visio XML)

包含**FaceName**元素的集合。 
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[FaceNames_Type](facenames_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |document .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="FaceNames" type="FaceNames_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[VisioDocument](visiodocument-elementvisio-xml.md) <br/> |[VisioDocument_Type](visiodocument_type-complextypevisio-xml.md) <br/> |Microsoft Visio 文档的根元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[FaceName](facename-element-facenames_type-complextypevisio-xml.md) <br/> |[FaceName_Type](facename_type-complextypevisio-xml.md) <br/> |包含有关字体的信息。  <br/> |
   
### <a name="attributes"></a>Attributes

无。
  

