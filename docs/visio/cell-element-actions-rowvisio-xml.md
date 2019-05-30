---
title: Cell 元素 ("操作" 行) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5ae2b4db-03f4-1b8a-1274-7eb1521f2f59
description: 指定与快捷菜单或动作标记菜单上的自定义命令相关联的操作的一个属性。
ms.openlocfilehash: 8cce85bdfb7d0ce54d968e00cda56e4e6c2455bc
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538779"
---
# <a name="cell-element-actions-row-visio-xml"></a>Cell 元素 ("操作" 行) (Visio XML)

指定与快捷菜单或动作标记菜单上的自定义命令相关联的操作的一个属性。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |.master、主 # .xml、pages、.xml、.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Row 元素 ("Actions" 内容)](row-element-actions-sectionvisio-xml.md) <br/> |[ActionsRow_Type](actionsrow_type-complextypevisio-xml.md) <br/> |指定与快捷菜单或动作标记菜单上的自定义命令相关联的操作的一个属性。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[RefBy](refby-element-cell_type-complextypevisio-xml.md) <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |指定对绘图页的引用。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|E  <br/> |xsd: string  <br/> |可选  <br/> |指示公式的计算结果为错误。 **E**的值是当前值 (一条错误消息字符串);**V**属性的值是最后一个有效的值。  <br/> |错误消息字符串。  <br/> |
|F  <br/> |xsd: string  <br/> |可选  <br/> | 代表元素的公式。 此属性可以包含以下字符串之一:  <br/>  "(某些公式)" 如果该公式在本地存在  <br/>  `No Formula`如果公式为本地删除或被阻止  <br/>  `Inh`如果公式是继承的。  <br/> |一个公式。  <br/> |
|N  <br/> |xsd: string  <br/> |必需  <br/> |代表 ShapeSheet 单元格的名称。  <br/> |ShapeSheet 单元格的名称。  <br/> 请参阅下面的 "备注" 部分。  <br/> |
|U  <br/> |xsd: string  <br/> |可选  <br/> |表示一个度量单位, 默认值为 DL。  <br/> |单元格的单位。  <br/> |
|部分  <br/> |xsd: string  <br/> |可选  <br/> |表示单元格的值。  <br/> |ShapeSheet 单元格的值。  <br/> |
   
## <a name="remarks"></a>备注

此**单元格**元素的**N**属性必须是与 ShapeSheet 单元格相对应的一组有限的值之一。 请参阅下表, 以确定此**单元格**元素允许的**N**属性的值。 
  
|**值**|**说明**|**详细信息**|
|:-----|:-----|:-----|
|操作  <br/> |包含当用户选择快捷菜单或动作标记菜单上的命令时要执行的公式。  <br/> |[Action Cell (Actions Section)](action-cell-actions-section.md) <br/> |
|BeginGroup  <br/> |指示是否在此动作之上的菜单中插入分隔符。  <br/> |[BeginGroup Cell (Actions Section)](begingroup-cell-actions-section.md) <br/> |
|ButtonFace  <br/> |标识在快捷菜单或动作标记菜单上的项旁边显示的图标。  <br/> |[ButtonFace Cell (Actions Section)](buttonface-cell-actions-section.md) <br/> |
|Checked  <br/> |指示是否在快捷菜单或动作标记菜单上选取了某项。  <br/> |[Checked Cell (Actions Section)](checked-cell-actions-section.md) <br/> |
|已禁用  <br/> |指示快捷菜单或动作标记菜单上的某项是否被禁用。  <br/> |[Disabled Cell (Actions Section)](disabled-cell-actions-section.md) <br/> |
|FlyoutChild  <br/> |确定该行是否为不是弹出子菜单的上一行的弹出子菜单。  <br/> |[FlyoutChild 单元格 ("Actions" 内容)](flyoutchild-cell-actions-section.md) <br/> |
|隐藏  <br/> |指示动作标记或快捷菜单上是否显示动作。  <br/> |[Invisible Cell (Actions Section)](invisible-cell-actions-section.md) <br/> |
|菜单  <br/> |定义形状或页的快捷菜单或动作标记菜单上显示的菜单项的名称。  <br/> |[Menu Cell (Actions Section)](menu-cell-actions-section.md) <br/> |
|ReadOnly  <br/> |控制动作标记菜单或快捷菜单上的动作是否为只读。  <br/> |[ReadOnly Cell (Actions Section)](readonly-cell-actions-section.md) <br/> |
|关键字  <br/> |确定动作在快捷菜单或动作标记菜单上显示的顺序的数字。  <br/> |[SortKey 单元格 ("Actions" 内容) SortKey 单元格 ("Actions" 内容)](sortkey-cell-actions-section.md) <br/> |
|TagName  <br/> |包含此动作所关联的动作标记的名称。  <br/> |[TagName Cell (Actions Section)](tagname-cell-actions-section.md) <br/> |
   

