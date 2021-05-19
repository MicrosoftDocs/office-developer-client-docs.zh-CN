---
title: 'EventItem 元素 (EventList_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6b347117-a1c1-d090-0d71-ea8528ac70c6
description: 封装事件代码。
ms.openlocfilehash: 0db88a175d3e0330cb648f870559d9d2bd4dc1d8
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541838"
---
# <a name="eventitem-element-eventlist_type-complextype-visio-xml"></a>EventItem 元素 (EventList_Type COMPLEXType)  (Visio XML) 

封装事件代码。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[EventItem_Type](eventitem_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |document.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="EventItem" type="EventItem_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[EventList](eventlist-element-visiodocument_type-complextypevisio-xml.md) <br/> |[EventList_Type](eventlist_type-complextypevisio-xml.md) <br/> |包含对象应响应的每个事件的 **EventItem** 元素。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|Action  <br/> |xsd：unsignedShort  <br/> |必需  <br/> |指定父 **EventItem** 元素的操作代码。  <br/> |xsd：unsignedShort 类型的值。  <br/> |
|已启用  <br/> |xsd：boolean  <br/> |可选  <br/> |表示一个标志，指示是启用还是禁用该事件。  <br/> |xsd：boolean 类型的值。  <br/> |
|EventCode  <br/> |xsd：unsignedShort  <br/> |必需  <br/> |指示触发加载项的事件的代码。  <br/> |xsd：unsignedShort 类型的值。  <br/> |
|ID  <br/> |xsd：unsignedInt  <br/> |必需  <br/> |事件的 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|Target  <br/> |xsd：string  <br/> |必需  <br/> |指定事件的目标。  <br/> |xsd：string 类型的值。  <br/> |
|TargetArgs  <br/> |xsd：string  <br/> |必需  <br/> |指定包含要发送到事件目标的参数的字符串。  <br/> |xsd：string 类型的值。  <br/> |
   

