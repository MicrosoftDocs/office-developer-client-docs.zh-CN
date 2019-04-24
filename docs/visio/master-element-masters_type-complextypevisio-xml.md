---
title: Master 元素 (Masters_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c102fd71-c621-2bde-9fbb-8e9203fdf31e
description: 包含用于定义文档主控形状的元素。
ms.openlocfilehash: f6effa521b7c5ea69d41b6770ee2dbef61af097c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283963"
---
# <a name="master-element-masterstype-complextype-visio-xml"></a>Master 元素 (Masters_Type 复杂类型) ("Visio XML")

包含用于定义文档主控形状的元素。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Master_Type](master_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |主控 xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Master" type="Master_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Masters](masters-elementvisio-xml.md) <br/> |[Masters_Type](masters_type-complextypevisio-xml.md) <br/> |包含文档的**主控形状**元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Connects](connects-element-pagecontents_type-complextypevisio-xml.md) <br/> |[Connects_Type](connects_type-complextypevisio-xml.md) <br/> |包含绘图中两个形状之间的每个连接的**Connect**元素。  <br/> |
|[Icon](icon-element-master_type-complextypevisio-xml.md) <br/> |[Icon_Type](icon_type-complextypevisio-xml.md) <br/> |为文档中的**主控形状**或**MasterShortcut**元素指定 MIME (多用途 Internet 邮件扩展) 编码的二进制图标 (在 .ico 格式中)。  <br/> |
|[PageSheet](pagesheet-element-master_type-complextypevisio-xml.md) <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> |包含用于定义**page**或**Master**元素的页面表的元素。  <br/> |
|形状  <br/> |Shapes_Type  <br/> |包含**Shape**元素的集合。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|AlignName  <br/> |xsd: unsignedShort  <br/> |可选  <br/> |指定是否在模具窗口中左对齐、右对齐或居中对齐主控形状的文本。  <br/> |xsd: unsignedShort 类型的值。  <br/> |
|BaseID  <br/> |xsd: string  <br/> |可选  <br/> |标识文档的主控形状的 GUID (全局唯一标识符)。  <br/> |xsd: string 类型的值。  <br/> |
|Hidden  <br/> |xsd: boolean  <br/> |可选  <br/> |指定是否在用户界面中隐藏主控形状。  <br/> |xsd: boolean 类型的值。  <br/> |
|IconSize  <br/> |xsd: unsignedShort  <br/> |可选  <br/> |元素的图标的大小。  <br/> |xsd: unsignedShort 类型的值。  <br/> |
|IconUpdate  <br/> |xsd: boolean  <br/> |可选  <br/> |指定是否自动从母版本身生成图标。  <br/> |xsd: boolean 类型的值。  <br/> |
|ID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |元素在其父元素中的唯一 ID。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|MatchByName  <br/> |xsd: boolean  <br/> |可选  <br/> |确定在将主控形状的实例放在绘图页上时, Microsoft Visio 如何确定文档主控形状是否已存在。  <br/> |xsd: boolean 类型的值。  <br/> |
|名称  <br/> |xsd: string  <br/> |可选  <br/> |元素的名称。  <br/> |xsd: string 类型的值。  <br/> |
|NameU  <br/> |xsd: string  <br/> |可选  <br/> |元素的通用名称。  <br/> |xsd: string 类型的值。  <br/> |
|PatternFlags  <br/> |xsd: unsignedShort  <br/> |可选  <br/> |确定主控形状是否表现为自定义图案。  <br/> |xsd: unsignedShort 类型的值。  <br/> |
|Prompt  <br/> |xsd: string  <br/> |可选  <br/> |元素的状态栏和工具提示提示。  <br/> |xsd: string 类型的值。  <br/> |
|UniqueID  <br/> |xsd: string  <br/> |可选  <br/> |标识文档中的主控形状的 GUID。  <br/> |xsd: string 类型的值。  <br/> |
   

