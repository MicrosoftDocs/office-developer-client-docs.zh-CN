---
title: SnapExtensions 元素 （DocumentSettings_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d55b6676-125f-7cf1-509d-21dee548f5a1
description: 指定是否启用或禁用活动窗口的特定管理单元扩展设置。
ms.openlocfilehash: 9f21653fca7f1f5fa7be7449f1e588cf5ef67263
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387613"
---
# <a name="snapextensions-element-documentsettingstype-complextype-visio-xml"></a>SnapExtensions 元素 （DocumentSettings_Type 复杂类型） (Visio XML)

指定是否启用或禁用活动窗口的特定管理单元扩展设置。 
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[SnapExtensions_Type](snapextensions_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |document.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
<xs:element name="SnapExtensions" type="SnapExtensions_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DocumentSettings](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[DocumentSettings_Type](documentsettings_type-complextypevisio-xml.md) <br/> |包含指定文档设置的元素。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

无。
  
## <a name="remarks"></a>说明

**SnapExtensions**元素的值可以是下表中值的总和。 
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |不与任何内容对齐。  <br/> |
|1  <br/> |与对齐框延长线对齐。  <br/> |
|2  <br/> |与中心轴扩展对齐。  <br/> |
|4  <br/> |与曲线切线扩展对齐。  <br/> |
|8  <br/> |与终结点扩展对齐。  <br/> |
|16  <br/> |与中点扩展对齐。  <br/> |
|32  <br/> |与直线延长线对齐。  <br/> |
|64  <br/> |与曲线扩展对齐。  <br/> |
|128  <br/> |终结点的垂直扩展名与对齐。  <br/> |
|256  <br/> |与中点 perpendicular 扩展对齐。  <br/> |
|512  <br/> |终结点的水平扩展名与对齐。  <br/> |
|1024  <br/> |终结点的垂直扩展名与对齐。  <br/> |
|2048  <br/> |椭圆中心扩展名与对齐。  <br/> |
|4096  <br/> |与扩展等角对齐。  <br/> |
   

