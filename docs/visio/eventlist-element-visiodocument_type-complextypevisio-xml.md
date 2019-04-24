---
title: EventList 元素 (VisioDocument_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 40bb8c7c-89ef-22e1-5edf-e2423fc89660
description: 包含对象应响应的每个事件的 EventItem 元素。
ms.openlocfilehash: 5331f1b4a510b05b862f8c7c6306c89c6be4d9f0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351049"
---
# <a name="eventlist-element-visiodocumenttype-complextype-visio-xml"></a>EventList 元素 (VisioDocument_Type 复杂类型) ("Visio XML")

包含对象应响应的每个事件的**EventItem**元素。 
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[EventList_Type](eventlist_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |document .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="EventList" type="EventList_Type" minOccurs="0" maxOccurs="1" >
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
|[EventItem](eventitem-element-eventlist_type-complextypevisio-xml.md) <br/> |[EventItem_Type](eventitem_type-complextypevisio-xml.md) <br/> |封装事件代码。  <br/> |
   
### <a name="attributes"></a>Attributes

无。
  

