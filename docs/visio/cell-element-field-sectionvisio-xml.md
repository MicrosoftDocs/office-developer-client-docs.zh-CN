---
title: 'Cell 元素 (Field Section)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1a51a5ca-6b68-d2d8-befb-2b1d9cda1b8e
description: 显示使用“域”对话框在形状的文本中插入的函数和公式。
ms.openlocfilehash: b3bae89d20a4defed591e95ce0155f70d806e6f2
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540054"
---
# <a name="cell-element-field-section-visio-xml"></a>Cell 元素 (Field Section)  (Visio XML) 

显示使用“域”对话框在形状的文本中插入的函数和公式。
  
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
|[Field Section (Row 元素) ](row-element-field-sectionvisio-xml.md) <br/> |[FieldRow_Type](fieldrow_type-complextypevisio-xml.md) <br/> |显示使用“域”对话框在形状的文本中插入的函数和公式。  <br/> |
   
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
|日历  <br/> |确定当文本字段为 Date 时用于数据类型日历。  <br/> |[Calendar Cell (Text Fields Section)](calendar-cell-text-fields-section.md) <br/> |
|Format  <br/> |指定文本域的格式，该文本字段可以是字符串、数字、日期或时间、持续时间或货币。  <br/> |[Format Cell (Text Fields Section)](format-cell-text-fields-section.md) <br/> |
|ObjectKind  <br/> |指示文本域的类型。  <br/> |[ObjectKind Cell (Text Fields Section)](objectkind-cell-text-fields-section.md) <br/> |
|类型  <br/> |指定文本域值的数据类型。  <br/> |[Type Cell (Text Fields Section)](type-cell-text-fields-section.md) <br/> |
|UICat  <br/> |确定插入字段的类别。 "字段和数据格式"对话框使用此单元格来确定字段和类别信息。  <br/> |[UICategory Cell (Text Fields Section)](uicategory-cell-text-fields-section.md) <br/> |
|UICod  <br/> |确定插入域的代码。 "字段和数据格式"对话框使用此单元格来确定字段和类别信息。  <br/> |[UICode Cell (Text Fields Section)](uicode-cell-text-fields-section.md) <br/> |
|UIFmt  <br/> |确定插入域的格式。 "字段和数据格式"对话框使用此单元格来确定字段和  <br/> |[UIFormat Cell (Text Fields Section)](uiformat-cell-text-fields-section.md) <br/> |
|值  <br/> |包含域的函数。  <br/> |[Value Cell (Text Fields Section)](value-cell-text-fields-section.md) <br/> |
   

