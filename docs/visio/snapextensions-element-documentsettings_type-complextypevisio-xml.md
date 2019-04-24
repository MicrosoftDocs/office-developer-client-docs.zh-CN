---
title: SnapExtensions 元素 (DocumentSettings_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d55b6676-125f-7cf1-509d-21dee548f5a1
description: 指定是否为活动窗口启用或禁用特定的快照扩展设置。
ms.openlocfilehash: 9f21653fca7f1f5fa7be7449f1e588cf5ef67263
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334529"
---
# <a name="snapextensions-element-documentsettingstype-complextype-visio-xml"></a>SnapExtensions 元素 (DocumentSettings_Type 复杂类型) ("Visio XML")

指定是否为活动窗口启用或禁用特定的快照扩展设置。 
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[SnapExtensions_Type](snapextensions_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |document .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
<xs:element name="SnapExtensions" type="SnapExtensions_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DocumentSettings](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[DocumentSettings_Type](documentsettings_type-complextypevisio-xml.md) <br/> |包含指定文档设置的元素。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>Attributes

无。
  
## <a name="remarks"></a>注解

**SnapExtensions**元素的值可以是下表中的值的总和。 
  
|**Value**|**说明**|
|:-----|:-----|
|0  <br/> |不与任何内容对齐。  <br/> |
|1  <br/> |与对齐框的延伸对齐。  <br/> |
|双面  <br/> |居中轴延长线。  <br/> |
|4  <br/> |与曲线相切延长线对齐。  <br/> |
|utf-8  <br/> |与终结点扩展对齐。  <br/> |
|位  <br/> |与中点扩展对齐。  <br/> |
|32  <br/> |与线性延伸对齐。  <br/> |
|64  <br/> |与曲线延长线对齐。  <br/> |
|128  <br/> |与终结点垂直扩展对齐。  <br/> |
|256  <br/> |与中点垂直延伸对齐。  <br/> |
|512  <br/> |对齐终结点水平扩展。  <br/> |
|1024  <br/> |与终结点垂直扩展对齐。  <br/> |
|2048  <br/> |与椭圆中心延伸对齐。  <br/> |
|4096  <br/> |对齐等角扩展。  <br/> |
   

