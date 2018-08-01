---
title: 单元格元素 （操作标记内容） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6210ff71-fbcd-2c97-6dde-1e334891e08d
description: 定义形状或页上的某个动作标记的一个属性。
ms.openlocfilehash: 0945235c49e77210564e50e5c111579ab37f3e31
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779805"
---
# <a name="cell-element-action-tag-section-visio-xml"></a>单元格元素 （操作标记内容） (Visio XML)

定义形状或页上的某个动作标记的一个属性。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |masters.xml、 主 #.xml、 pages.xml、 页 #.xml  <br/> |
   
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
|[Row 元素 （ActionTag 部分）](row-element-action-tag-sectionvisio-xml.md) <br/> |[ActionTagRow_Type](actiontag_type-complextypevisio-xml.md) <br/> |定义形状或页上的某个动作标记。  <br/> |
   
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
|ButtonFace  <br/> |包含动作标记按钮上显示的按钮外表图像的 ID。  <br/> |[ButtonFace Cell (Action Tags Section)](buttonface-cell-action-tags-section.md) <br/> |
|说明  <br/> |包含描述动作标记的字符串。当用户将鼠标指针悬停于动作标记上时，此字符串以工具提示的形式显示。  <br/> |[Description Cell (Action Tags Section)](description-cell-action-tags-section.md) <br/> |
|已禁用  <br/> |指示动作标记是否在绘图窗口中显示。  <br/> |[Disabled Cell (Action Tags Section)](disabled-cell-action-tags-section.md) <br/> |
|DisplayMode  <br/> |确定动作标记是否显示用户将指针移到标记上时，选择形状后，或所有的时间。  <br/> |[DisplayMode Cell (Action Tags Section)](displaymode-cell-action-tags-section.md) <br/> |
|TagName  <br/> |用作将动作标记与其动作相关联的关键字的动作标记的名称。  <br/> |[TagName Cell (Action Tags Section)](tagname-cell-action-tags-section.md) <br/> |
|X  <br/> |形状上放置动作标记按钮的位置在形状的本地坐标系中的 x 坐标。  <br/> |[X Cell (Action Tags Section)](x-cell-action-tags-section.md) <br/> |
|XJustify  <br/> |动作标记按钮相对于由 X 单元格和 Y 单元格定义的点的 x 轴偏移量。  <br/> |[X Justify Cell (Action Tags Section)](x-justify-cell-action-tags-section.md) <br/> |
|Y  <br/> |形状上放置动作标记按钮的位置在形状的本地坐标系中的 y 坐标。  <br/> |[Y Cell (Action Tags Section)](y-cell-action-tags-section.md) <br/> |
|YJustify  <br/> |动作标记按钮相对于由 X 单元格和 Y 单元格定义的点的 y 轴偏移量。  <br/> |[Y Justify Cell (Action Tags Section)](y-justify-cell-action-tags-section.md) <br/> |
   

