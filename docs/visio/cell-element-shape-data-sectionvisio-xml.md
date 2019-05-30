---
title: Cell 元素 ("Shape Data" 内容) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 98643832-7861-385d-3a52-0060ea413e2e
description: 指定形状数据的一个属性。
ms.openlocfilehash: 3a6238f19f27d001d3c9eebcbcec720822a0ed40
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539374"
---
# <a name="cell-element-shape-data-section-visio-xml"></a>Cell 元素 ("Shape Data" 内容) (Visio XML)

指定形状数据的一个属性。
  
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
|[Row 元素 ("Shape Data" 内容)](row-element-shape-data-sectionvisio-xml.md) <br/> |[Shape Data_Type](propertyrow_type-complextypevisio-xml.md) <br/> |指定一个形状数据输入, 用于将数据与形状相关联。  <br/> |
   
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
|日历  <br/> |指定当形状数据项的类型为“Date”时，使用的日历的类型。  <br/> |[Calendar Cell (Shape Data Section)](calendar-cell-shape-data-section.md) <br/> |
|DataLinked  <br/> |指示形状数据行当前是否已链接到数据记录集中的字段。  <br/> ||
|Format  <br/> |指定形状数据项的格式，这些数据项是字符串、固定列表、数字、可变列表、日期或时间、持续时间或货币。  <br/> |[Format Cell (Shape Data Section)](format-cell-shape-data-section.md) <br/> |
|隐藏  <br/> |指定形状数据项在“形状数据”窗口中是否可见。  <br/> |[Invisible Cell (Shape Data Section)](invisible-cell-shape-data-section.md) <br/> |
|标签  <br/> |指定在“形状数据”窗口中向用户显示的标签。 标签由字母数字字符组成，包括下划线 (_) 字符。  <br/> |[Label Cell (Shape Data Section)](label-cell-shape-data-section.md) <br/> |
|LangID  <br/> |指示输入形状数据值所使用的语言。  <br/> |[LangID Cell (Shape Data Section)](langid-cell-shape-data-section.md) <br/> |
|Prompt  <br/> |指定当鼠标悬停在“形状数据”窗口中的某个值上时作为提示出现的说明性文本或指导性文本。  <br/> |[Prompt Cell (Shape Data Section)](prompt-cell-shape-data-section.md) <br/> |
|关键字  <br/> |对影响在“形状数据”窗口中列出的项目的顺序的字符串求值。  <br/> |[SortKey Cell (Shape Data Section)](sortkey-cell-shape-data-section.md) <br/> |
|类型  <br/> |指定形状数据值的数据类型。  <br/> |[Type Cell (Shape Data Section)](type-cell-shape-data-section.md) <br/> |
|值  <br/> |包含与在“定义形状数据”对话框中输入的形状数据项值相同的值。  <br/> |[Value Cell (Shape Data Section)](value-cell-shape-data-section.md) <br/> |
|Verify  <br/> |指定在创建实例或复制或复制形状时, 是否查询用户输入形状的自定义属性信息。  <br/> |无。  <br/> |
   

