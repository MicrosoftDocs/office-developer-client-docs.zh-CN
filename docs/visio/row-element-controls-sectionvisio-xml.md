---
title: Row 元素 （Controls 内容） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bb61870d-3f93-59e3-6671-e545c3a85718
description: 包含特定的控制手柄为形状定义的单元格。
ms.openlocfilehash: cf8015b82f759ba2c166ff5179b2c4324c168e44
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781140"
---
# <a name="row-element-controls-section-visio-xml"></a>Row 元素 （Controls 内容） (Visio XML)

包含特定的控制手柄为形状定义的单元格。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[ControlRow_Type](controlrow_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |母版页 #.xml、 页面 #.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Row" type="ControlRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Section](section-element-sheet_type-complextypevisio-xml.md) <br/> |[Section_Type](section_type-complextypevisio-xml.md) <br/> |包含特定的控制手柄为形状定义的单元格。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Cell](cell-element-controls-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |包含特定的控制手柄为形状定义的属性。  <br/> |
   
### <a name="attributes"></a>Attributes

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|Del  <br/> |化  <br/> |可选  <br/> |指定是否已删除的行，否则将继承主控形状。  <br/> |化类型的值。  <br/> |
|IX  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |指定行的基于一的标识符。 该文件应该是唯一且大于同一节中的其他标识符。IX 属性只用于字符、 连接、 字段、 FillGradient、 geometry、 层、 LineGradient、 段落、 审核、 挑战和选项卡部分。 行只能有一个 IX 或 N 属性。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|LocalName  <br/> |xsd: string  <br/> |可选  <br/> |指定行的唯一依赖于语言的名称。  <br/> |Xsd: string 类型的值。  <br/> |
|N  <br/> |xsd: string  <br/> |可选  <br/> |指定行的唯一的独立于语言的名称。N 属性仅用于用户、 属性、 操作、 控件、 连接、 超链接和 ActionTag 部分。 行只能有一个 IX 或 N 属性。  <br/> |Xsd: string 类型的值。  <br/> |
|T  <br/> |xsd: string  <br/> |可选  <br/> |指定由行和 geometry 可视化中使用的几何路径类型。 T 属性只用于 geometry 内容。  <br/> |Xsd: string 类型的值。  <br/> |
   

