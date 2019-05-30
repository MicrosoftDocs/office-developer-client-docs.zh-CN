---
title: Cell 元素 ("超链接" 行) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d2089db4-39eb-06d3-d2f8-9465baef5c75
description: 包含与形状相关联的单个超链接的信息。 对于每个超链接，形状中都将包含一个与之对应的 Hyperlink 行。
ms.openlocfilehash: f9526b3e4bb7dc9216a0b72c0a816e136c6e89bf
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539791"
---
# <a name="cell-element-hyperlink-row-visio-xml"></a>Cell 元素 ("超链接" 行) (Visio XML)

包含与形状相关联的单个超链接的信息。 一个形状将包含每个超链接的一个**超链接**行。 
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |master # .xml、第 .xml 页  <br/> |
   
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
|[Row 元素 ("超链接" 部分)](row-element-hyperlink-sectionvisio-xml.md) <br/> |[HyperlinkRow_Type](hyperlinkrow_type-complextypevisio-xml.md) <br/> |包含与形状相关联的单个超链接的信息。 一个形状将包含每个超链接的一个**超链接**行。  <br/> |
   
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
|Address  <br/> |指定要跳转到的 URL 地址、文件名或 UNC 路径。  <br/> |[Address Cell (Hyperlinks Section)](address-cell-hyperlinks-section.md) <br/> |
|默认  <br/> |确定形状或页的默认超链接。  <br/> |[Default Cell (Hyperlinks Section)](default-cell-hyperlinks-section.md) <br/> |
|说明  <br/> |代表超链接的说明性文本字符串。  <br/> |[Description Cell (Hyperlinks Section)](description-cell-hyperlinks-section.md) <br/> |
|ExtraInfo  <br/> |表示传递解析 URL 所需信息的字符串，如图像映射的坐标。  <br/> |[ExtraInfo Cell (Hyperlinks Section)](extrainfo-cell-hyperlinks-section.md) <br/> |
|Frame  <br/> |代表当应用程序作为活动文档在某一容器应用程序中打开时的目标框架名。默认值为空字符串。  <br/> |[Frame Cell (Hyperlinks Section)](frame-cell-hyperlinks-section.md) <br/> |
|隐藏  <br/> |指示超链接是否出现在形状或页面的快捷菜单上。  <br/> |[Invisible Cell (Hyperlinks Section)](invisible-cell-hyperlinks-section.md) <br/> |
|NewWindow  <br/> |指定是否在新窗口中打开超链接。  <br/> |[NewWindow Cell (Hyperlinks Section)](newwindow-cell-hyperlinks-section.md) <br/> |
|关键字  <br/> |确定超链接在快捷菜单上显示的顺序的数字。  <br/> |[SortKey Cell (Hyperlinks Section)](sortkey-cell-hyperlinks-section.md) <br/> |
|SubAddress  <br/> |指定要链接到的目标文档内的位置。  <br/> |[SubAddress Cell (Hyperlinks Section)](subaddress-cell-hyperlinks-section.md) <br/> |
   

