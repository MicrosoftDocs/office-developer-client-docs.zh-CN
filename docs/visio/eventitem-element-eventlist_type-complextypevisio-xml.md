---
title: EventItem 元素 (EventList_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6b347117-a1c1-d090-0d71-ea8528ac70c6
description: 封装事件代码。
ms.openlocfilehash: 6ed539bd6cb4524b2498b636295442bed917c72a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337196"
---
# <a name="eventitem-element-eventlisttype-complextype-visio-xml"></a>EventItem 元素 (EventList_Type 复杂类型) ("Visio XML")

封装事件代码。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[EventItem_Type](eventitem_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |document .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="EventItem" type="EventItem_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[EventList](eventlist-element-visiodocument_type-complextypevisio-xml.md) <br/> |[EventList_Type](eventlist_type-complextypevisio-xml.md) <br/> |包含对象应响应的每个事件的**EventItem**元素。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|操作  <br/> |xsd: unsignedShort  <br/> |必需  <br/> |指定父**EventItem**元素的操作代码。  <br/> |xsd: unsignedShort 类型的值。  <br/> |
|已启用  <br/> |xsd: boolean  <br/> |可选  <br/> |表示一个标志, 该标志指示事件是否已启用或已禁用。  <br/> |xsd: boolean 类型的值。  <br/> |
|EventCode  <br/> |xsd: unsignedShort  <br/> |必需  <br/> |指示触发加载项的事件的代码。  <br/> |xsd: unsignedShort 类型的值。  <br/> |
|ID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |事件的 ID。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|Target  <br/> |xsd: string  <br/> |必需  <br/> |指定事件的目标。  <br/> |xsd: string 类型的值。  <br/> |
|TargetArgs  <br/> |xsd: string  <br/> |必需  <br/> |指定一个字符串, 其中包含要发送到事件目标的参数。  <br/> |xsd: string 类型的值。  <br/> |
   

