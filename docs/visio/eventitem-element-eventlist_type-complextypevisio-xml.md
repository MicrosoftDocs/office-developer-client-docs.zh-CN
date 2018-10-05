---
title: EventItem 元素 （EventList_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6b347117-a1c1-d090-0d71-ea8528ac70c6
description: 封装了事件代码。
ms.openlocfilehash: 6ed539bd6cb4524b2498b636295442bed917c72a
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25394396"
---
# <a name="eventitem-element-eventlisttype-complextype-visio-xml"></a>EventItem 元素 （EventList_Type 复杂类型） (Visio XML)

封装了事件代码。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[EventItem_Type](eventitem_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |document.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="EventItem" type="EventItem_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[EventList](eventlist-element-visiodocument_type-complextypevisio-xml.md) <br/> |[EventList_Type](eventlist_type-complextypevisio-xml.md) <br/> |包含与对象应响应每个事件**EventItem**元素。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|操作  <br/> |xsd:unsignedShort  <br/> |必需  <br/> |指定父**EventItem**元素的动作代码。  <br/> |Xsd:unsignedShort 类型的值。  <br/> |
|已启用  <br/> |化  <br/> |可选  <br/> |代表一个标志，指示是否启用或禁用事件。  <br/> |化类型的值。  <br/> |
|EventCode  <br/> |xsd:unsignedShort  <br/> |必需  <br/> |指示的事件的触发该加载项的代码。  <br/> |Xsd:unsignedShort 类型的值。  <br/> |
|ID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |事件 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|目标  <br/> |xsd: string  <br/> |必需  <br/> |指定事件的目标。  <br/> |Xsd: string 类型的值。  <br/> |
|TargetArgs  <br/> |xsd: string  <br/> |必需  <br/> |指定包含要发送到目标事件的参数字符串。  <br/> |Xsd: string 类型的值。  <br/> |
   

