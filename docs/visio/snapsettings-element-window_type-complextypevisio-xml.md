---
title: SnapSettings 元素 (Window_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7b87a244-b331-7e93-d304-239f8ca77061
description: 指定在窗口中的 "对齐" 处于活动状态时, 形状将对齐到的对象。
ms.openlocfilehash: b4793c6d9c13a922db4d3ed9504a3a08e933230a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334501"
---
# <a name="snapsettings-element-windowtype-complextype-visio-xml"></a>SnapSettings 元素 (Window_Type 复杂类型) ("Visio XML")

指定在窗口中的 "对齐" 处于活动状态时, 形状将对齐到的对象。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[SnapSettings_Type](snapsettings_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |windows .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="SnapSettings" type="SnapSettings_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Window](window-element-windows_type-complextypevisio-xml.md) <br/> |[Window_Type](window_type-complextypevisio-xml.md) <br/> |代表 Microsoft Visio 实例中打开的窗口。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>Attributes

无。
  
## <a name="remarks"></a>注解

该值可以是下表中的值的总和。
  
|**Value**|**说明**|
|:-----|:-----|
|0  <br/> |不与任何内容对齐。  <br/> |
|1  <br/> |与标尺细分线对齐。  <br/> |
|双面  <br/> |与网格对齐。  <br/> |
|4  <br/> |与参考线对齐。  <br/> |
|utf-8  <br/> |与选择手柄对齐。  <br/> |
|位  <br/> |与顶点对齐。  <br/> |
|32  <br/> |与连接点对齐。  <br/> |
|256  <br/> |与形状的可见边缘对齐。  <br/> |
|512  <br/> |与对齐框对齐。  <br/> |
|1024  <br/> |与形状延长线选项对齐。  <br/> |
|32768  <br/> |已禁用快照。  <br/> |
|65536  <br/> |与相交的部分对齐。  <br/> |
   

