---
title: MasterShortcut 元素 （Masters_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 62f0e093-5385-e552-f91a-02a65eb0e6e1
description: 指定文档中定义的主控形状快捷方式。
ms.openlocfilehash: 03196c6fc1f3424c61bcce406dc050f2d5a73365
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392954"
---
# <a name="mastershortcut-element-masterstype-complextype-visio-xml"></a>MasterShortcut 元素 （Masters_Type 复杂类型） (Visio XML)

指定文档中定义的主控形状快捷方式。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[MasterShortcut_Type](mastershortcut_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |主 #.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="MasterShortcut" type="MasterShortcut_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Masters](masters-elementvisio-xml.md) <br/> |[Masters_Type](masters_type-complextypevisio-xml.md) <br/> |包含文档的**主控形状**元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[图标](icon-element-mastershortcut_type-complextypevisio-xml.md) <br/> |[Icon_Type](icon_type-complextypevisio-xml.md) <br/> |指定的 MIME （多用途 Internet 邮件扩展） 的文档中的**主控形状**或**MasterShortcut**元素编码二进制图标 （.ico 格式）。  <br/> |
   
### <a name="attributes"></a>Attributes

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|AlignName  <br/> |xsd:unsignedShort  <br/> |可选  <br/> |指定模具窗口中的元素的文本是左、 右对齐还是中心。  <br/> |Xsd:unsignedShort 类型的值。  <br/> |
|IconSize  <br/> |xsd:unsignedShort  <br/> |可选  <br/> |元素的图标的大小。  <br/> |Xsd:unsignedShort 类型的值。  <br/> |
|ID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |其父元素中的元素的唯一 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|名称  <br/> |xsd: string  <br/> |可选  <br/> |元素的名称。  <br/> |Xsd: string 类型的值。  <br/> |
|NameU  <br/> |xsd: string  <br/> |可选  <br/> |元素的通用名称。  <br/> |Xsd: string 类型的值。  <br/> |
|PatternFlags  <br/> |xsd:unsignedShort  <br/> |可选  <br/> |确定是否主控形状表现为自定义模式。  <br/> |Xsd:unsignedShort 类型的值。  <br/> |
|提示  <br/> |xsd: string  <br/> |可选  <br/> |状态栏和工具提示提示的元素。  <br/> |Xsd: string 类型的值。  <br/> |
|ShortcutHelp  <br/> |xsd: string  <br/> |可选  <br/> |元素的帮助字符串。  <br/> |Xsd: string 类型的值。  <br/> |
|ShortcutURL  <br/> |xsd: string  <br/> |可选  <br/> |指向**MasterShortcut**元素的 URL。  <br/> |Xsd: string 类型的值。  <br/> |
   

