---
title: 'Cell 元素 (控件行)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3c04d243-002c-bb00-a4be-0bcb8e156402
description: 包含为形状定义的特定控制手柄的属性。
ms.openlocfilehash: 662dfe730c92ae25b3d243364bf1fa22a5eb8605
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541832"
---
# <a name="cell-element-controls-row-visio-xml"></a>Cell 元素 (控件行)  (Visio XML) 

包含为形状定义的特定控制手柄的属性。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |master#.xml，page#.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Row 元素 (Controls Section) ](row-element-controls-sectionvisio-xml.md) <br/> |[ControlRow_Type](controlrow_type-complextypevisio-xml.md) <br/> |包含为形状定义的特定控制手柄的属性。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[RefBy](refby-element-cell_type-complextypevisio-xml.md) <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |指定对绘图页的引用。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|E  <br/> |xsd：string  <br/> |可选  <br/> |指示公式计算结果为错误。 **E** 的值是错误消息字符串 (的当前) ;**V** 属性的值是最后一个有效值。  <br/> |错误消息字符串。  <br/> |
|F  <br/> |xsd：string  <br/> |可选  <br/> | 表示元素的公式。 此属性可以包含以下字符串之一：  <br/>  如果 (存在) ，则"设置一些公式"。  <br/>  `No Formula` 如果公式在本地删除或阻止  <br/>  `Inh` 如果公式是继承的。  <br/> |公式。  <br/> |
|N  <br/> |xsd：string  <br/> |必需  <br/> |代表 ShapeSheet 单元格的名称。  <br/> |ShapeSheet 单元格的名称。  <br/> 请参阅下面的"备注"部分。  <br/> |
|U  <br/> |xsd：string  <br/> |可选  <br/> |表示度量单位 默认值为 DL。  <br/> |单元格的单位。  <br/> |
|V  <br/> |xsd：string  <br/> |可选  <br/> |表示单元格的值。  <br/> |ShapeSheet 单元格的值。  <br/> |
   
## <a name="remarks"></a>备注

此 **Cell** 元素的 **N** 属性必须是与 ShapeSheet 单元格对应的一组有限值之一。 请参阅下表以确定此 **Cell** 元素允许的 **N** 属性的值。 
  
|**值**|**说明**|**详细信息**|
|:-----|:-----|:-----|
|CanGlue  <br/> |确定控制手柄能否粘附到其他形状上。  <br/> |[Can Glue Cell (Controls Section)](can-glue-cell-controls-section.md) <br/> |
|Prompt  <br/> |表示说明性文本字符串，用户将指针悬停于形状的控制手柄上时，此字符串以工具提示的形式显示。  <br/> |[Tip Cell (Controls Section)](tip-cell-controls-section.md) <br/> |
|X  <br/> |表示指明形状的控制手柄在本地坐标系中的位置的 x 坐标。  <br/> |[X Cell (Controls Section)](x-cell-controls-section.md) <br/> |
|xCon  <br/> |指定控制手柄的 x 坐标在手柄移动后的行为类型。  <br/> |无。  <br/> |
|xDyn  <br/> |表示控制手柄的锚点在本地坐标系中的 x 坐标。  <br/> |[X Dynamics Cell (Controls Section)](x-dynamics-cell-controls-section.md) <br/> |
|Y  <br/> |表示指明形状的控制手柄在本地坐标系中的位置的 y 坐标。  <br/> |[Y Cell (Controls Section)](y-cell-controls-section.md) <br/> |
|YCon  <br/> |指定控制手柄的 y 坐标在手柄移动后将呈现的行为类型。  <br/> |无。  <br/> |
|YDyn  <br/> |表示控制手柄的锚点在本地坐标系中的 y 坐标。  <br/> |[Y Dynamics Cell (Controls Section)](y-dynamics-cell-controls-section.md) <br/> |
   

