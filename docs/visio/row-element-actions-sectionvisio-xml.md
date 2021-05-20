---
title: 'Row 元素 (Actions Section)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5141589b-10f3-f908-56d2-206244f449fb
description: 包含描述形状或页的快捷菜单或动作标记菜单上的菜单项的行。
ms.openlocfilehash: dfe23aa7d635fc09d625c414e5548a0166384fbb
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540411"
---
# <a name="row-element-actions-section-visio-xml"></a>Row 元素 (Actions Section)  (Visio XML) 

包含描述形状或页的快捷菜单或动作标记菜单上的菜单项的行。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[ActionsRow_Type](actionsrow_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |masters.xml、master#.xml、pages.xml、page#.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Row" type="ActionsRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Section](section-element-sheet_type-complextypevisio-xml.md) <br/> |[Section_Type](section_type-complextypevisio-xml.md) <br/> |包含描述形状或页的快捷菜单或动作标记菜单上的菜单项的行。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Cell](cell-element-actions-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定与快捷菜单或动作标记菜单上的自定义命令相关联的动作的一个属性。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|Del  <br/> |xsd：boolean  <br/> |可选  <br/> |指定是否已删除从主控形状继承的行。  <br/> |xsd：boolean 类型的值。  <br/> |
|IX  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |指定行的从 1 开始标识符。 它应不唯一，并且大于同一节中的其他标识符。IX 属性仅用于 Character、Connection、Field、FillGradient、Geometry、Layer、LineGradient、Paragraph、Reviewer、Scratch 和 Tabs 部分。 一行只能有一个 IX 或 N 属性。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|LocalName  <br/> |xsd：string  <br/> |可选  <br/> |指定行的唯一依赖于语言的名称。  <br/> |xsd：string 类型的值。  <br/> |
|N  <br/> |xsd：string  <br/> |可选  <br/> |指定行的唯一与语言无关的名称。N 属性仅用于 User、Property、Actions、Control、Connection、Hyperlink 和 ActionTag 部分。 一行只能有一个 IX 或 N 属性。  <br/> |xsd：string 类型的值。  <br/> |
|T  <br/> |xsd：string  <br/> |可选  <br/> |指定由行表示的几何路径类型，并用于几何可视化。 T 属性仅用于"Geometry"内容。  <br/> |xsd：string 类型的值。  <br/> |
   

