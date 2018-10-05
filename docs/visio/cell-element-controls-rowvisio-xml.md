---
title: 单元格元素 （控件行） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3c04d243-002c-bb00-a4be-0bcb8e156402
description: 包含特定的控制手柄为形状定义的属性。
ms.openlocfilehash: ea54865a645486dfba53688278cb380142899d77
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401270"
---
# <a name="cell-element-controls-row-visio-xml"></a>单元格元素 （控件行） (Visio XML)

包含特定的控制手柄为形状定义的属性。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |母版页 #.xml、 页面 #.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Row 元素（“Controls”部分）](row-element-controls-sectionvisio-xml.md) <br/> |[ControlRow_Type](controlrow_type-complextypevisio-xml.md) <br/> |包含特定的控制手柄为形状定义的属性。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[RefBy](refby-element-cell_type-complextypevisio-xml.md) <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |指定在绘图页上的引用。  <br/> |
   
### <a name="attributes"></a>Attributes

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|E  <br/> |xsd: string  <br/> |可选  <br/> |指示该公式计算为错误。 **E**的值是当前值 （错误消息字符串）;**V**属性的值是最后一个有效的值。  <br/> |错误消息字符串。  <br/> |
|F  <br/> |xsd: string  <br/> |可选  <br/> | 代表元素的公式。 此属性可以包含以下字符串之一：  <br/>  （某些公式） 如果公式本地存在  <br/>  `No Formula`如果本地删除或阻止公式  <br/>  `Inh`如果继承的公式。  <br/> |公式。  <br/> |
|N  <br/> |xsd: string  <br/> |必需  <br/> |表示的 ShapeSheet 单元格的名称。  <br/> |ShapeSheet 单元格的名称。  <br/> 请参阅下面的备注部分。  <br/> |
|U  <br/> |xsd: string  <br/> |可选  <br/> |代表单位默认值是度量的 DL。  <br/> |单元格的单位。  <br/> |
|V  <br/> |xsd: string  <br/> |可选  <br/> |代表单元格的值。  <br/> |ShapeSheet 单元格的值。  <br/> |
   
## <a name="remarks"></a>说明

此**单元格**元素的**N**属性必须为一组有限的对应于 ShapeSheet 单元格的值之一。 请参阅下表为确定允许此**单元格**元素的**N**属性的值。 
  
|**值**|**说明**|**更多信息**|
|:-----|:-----|:-----|
|CanGlue  <br/> |确定控制手柄能否粘附到其他形状上。  <br/> |[Can Glue Cell (Controls Section)](can-glue-cell-controls-section.md) <br/> |
|提示  <br/> |表示说明性文本字符串，用户将指针悬停于形状的控制手柄上时，此字符串以工具提示的形式显示。  <br/> |[Tip Cell (Controls Section)](tip-cell-controls-section.md) <br/> |
|X  <br/> |表示指明形状的控制手柄在本地坐标系中的位置的 x 坐标。  <br/> |[X Cell (Controls Section)](x-cell-controls-section.md) <br/> |
|xCon  <br/> |指定的控制手柄的 x 轴坐标在手柄移动后将展示的行为的类型。  <br/> |无。  <br/> |
|xDyn  <br/> |表示控制手柄的锚点在本地坐标系中的 x 坐标。  <br/> |[X Dynamics Cell (Controls Section)](x-dynamics-cell-controls-section.md) <br/> |
|Y  <br/> |表示指明形状的控制手柄在本地坐标系中的位置的 y 坐标。  <br/> |[Y Cell (Controls Section)](y-cell-controls-section.md) <br/> |
|YCon  <br/> |指定的控制手柄的 y 坐标在手柄移动后将表现的行为的类型。  <br/> |无。  <br/> |
|YDyn  <br/> |表示控制手柄的锚点在本地坐标系中的 y 坐标。  <br/> |[Y Dynamics Cell (Controls Section)](y-dynamics-cell-controls-section.md) <br/> |
   

