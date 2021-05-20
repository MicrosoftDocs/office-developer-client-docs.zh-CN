---
title: 'SnapSettings 元素 (Window_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7b87a244-b331-7e93-d304-239f8ca77061
description: 指定当窗口中的对齐处于活动状态时形状所对齐的对象。
ms.openlocfilehash: 0fbe54f56f79d84e6c6bd8ddc11aa28b7e5ba1dc
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540313"
---
# <a name="snapsettings-element-window_type-complextype-visio-xml"></a>SnapSettings 元素 (Window_Type COMPLEXType)  (Visio XML) 

指定当窗口中的对齐处于活动状态时形状所对齐的对象。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[SnapSettings_Type](snapsettings_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |windows.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="SnapSettings" type="SnapSettings_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Window](window-element-windows_type-complextypevisio-xml.md) <br/> |[Window_Type](window_type-complextypevisio-xml.md) <br/> |代表 Microsoft Visio 实例中打开的窗口。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>Attributes

无。
  
## <a name="remarks"></a>说明

该值可能是下表中值的总和。
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |不与任何内容对齐。  <br/> |
|1  <br/> |贴靠标尺细分线。  <br/> |
|2  <br/> |贴靠网格。  <br/> |
|4   <br/> |与参考线对齐。  <br/> |
|8   <br/> |与选择手柄对齐。  <br/> |
|16   <br/> |与顶点对齐。  <br/> |
|32  <br/> |与连接点对齐。  <br/> |
|256  <br/> |贴靠形状的可见边缘。  <br/> |
|512  <br/> |贴靠对齐框。  <br/> |
|1024  <br/> |与形状延长线选项对齐。  <br/> |
|32768  <br/> |贴靠禁用。  <br/> |
|65536  <br/> |与相交的部分对齐。  <br/> |
   

