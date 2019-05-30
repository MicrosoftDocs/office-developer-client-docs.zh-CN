---
title: Row 元素 ("Actions" 内容) (Visio XML)
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
# <a name="row-element-actions-section-visio-xml"></a>Row 元素 ("Actions" 内容) (Visio XML)

包含描述形状或页的快捷菜单或动作标记菜单上的菜单项的行。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[ActionsRow_Type](actionsrow_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |.master、主 # .xml、pages、.xml、.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Row" type="ActionsRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Section](section-element-sheet_type-complextypevisio-xml.md) <br/> |[Section_Type](section_type-complextypevisio-xml.md) <br/> |包含描述形状或页的快捷菜单或动作标记菜单上的菜单项的行。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Cell](cell-element-actions-rowvisio-xml.md) <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |指定与快捷菜单或动作标记菜单上的自定义命令相关联的操作的一个属性。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|键  <br/> |xsd: boolean  <br/> |可选  <br/> |指定是否已删除要从主控形状继承的行。  <br/> |Xsd: boolean 类型的值。  <br/> |
|IX  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |指定行的从1开始的标识符。 它应是唯一, 并且大于同一节中的其他标识符。IX 属性仅用于字符、Connection、Field、FillGradient、Geometry、Layer、LineGradient、段落、审阅者、草稿和选项卡部分。 行只能具有 IX 或 N 属性中的一个。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|LocalName  <br/> |xsd: string  <br/> |可选  <br/> |指定行的与语言相关的唯一名称。  <br/> |Xsd: string 类型的值。  <br/> |
|N  <br/> |xsd: string  <br/> |可选  <br/> |指定行的与语言无关的唯一名称。N 属性仅用于用户、属性、操作、控制、Connection、Hyperlink 和 ActionTag 节。 行只能具有 IX 或 N 属性中的一个。  <br/> |Xsd: string 类型的值。  <br/> |
|T  <br/> |xsd: string  <br/> |可选  <br/> |指定由行表示并在几何图形可视化中使用的几何路径的类型。 T 属性仅用于 "Geometry" 部分。  <br/> |Xsd: string 类型的值。  <br/> |
   

