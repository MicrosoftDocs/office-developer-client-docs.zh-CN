---
title: 'XML (Action Tag Section)  (Visio Cell) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6210ff71-fbcd-2c97-6dde-1e334891e08d
description: 为形状或页面上的动作标记定义一个属性。
ms.openlocfilehash: 3b43206838dae432df677a3ff8792c85328db53b
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538800"
---
# <a name="cell-element-action-tag-section-visio-xml"></a>XML (Action Tag Section)  (Visio Cell) 

为形状或页面上的动作标记定义一个属性。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |masters.xml、master#.xml、pages.xml、page#.xml  <br/> |
   
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
|[ActionTag (的 Row 元素) ](row-element-action-tag-sectionvisio-xml.md) <br/> |[ActionTagRow_Type](actiontag_type-complextypevisio-xml.md) <br/> |定义形状或页面上的动作标记。  <br/> |
   
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
|ButtonFace  <br/> |包含动作标记按钮上显示的按钮外表图像的 ID。  <br/> |[ButtonFace Cell (Action Tags Section)](buttonface-cell-action-tags-section.md) <br/> |
|说明  <br/> |包含描述动作标记的字符串。当用户将鼠标指针悬停于动作标记上时，此字符串以工具提示的形式显示。  <br/> |[Description Cell (Action Tags Section)](description-cell-action-tags-section.md) <br/> |
|已禁用  <br/> |指示动作标记是否在绘图窗口中显示。  <br/> |[Disabled Cell (Action Tags Section)](disabled-cell-action-tags-section.md) <br/> |
|DisplayMode  <br/> |确定当用户将指针移动到标记上时、选择形状时还是所有时间都显示动作标记。  <br/> |[DisplayMode Cell (Action Tags Section)](displaymode-cell-action-tags-section.md) <br/> |
|TagName  <br/> |用作将动作标记与其动作相关联的关键字的动作标记的名称。  <br/> |[TagName Cell (Action Tags Section)](tagname-cell-action-tags-section.md) <br/> |
|X  <br/> |形状上放置动作标记按钮的位置在形状的本地坐标系中的 x 坐标。  <br/> |[X Cell (Action Tags Section)](x-cell-action-tags-section.md) <br/> |
|XJustify  <br/> |动作标记按钮相对于由 X 单元格和 Y 单元格定义的点的 x 轴偏移量。  <br/> |[X Justify Cell (Action Tags Section)](x-justify-cell-action-tags-section.md) <br/> |
|Y  <br/> |形状上放置动作标记按钮的位置在形状的本地坐标系中的 y 坐标。  <br/> |[Y Cell (Action Tags Section)](y-cell-action-tags-section.md) <br/> |
|YJustify  <br/> |动作标记按钮相对于由 X 单元格和 Y 单元格定义的点的 y 轴偏移量。  <br/> |[Y Justify Cell (Action Tags Section)](y-justify-cell-action-tags-section.md) <br/> |
   

