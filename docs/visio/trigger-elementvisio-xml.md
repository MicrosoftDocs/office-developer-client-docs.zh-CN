---
title: 'Trigger 元素 (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d897d2d1-25ba-48d7-b87e-d3c533d88c15
description: 向 Microsoft 提供Visio重新计算文档部件在文档部件之间Visio的说明。
ms.openlocfilehash: e757331984586dc910ada7d14e6385761f15929f
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542903"
---
# <a name="trigger-element-visio-xml"></a>Trigger 元素 (Visio XML) 

向 Microsoft 提供Visio重新计算文档部件在文档部件之间Visio的说明。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Trigger_Type](trigger_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |master#.xml，page#.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
<xs:element name="Trigger" type="Trigger_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element>
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[ShapeSheet_Type](shapesheet_type-complextypevisio-xml.md) <br/> |指定单元格元素，这些元素为形状的定义提供信息。  <br/> |
|[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |[DocumentSheet_Type](documentsheet_type-complextypevisio-xml.md) <br/> |定义 DocumentSheet 结构。  <br/> |
|[StyleSheet](stylesheet-element-stylesheets_type-complextypevisio-xml.md) <br/> |[StyleSheet_Type](stylesheets_type-complextypevisio-xml.md) <br/> |表示在文档中定义的样式。  <br/> |
|[PageSheet (Master_Type complexType) ](pagesheet-element-master_type-complextypevisio-xml.md) <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> |指定与主控板关联的绘图页的属性。  <br/> |
|[PageSheet (Page_Type complexType) ](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> |指定与绘图页关联的绘图页的属性。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[RefBy](refby-element-trigger_type-complextypevisio-xml.md) <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |指定对绘图中页面的引用。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|N  <br/> |xsd：string  <br/> |必需  <br/> |激活触发器时要调用的公式的名称。  <br/> 请参阅"备注"部分。  <br/> |xsd：string 类型的值。  <br/> |
   
## <a name="remarks"></a>备注

此 **Trigger** 元素的 **N** 属性必须是与触发器指令对应的一组有限值之一。 请参阅下表以确定此 **Trigger** 元素允许的 **N** 属性的值。 
  
|**值**|**父元素**|**说明**|
|:-----|:-----|:-----|
|CategoryChanged  <br/> |[PageSheet (Page_Type complexType) ](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |存在使用 **HASCATEGORIES** 函数的跨部分引用时出现在形状上的触发器。  <br/> |
|RecalcBkgPageName  <br/> |[PageSheet (Page_Type complexType) ](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |存在使用 **BKGPAGENAME** 函数的跨部分引用时出现在页面上的触发器  <br/> |
|RecalcColor  <br/> |[PageSheet (Page_Type complexType) ](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |只要页面或任何所包含的形状使用 **RGB** 函数，就会在页面上出现的触发器。  <br/> |
|RecalcCreateDT  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |存在使用 **DOCCREATION** 函数的跨部分引用时出现在文档中的触发器。  <br/> |
|RecalcData1  <br/> |[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |存在使用 **DATA1** 函数的跨部分引用时出现在形状上的触发器。  <br/> |
|RecalcData2  <br/> |[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |存在使用 **DATA2** 函数的跨部件引用时出现在形状上的触发器。  <br/> |
|RecalcData3  <br/> |[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |当存在使用 **DATA3** 函数的跨部分引用时，出现在形状上的触发器。  <br/> |
|RecalcEditDT  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |存在使用 **DOCLASTEDIT** 函数的跨部分引用时出现在文档中的触发器。  <br/> |
|RecalcID  <br/> |[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |存在使用 **ID** 函数的跨部分引用时出现在形状上的触发器。  <br/> |
|RecalcMasterName  <br/> |[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |存在使用 **MASTERNAME** 函数的跨部分引用时出现在形状上的触发器。  <br/> |
|RecalcName  <br/> |[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |存在使用 **NAME** 函数的跨部分引用时出现在形状上的触发器。  <br/> |
|RecalcNowAndRand  <br/> |[PageSheet (Page_Type complexType) ](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |如果页面或任何包含形状的 **NOW** 或 **RAND** 函数，则出现在页面上的触发器。  <br/> |
|RecalcPageCount  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |存在使用 **PAGECOUNT** 函数的跨部分引用时在文档中出现的触发器。  <br/> |
|RecalcPageName  <br/> |[PageSheet (Page_Type complexType) ](pagesheet-element-page_type-complextypevisio-xml.md) <br/> [Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |存在使用 **PAGENAME** 函数的跨部分引用时出现在形状上的触发器。  <br/> |
|RecalcPageNum  <br/> |[PageSheet (Page_Type complexType) ](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |存在使用 **PAGENUMBER** 函数的跨部分引用时出现在页面上的触发器。  <br/> |
|RecalcPath  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |当存在使用 **POINTALONGPATH、PATHLENGTH** 或 **PATHSEGMENT** 函数的跨部分引用时，形状上出现的触发器。  <br/> |
|RecalcPrintDT  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |存在使用 **DOCLASTPRINT** 函数的跨部分引用时出现在文档中的触发器。  <br/> |
|RecalcSaveDT  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |存在使用 **DOCLASTSAVE** 函数的跨部分引用时出现在文档中的触发器。  <br/> |
|RecalcSummary  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |当存在使用CATEGORY、CREATOR、DESCRIPTION、KEYWORDS、SUBJECT 或 **TITLE** 函数的跨部分引用时，在文档中出现的触发器。   <br/> |
|RecalcType  <br/> |[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |存在使用 **TYPE** 函数的跨部分引用时出现在形状上的触发器。  <br/> |
|RelChanged  <br/> |[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |存在使用 **CONTAINERMEMBERCOUNT** 函数的跨部分引用时出现在形状上的触发器。  <br/> |
|ZOrderChanged  <br/> |[PageSheet (Page_Type complexType) ](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |存在使用 **CONTAINERSHEETREF** 函数的跨部件引用时出现在页面上的触发器。  <br/> |
|路径  <br/> |[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |存在使用 **POINTALONGPATH、PATHLENGTH** 或 **PATHSEGMENT** 函数的跨部分引用时出现在页面上的触发器。  <br/> |
   

