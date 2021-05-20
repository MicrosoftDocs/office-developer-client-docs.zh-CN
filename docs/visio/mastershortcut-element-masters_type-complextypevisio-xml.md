---
title: 'MasterShortcut (Masters_Type complexType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 62f0e093-5385-e552-f91a-02a65eb0e6e1
description: 指定文档中定义的主控母版快捷方式。
ms.openlocfilehash: 94ac64ff0080bf7d50df67674022ce53f32339a4
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538205"
---
# <a name="mastershortcut-element-masters_type-complextype-visio-xml"></a>MasterShortcut (Masters_Type complexType)  (Visio XML) 

指定文档中定义的主控母版快捷方式。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[MasterShortcut_Type](mastershortcut_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |master#.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="MasterShortcut" type="MasterShortcut_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Masters](masters-elementvisio-xml.md) <br/> |[Masters_Type](masters_type-complextypevisio-xml.md) <br/> |包含 **文档的 Master** 元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Icon](icon-element-mastershortcut_type-complextypevisio-xml.md) <br/> |[Icon_Type](icon_type-complextypevisio-xml.md) <br/> |指定 MIME (Master 或 **MasterShortcut** 元素的 MIME) 编码的二进制图标 (，格式为 .ico ) 。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|AlignName  <br/> |xsd：unsignedShort  <br/> |可选  <br/> |指定模具窗口中元素的文本是左对齐、右对齐还是居中对齐。  <br/> |xsd：unsignedShort 类型的值。  <br/> |
|IconSize  <br/> |xsd：unsignedShort  <br/> |可选  <br/> |元素图标的大小。  <br/> |xsd：unsignedShort 类型的值。  <br/> |
|ID  <br/> |xsd：unsignedInt  <br/> |必需  <br/> |元素在其父元素中的唯一 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|名称  <br/> |xsd：string  <br/> |可选  <br/> |元素的名称。  <br/> |xsd：string 类型的值。  <br/> |
|NameU  <br/> |xsd：string  <br/> |可选  <br/> |元素的通用名称。  <br/> |xsd：string 类型的值。  <br/> |
|PatternFlags  <br/> |xsd：unsignedShort  <br/> |可选  <br/> |确定主控形状是否表现为自定义图案。  <br/> |xsd：unsignedShort 类型的值。  <br/> |
|Prompt  <br/> |xsd：string  <br/> |可选  <br/> |元素的状态栏和工具提示提示。  <br/> |xsd：string 类型的值。  <br/> |
|ShortcutHelp  <br/> |xsd：string  <br/> |可选  <br/> |元素的帮助字符串。  <br/> |xsd：string 类型的值。  <br/> |
|ShortcutURL  <br/> |xsd：string  <br/> |可选  <br/> |**MasterShortcut** 元素的 URL。  <br/> |xsd：string 类型的值。  <br/> |
   

