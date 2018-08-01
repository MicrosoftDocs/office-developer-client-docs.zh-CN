---
title: 主元素 （Masters_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c102fd71-c621-2bde-9fbb-8e9203fdf31e
description: 包含用于定义文档主控形状的元素。
ms.openlocfilehash: 51c5f0ad8bee5000e981fcfd4d15e2e49f2bda3b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780698"
---
# <a name="master-element-masterstype-complextype-visio-xml"></a>主元素 （Masters_Type 复杂类型） (Visio XML)

包含用于定义文档主控形状的元素。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Master_Type](master_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |masters.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Master" type="Master_Type" minOccurs="0" maxOccurs="unbounded" >
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
|[Connects](connects-element-pagecontents_type-complextypevisio-xml.md) <br/> |[Connects_Type](connects_type-complextypevisio-xml.md) <br/> |包含与绘图中的两个形状间的每个连接的**Connect**元素。  <br/> |
|[图标](icon-element-master_type-complextypevisio-xml.md) <br/> |[Icon_Type](icon_type-complextypevisio-xml.md) <br/> |指定的 MIME （多用途 Internet 邮件扩展） 的文档中的**主控形状**或**MasterShortcut**元素编码二进制图标 （.ico 格式）。  <br/> |
|[PageSheet](pagesheet-element-master_type-complextypevisio-xml.md) <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> |包含定义**页**或**主控形状**的元素的页表的元素。  <br/> |
|Shapes  <br/> |Shapes_Type  <br/> |包含**形状**元素的集合。  <br/> |
   
### <a name="attributes"></a>Attributes

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|AlignName  <br/> |xsd:unsignedShort  <br/> |可选  <br/> |指定模具窗口中的主控形状的文本是左、 右对齐还是中心。  <br/> |Xsd:unsignedShort 类型的值。  <br/> |
|BaseID  <br/> |xsd: string  <br/> |可选  <br/> |标识文档间的主控形状的 GUID （全局唯一标识符）。  <br/> |Xsd: string 类型的值。  <br/> |
|隐藏  <br/> |化  <br/> |可选  <br/> |指定在用户界面中是否隐藏的主控形状。  <br/> |化类型的值。  <br/> |
|IconSize  <br/> |xsd:unsignedShort  <br/> |可选  <br/> |元素的图标的大小。  <br/> |Xsd:unsignedShort 类型的值。  <br/> |
|IconUpdate  <br/> |化  <br/> |可选  <br/> |指定是否从主控形状本身自动生成图标。  <br/> |化类型的值。  <br/> |
|ID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |其父元素中的元素的唯一 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|MatchByName  <br/> |化  <br/> |可选  <br/> |确定 Microsoft Visio 如何决定是否文档主控形状已存在的实例时主控形状放在绘图页上。  <br/> |化类型的值。  <br/> |
|名称  <br/> |xsd: string  <br/> |可选  <br/> |元素的名称。  <br/> |Xsd: string 类型的值。  <br/> |
|NameU  <br/> |xsd: string  <br/> |可选  <br/> |元素的通用名称。  <br/> |Xsd: string 类型的值。  <br/> |
|PatternFlags  <br/> |xsd:unsignedShort  <br/> |可选  <br/> |确定是否主控形状表现为自定义模式。  <br/> |Xsd:unsignedShort 类型的值。  <br/> |
|提示  <br/> |xsd: string  <br/> |可选  <br/> |状态栏和工具提示提示的元素。  <br/> |Xsd: string 类型的值。  <br/> |
|UniqueID  <br/> |xsd: string  <br/> |可选  <br/> |一个标识文档内的母版的 GUID。  <br/> |Xsd: string 类型的值。  <br/> |
   

